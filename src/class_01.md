# Packages and Crates
* A package can contain as many binary crates as you like, but at most only one library crate. A package must contain at least one crate, whether that’s a library or binary crate. [出處](https://doc.rust-lang.org/book/ch07-01-packages-and-crates.html)
* 重點: crate有兩種,(1) binary, (2) library。一個package一定至少一個crate, 可以有多個binary, 但只能有一個library。
* We’re passing --bin because we’re making a binary program: if we were making a library, we’d pass --lib. This also initializes a new git repository by default. [出處](https://doc.rust-lang.org/cargo/guide/creating-a-new-project.html?highlight=cargo%20new%20lib#creating-a-new-package)
  ```
  cargo new hello_world --bin
  ```
* 重點: cargo的指令
    * cargo new
    * cargo run
    * cargo build
* If a binary, example, bench, or integration test consists of multiple source files, place a main.rs file along with the extra modules within a subdirectory of the src/bin, examples, benches, or tests directory. The name of the executable will be the directory name. [出處](https://doc.rust-lang.org/cargo/guide/project-layout.html)
* 重點: Package Layout