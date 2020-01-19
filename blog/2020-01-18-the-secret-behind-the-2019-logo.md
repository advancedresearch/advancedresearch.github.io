# The Secret Behind the 2019 Logo
by Sven Nilsen, 2020

In this blog post I am going to reveal how to solve the puzzle which made up the logo of [Path Semantics](https://github.com/advancedresearch/path_semantics) for 2019.

The solution to this puzzle is also a compression algorithm.
A naive extension to color images beats PNG compression in some cases: [View tweet](https://twitter.com/PistonDeveloper/status/1180669893898854400)

I am also going to give you a work-in-progress generalized algorithm developed further down this line of research.

I assume you:

- Have some experience programming Rust
- Is interested in mathematics and puzzles

The puzzle/logo consists of the following image:

![Logo 2019](https://github.com/advancedresearch/path_semantics/blob/master/images/fractal.png)

Together with the number sequence `[85, 164, 56, 161, 184, 74, 170, 85, 170, 170, 163, 43]`.

Unfortunately, nobody managed to solve the puzzle of 2019.

I will reveal the solution to this puzzle in the way somebody might solve it.

### Observation 1: Four Split

The image can be split into 4 parts. There are no rotated elements.

### Observation 2: Fractal

The image repeats itself in different ways, like a fractal.

### Observation 3: Binary Code

Translated into binary code, the number sequence becomes:

`[0b01010101, 0b10100100, 0b00111000, 0b10100001, 0b10111000, 0b01001010, 0b10101010, 0b01010101, 0b10101010, 0b10101010, 0b10100011, 0b00101011]`

To print out something in binary, one can use the following code (link to [playground](https://play.rust-lang.org/?version=stable&mode=debug&edition=2018&gist=1e6e8aca15a7a15877c2ce588be8bd39)):

```rust
use std::fmt;

/// Can be used to print binary numbers.
pub struct PrintBinary<'a>(pub &'a [u8]);

impl<'a> fmt::Binary for PrintBinary<'a> {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        write!(f, "[")?;
        for (count, n) in self.0.iter().enumerate() {
            if count != 0 { write!(f, ", ")?; }

            write!(f, "0b{:08b}", n)?;
        }
        write!(f, "]")?;

        Ok(())
    }
}

fn main() {
    let x: &[u8] = &[85, 164, 56, 161, 184, 74, 170, 85, 170, 170, 163, 43];
    println!("{:b}", PrintBinary(x));
}
```

### Observation 4: The Image is Black/White

There are no colors in the image, only black and white.

### Hypothesis 1: Quad Tree-Like Structure

The image can be split into 4 parts, but these parts might again be split into 4, and so on.

This hints at a quad tree-like structure.

In a quad tree, every branch has 4 child nodes:

- Left-top (LT)
- Righ-top (RT)
- Left-bottom (LB)
- Right-bottom (RB)

### Hypothesis 2: The Code Describes a Set That Reflects the Image

The code is an equivalent representation of the image.

Since there are only black/white pixels in the image, it is reasonable to believe the code represents a set.

For example, a black pixel could mean that a coordinate belongs to the set.
A white pixel could mean that a coordinate does not belong to the set.

With other words, the code is a function of the type `pixel -> bool`.

### Hypothesis 3: Two-Bit Code for Nodes

A byte has 8 bits, which divided by 4 gives 2 bits per node.

Assuming that the bytes are not scrambled,
there are `4! = 24` possible ways to arrange the code.

One can assume the code is designed for readability.

In western culture the standard reading direction is left-to-right, top-to-bottom.

With other words:

`LT, RT, LB, RB`

However, when the 2-bits are encoded with [little-endianness](https://en.wikipedia.org/wiki/Endianness), the order becomes:

`RB, LB, RT, LT`

For example: `0b11001001` tells `11 (RB), 00 (LB), 10 (RT), 01 (LT)`.

### Hypothesis 4: Codes

Some necessary theory from computer science:

- A terminal symbol means there are no more bytes for a particular node
- A nonterminal symbol means there are more bytes

Using 2 bits per node, suggesting the following representations:

- `00`: No-fill (terminal symbol)
- `11`: Fill (terminal symbol)

A quad tree code must contain a split code.

Using 2 bits per node, this means there is only one possibility left: For the fractal property.

- `01`: Split into 4 children (nonterminal symbol)
- `10`: Fractal (terminal symbol)

Split requires another byte (4 children).
The order of these bytes are `LT, RT, LB, RB`.

The fractal code repeats the parent node recursively.

### Testing Hypotheses

So far, the codes fit nicely with a quad tree-like structure:

```
[
  0b01010101, // Split (RB), Split (LB), Split (RT), Split (LT)
    0b10100100, // LT: Fractal (RB), Fractal (LB), Split (RT), No-fill (LT)
      0b00111000, // RT: No-fill (RB), Fill (LB), Fractal (RT), No-fill (LB)
    0b10100001, // RT: Fractal (RB), Fractal (LB), No-fill (RT), Split (LT)
      0b10111000, // LT: Fractal (RB), Fill (LB), Fractal (RT), No-fill (LT)
    0b01001010, // LB: Split (RB), No-fill (LB), Fractal (RT), Fractal (LT)
      0b10101010, // RB: All fractals ???
    0b01010101, // RB: Split (RB), Split (LB), Split (RT), Split (LT)
      0b10101010, // LT: All fractals ???
      0b10101010, // RT: All fractals ???
      0b10100011, // LB: Fractal (RB), Fractal (LB), No-fill (RT), Fill (LT)
      0b00101011  // RB: No-fill (RB), Fractal (LB), Fractal (RT), Fill (LT)
]
```

Notice that the last byte *constructs a triangle* although the format does not support anything but axis-aligned edges!

### `0b10101010` - Undefined Behavior Interpreted as Something Else

The problem is what `0b10101010` means.

Mathematically, repeating all 4 parts as fractals does not make sense.

Just try to draw a picture where each part is divided into a repetition of the whole image: How does it look like?

It is like expressing an undecidable idea, giving undefined behavior for the set.

Looking at the image, `0b10101010` repeats the grand-parent recursively.
Instead of repeating the parent `10`, it is like "jumping two steps back" instead of just one.

This is an example of reusing codes for something else that otherwise would be useless.

Formally, using the [Chomsky hierarchy](https://en.wikipedia.org/wiki/Chomsky_hierarchy),
the ability to refer to the grand-parent is a small extension into the universe of context-sensitive grammar.

### General Zero-Cost Tricks of Compression

In general, one can use these two tricks in codes for recursive sets:

- Codes that result in undefined behavior can be interpreted as something else
- Codes that are non-trivial tautologies or contradictions can be interpreted as something else

A non-trivial tautology is something that equals "fill" but has a more complex construction.
Since one can just use `11` for fill, the non-trivial tautologies are not needed and might be used for other stuff.

A non-trivial contradiction is something that equals "no-fill" but has a more complex construction.
Since one can just use `00` for no-fill, the non-trivial contradictions are not needed and might be used for other stuff.

### Summary This Far

This relatively simple setup represents three sophisticated mathematical ideas:

- Construction of rational shapes using fractals
- Playing with context-sensitive grammar
- Zero-cost tricks of compression based on proof logic

Fast forward in time, using these tricks over and over, I have ventured into the depths of undecidability.

### The Monster Algorithm: Exploring the Depths of Undecidability

This algorithm can do everything what the solution to the puzzle can, but also much more:

- a cache that speeds up performance on large sets
- repeat parent
- repeat grand parent
- repeat specify great grand parent
- repeat sibling
- repeat sibling flip x-axis
- repeat sibling flip y-axis
- shrink the square along one axis to one side

```rust
/// Determines whether a pixel is on or off.
///
/// Uses a cache to store temporary values that must be initialized to four times the size of data.
pub fn pxl(pos: [u32; 2], size: u32, f: &[u8], cache: &mut [u32]) -> bool {
    if f.len() == 0 {return false};
    let mut pos: [f64; 2] = [pos[0] as f64 / size as f64, pos[1] as f64 / size as f64];
    let mut stack: Vec<usize> = vec![];
    let mut i = 0;
    let mut b = f[i];
    let mut child = 0;
    let val = true;

    for _ in 0..64 {
        if pos[0] < 0.0 || pos[0] > 1.0 || pos[1] < 0.0 || pos[1] > 1.0 {return !val};
        // Erasing parent from stack while continuing to the next instruction.
        while b == 0b00000000 {
            if stack.pop().is_none() {return !val};
            i += 1;
            b = f[i];
            continue;
        }
        match b {
            // Four fractals means go to grand parent.
            0b10101010 => {
                if stack.pop().is_none() {return !val};
                if let Some(j) = stack.pop() {
                    i = j;
                    b = f[i];
                }
            }
            // Four fills means go to parent.
            // This is usually `10` in the parent,
            // but when some transforms are used in the child,
            // these transforms gets applied to the parent too.
            0b11111111 => {
                if let Some(j) = stack.pop() {
                    i = j;
                    b = f[i];
                }
            }
            // Repeat upper-left child.
            0b11111110 => {
                match child {
                    1 | 2 | 3 => {
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                    }
                    _ => {}
                }
                if let Some(j) = stack.pop() {
                    i = j;
                    b = f[i];
                }
                continue;
            }
            // Repeat upper-left child, flip y-axis.
            0b00000010 => {
                match child {
                    1 | 2 | 3 => {
                        // Flip such that `< 0.5` becomes `<= 0.5`.
                        pos[1] = 1.0 - pos[1] - std::f64::EPSILON;
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                    }
                    _ => {}
                }
                if let Some(j) = stack.pop() {
                    i = j;
                    b = f[i];
                }
                continue;
            }
            // Repeat upper-right child.
            0b11111011 => {
                match child {
                    0 => {
                        pos[0] = 1.0 - pos[0] - std::f64::EPSILON;
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                        pos[0] += 0.5;
                    }
                    2 | 3 => {
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                        pos[0] += 0.5;
                    }
                    _ => {}
                }
                if let Some(j) = stack.pop() {
                    i = j;
                    b = f[i];
                }
                continue;
            }
            // Repeat upper-right child, flip y-axis.
            0b00001000 => {
                match child {
                    0 => {
                        pos[0] = 1.0 - pos[0] - std::f64::EPSILON;
                        pos[1] = 1.0 - pos[1] - std::f64::EPSILON;
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                        pos[0] += 0.5;
                    }
                    2 | 3 => {
                        pos[1] = 1.0 - pos[1] - std::f64::EPSILON;
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                        pos[0] += 0.5;
                    }
                    _ => {}
                }
                if let Some(j) = stack.pop() {
                    i = j;
                    b = f[i];
                }
                continue;
            }
            // Repeat lower-left child.
            0b11101111 => {
                match child {
                    0 | 1 => {
                        pos[0] = 1.0 - pos[0] - std::f64::EPSILON;
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                        pos[1] += 0.5;
                    }
                    3 => {
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                        pos[1] += 0.5;
                    }
                    _ => {}
                }
                if let Some(j) = stack.pop() {
                    i = j;
                    b = f[i];
                }
                continue;
            }
            // Repeat lower-left child, flip y-axis.
            0b00100000 => {
                match child {
                    0 | 1 => {
                        // Flip such that `< 0.5` becomes `<= 0.5`.
                        pos[0] = 1.0 - pos[0] - std::f64::EPSILON;
                        pos[1] = 1.0 - pos[1] - std::f64::EPSILON;
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                        pos[1] += 0.5;
                    }
                    3 => {
                        pos[1] = 1.0 - pos[1] - std::f64::EPSILON;
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                        pos[1] += 0.5;
                    }
                    _ => {}
                }
                if let Some(j) = stack.pop() {
                    i = j;
                    b = f[i];
                }
                continue;
            }
            // Repeat lower-right child.
            0b10111111 => {
                match child {
                    0 | 1 | 2 => {
                        pos[0] = 1.0 - pos[0] - std::f64::EPSILON;
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                        pos[0] += 0.5;
                        pos[1] += 0.5;
                    }
                    _ => {}
                }
                if let Some(j) = stack.pop() {
                    i = j;
                    b = f[i];
                }
                continue;
            }
            // Repeat lower-right child, flip y-axis.
            0b10000000 => {
                match child {
                    0 | 1 | 2 => {
                        pos[0] = 1.0 - pos[0] - std::f64::EPSILON;
                        pos[1] = 1.0 - pos[1] - std::f64::EPSILON;
                        pos[0] *= 0.5;
                        pos[1] *= 0.5;
                        pos[0] += 0.5;
                        pos[1] += 0.5;
                    }
                    _ => {}
                }
                if let Some(j) = stack.pop() {
                    i = j;
                    b = f[i];
                }
                continue;
            }
            // Shrink down, put empty at top.
            0b10100000 => {
                if pos[1] < 0.5 {return !val};
                pos[1] -= 0.5;
                pos[1] *= 2.0;
                i += 1;
                b = f[i];
                continue;
            }
            // Shrink down, put filled at top.
            0b10101111 => {
                if pos[1] < 0.5 {return val};
                pos[1] -= 0.5;
                pos[1] *= 2.0;
                i += 1;
                b = f[i];
                continue;
            }
            // Shrink up, put empty at bottom.
            0b00001010 => {
                if pos[1] >= 0.5 {return !val};
                pos[1] *= 2.0;
                i += 1;
                b = f[i];
                continue;
            }
            // Shrink up, put filled at bottom.
            0b11111010 => {
                if pos[1] >= 0.5 {return val};
                pos[1] *= 2.0;
                i += 1;
                b = f[i];
                continue;
            }
            // Shrink left, put empty at right.
            0b00100010 => {
                if pos[0] >= 0.5 {return !val};
                pos[0] *= 2.0;
                i += 1;
                b = f[i];
                continue;
            }
            // Shrink left, put filled at right.
            0b11101110 => {
                if pos[0] >= 0.5 {return val};
                pos[0] *= 2.0;
                i += 1;
                b = f[i];
                continue;
            }
            // Shrink right, put empty at left.
            0b10001000 => {
                if pos[0] < 0.5 {return !val};
                pos[0] -= 0.5;
                pos[0] *= 2.0;
                i += 1;
                b = f[i];
                continue;
            }
            // Shrink right, put filled at left.
            0b10111011 => {
                if pos[0] < 0.5 {return val};
                pos[0] -= 0.5;
                pos[0] *= 2.0;
                i += 1;
                b = f[i];
                continue;
            }
            _ => {}
        }
        child = if pos[1] < 0.5 {
                        if pos[0] < 0.5 {0} else {1}
                    } else {
                        if pos[0] < 0.5 {2} else {3}
                    };
        let code = b >> (child << 1) & 0b11;
        match code {
            // No fill.
            0b00 => return !val,
            // Split.
            0b01 => {
                let ind = if cache[i * 4 + child] == 0 {
                    // Get the number of splits before this split.
                    let mut ind: usize = match child {
                        0 => 0,
                        1 => {
                            if b & 0b11 == 0b01 {1} else {0}
                        }
                        2 => {
                            (if b & 0b11 == 0b01 {1} else {0}) +
                            (if b >> 2 & 0b11 == 0b01 {1} else {0})
                        }
                        _ => {
                            (if b & 0b11 == 0b01 {1} else {0}) +
                            (if b >> 2 & 0b11 == 0b01 {1} else {0}) +
                            (if b >> 4 & 0b11 == 0b01 {1} else {0})
                        }
                    };
                    if ind > 0 {
                        // Sum the splits that are children of splits before this split.
                        let mut k = i + 1;
                        let mut reach = k + ind;
                        loop {
                            if k >= f.len() {return !val};
                            let b = f[k];
                            match b {
                                0b000000 |
                                0b10100000 | 0b10101111 |
                                0b00001010 | 0b11111010 |
                                0b00100010 | 0b11101110 |
                                0b10001000 | 0b10111011 => {
                                    ind += 1;
                                    k += 1;
                                    reach += 1;
                                    continue;
                                }
                                _ => {}
                            }
                            let new_splits =
                                (if b & 0b11 == 0b01 {1} else {0}) +
                                (if b >> 2 & 0b11 == 0b01 {1} else {0}) +
                                (if b >> 4 & 0b11 == 0b01 {1} else {0}) +
                                (if b >> 6 & 0b11 == 0b01 {1} else {0});
                            ind += new_splits;
                            reach += new_splits;
                            k += 1;
                            if k >= reach {break}
                        }
                        k
                    } else {i+1};
                    cache[i * 4 + child] = (ind + 1) as u32;
                    ind
                } else {cache[i * 4 + child] as usize - 1};

                // Remember parent.
                stack.push(i);
                i += 1 + ind;
                if i >= f.len() {return !val};
                b = f[i];
                if pos[0] >= 0.5 {pos[0] -= 0.5}
                if pos[1] >= 0.5 {pos[1] -= 0.5}
                pos = [pos[0] * 2.0, pos[1] * 2.0];
            }
            // Fractal.
            0b10 => {
                if pos[0] >= 0.5 {pos[0] -= 0.5}
                if pos[1] >= 0.5 {pos[1] -= 0.5}
                pos = [pos[0] * 2.0, pos[1] * 2.0];
            }
            // Fill.
            _ => return val,
        }
    }
    !val
}
```
