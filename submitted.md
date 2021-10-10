# Add #[must_use] to stdin/stdout/stderr locks #89693

```rust
std/src/io/stdio.rs:351:1                                   std::io                                                     fn stdin_locked() -> StdinLock<'static>;
std/src/io/stdio.rs:378:5                                   std::io::Stdin                                              fn lock(&self) -> StdinLock<'_>;
std/src/io/stdio.rs:446:5                                   std::io::Stdin                                              fn into_locked(self) -> StdinLock<'static>;
std/src/io/stdio.rs:715:1                                   std::io                                                     fn stdout_locked() -> StdoutLock<'static>;
std/src/io/stdio.rs:755:5                                   std::io::Stdout                                             fn lock(&self) -> StdoutLock<'_>;
std/src/io/stdio.rs:792:5                                   std::io::Stdout                                             fn into_locked(self) -> StdoutLock<'static>;
std/src/io/stdio.rs:992:1                                   std::io                                                     fn stderr_locked() -> StderrLock<'static>;
std/src/io/stdio.rs:1018:5                                  std::io::Stderr                                             fn lock(&self) -> StderrLock<'_>;
std/src/io/stdio.rs:1052:5                                  std::io::Stderr                                             fn into_locked(self) -> StderrLock<'static>;
```


# Add #[must_use] to string transformation methods #89694

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

# Add #[must_use] to is_condition checks #89718

