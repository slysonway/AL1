# Big project guidelines: a not so simple PPM image manipulation library

## Lvl 0 - Warmup

- Create a new `ppm` Rust project as a library
- Make a `dummy` function that return `42`
- Call this function in another language using FFI

> The Rust doc has a really handy page on the subject:
> <https://doc.rust-lang.org/1.2.0/book/rust-inside-other-languages.html>


## Lvl 1 - Struct

- Create a nice custom Rust data-structure `Image` to handle 24bits images.

> Create first a `Pixel` structure to encode an RGB color.


## Lvl 2 - Unsafe

- Create an `readPPM` function to read `.ppm` files
- Create an `writePPM` function to read `.ppm` files

> Use PPMA_IO: Portable Pixel Map (ASCII) Files Read and Write Utilities
> <https://people.sc.fsu.edu/~jburkardt/c_src/ppma_io/ppma_io.html>
>
> You may need to call C code in Rust using `unsafe` blocks.
> If you want to know about some dark magics, read <https://doc.rust-lang.org/nomicon/ffi.html>
>
> You can start with a simpler format like `.pbm` or `.pgm`.
>
> You should make a static library and include it,
> [this StackOverflow post](https://stackoverflow.com/questions/43826572/where-should-i-place-a-static-library-so-i-can-link-it-with-a-rust-program)
> could help!


## Lvl 3 - Multithreading

- Create an `invert` function that inverts image colors
- Create a `grayscale` function that makes image B&W based on a filter color

> The whole purpose of this part is to do these computations using several threads,
> and to develop a strategy to find a good compromise on the number of threads to assign
> (e.g. one thread by pixel is maybe a bit too much ...)
>
> Try to calls theses functions from another language!


## Lvl 4 - Benchmarks

- Add benchmark tests to measure your perfs

> Rust have off course a guide on this topic
> <https://doc.rust-lang.org/1.2.0/book/benchmark-tests.html>


## Lvl 5 - Buffering (optionnal)

- Try to with really big files, improve perfs

> [Here](https://mega.nz/#!dQNSyASY!Vk6rM8ZqxpbwvSyRFzHdYVB1Rh8p_6yKTDewtUxVe6Q)
> is a big `.ppm` the file of a Mandelbrot fractal for your tests!
>
> You may want to open the file in Rust using a buffer to do the reading of the file and
> image operations in parallel <https://doc.rust-lang.org/std/io/trait.Read.html>
>
> `.ppm` file format has a simple syntax specified here:
> <http://netpbm.sourceforge.net/doc/ppm.html>
>
> The purpose of this level is to code a custom `.ppm` reading function in Rust!

## Bonuses

- What about having your fresh new lib working in the browser server-side by making a web API?
- What about having your stunning new lib working in the browser client-side by making it compile to WebAssembly?
- What about having your fancy new lib working in CLI by displaying an image using `ncurses`

> For performing all that you should take a look at some nice crates in:
>
> - <https://www.arewewebyet.org>
> - <https://rustwasm.github.io/docs/wasm-pack/>
> - <https://rust-lang-nursery.github.io/rust-cookbook/>