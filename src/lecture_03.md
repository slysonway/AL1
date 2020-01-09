Hello everybody,

Again, a too-long email, the french version is behind!

# ⚠️ IMPORTANT

I intend to assign you grades and I need you to be sure that I have the good matching between your mails, GitHub IDs, and names:
<https://docs.google.com/spreadsheets/d/1O8OsWIaI7GBfuLfFsIT0vmGJkdTsDXf9S7wYtnWxTW0/edit#gid=1826358230>

## Recap from the last session

- Recall previous episode:
    * Rust philosophy "zero-cost abstractions" => play a bit with `cargo inspect`, `cargo fmt`, `cargo clippy`

- Let's talk a bit about POSIX, UNIX, Linux, etc ... and file abstraction
    * Named pipe example: `mkfifo` (to send a synchronous message)
    * What about serialization? Do you know protocol buffer? => <https://developers.google.com/protocol-buffers>
        (SPOILER: shared memory is better) => <https://capnproto.org>

- A multi-thread parallel cat? <https://gist.github.com/yvan-sraka/6b597ec60e679953f7cda9128724c522>
    * Talk about process scheduling, etc...
    * Show `htop` tree view, play with small tests using Valgrind / GDB

## To go further

- Learn about File Descriptor <https://en.wikipedia.org/wiki/File_descriptor>
- IOStream Is Hopelessly Broken <https://www.moria.us/articles/iostream-is-hopelessly-broken/>
- Writing an OS in Rust <https://os.phil-opp.com/>
- Why is a Rust executable large? <https://lifthrasiir.github.io/rustlog/why-is-a-rust-executable-large.html>
- Smart pointers in Rust <https://doc.rust-lang.org/book/ch15-00-smart-pointers.html>
- Rust sucks because ... <https://wiki.theory.org/index.php/YourLanguageSucks#Rust_sucks_because>

## Prepare the next session (keep talking about Unix tools for binaries analysis)

- <https://lldb.llvm.org>
- <https://godbolt.org>
- <https://en.wikipedia.org/wiki/Executable_and_Linkable_Format>
- <https://en.wikipedia.org/wiki/GNU_Binutils>
- <https://en.wikipedia.org/wiki/Strace>

We will play with => FFI: Foreign Function Interface

I wish all of you enjoyed end-of-year celebrations.

Best, Yvan

P.S. <https://xkcd.com/835/> & <https://xkcd.com/2248/>