```rust
alloc/src/collections/btree/set.rs:538:5                    alloc::collections::btree_set::BTreeSet<T>                  fn is_disjoint(&self, other: &BTreeSet<T>) -> bool;
alloc/src/collections/btree/set.rs:563:5                    alloc::collections::btree_set::BTreeSet<T>                  fn is_subset(&self, other: &BTreeSet<T>) -> bool;
alloc/src/collections/btree/set.rs:642:5                    alloc::collections::btree_set::BTreeSet<T>                  fn is_superset(&self, other: &BTreeSet<T>) -> bool;
core/src/char/methods.rs:283:5                              char                                                        fn is_digit(self, radix: u32) -> bool;
core/src/char/methods.rs:697:5                              char                                                        fn is_alphabetic(self) -> bool;
core/src/char/methods.rs:729:5                              char                                                        fn is_lowercase(self) -> bool;
core/src/char/methods.rs:761:5                              char                                                        fn is_uppercase(self) -> bool;
core/src/char/methods.rs:789:5                              char                                                        fn is_whitespace(self) -> bool;
core/src/char/methods.rs:817:5                              char                                                        fn is_alphanumeric(self) -> bool;
core/src/char/methods.rs:842:5                              char                                                        fn is_control(self) -> bool;
core/src/char/methods.rs:886:5                              char                                                        fn is_numeric(self) -> bool;
core/src/char/methods.rs:1062:5                             char                                                        const fn is_ascii(&self) -> bool;
core/src/char/methods.rs:1237:5                             char                                                        const fn is_ascii_alphabetic(&self) -> bool;
core/src/char/methods.rs:1270:5                             char                                                        const fn is_ascii_uppercase(&self) -> bool;
core/src/char/methods.rs:1303:5                             char                                                        const fn is_ascii_lowercase(&self) -> bool;
core/src/char/methods.rs:1339:5                             char                                                        const fn is_ascii_alphanumeric(&self) -> bool;
core/src/char/methods.rs:1372:5                             char                                                        const fn is_ascii_digit(&self) -> bool;
core/src/char/methods.rs:1408:5                             char                                                        const fn is_ascii_hexdigit(&self) -> bool;
core/src/char/methods.rs:1445:5                             char                                                        const fn is_ascii_punctuation(&self) -> bool;
core/src/char/methods.rs:1478:5                             char                                                        const fn is_ascii_graphic(&self) -> bool;
core/src/char/methods.rs:1528:5                             char                                                        const fn is_ascii_whitespace(&self) -> bool;
core/src/char/methods.rs:1563:5                             char                                                        const fn is_ascii_control(&self) -> bool;
core/src/num/f32.rs:442:5                                   core::num::f32                                              const fn is_nan(self) -> bool;
core/src/num/f32.rs:473:5                                   core::num::f32                                              const fn is_infinite(self) -> bool;
core/src/num/f32.rs:494:5                                   core::num::f32                                              const fn is_finite(self) -> bool;
core/src/num/f32.rs:521:5                                   core::num::f32                                              const fn is_subnormal(self) -> bool;
core/src/num/f32.rs:547:5                                   core::num::f32                                              const fn is_normal(self) -> bool;
core/src/num/f32.rs:593:5                                   core::num::f32                                              const fn is_sign_positive(self) -> bool;
core/src/num/f32.rs:610:5                                   core::num::f32                                              const fn is_sign_negative(self) -> bool;
core/src/num/f64.rs:441:5                                   core::num::f64                                              const fn is_nan(self) -> bool;
core/src/num/f64.rs:472:5                                   core::num::f64                                              const fn is_infinite(self) -> bool;
core/src/num/f64.rs:493:5                                   core::num::f64                                              const fn is_finite(self) -> bool;
core/src/num/f64.rs:520:5                                   core::num::f64                                              const fn is_subnormal(self) -> bool;
core/src/num/f64.rs:546:5                                   core::num::f64                                              const fn is_normal(self) -> bool;
core/src/num/f64.rs:592:5                                   core::num::f64                                              const fn is_sign_positive(self) -> bool;
core/src/num/f64.rs:600:5                                   core::num::f64                                              fn is_positive(self) -> bool;
core/src/num/f64.rs:617:5                                   core::num::f64                                              const fn is_sign_negative(self) -> bool;
core/src/num/f64.rs:625:5                                   core::num::f64                                              fn is_negative(self) -> bool;
core/src/num/int_macros.rs:2318:9                           $Int                                                        const fn is_positive(self) -> bool;
core/src/num/int_macros.rs:2334:9                           $Int                                                        const fn is_negative(self) -> bool;
core/src/num/mod.rs:265:5                                   u8                                                          const fn is_ascii(&self) -> bool;
core/src/num/mod.rs:423:5                                   u8                                                          const fn is_ascii_alphabetic(&self) -> bool;
core/src/num/mod.rs:456:5                                   u8                                                          const fn is_ascii_uppercase(&self) -> bool;
core/src/num/mod.rs:489:5                                   u8                                                          const fn is_ascii_lowercase(&self) -> bool;
core/src/num/mod.rs:525:5                                   u8                                                          const fn is_ascii_alphanumeric(&self) -> bool;
core/src/num/mod.rs:558:5                                   u8                                                          const fn is_ascii_digit(&self) -> bool;
core/src/num/mod.rs:594:5                                   u8                                                          const fn is_ascii_hexdigit(&self) -> bool;
core/src/num/mod.rs:631:5                                   u8                                                          const fn is_ascii_punctuation(&self) -> bool;
core/src/num/mod.rs:664:5                                   u8                                                          const fn is_ascii_graphic(&self) -> bool;
core/src/num/mod.rs:714:5                                   u8                                                          const fn is_ascii_whitespace(&self) -> bool;
core/src/num/mod.rs:749:5                                   u8                                                          const fn is_ascii_control(&self) -> bool;
core/src/num/nonzero.rs:883:17                              core::num::NonZero$Int                                      const fn is_power_of_two(self) -> bool;
core/src/num/saturating.rs:852:13                           core::num::Saturating<$Int>                                 const fn is_positive(self) -> bool;
core/src/num/saturating.rs:872:13                           core::num::Saturating<$Int>                                 const fn is_negative(self) -> bool;
core/src/num/saturating.rs:930:13                           core::num::Saturating<$Int>                                 fn is_power_of_two(self) -> bool;
core/src/num/uint_macros.rs:1993:9                          $Int                                                        const fn is_power_of_two(self) -> bool;
core/src/num/wrapping.rs:849:13                             core::num::Wrapping<$Int>                                   const fn is_positive(self) -> bool;
core/src/num/wrapping.rs:869:13                             core::num::Wrapping<$Int>                                   const fn is_negative(self) -> bool;
core/src/num/wrapping.rs:916:13                             core::num::Wrapping<$Int>                                   fn is_power_of_two(self) -> bool;
core/src/str/mod.rs:193:5                                   str                                                         fn is_char_boundary(&self, index: usize) -> bool;
core/src/time.rs:297:5                                      core::time::Duration                                        const fn is_zero(&self) -> bool;
```

