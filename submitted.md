# Add `#[must_use]` to stdin/stdout/stderr locks #89693

```rust
std/src/io/stdio.rs:351:1                                   std::io                                                     fn stdin_locked() -> StdinLock<'static>;
std/src/io/stdio.rs:378:5                                   std::io::Stdin                                              fn lock(&self) -> StdinLock<'_>;
std/src/io/stdio.rs:715:1                                   std::io                                                     fn stdout_locked() -> StdoutLock<'static>;
std/src/io/stdio.rs:755:5                                   std::io::Stdout                                             fn lock(&self) -> StdoutLock<'_>;
std/src/io/stdio.rs:992:1                                   std::io                                                     fn stderr_locked() -> StderrLock<'static>;
std/src/io/stdio.rs:1018:5                                  std::io::Stderr                                             fn lock(&self) -> StderrLock<'_>;
```


# Add `#[must_use]` to string transformation methods

```rust
alloc/src/slice.rs:667:5                                    [u8]                                                        fn to_ascii_uppercase(&self) -> Vec<u8>;
alloc/src/slice.rs:685:5                                    [u8]                                                        fn to_ascii_lowercase(&self) -> Vec<u8>;
alloc/src/str.rs:371:5                                      str                                                         fn to_lowercase(&self) -> String;
alloc/src/str.rs:451:5                                      str                                                         fn to_uppercase(&self) -> String;
alloc/src/str.rs:539:5                                      str                                                         fn to_ascii_uppercase(&self) -> String;
alloc/src/str.rs:570:5                                      str                                                         fn to_ascii_lowercase(&self) -> String;
core/src/char/methods.rs:954:5                              char                                                        fn to_lowercase(self) -> ToLowercase;
core/src/char/methods.rs:1044:5                             char                                                        fn to_uppercase(self) -> ToUppercase;
core/src/char/methods.rs:1091:5                             char                                                        const fn to_ascii_uppercase(&self) -> char;
core/src/char/methods.rs:1124:5                             char                                                        const fn to_ascii_lowercase(&self) -> char;
core/src/num/mod.rs:288:5                                   u8                                                          const fn to_ascii_uppercase(&self) -> u8;
core/src/num/mod.rs:312:5                                   u8                                                          const fn to_ascii_lowercase(&self) -> u8;
core/src/num/mod.rs:774:5                                   u8                                                          fn escape_ascii(&self) -> ascii::EscapeDefault;
core/src/slice/ascii.rs:76:5                                slice                                                       fn escape_ascii(&self) -> EscapeAscii<'_>;
core/src/str/mod.rs:803:5                                   str                                                         fn split_whitespace(&self) -> SplitWhitespace<'_>;
core/src/str/mod.rs:844:5                                   str                                                         fn split_ascii_whitespace(&self) -> SplitAsciiWhitespace<'_>;
core/src/str/mod.rs:918:5                                   str                                                         fn encode_utf16(&self) -> EncodeUtf16<'_>;
core/src/str/mod.rs:1850:5                                  str                                                         fn trim_left(&self) -> &str;
core/src/str/mod.rs:1892:5                                  str                                                         fn trim_right(&self) -> &str;
core/src/str/mod.rs:2350:5                                  str                                                         fn escape_debug(&self) -> EscapeDebug<'_>;
core/src/str/mod.rs:2394:5                                  str                                                         fn escape_default(&self) -> EscapeDefault<'_>;
core/src/str/mod.rs:2430:5                                  str                                                         fn escape_unicode(&self) -> EscapeUnicode<'_>;
std/src/ffi/os_str.rs:781:5                                 std::ffi::OsStr                                             fn to_ascii_lowercase(&self) -> OsString;
std/src/ffi/os_str.rs:802:5                                 std::ffi::OsStr                                             fn to_ascii_uppercase(&self) -> OsString;
```
