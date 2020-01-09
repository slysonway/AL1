Hello everyone!

You will find a French version of this mail bellow, read it carefully and enjoy a homework bit trickier than the previous time:


# Recap from the previous session

- QCM is a huge success, the mean of the class is 15,92 / 20 (negative points are on me this time)
- Correction of last homework: <https://gist.github.com/yvan-sraka/94638a5dd95f46cdaecf5ab4d7ed2676>
- I strongly advise you to try to finish rustlings to be more comfortable with basic language features <https://github.com/rust-lang/rustlings>
- The small Rust code I wrote in class to play with ownership and borrowing: <https://gist.github.com/yvan-sraka/81f3f6ea6e7147b69a334b023d71f0bb>

REMINDER: Rule of thumbs of Rust -> they cannot have both aliasing AND mutability!


# Mandatory for the next session (December 19)

⚠️ Have a UNIX system with Rust installed inside:

For those that run a Windows machine, I highly recommend the installation of a WSL (Windows Subsystem for Linux) <https://docs.microsoft.com/en-us/windows/wsl/install-win10>

and the nice VSCode extension <https://code.visualstudio.com/remote-tutorials/wsl/run-in-wsl> that allows you to run `code` command remotely in bash.exe shell!

(and, of course, to have a working Rust dev environment with RLS setup <https://github.com/rust-lang/rls>)


# Go deeper into Rust

We, at this point cover, all of 6 first chapters, and most of 7, 8 and 9 of the Rust Book <https://doc.rust-lang.org/stable/book/>

We will not advance to much in Rust specific feature after this point (I will not make a class about trait e.g.), I let you free of learning more about it or not!

I give you here three handy tools that will help you with homework and graded project:
- <https://github.com/rust-lang/rust-clippy>
- <https://github.com/rust-lang/rustfmt>
- <https://github.com/mre/cargo-inspect> (play with it!)


# Go deeper into memory

Try to create a small C program that creates a memory leak (like a loop that malloc but never free) and open it in Valgrind, translates the program in Rust and redo the test.

Do you know that the program stack has a fixed space size in memory? What’s happen when you fill it all with function calls? -> a stack overflow!

You can look at this minimalist malloc implementation from mine, using mmap syscall (read its man) to allocate memory pages: <https://github.com/yvan-sraka/malloc>

Supplementary links to feed your curiosity (bonus, not mandatory):

- There no null pointers in Rust! Why? Watch “Null References: The Billion Dollar Mistake” from Tony Hoare <https://www.infoq.com/presentations/Null-References-The-Billion-Dollar-Mistake-Tony-Hoare/>
- Some more readings for the brave: “What Every Programmer Should Know About Memory” by Ulrich Drepper from Red Hat <https://people.freebsd.org/~lstewart/articles/cpumemory.pdf>


# Homework due to next session

You have to recode a small pipe-like program, working like this:

```
$ mypipe --in fortune --out cowsay
```

```
 _______________________________________
/ Q: What's tiny and yellow and very,   \
| very, dangerous? A: A canary with the |
\ super-user password.                  /
 ---------------------------------------
          \   ^__^
           \  (oo)\_______
              (__)\       )\/\
                  ||----w |
                  ||     ||
```

You can use <https://clap.rs> to parse the command-line arguments, and also follow the guide <https://rust-lang-nursery.github.io/cli-wg/>

Upload your code by doing a PR here: <https://github.com/rust-esgi/mypipe>


# Big Project

I will present during the next class the final project on which you will be evaluated. You’re free to come with your idea of an alternative project if you have already in mind something that you want to code in Rust. I will accept any idea that could be reasonably doable by a group of 3 or 4 students (chosen randomly), that implies features specific to systems or networks programming (think about playing with binary encoding, intense computing with concurrent programming, low-level binding with another library or just any funny syscalls, etc…)!

Cheers, Yvan