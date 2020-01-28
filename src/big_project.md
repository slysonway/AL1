# Big project guidelines: a not so simple PPM image manipulation library
 
Goals: Manipulating IO, Memory, Concurrent programming with threads and exposing Rust function
through Foreign Function Interface.
 
We will use the [Portable Pixel Map](https://en.wikipedia.org/wiki/Netpbm_format) in binary format.
 
## Lvl 0 - Warmup
 
- Create a new `ppm` Rust project as a library
- Make a little readme present your team
- Complete a little bit your Cargo.toml to add yourselves as author
- Make sure that `cargo build` is working
 
## Lvl 1 - Struct
 
- Create a nice custom Rust data-structure `Image` to handle 24bits images.
 
> Create first a `Pixel` structure to encode an RGB color.
 
In a PPM file pixels il take 24bits; 8 bits (octet) par color:
 
- 8 for red
- 8 for green
- 8 for blue
 
### Epic Functions for an Epic `Pixels`
 
Because test are nices: Write a test for all the functions [doc](https://doc.rust-lang.org/book/ch11-01-writing-tests.html)
Also, write a doc in rust style *Prof! I don't how to write doc!* [short awnser](https://doc.rust-lang.org/rust-by-example/meta/doc.html); [long answer](https://doc.rust-lang.org/1.30.0/book/2018-edition/ch14-02-publishing-to-crates-io.html?highlight=document#making-useful-documentation-comments)
TL;DR writes how to use the function if it panic says it! make an example in the doc!
 
Warmups functions:
 
- Write a block `impl Pixel` for next questions
- Write a nice constructor `fn new(red: u8, green: u8, blue: u8 -> Self`
- (Optional) Derive `Clone` and `Copy` because a Pixel is a tiny type who fits in a register.
- Make a `fn display(self) -> String` to render a pixel in terminal
- Carve a function `fn invert(&mut self)` that inverts a pixel. Advise think [bitwise](https://doc.rust-lang.org/std/ops/trait.Not.html)*!* ;)
 
Not so warmup:
 
- Make a function `fn eq(self, other: Pixel) -> bool`
- Rewrite your code of `eq` function to implement `PartialEq` [Doc PartialEq](https://doc.rust-lang.org/std/cmp/trait.Eq.html)!
 
Advice: Read the doc again! :)
 
Need some engagement:
 
- Make a function `grayscale` who convert an RGB pixel to a grayscale pixel
 
## Lvl 2 - Image manipulation
 
Write a little `struct Image` that represents a struct you might need the following fields:
 
- `Vec<Pixel>` to represent the pixels buffer
- `heigth` with type `usize`
- `width` with type `usize`
- Maybe other fields?
 
Now write some function to manipulate images!
A function `fn new_with_file(filename: &Path) -> Image` that read in text mode a ppm image you might need to write
the `.ppm` file format definition [here](http://netpbm.sourceforge.net/doc/ppm.html).
 
Write in a `impl Image` a function `fn save(filename: &Path)` who saves your struct into a file.
 
An example file in text mode looks like:
 
```text
P3
3 2
255
# The part above is the header
# "P3" means this is an RGB color image in ASCII
# "3 2" is the width and height of the image in pixels
# "255" is the maximum value for each color
# The part below is image data: RGB triplets
255 0   0   # red
0   255 0   # green
0   0   255 # blue
255 255 0   # yellow
255 255 255 # white
0   0   0   # black
```
 
- Create an `invert` function that inverts image colors (reuse your code!)
- Create a `grayscale` function that makes image B&W based on a filter color
 
### Buffering
 
Try to with really big files, improve performances. Maybe this doc pointer can help: [std::io::BufRead](https://doc.rust-lang.org/std/io/trait.BufRead.html)
 
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
 
### Bonus binary edition
 
- Prepare yourself to read the pixel part in binary mode write a `fn new_with_file_bin(Path filename) -> Image`
 
> The whole purpose of this part is to do these computations using several threads,
> and to develop a strategy to find a good compromise on the number of threads to assign
> (e.g. one thread by pixel is maybe a bit too much ...)
>
> Try to calls these functions from another language!
 
## Lvl 3 - Benchmarks
 
- Add benchmarks tests to measure your performances
 
> Rust have off course a guide on this topic
> <https://doc.rust-lang.org/1.2.0/book/benchmark-tests.html>
 
## Going further
 
### Lvl 4 - Unsafe - Optional C fun with Rust
 
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
 
### Lvl 5 - FFI for the fun and profit
 
Relatively easy:
 
- Make a `dummy()` function that return `42`
- Call this function in another language like Python using basic Foreign Function Interface FFI
 
_Note:_
> The Rust doc has a really handy page on the subject:
> <https://doc.rust-lang.org/1.2.0/book/rust-inside-other-languages.html>
 
Somewhat harder:
 
- Exposes functions of your `ppm` crate to Python
- Use [PyO3](https://github.com/PyO3/pyo3) and [Maturin](https://github.com/PyO3/maturin) read the README of the projects!