# Add #[must_use] to char escape methods #89719

```rust
core/src/char/methods.rs:382:5                              char                                                        fn escape_unicode(self) -> EscapeUnicode;
core/src/char/methods.rs:458:5                              char                                                        fn escape_debug(self) -> EscapeDebug;
core/src/char/methods.rs:512:5                              char                                                        fn escape_default(self) -> EscapeDefault;
```

# Add #[must_use] to math and bit manipulation methods #89720

```rust
core/src/num/f32.rs:641:5                                   core::num::f32                                              fn to_degrees(self) -> f32;
core/src/num/f32.rs:658:5                                   core::num::f32                                              fn to_radians(self) -> f32;
core/src/num/f32.rs:717:5                                   core::num::f32                                              unsafe fn to_int_unchecked<Int>(self) -> Int;
core/src/num/f32.rs:746:5                                   core::num::f32                                              const fn to_bits(self) -> u32;
core/src/num/f32.rs:808:5                                   core::num::f32                                              const fn to_be_bytes(self) -> [u8; 4];
core/src/num/f32.rs:824:5                                   core::num::f32                                              const fn to_le_bytes(self) -> [u8; 4];
core/src/num/f32.rs:853:5                                   core::num::f32                                              const fn to_ne_bytes(self) -> [u8; 4];
core/src/num/f64.rs:654:5                                   core::num::f64                                              fn to_degrees(self) -> f64;
core/src/num/f64.rs:672:5                                   core::num::f64                                              fn to_radians(self) -> f64;
core/src/num/f64.rs:731:5                                   core::num::f64                                              unsafe fn to_int_unchecked<Int>(self) -> Int;
core/src/num/f64.rs:760:5                                   core::num::f64                                              const fn to_bits(self) -> u64;
core/src/num/f64.rs:822:5                                   core::num::f64                                              const fn to_be_bytes(self) -> [u8; 8];
core/src/num/f64.rs:838:5                                   core::num::f64                                              const fn to_le_bytes(self) -> [u8; 8];
core/src/num/f64.rs:867:5                                   core::num::f64                                              const fn to_ne_bytes(self) -> [u8; 8];
core/src/num/int_macros.rs:85:9                             $Int                                                        const fn count_ones(self) -> u32;
core/src/num/int_macros.rs:85:9                             $Int                                                        const fn count_ones(self) -> u32;
core/src/num/int_macros.rs:99:9                             $Int                                                        const fn count_zeros(self) -> u32;
core/src/num/int_macros.rs:99:9                             $Int                                                        const fn count_zeros(self) -> u32;
core/src/num/int_macros.rs:117:9                            $Int                                                        const fn leading_zeros(self) -> u32;
core/src/num/int_macros.rs:135:9                            $Int                                                        const fn trailing_zeros(self) -> u32;
core/src/num/int_macros.rs:153:9                            $Int                                                        const fn leading_ones(self) -> u32;
core/src/num/int_macros.rs:171:9                            $Int                                                        const fn trailing_ones(self) -> u32;
core/src/num/int_macros.rs:240:9                            $Int                                                        const fn swap_bytes(self) -> Self;
core/src/num/int_macros.rs:348:9                            $Int                                                        const fn to_be(self) -> Self;
core/src/num/int_macros.rs:379:9                            $Int                                                        const fn to_le(self) -> Self;
core/src/num/int_macros.rs:649:9                            $Int                                                        const fn checked_neg(self) -> Option<Self>;
core/src/num/int_macros.rs:761:9                            $Int                                                        const fn checked_abs(self) -> Option<Self>;
core/src/num/int_macros.rs:867:9                            $Int                                                        const fn saturating_neg(self) -> Self;
core/src/num/int_macros.rs:888:9                            $Int                                                        const fn saturating_abs(self) -> Self;
core/src/num/int_macros.rs:1174:9                           $Int                                                        const fn wrapping_neg(self) -> Self;
core/src/num/int_macros.rs:1257:9                           $Int                                                        const fn wrapping_abs(self) -> Self;
core/src/num/int_macros.rs:1271:9                           $Int                                                        const fn unsigned_abs(self) -> $UnsignedT;
core/src/num/int_macros.rs:1595:9                           $Int                                                        const fn overflowing_neg(self) -> (Self, bool);
core/src/num/int_macros.rs:1669:9                           $Int                                                        const fn overflowing_abs(self) -> (Self, bool);
core/src/num/int_macros.rs:2227:9                           $Int                                                        const fn abs(self) -> Self;
core/src/num/int_macros.rs:2257:9                           $Int                                                        const fn abs_diff(self) -> $UnsignedT;
core/src/num/int_macros.rs:2296:9                           $Int                                                        const fn signum(self) -> Self;
core/src/num/int_macros.rs:2350:9                           $Int                                                        const fn to_be_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/int_macros.rs:2368:9                           $Int                                                        const fn to_le_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/int_macros.rs:2402:9                           $Int                                                        const fn to_ne_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/nonzero.rs:202:17                              core::num::NonZero$Int                                      const fn leading_zeros(self) -> u32;
core/src/num/nonzero.rs:224:17                              core::num::NonZero$Int                                      const fn trailing_zeros(self) -> u32;
core/src/num/nonzero.rs:319:17                              core::num::NonZero$Int                                      const fn checked_add(self, other: $Int) -> Option<$Ty>;
core/src/num/nonzero.rs:352:17                              core::num::NonZero$Int                                      const fn saturating_add(self, other: $Int) -> $Ty;
core/src/num/nonzero.rs:382:17                              core::num::NonZero$Int                                      const unsafe fn unchecked_add(self, other: $Int) -> $Ty;
core/src/num/nonzero.rs:414:17                              core::num::NonZero$Int                                      const fn checked_next_power_of_two(self) -> Option<$Ty>;
core/src/num/nonzero.rs:464:17                              core::num::NonZero$Int                                      const fn abs(self) -> $Ty;
core/src/num/nonzero.rs:494:17                              core::num::NonZero$Int                                      const fn checked_abs(self) -> Option<$Ty>;
core/src/num/nonzero.rs:528:17                              core::num::NonZero$Int                                      const fn overflowing_abs(self) -> ($Ty, bool);
core/src/num/nonzero.rs:566:17                              core::num::NonZero$Int                                      const fn saturating_abs(self) -> $Ty;
core/src/num/nonzero.rs:599:17                              core::num::NonZero$Int                                      const fn wrapping_abs(self) -> $Ty;
core/src/num/nonzero.rs:632:17                              core::num::NonZero$Int                                      const fn unsigned_abs(self) -> $Uty;
core/src/num/nonzero.rs:679:17                              core::num::NonZero$Int                                      const fn checked_mul(self, other: $Ty) -> Option<$Ty>;
core/src/num/nonzero.rs:713:17                              core::num::NonZero$Int                                      const fn saturating_mul(self, other: $Ty) -> $Ty;
core/src/num/nonzero.rs:753:17                              core::num::NonZero$Int                                      const unsafe fn unchecked_mul(self, other: $Ty) -> $Ty;
core/src/num/nonzero.rs:782:17                              core::num::NonZero$Int                                      const fn checked_pow(self, other: u32) -> Option<$Ty>;
core/src/num/nonzero.rs:824:17                              core::num::NonZero$Int                                      const fn saturating_pow(self, other: u32) -> $Ty;
core/src/num/saturating.rs:478:13                           core::num::Saturating<$Int>                                 const fn count_ones(self) -> u32;
core/src/num/saturating.rs:496:13                           core::num::Saturating<$Int>                                 const fn count_zeros(self) -> u32;
core/src/num/saturating.rs:516:13                           core::num::Saturating<$Int>                                 const fn trailing_zeros(self) -> u32;
core/src/num/saturating.rs:542:13                           core::num::Saturating<$Int>                                 const fn rotate_left(self, n: u32) -> Self;
core/src/num/saturating.rs:568:13                           core::num::Saturating<$Int>                                 const fn rotate_right(self, n: u32) -> Self;
core/src/num/saturating.rs:592:13                           core::num::Saturating<$Int>                                 const fn swap_bytes(self) -> Self;
core/src/num/saturating.rs:702:13                           core::num::Saturating<$Int>                                 const fn to_be(self) -> Self;
core/src/num/saturating.rs:729:13                           core::num::Saturating<$Int>                                 const fn to_le(self) -> Self;
core/src/num/saturating.rs:757:13                           core::num::Saturating<$Int>                                 fn pow(self, exp: u32) -> Self;
core/src/num/saturating.rs:785:13                           core::num::Saturating<$Int>                                 const fn leading_zeros(self) -> u32;
core/src/num/saturating.rs:808:13                           core::num::Saturating<$Int>                                 fn abs(self) -> Saturating<$t>;
core/src/num/saturating.rs:832:13                           core::num::Saturating<$Int>                                 fn signum(self) -> Saturating<$t>;
core/src/num/saturating.rs:911:13                           core::num::Saturating<$Int>                                 const fn leading_zeros(self) -> u32;
core/src/num/uint_macros.rs:84:9                            $Int                                                        const fn count_ones(self) -> u32;
core/src/num/uint_macros.rs:100:9                           $Int                                                        const fn count_zeros(self) -> u32;
core/src/num/uint_macros.rs:118:9                           $Int                                                        const fn leading_zeros(self) -> u32;
core/src/num/uint_macros.rs:137:9                           $Int                                                        const fn trailing_zeros(self) -> u32;
core/src/num/uint_macros.rs:155:9                           $Int                                                        const fn leading_ones(self) -> u32;
core/src/num/uint_macros.rs:174:9                           $Int                                                        const fn trailing_ones(self) -> u32;
core/src/num/uint_macros.rs:242:9                           $Int                                                        const fn swap_bytes(self) -> Self;
core/src/num/uint_macros.rs:353:9                           $Int                                                        const fn to_be(self) -> Self;
core/src/num/uint_macros.rs:385:9                           $Int                                                        const fn to_le(self) -> Self;
core/src/num/uint_macros.rs:842:9                           $Int                                                        const fn checked_neg(self) -> Option<Self>;
core/src/num/uint_macros.rs:1277:9                          $Int                                                        const fn wrapping_neg(self) -> Self;
core/src/num/uint_macros.rs:1506:9                          $Int                                                        const fn abs_diff(self, other: Self) -> Self;
core/src/num/uint_macros.rs:1679:9                          $Int                                                        const fn overflowing_neg(self) -> (Self, bool);
core/src/num/uint_macros.rs:1894:9                          $Int                                                        const fn unstable_div_floor(self, rhs: Self) -> Self;
core/src/num/uint_macros.rs:1915:9                          $Int                                                        const fn unstable_div_ceil(self, rhs: Self) -> Self;
core/src/num/uint_macros.rs:2038:9                          $Int                                                        const fn next_power_of_two(self) -> Self;
core/src/num/uint_macros.rs:2058:9                          $Int                                                        const fn checked_next_power_of_two(self) -> Option<Self>;
core/src/num/uint_macros.rs:2080:9                          $Int                                                        const fn wrapping_next_power_of_two(self) -> Self;
core/src/num/uint_macros.rs:2098:9                          $Int                                                        const fn to_be_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/uint_macros.rs:2116:9                          $Int                                                        const fn to_le_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/uint_macros.rs:2150:9                          $Int                                                        const fn to_ne_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/wrapping.rs:473:13                             core::num::Wrapping<$Int>                                   const fn count_ones(self) -> u32;
core/src/num/wrapping.rs:491:13                             core::num::Wrapping<$Int>                                   const fn count_zeros(self) -> u32;
core/src/num/wrapping.rs:511:13                             core::num::Wrapping<$Int>                                   const fn trailing_zeros(self) -> u32;
core/src/num/wrapping.rs:537:13                             core::num::Wrapping<$Int>                                   const fn rotate_left(self, n: u32) -> Self;
core/src/num/wrapping.rs:563:13                             core::num::Wrapping<$Int>                                   const fn rotate_right(self, n: u32) -> Self;
core/src/num/wrapping.rs:587:13                             core::num::Wrapping<$Int>                                   const fn swap_bytes(self) -> Self;
core/src/num/wrapping.rs:696:13                             core::num::Wrapping<$Int>                                   const fn to_be(self) -> Self;
core/src/num/wrapping.rs:723:13                             core::num::Wrapping<$Int>                                   const fn to_le(self) -> Self;
core/src/num/wrapping.rs:750:13                             core::num::Wrapping<$Int>                                   fn pow(self, exp: 32) -> Self;
core/src/num/wrapping.rs:779:13                             core::num::Wrapping<$Int>                                   const fn leading_zeros(self) -> u32;
core/src/num/wrapping.rs:805:13                             core::num::Wrapping<$Int>                                   fn abs(self) -> Wrapping<$t>;
core/src/num/wrapping.rs:829:13                             core::num::Wrapping<$Int>                                   fn signum(self) -> Wrapping<$t>;
core/src/num/wrapping.rs:897:13                             core::num::Wrapping<$Int>                                   const fn leading_zeros(self) -> u32;
core/src/num/wrapping.rs:940:13                             core::num::Wrapping<$Int>                                   fn next_power_of_two(self) -> Self;
core/src/time.rs:469:5                                      core::time::Duration                                        const fn checked_add(self, rhs: Duration) -> Option<Duration>;
core/src/time.rs:502:5                                      core::time::Duration                                        const fn saturating_add(self, rhs: Duration) -> Duration;
core/src/time.rs:525:5                                      core::time::Duration                                        const fn checked_sub(self, rhs: Duration) -> Option<Duration>;
core/src/time.rs:556:5                                      core::time::Duration                                        const fn saturating_sub(self, rhs: Duration) -> Duration;
core/src/time.rs:579:5                                      core::time::Duration                                        const fn checked_mul(self, rhs: u32) -> Option<Duration>;
core/src/time.rs:608:5                                      core::time::Duration                                        const fn saturating_mul(self, rhs: u32) -> Duration;
core/src/time.rs:632:5                                      core::time::Duration                                        const fn checked_div(self, rhs: u32) -> Option<Duration>;
core/src/time.rs:819:5                                      core::time::Duration                                        const fn mul_f64(self, rhs: f64) -> Duration;
core/src/time.rs:841:5                                      core::time::Duration                                        const fn mul_f32(self, rhs: f32) -> Duration;
core/src/time.rs:862:5                                      core::time::Duration                                        const fn div_f64(self, rhs: f64) -> Duration;
core/src/time.rs:885:5                                      core::time::Duration                                        const fn div_f32(self, rhs: f32) -> Duration;
core/src/time.rs:903:5                                      core::time::Duration                                        const fn div_duration_f64(self, rhs: Duration) -> f64;
core/src/time.rs:921:5                                      core::time::Duration                                        const fn div_duration_f32(self, rhs: Duration) -> f32;
```

