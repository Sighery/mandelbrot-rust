This is an implementation of a Mandelbrot set in Rust, using concurrency.

This is taken from Chapter 2 of a Rust programming book, called [Programming
Rust: Fast, Safe Systems Development](https://www.amazon.com/_/dp/1491927283)
by Jim Blandy and Jason Orendorff.

The Mandelbrot set is best explained in this [ELI5 Mandelbrot sets and fractals
Reddit post](https://www.reddit.com/r/explainlikeimfive/comments/16ux4e/).

---

## Build

Simply clone and then, in the directory you cloned the repository in, run:

```bash
cargo build --release
```

---

## Execution

When you build it, the Rust compiler will create an executable on
`target/release/mandelbrot`, however, you can just run it through `cargo` like:

```bash
cargo run --release mandel.png 9000x6000 -2,1 1,-1
```

This will produce something like the following image:

![Complete Mandelbrot set](mandel.png)

To get help, you can simply execute the program without any arguments and it
will display this:

```
mandelbrot FILE PIXELS UPPERLEFT LOWERRIGHT
```

To explain certain arguments:

- **FILE**: A PNG filename, such as `mandel.png`.
- **PIXELS**: Two positive numbers (integers) separated by `x`, such as
  `9000x6000`.
- **UPPERLEFT**: Two decimal numbers (float), either positive or negative,
  separated by `,`, such as `-2,1`.
- **LOWERRIGHT**: Two decimal numbers (float), either positive or negative,
  separated by `,`, such as `1,-1`.

---

### Notes

There's a `fn main` implementation that doesn't use concurrency. If you are
curious about the performance, you can comment the concurrent `main`, and
enable the non-current one to compare times.
