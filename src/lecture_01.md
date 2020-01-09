Hello everybody,


A quick mail about "Systems and networks programming in Rust” lecture, read it entirely, there is some homework for you at the end.


## In the previous episode

Rust basics (Introduction, Syntax, Error Handling):

- 0. Schedule, purpose, and rules of the class (planning, assignments, grades, etc..)

- 1. What's systems programming? Why systems (and networks) programming? Why Rust?

- 2. Setup a Rust dev environment with <https://rustup.rs>, and a code editor (<https://www.rust-lang.org/tools>) with RLS support (<https://github.com/rust-lang/rls>) and be sure to not have just the VSCode extension but to install it with command `rustup component add rls rust-analysis rust-src`

N.B. People on Windows should read this <https://github.com/rust-lang/rustup.rs/#working-with-rust-on-windows>, and installing Visual Studio C/C++ tools suite (like link.exe to link program) using Visual Studio Installer.

I also recommend to get you a WLS and install Rust with rustup in bash.exe, since starting from course 3 we will play with Linux file abstraction.

- 3. Get familiar with language syntax by playing a bit with <https://github.com/rust-lang/rustlings>

- 4. Theoretical recap about the semantics of a Rust program (we talk about functions VS macros, type inference, enumeration types <https://doc.rust-lang.org/std/result/enum.Result.html>)

- 5. Show off basic tooling: how to create a binary/library with cargo, how to add a dependency form crate.io to our project, we start writing a little MASTERMIND game (Here is a link to the full implementation <https://github.com/yvan-sraka/mymastermind>)

Further information could be found in THE RUST BOOK -> <https://doc.rust-lang.org/stable/book/> <- (what we do in class match the 3 first chapters of the book)


## Program of the next lectures

- November 28: Rust advanced (static automated memory management: Ownership & Borrowing)
- December 19: Files (standard IO, synchronous message through pipes), Tasks (process, thread) and other POSIX stuff
- January  10: FFI, unsafe world (let’s talk about “lifetimes”) and the C runtime (stack & heap)
- January  23: *** NETWORK (finally, something fun for the last class) ***


## Homeworks (mandatory) - deadline: push it before the class

Make a PR (Pull-Request) on this repository that fixes this code: <https://github.com/rust-esgi/base64decode/blob/master/src/main.rs>

It will be automatically validated by GitHub Actions (Continuous Integration), so if it’s green you already have a good grade. I will give you extra points if you succeed to reduce the size of the codebase without breaking it!

You can test your code by trying to decrypt this secret message:

    TGEgcmFjbGV0dGUgKEJyYXRjaMOkcywgwqsgZnJvbWFnZSDCuyByw7R0aSwgZW4gc3Vpc3NlIGFsbGVtYW5kKSBlc3QgZCd1bmUgcGFydCB1biBmcm9tYWdlIChsZSBvdSBsYSByYWNsZXR0ZSkgb3JpZ2luYWlyZSBkdSBjYW50b24gZHUgVmFsYWlzIGVuIFN1aXNzZSwgZXQgZCdhdXRyZSBwYXJ0LCB1bmUgcmVjZXR0ZSBkZSBjdWlzaW5lIHRyYWRpdGlvbm5lbGxlIGV0IGVtYmzDqW1hdGlxdWUgZGUgbGEgY3Vpc2luZSBzdWlzc2UsIGNvbm51ZSBkYW5zIGxlIG1vbmRlIGVudGllciwgdmFyaWFudGUgZGVzIGZvbmR1ZXMgYXUgZnJvbWFnZSwgw6AgYmFzZSBkZSBjZSBmcm9tYWdlIGZvbmR1LCByYWNsw6kgYXUgZnVyIGV0IMOgIG1lc3VyZSBxdeKAmWlsIGZvbmQsIGV0IHNlcnZpZSB0cmFkaXRpb25uZWxsZW1lbnQgYXZlYyBkZXMgcG9tbWVzIGRlIHRlcnJlIGVuIHJvYmUgZGVzIGNoYW1wcyBldCBhY2NvbXBhZ27DqWUgZGUgbMOpZ3VtZXMgYXUgdmluYWlncmUgKGNvcm5pY2hvbnMsIG9pZ25vbnMpLg==


⚠️ Reminder, next class will start with a quick test (don’t be late), it will be grade and take the form of a QCM.

Cheers, Yvan