# Add #[must_use] to constructors #TBD

```rust
alloc/src/boxed.rs:215:5                                    alloc::boxed::Box                                           fn new_uninit() -> Box<mem::MaybeUninit<T>>;
alloc/src/boxed.rs:240:5                                    alloc::boxed::Box                                           fn new_zeroed() -> Box<mem::MaybeUninit<T>>;
alloc/src/boxed.rs:564:5                                    alloc::boxed::Box                                           fn new_uninit_slice(len: usize) -> Box<[mem::MaybeUninit<T>]>;
alloc/src/boxed.rs:588:5                                    alloc::boxed::Box                                           fn new_zeroed_slice(len: usize) -> Box<[mem::MaybeUninit<T>]>;
alloc/src/collections/binary_heap.rs:367:5                  alloc::collections::binary_heap::BinaryHeap<T>              fn new() -> BinaryHeap<T>;
alloc/src/collections/binary_heap.rs:386:5                  alloc::collections::binary_heap::BinaryHeap<T>              fn with_capacity(capacity: usize) -> BinaryHeap<T>;
alloc/src/collections/btree/map.rs:505:5                    alloc::collections::btree_map::BTreeMap<K, V>               const fn new() -> BTreeMap<K, V>;
alloc/src/collections/btree/set.rs:251:5                    alloc::collections::btree_set::BTreeSet<T>                  const fn new() -> BTreeSet<T>;
alloc/src/collections/linked_list.rs:420:5                  alloc::collections::linked_list::LinkedList<T>              const fn new() -> Self;
alloc/src/collections/vec_deque/mod.rs:478:5                alloc::collections::vec_deque::VecDeque<T>                  fn new() -> VecDeque<T>;
alloc/src/collections/vec_deque/mod.rs:493:5                alloc::collections::vec_deque::VecDeque<T>                  fn with_capacity(capacity: usize) -> VecDeque<T>;
alloc/src/raw_vec.rs:72:5                                   alloc::raw_vec::RawVec<T, Global>                           const fn new() -> Self;
alloc/src/raw_vec.rs:91:5                                   alloc::raw_vec::RawVec<T, Global>                           fn with_capacity(capacity: usize) -> Self;
alloc/src/raw_vec.rs:98:5                                   alloc::raw_vec::RawVec<T, Global>                           fn with_capacity_zeroed(capacity: usize) -> Self;
alloc/src/rc.rs:455:5                                       alloc::rc::Rc<T>                                            fn new_uninit() -> Rc<mem::MaybeUninit<T>>;
alloc/src/rc.rs:487:5                                       alloc::rc::Rc<T>                                            fn new_zeroed() -> Rc<mem::MaybeUninit<T>>;
alloc/src/rc.rs:661:5                                       alloc::rc::Rc<T>                                            fn new_uninit_slice(len: usize) -> Rc<[mem::MaybeUninit<T>]>;
alloc/src/rc.rs:687:5                                       alloc::rc::Rc<T>                                            fn new_zeroed_slice(len: usize) -> Rc<[mem::MaybeUninit<T>]>;
alloc/src/rc.rs:2047:5                                      alloc::rc::Weak<T>                                          fn new() -> Weak<T>;
alloc/src/string.rs:381:5                                   alloc::string::String                                       const fn new() -> String;
alloc/src/string.rs:425:5                                   alloc::string::String                                       fn with_capacity(capacity: usize) -> String;
alloc/src/sync.rs:451:5                                     alloc::sync::Arc<T>                                         fn new_uninit() -> Arc<mem::MaybeUninit<T>>;
alloc/src/sync.rs:483:5                                     alloc::sync::Arc<T>                                         fn new_zeroed() -> Arc<mem::MaybeUninit<T>>;
alloc/src/sync.rs:665:5                                     alloc::sync::Arc<[T]>                                       fn new_uninit_slice(len: usize) -> Arc<[mem::MaybeUninit<T>]>;
alloc/src/sync.rs:691:5                                     alloc::sync::Arc<[T]>                                       fn new_zeroed_slice(len: usize) -> Arc<[mem::MaybeUninit<T>]>;
alloc/src/sync.rs:1681:5                                    alloc::sync::Weak<T>                                        fn new() -> Weak<T>;
alloc/src/vec/mod.rs:423:5                                  alloc::vec::Vec<T>                                          const fn new() -> Self;
alloc/src/vec/mod.rs:467:5                                  alloc::vec::Vec<T>                                          fn with_capacity(capacity: usize) -> Self;
core/src/alloc/layout.rs:123:5                              core::alloc::Layout                                         const fn new<T>() -> Self;
core/src/hash/sip.rs:160:5                                  core::hash::SipHasher                                       fn new() -> SipHasher;
core/src/hash/sip.rs:171:5                                  core::hash::SipHasher                                       fn new_with_keys(key0: u64, key1: u64) -> SipHasher;
core/src/lazy.rs:86:5                                       core::lazy::Lazy                                            const fn new() -> OnceCell<T>;
core/src/mem/maybe_uninit.rs:317:5                          core::mem::MaybeUninit<T>                                   const fn uninit() -> MaybeUninit<T>;
core/src/mem/maybe_uninit.rs:353:5                          core::mem::MaybeUninit<T>                                   const fn uninit_array<const LEN: usize>() -> [Self; LEN];
core/src/mem/maybe_uninit.rs:396:5                          core::mem::MaybeUninit<T>                                   fn zeroed() -> MaybeUninit<T>;
core/src/num/nonzero.rs:54:17                               core::num::NonZero$Int                                      const unsafe fn new_unchecked(n: $Int) -> Self;
core/src/num/nonzero.rs:63:17                               core::num::NonZero$Int                                      const fn new(n: $Int) -> Option<Self>;
core/src/sync/atomic.rs:293:5                               core::sync::atomic::AtomicBool                              const fn new(v: bool) -> AtomicBool;
core/src/sync/atomic.rs:1395:13                             core::sync::atomic::Atomic$int_type                         const fn new(v: $int_type) -> Self;
core/src/task/wake.rs:42:5                                  core::task::RawWaker                                        const fn new(data: *const (), vtable: &'static RawWakerVTable) -> RawWaker;
core/src/time.rs:184:5                                      core::time::Duration                                        const fn new(secs: u64, nanos: u32) -> Duration;
std/src/collections/hash/map.rs:227:5                       std::collections::hash_map::HashMap<K, V>                   fn new() -> HashMap<K, V, RandomState>;
std/src/collections/hash/map.rs:244:5                       std::collections::hash_map::HashMap<K, V>                   fn with_capacity(capacity: usize) -> HashMap<K, V, RandomState>;
std/src/collections/hash/map.rs:2895:5                      std::collections::hash_map::RandomState                     fn new() -> RandomState;
std/src/collections/hash/map.rs:2946:5                      std::collections::hash_map::DefaultHasher                   fn new() -> DefaultHasher;
std/src/collections/hash/set.rs:130:5                       std::collections::hash_set::HashSet<T>                      fn new() -> HashSet<T, RandomState>;
std/src/collections/hash/set.rs:148:5                       std::collections::hash_set::HashSet<T>                      fn with_capacity(capacity: usize) -> HashSet<T, RandomState>;
std/src/ffi/os_str.rs:123:5                                 std::ffi::OsString                                          fn new() -> OsString;
std/src/ffi/os_str.rs:203:5                                 std::ffi::OsString                                          fn with_capacity(capacity: usize) -> OsString;
std/src/fs.rs:725:5                                         std::fs::OpenOptions                                        fn new() -> Self;
std/src/fs.rs:2165:5                                        std::fs::DirBuilder                                         fn new() -> DirBuilder;
std/src/io/mod.rs:1199:5                                    std::io::IoSlice<'a>                                        fn new(buf: &'a [u8]) -> IoSlice<'a>;
std/src/lazy.rs:174:5                                       std::lazy::SyncOnceCell<T>                                  const fn new() -> SyncOnceCell<T>;
std/src/net/addr.rs:134:5                                   std::net::SocketAddr                                        fn new(ip: IpAddr, port: u16) -> SocketAddr;
std/src/net/addr.rs:275:5                                   std::net::SocketAddrV4                                      fn new(ip: Ipv4Addr, port: u16) -> SocketAddrV4;
std/src/net/addr.rs:371:5                                   std::net::SocketAddrV6                                      fn new(ip: Ipv6Addr, port: u16, flowinfo: u32, scope_id: u32) -> SocketAddrV6;
std/src/net/ip.rs:446:5                                     std::net::Ipv4Addr                                          const fn new(a: u8, b: u8, c: u8, d: u8) -> Ipv4Addr;
std/src/net/ip.rs:1196:5                                    std::net::Ipv6Addr                                          const fn new(a: u16, b: u16, c: u16, d: u16, e: u16, f: u16, g: u16, h: u16) -> Ipv6Addr;
std/src/os/unix/net/ancillary.rs:192:5                      std::os::unix::net::SocketCred                              fn new() -> SocketCred;
std/src/path.rs:1149:5                                      std::path::PathBuf                                          fn new() -> PathBuf;
std/src/path.rs:1173:5                                      std::path::PathBuf                                          fn with_capacity(capacity: usize) -> PathBuf;
std/src/sync/barrier.rs:83:5                                std::sync::Barrier                                          fn new(n: usize) -> Barrier;
std/src/sync/condvar.rs:124:5                               std::sync::Condvar                                          fn new() -> Condvar;
std/src/sync/once.rs:189:5                                  std::sync::Once                                             const fn new() -> Once;
std/src/thread/mod.rs:289:5                                 std::thread::Builder
fn new() -> Builder;
```
