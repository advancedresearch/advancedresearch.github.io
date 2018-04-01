# New Theoretical Breakthrough in Dynamic Graphs Paves Way for Large Scale Realistic Virtual Worlds
by Sven Nilsen, 2018

![the matrix](https://proxy.duckduckgo.com/iu/?u=http%3A%2F%2Fwww.fliwave.com%2Fwp-content%2Fuploads%2F2014%2F04%2Fthematrix11.jpg&f=1)

If you watched the movies "The Matrix" or "Ready Player One",
the action takes place inside a computer simulation of a large scale realistic virtual world.

The basic problem of creating such large worlds and simulate them in realistic detail is to organize the information efficiently.

Up until now, virtual worlds have been using various forms of grids, oct-trees or procedural generated content.

These techniques have different downsides:

- Grids introduces scale-invariance and multi-cell interaction complexity
- Oct-trees are not composable and restricted to certain types of algorithms
- Procedurally generated content is difficult to combine with player interactions with the world

So, I have been looking for a fourth alternative to overcome some of these limitations.
I wanted something that makes it easier to create super large scale, highly realistic and interactive virtual worlds.

One inspiration came from graphs of social networks:

- There are 7 billion people in the world, yet there almost no one that is not in contact with civilization
- People use their social network to find interests, opportunities, jobs and partners
- Each person has a limited number of people they are regularly in touch with

The challenge was to figure out how graphs behaving like social networks could be modified to behave
more like a grid or oct-tree, while allowing a similar language for procedurally generated content.

If you are familiar with the Traveling Salesman Problem, the challenge is to find the shortest route between all cities.

A much simpler problem is to find the closest city to any other city.  
This is called the "All Nearest Neighbors" problem.  

The problem of virtual worlds is just to learn which city is close to others,
except that cities moves around and interact with each other in complex ways.

The naive algorithm to do this for `N` cities takes in worst case `N^2` steps.  
It searches through the list of all cities for each city to find the closest one.

The traditional way to solve this is by e.g. using an oct-tree in 3D, like in [this paper](https://link.springer.com/content/pdf/10.1007%2FBF02187718.pdf).

I asked myself: Is it possible to do it without using an oct-tree but instead using something like a social graph?

Basically, one starts with a chaotic network like this:

![initial graph](https://i.imgur.com/1uH6iIT.png)

Here it is unknown which cities are closest to each other.  
All nodes are randomly connected to other nodes.

Which gets optimized to look like this:

![finished graph](https://i.imgur.com/jiQmQG1.png)

Now the links are connecting cities that are closest to each other.

Instead of searching for the closest city, one looks for e.g. the 4 closest cities at the same time.

The problem with incremental algorithms on such graphs is that you have no 100% certain proof that the links connects the closest cities.  
This is unlike an oct-tree where you know for certain that the content is optimized.  
Basically, the problem is to predict when the graph is "good enough" for interactive use.

Using a simple, un-optimized algorithm, I found out was that there is a way to predict how many iterations it take to optimize the network.

For a network of `N` nodes and `4` links per node,  
the steps requires is approximately `2 * N * ln(N)`.

This is the same complexity as using an oct-tree, which implies algorithms exists which yield similar performance.

The algorithm used to optimize the graph was:

1. Look for closer nodes among neighbor's link until local minima
2. When stuck in local minima, the link with longest distance is connected to a random node in the graph

This means that when the graph converges toward a solution, all links except the longest ones are stable.

To predict the steps required to optimize the graph,
one simply counts all improvements to a link which is not the node's link with longest distance (improving a stable link).  
Empirical evidence suggests this converges to `2 * N * ln(N)` for a graph with `N` nodes and 4 links.

Now, to the major points:

- An optimized algorithm might be parallelized very easily, reducing the steps required to `k * ln(N)` per kernel.
- The graph can be translated, rotated and scaled in all dimensions without changing links
- Two graphs can be optimized independently and merged, reusing their existing links
- The algorithm only needs a metric and is therefore dimensional agnostic (2D and 3D can use the same algorithm)

This means that two virtual worlds that are originally separate, can be connected together.  
It takes some time to connect them, but this can be made very fast using an optimized algorithm.  
A heuristic algorithm is used to predict when the two virtual worlds can be interacted with in a consistent way.

Players can interact with only the part of the world that is nearby, while the unused parts are stored offline.
This means that the size of the world is limited mostly by storage space and not the algorithm used for managing the information.

By the way:

**Happy April fools day!** HAHAHAHA! :)

This is an experiment to see whether the prediction heuristics worked, but I faked the conclusions.  
It is still **unknown** whether faster algorithms exists that are more beneficial than oct-trees.  
Only because a prediction heuristics algorithm exist, does not imply that there exists an efficient algorithm.  
However, it is still a possibility...

Here is the Dyon source code  
(`cargo install piston-dyon_interactive --example dyongame`, to run `dyongame <file.dyon>`):

```rust
fn main() {
    ~ ps := []
    ~ links := []
    ~ max_links := 4
    ~ count := 0

    cursor := none()
    mouse_down := false
    timer := now()
    loop {
        if !next_event() {break}

        if render() {
            ~ draw_list := []
            clear(color: #ffffff)
            rad := 2
            // Render links.
            for i {
                // Do not render the furthest neighbor, because it gets swapped.
                max_j := max j {|ps[i] - ps[links[i][j]]|}
                if !is_nan(max_j) {
                    where := where(max_j)
                    for j {
                        if j == where[0] {continue}
                        line(color: #00000050, radius: 0.1 * rad, from: ps[i], to: ps[links[i][j]])
                    }
                }
            }

            // Render points.
            for i {
                ellipse(color: #ff0000, corner: ps[i] - (rad, rad), size: (2*rad, 2*rad), resolution: 8)
            }

            draw(draw_list)
        }

        if mouse_cursor() {
            cursor = mouse_cursor_pos()
            if mouse_down {
                // Create a new point with no links.
                push(mut ps, unwrap(cursor))
                push(mut links, [])
            }
        }

        if press() {
            button := press_mouse_button()
            if button != none() {
                button := unwrap(button)
                if (button == 1) && (cursor != none()) {
                    // Create a new point with no links.
                    push(mut ps, unwrap(cursor))
                    push(mut links, [])
                    mouse_down = true
                }
            }
        }

        if release() {
            button := release_mouse_button()
            if button != none() {
                button := unwrap(button)
                if button == 1 {
                    mouse_down = false
                }
            }
        }

        if update() {
            old_count := count
            optimize()
            if old_count != count {
                timer = now()
                set_window(title: str(link {count"/"len(ps)}))
            }

            if (now() - timer) > 60 {
                println("It has been one minute")
                println(link {count"/"len(ps)})
                break
            }
        }
    }
}

fn optimize() ~ ps: [vec4], mut links: [[f64]], max_links: f64, mut count: f64 {
    if len(ps) > 0 {
        i := floor(random() * len(ps))

        // Create a link to a random node.
        if len(links[i]) < max_links {
            j := floor(random() * len(ps))
            if !any k {links[i][k] == j} && (i != j) {
                ls := links[i]
                push(mut ls, j)
                links[i] = clone(ls)
            }
        }

        // If any neighbor's links are closer, use it.
        for j {
            dist := |ps[i] - ps[links[i][j]]|
            closer := any k {
                id := links[links[i][j]][k]
                if id == i {continue}
                if id == j {continue}
                |ps[i] - ps[id]| < dist
            }
            if closer {
                why := why(closer)
                new_j := links[links[i][j]][why[0]]
                if !any k {links[i][k] == new_j} {
                    max_j := max j {|ps[i] - ps[links[i][j]]|}

                    links[i][j] = clone(new_j)

                    where := where(max_j)
                    if j != where[0] {
                        count += 1
                    }
                    return
                }
            }
        }

        // Swap to a random node to prevent stagnation.
        if len(links[i]) > 1 {
            max_j := max j {|ps[i] - ps[links[i][j]]|}
            if !is_nan(max_j) {
                where := where(max_j)
                new_j := floor(random() * len(ps))
                if !any k {links[i][k] == new_j} && (new_j != i) {
                    links[i][where[0]] = clone(new_j)
                }
            }
        }
    }
}
```
