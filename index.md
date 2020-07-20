# Learning Rust Part 1: Hello, World!

> 📚 Series: [Part 1](https://github.com/lopossumi/Rust-Hello) - [Part 2](https://github.com/lopossumi/Rust-Output-Image) - [Part 3](https://github.com/lopossumi/Rust-Vectors) - [Part 4](https://github.com/lopossumi/Rust-Rays) - [Part 5](https://github.com/lopossumi/Rust-Materials)

Trying to learn [Rust](https://www.rust-lang.org/) from scratch? Me too! And aside from a course at the university some 15 years ago and a couple of spare time embedded projects, I'm also a newbie with C / C++.

As we are dealing with a fairly low-level language, we should forget about to-do apps and choose something where performance is key. A good resource for that is Peter Shirley's [*Raytracing in One Weekend*](https://raytracing.github.io/books/RayTracingInOneWeekend.html), although learning *anything* new in one weekend sounds ambitious (did I mention I don't know much about computer graphics either?).

We're probably already behind schedule, so let's get started!

## Installation

I'm running Windows 10, so currently (July 2020) the easiest way to get started with Rust is to install the latest ```rustup-init.exe``` from [rust-lang.org](https://www.rust-lang.org/tools/install). The docs mention [other installation methods](https://forge.rust-lang.org/infra/other-installation-methods.html) and the possibility of adding a signed .msi installer in the future, so do check if those are more suitable for your use case.

The recommended installer *is* kind of scary with all the Windows protection warnings, but let's proceed anyway - it's not like anything bad ever came from the internet?

Running the installer we already run into our first warnings:

```
Rust Visual C++ prerequisites

[...]

Install the C++ build tools before proceeding.

If you will be targeting the GNU ABI or otherwise know what you are
doing then it is fine to continue installation without the build
tools, but otherwise, install the C++ build tools before proceeding.

Continue? (Y/n)
```

I thought we were going to learn Rust instead of C++? It seems I definitely do *not* know what I'm doing, so let's answer "no".

After installing the C++ packages, the rustup installer proceeds without warnings. Opening a new terminal window we can see that cargo (the Rust package manager) is installed and found in PATH.

```powershell
PS C:\> cargo --version
cargo 1.44.1 (88ba85757 2020-06-11)
```

## Initializing the project

Before diving into raytracing, let's ensure that everything is working as intended. New projects can be created with cargo using the command ```cargo new [project name]```, which also creates a new sub-directory for the project. 
```powershell
PS D:\RustProjects> cargo new hello
     Created binary (application) `hello` package
```
Opening the ```hello``` project folder we can see that our starter project already contains a "Hello, world!" program in the ```src/main.rs``` file. In the project root there is also an important looking [*manifest*](https://doc.rust-lang.org/cargo/reference/manifest.html) file called ```Cargo.toml```, which contains package information and an empty list of dependencies.

## Compiling and running the program

With Rust, it seems that everything can be done with ```cargo```. Building and running the project can be done from the command line:
```powershell
PS D:\RustProjects\hello> cargo build
   Compiling hello v0.1.0 (D:\RustProjects\hello)
    Finished dev [unoptimized + debuginfo] target(s) in 0.61s

PS D:\RustProjects\hello> cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.01s
     Running `target\debug\hello.exe`
Hello, world!
```
## VS Code and extensions

As a C# developer I'm so used to IntelliSense that I can't really imagine working without code navigation and completion. Luckily there's a bunch of plugins for [VS Code](https://code.visualstudio.com/) making life a little bit easier.

The extension simply named *Rust* ([rust-lang.rust](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust)) says to provide "lints, code completion and navigation, formatting and more" and is the most common Rust plugin with over half a million downloads.

After installing the extension and opening the ```src/main.rs``` file, a notification appears requesting some additional components to be installed by the extension. Finally, we can build our hello program using the ```SHIFT + CTRL + B``` shortcut.

The *Rust* extension doesn't seem to do anything for ```Cargo.toml```. An extension called *crates* ([serayuzgur.crates](https://marketplace.visualstudio.com/items?itemName=serayuzgur.crates)) aims to help with dependencies from crates.io, but it seems a bit glitchy as of version 0.5.1. Instead I opted for a simple syntax highlighter *Better TOML* ([bungcip.better-toml](https://marketplace.visualstudio.com/items?itemName=bungcip.better-toml)).

## Conclusion

The development environment is now installed and seems to work just fine. In the [next session](https://github.com/lopossumi/Rust-Output-Image) we're going to learn some Rust basics and draw something.