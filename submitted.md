
1.  Add `#[must_use]` to stdin/stdout/stderr locks
    [#89693](https://github.com/rust-lang/rust/pull/89693)

    ```rust
    std/src/io/stdio.rs:351:1                                   std::io                                                     fn stdin_locked() -> StdinLock<'static>;
    std/src/io/stdio.rs:378:5                                   std::io::Stdin                                              fn lock(&self) -> StdinLock<'_>;
    std/src/io/stdio.rs:715:1                                   std::io                                                     fn stdout_locked() -> StdoutLock<'static>;
    std/src/io/stdio.rs:755:5                                   std::io::Stdout                                             fn lock(&self) -> StdoutLock<'_>;
    std/src/io/stdio.rs:992:1                                   std::io                                                     fn stderr_locked() -> StderrLock<'static>;
    std/src/io/stdio.rs:1018:5                                  std::io::Stderr                                             fn lock(&self) -> StderrLock<'_>;
    ```
