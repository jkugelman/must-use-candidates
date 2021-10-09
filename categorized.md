# Misleading

```rust
core/src/num/f32.rs:641:5                                   core::num::f32                                              fn to_degrees(self) -> f32;
core/src/num/f32.rs:658:5                                   core::num::f32                                              fn to_radians(self) -> f32;
core/src/num/f64.rs:654:5                                   core::num::f64                                              fn to_degrees(self) -> f64;
core/src/num/f64.rs:672:5                                   core::num::f64                                              fn to_radians(self) -> f64;
core/src/num/saturating.rs:542:13                           core::num::Saturating<$Int>                                 const fn rotate_left(self, n: u32) -> Self;
core/src/num/saturating.rs:568:13                           core::num::Saturating<$Int>                                 const fn rotate_right(self, n: u32) -> Self;
core/src/num/wrapping.rs:537:13                             core::num::Wrapping<$Int>                                   const fn rotate_left(self, n: u32) -> Self;
core/src/num/wrapping.rs:563:13                             core::num::Wrapping<$Int>                                   const fn rotate_right(self, n: u32) -> Self;
std/src/net/ip.rs:423:5                                     std::net::IpAddr                                            const fn to_canonical(&self) -> IpAddr;
std/src/net/ip.rs:1683:5                                    std::net::Ipv6Addr                                          const fn to_canonical(&self) -> IpAddr;

alloc/src/rc.rs:2226:5                                      alloc::rc::Weak<T>                                          fn upgrade(&self) -> Option<Rc<T>>;
alloc/src/sync.rs:894:5                                     alloc::sync::Arc<T>                                         fn downgrade(this: &Self) -> Weak<T>;
alloc/src/sync.rs:1856:5                                    alloc::sync::Weak<T>                                        fn upgrade(&self) -> Option<Arc<T>>;
core/src/alloc/layout.rs:115:5                              core::alloc::Layout                                         const fn align(&self) -> usize;
core/src/alloc/layout.rs:264:5                              core::alloc::Layout                                         fn pad_to_align(&self) -> Layout;
std/src/path.rs:2510:5                                      std::path::Path                                             fn display(&self) -> Display<'_>;

core/src/num/nonzero.rs:319:17                              core::num::NonZero$Int                                      const fn checked_add(self, other: $Int) -> Option<$Ty>;
core/src/num/nonzero.rs:352:17                              core::num::NonZero$Int                                      const fn saturating_add(self, other: $Int) -> $Ty;
core/src/num/nonzero.rs:382:17                              core::num::NonZero$Int                                      const unsafe fn unchecked_add(self, other: $Int) -> $Ty;
core/src/num/nonzero.rs:679:17                              core::num::NonZero$Int                                      const fn checked_mul(self, other: $Ty) -> Option<$Ty>;
core/src/num/nonzero.rs:713:17                              core::num::NonZero$Int                                      const fn saturating_mul(self, other: $Ty) -> $Ty;
core/src/num/nonzero.rs:753:17                              core::num::NonZero$Int                                      const unsafe fn unchecked_mul(self, other: $Ty) -> $Ty;
core/src/num/nonzero.rs:782:17                              core::num::NonZero$Int                                      const fn checked_pow(self, other: u32) -> Option<$Ty>;
core/src/num/nonzero.rs:824:17                              core::num::NonZero$Int                                      const fn saturating_pow(self, other: u32) -> $Ty;
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

# Discarded guard

```rust
std/src/io/stdio.rs:489:5                                   std::io::Stdin                                              fn split(self, byte: u8) -> Split<StdinLock<'static>>;
```

# Discarded builder

```rust
std/src/thread/mod.rs:318:5                                 std::thread::Builder                                        fn name(mut self, name: String) -> Builder;
std/src/thread/mod.rs:341:5                                 std::thread::Builder                                        fn stack_size(mut self, size: usize) -> Builder;
```

# Expensive computations

```rust
alloc/src/collections/btree/set.rs:308:5                    alloc::collections::btree_set::BTreeSet<T>                  fn difference<'a>(&'a self, other: &'a BTreeSet<T>) -> Difference<'a, T>;
alloc/src/collections/btree/set.rs:369:5                    alloc::collections::btree_set::BTreeSet<T>                  fn symmetric_difference<'a>(&'a self, other: &'a BTreeSet<T>) -> SymmetricDifference<'a, T>
alloc/src/collections/btree/set.rs:397:5                    alloc::collections::btree_set::BTreeSet<T>                  fn intersection<'a>(&'a self, other: &'a BTreeSet<T>) -> Intersection<'a, T>;
alloc/src/collections/btree/set.rs:448:5                    alloc::collections::btree_set::BTreeSet<T>                  fn union<'a>(&'a self, other: &'a BTreeSet<T>) -> Union<'a, T>;
alloc/src/collections/btree/set.rs:538:5                    alloc::collections::btree_set::BTreeSet<T>                  fn is_disjoint(&self, other: &BTreeSet<T>) -> bool;
alloc/src/collections/btree/set.rs:563:5                    alloc::collections::btree_set::BTreeSet<T>                  fn is_subset(&self, other: &BTreeSet<T>) -> bool;
alloc/src/collections/btree/set.rs:642:5                    alloc::collections::btree_set::BTreeSet<T>                  fn is_superset(&self, other: &BTreeSet<T>) -> bool;
alloc/src/string.rs:555:5                                   alloc::string::String                                       fn from_utf8_lossy(v: &[u8]) -> Cow<'_, str>;
alloc/src/string.rs:649:5                                   alloc::string::String                                       fn from_utf16_lossy(v: &[u16]) -> String;
core/src/slice/ascii.rs:15:5                                slice                                                       fn is_ascii(&self) -> bool;
core/src/slice/ascii.rs:25:5                                slice                                                       fn eq_ignore_ascii_case(&self, other: &[u8]) -> bool;
core/src/slice/memchr.rs:41:1                               core::slice                                                 fn memchr(x: u8, text: &[u8]) -> Option<usize>;
core/src/slice/memchr.rs:94:1                               core::slice                                                 fn memrchr(x: u8, text: &[u8]) -> Option<usize>;
core/src/str/lossy.rs:24:5                                  core::str::lossy::Utf8Lossy                                 fn chunks(&self) -> Utf8LossyChunksIter<'_>;
core/src/str/mod.rs:678:5                                   str                                                         fn chars(&self) -> Chars<'_>;
core/src/str/mod.rs:735:5                                   str                                                         fn char_indices(&self) -> CharIndices<'_>;
core/src/str/mod.rs:890:5                                   str                                                         fn lines(&self) -> Lines<'_>;
core/src/str/mod.rs:899:5                                   str                                                         fn lines_any(&self) -> LinesAny<'_>;
core/src/str/mod.rs:2236:5                                  str                                                         fn is_ascii(&self) -> bool;
core/src/str/mod.rs:2257:5                                  str                                                         fn eq_ignore_ascii_case(&self, other: &str) -> bool;
std/src/ffi/os_str.rs:821:5                                 std::ffi::OsStr                                             fn is_ascii(&self) -> bool;
std/src/path.rs:2082:5                                      std::path::Path                                             fn parent(&self) -> Option<&Path>;
std/src/path.rs:2123:5                                      std::path::Path                                             fn ancestors(&self) -> Ancestors<'_>;
std/src/path.rs:2148:5                                      std::path::Path                                             fn file_name(&self) -> Option<&OsStr>;
std/src/path.rs:2282:5                                      std::path::Path                                             fn file_stem(&self) -> Option<&OsStr>;
std/src/path.rs:2315:5                                      std::path::Path                                             fn file_prefix(&self) -> Option<&OsStr>;
std/src/path.rs:2339:5                                      std::path::Path                                             fn extension(&self) -> Option<&OsStr>;
std/src/path.rs:2454:5                                      std::path::Path                                             fn components(&self) -> Components<'_>;
```

# Consumers

Functions that take ownership of `self`.

```rust
alloc/src/collections/binary_heap.rs:852:5                  alloc::collections::binary_heap::BinaryHeap<T>              fn into_iter_sorted(self) -> IntoIterSorted<T>;
alloc/src/collections/binary_heap.rs:1032:5                 alloc::collections::binary_heap::BinaryHeap<T>              fn into_vec(self) -> Vec<T>;
alloc/src/collections/btree/map.rs:1268:5                   alloc::collections::btree_map::BTreeMap<K, V>               fn into_keys(self) -> IntoKeys<K, V>;
alloc/src/collections/btree/map.rs:1290:5                   alloc::collections::btree_map::BTreeMap<K, V>               fn into_values(self) -> IntoValues<K, V>;
alloc/src/collections/btree/map/entry.rs:452:5              alloc::collections::btree_map::OccupiedEntry<'a, K, V>      fn into_mut(self) -> &'a mut V;
alloc/src/rc.rs:2134:5                                      alloc::rc::Weak<T>                                          fn into_raw(self) -> *const T;
alloc/src/string.rs:680:5                                   alloc::string::String                                       fn into_raw_parts(self) -> (*mut u8, usize, usize);
alloc/src/string.rs:785:5                                   alloc::string::String                                       fn into_bytes(self) -> Vec<u8>;
alloc/src/string.rs:1742:5                                  alloc::string::String                                       fn into_boxed_str(self) -> Box<str>;
alloc/src/string.rs:1787:5                                  alloc::string::FromUtf8Error                                fn into_bytes(self) -> Vec<u8>;
alloc/src/sync.rs:739:5                                     alloc::sync::Arc<MaybeUninit<T>>                            unsafe fn assume_init(self) -> Arc<T>;
alloc/src/sync.rs:780:5                                     alloc::sync::Arc<[MaybeUninit<T>]>                          unsafe fn assume_init(self) -> Arc<[T]>;
alloc/src/sync.rs:1763:5                                    alloc::sync::Weak<T>                                        fn into_raw(self) -> *const T;
core/src/option.rs:1477:5                                   core::option::Option<&mut T>                                fn copied(self) -> Option<T>;
core/src/option.rs:1515:5                                   core::option::Option<&mut T>                                fn cloned(self) -> Option<T>;
core/src/pin.rs:720:5                                       core::pin::Pin<&'a mut T>                                   const fn into_ref(self) -> Pin<&'a T>;
core/src/pin.rs:736:5                                       core::pin::Pin<&'a mut T>                                   const fn get_mut(self) -> &'a mut T;
core/src/pin.rs:756:5                                       core::pin::Pin<&'a mut T>                                   const unsafe fn get_unchecked_mut(self) -> &'a mut T;
core/src/pin.rs:815:5                                       core::pin::Pin<&'a mut Pin<P>>                              fn as_deref_mut(self) -> Pin<&'a mut P::Target>;
core/src/ptr/metadata.rs:196:5                              core::mem::DynMetadata<Dyn>                                 fn size_of(self) -> usize;
core/src/ptr/metadata.rs:202:5                              core::mem::DynMetadata<Dyn>                                 fn align_of(self) -> usize;
core/src/ptr/metadata.rs:208:5                              core::mem::DynMetadata<Dyn>                                 fn layout(self) -> crate::alloc::Layout;
core/src/ptr/unique.rs:105:5                                core::mem::Unique<T>                                        const fn as_ptr(self) -> *mut T;
core/src/ptr/unique.rs:135:5                                core::mem::Unique<T>                                        const fn cast<U>(self) -> Unique<U>;
core/src/slice/iter.rs:271:5                                core::slice::IterMut<'a, T>                                 fn into_slice(self) -> &'a mut [T];
core/src/slice/iter.rs:1873:5                               core::slice::ChunksExactMut<'a, T>                          fn into_remainder(self) -> &'a mut [T];
core/src/slice/iter.rs:2268:5                               core::slice::ArrayChunksMut<'a, T, N>                       fn into_remainder(self) -> &'a mut [T];
core/src/slice/iter.rs:2879:5                               core::slice::RChunksExactMut<'a, T>                         fn into_remainder(self) -> &'a mut [T];
std/src/collections/hash/map.rs:1724:5                      std::collections::hash_map::RawOccupiedEntryMut<'a, K, V>   fn into_key(self) -> &'a mut K;
std/src/collections/hash/map.rs:1739:5                      std::collections::hash_map::RawOccupiedEntryMut<'a, K, V>   fn into_mut(self) -> &'a mut V;
std/src/collections/hash/map.rs:1768:5                      std::collections::hash_map::RawOccupiedEntryMut<'a, K, V>   fn into_key_value(self) -> (&'a mut K, &'a mut V);
std/src/ffi/c_str.rs:325:5                                  std::ffi:FromVecWithNulError                                fn into_bytes(self) -> Vec<u8>;
std/src/ffi/c_str.rs:528:5                                  std::ffi::CString                                           fn into_raw(self) -> *mut c_char;
std/src/ffi/c_str.rs:575:5                                  std::ffi::CString                                           fn into_bytes(self) -> Vec<u8>;
std/src/ffi/c_str.rs:595:5                                  std::ffi::CString                                           fn into_bytes_with_nul(self) -> Vec<u8>;
std/src/ffi/c_str.rs:671:5                                  std::ffi::CString                                           fn into_boxed_c_str(self) -> Box<CStr>;
std/src/ffi/c_str.rs:1022:5                                 std::ffi::NulError                                          fn into_vec(self) -> Vec<u8>;
std/src/ffi/c_str.rs:1096:5                                 std::ffi::IntoStringError                                   fn into_cstring(self) -> CString;
std/src/ffi/os_str.rs:350:5                                 std::ffi::OsString                                          fn into_boxed_os_str(self) -> Box<OsStr>;
std/src/io/buffered/bufwriter.rs:480:5                      std::io::BufWriter<W>                                       fn into_inner(self) -> Vec<u8>;
std/src/io/error.rs:661:5                                   std::io::Error                                              fn into_inner(self) -> Option<Box<dyn error::Error + Send + Sync>>;
std/src/io/stdio.rs:446:5                                   std::io::Stdin                                              fn into_locked(self) -> StdinLock<'static>;
std/src/io/stdio.rs:467:5                                   std::io::Stdin                                              fn lines(self) -> Lines<StdinLock<'static>>;
std/src/io/stdio.rs:792:5                                   std::io::Stdout                                             fn into_locked(self) -> StdoutLock<'static>;
std/src/io/stdio.rs:1052:5                                  std::io::Stderr                                             fn into_locked(self) -> StderrLock<'static>;
std/src/net/tcp.rs:887:5                                    std::net::TcpListener                                       fn into_incoming(self) -> IntoIncoming;
std/src/path.rs:536:5                                       std::path::Component<'a>                                    fn as_os_str(self) -> &'a OsStr;
std/src/path.rs:1432:5                                      std::path::PathBuf                                          fn into_os_string(self) -> OsString;
std/src/path.rs:1439:5                                      std::path::PathBuf                                          fn into_boxed_path(self) -> Box<Path>;
```

# Conversions

```rust
core/src/ptr/non_null.rs:244:5                              core::mem::NonNull<T>                                       const fn to_raw_parts(self) -> (NonNull<()>, <T as super::Pointee>::Metadata);
core/src/ptr/non_null.rs:268:5                              core::mem::NonNull<T>                                       const fn as_ptr(self) -> *mut T;
core/src/ptr/non_null.rs:385:5                              core::mem::NonNull<T>                                       const fn cast<U>(self) -> NonNull<U>;
core/src/ptr/non_null.rs:460:5                              core::mem::NonNull<[T]>                                     const fn as_non_null_ptr(self) -> NonNull<T>;
core/src/ptr/non_null.rs:479:5                              core::mem::NonNull<[T]>                                     const fn as_mut_ptr(self) -> *mut T;

core/src/char/methods.rs:332:5                              char                                                        fn to_digit(self, radix: u32) -> Option<u32>;
std/src/ffi/c_str.rs:1330:5                                 std::ffi::CStr                                              fn to_bytes(&self) -> &[u8];
std/src/ffi/c_str.rs:1355:5                                 std::ffi::CStr                                              fn to_bytes_with_nul(&self) -> &[u8];
std/src/ffi/c_str.rs:1425:5                                 std::ffi::CStr                                              fn to_string_lossy(&self) -> Cow<'_, str>;
std/src/ffi/os_str.rs:576:5                                 std::ffi::OsStr                                             fn to_str(&self) -> Option<&str>;
std/src/ffi/os_str.rs:627:5                                 std::ffi::OsStr                                             fn to_string_lossy(&self) -> Cow<'_, str>;
std/src/ffi/os_str.rs:644:5                                 std::ffi::OsStr                                             fn to_os_string(&self) -> OsString;
std/src/net/ip.rs:885:5                                     std::net::Ipv4Addr                                          const fn to_ipv6_compatible(&self) -> Ipv6Addr;
std/src/net/ip.rs:910:5                                     std::net::Ipv4Addr                                          const fn to_ipv6_mapped(&self) -> Ipv6Addr;
std/src/net/ip.rs:1621:5                                    std::net::Ipv6Addr                                          const fn to_ipv4_mapped(&self) -> Option<Ipv4Addr>;
std/src/net/ip.rs:1658:5                                    std::net::Ipv6Addr                                          const fn to_ipv4(&self) -> Option<Ipv4Addr>;
std/src/path.rs:1944:5                                      std::path::Path                                             fn to_str(&self) -> Option<&str>;
std/src/path.rs:1970:5                                      std::path::Path                                             fn to_string_lossy(&self) -> Cow<'_, str>;
std/src/path.rs:1986:5                                      std::path::Path                                             fn to_path_buf(&self) -> PathBuf;

alloc/src/collections/binary_heap.rs:514:5                  alloc::collections::binary_heap::BinaryHeap<T>              fn into_sorted_vec(mut self) -> Vec<T>;
alloc/src/str.rs:247:5                                      str                                                         fn into_boxed_bytes(self: Box<str>) -> Box<[u8]>;
alloc/src/str.rs:484:5                                      str                                                         fn into_string(self: Box<str>) -> String;
alloc/src/sync.rs:801:5                                     alloc::sync::Arc<T>                                         fn into_raw(this: Self) -> *const T;
std/src/ffi/c_str.rs:1441:5                                 std::ffi::CStr                                              fn into_c_string(self: Box<CStr>) -> CString;
std/src/ffi/os_str.rs:700:5                                 std::ffi::OsStr                                             fn into_os_string(self: Box<OsStr>) -> OsString;
std/src/path.rs:2755:5                                      std::path::Path                                             fn into_path_buf(self: Box<Path>) -> PathBuf;
std/src/process.rs:1617:5                                   std::process::ExitStatusError                               fn into_status(&self) -> ExitStatus;

alloc/src/collections/binary_heap.rs:1010:5                 alloc::collections::binary_heap::BinaryHeap<T>              fn as_slice(&self) -> &[T];
alloc/src/collections/linked_list.rs:1388:5                 alloc::collections::linked_list::CursorMut<'a, T>           fn as_cursor(&self) -> Cursor<'_, T>;
alloc/src/rc.rs:2091:5                                      alloc::rc::Weak<T>                                          fn as_ptr(&self) -> *const T;
alloc/src/string.rs:802:5                                   alloc::string::String                                       fn as_str(&self) -> &str;
alloc/src/string.rs:1162:5                                  alloc::string::String                                       fn as_bytes(&self) -> &[u8];
alloc/src/string.rs:1764:5                                  alloc::string::FromUtf8Error                                fn as_bytes(&self) -> &[u8];
alloc/src/string.rs:2779:5                                  alloc::string::Drain<'a>                                    fn as_str(&self) -> &str;
alloc/src/sync.rs:824:5                                     alloc::sync::Arc<T>                                         fn as_ptr(this: &Self) -> *const T;
alloc/src/sync.rs:1720:5                                    alloc::sync::Weak<T>                                        fn as_ptr(&self) -> *const T;
alloc/src/vec/drain.rs:56:5                                 alloc::vec::Drain<'a, T, A>                                 fn as_slice(&self) -> &[T];
core/src/fmt/mod.rs:495:5                                   core::fmt::Arguments<'a>                                    const fn as_str(&self) -> Option<&'static str>;
core/src/option.rs:661:5                                    core::option::Option<T>                                     fn as_pin_ref(self: Pin<&Self>) -> Option<Pin<&T>>;
core/src/option.rs:672:5                                    core::option::Option<T>                                     fn as_pin_mut(self: Pin<&mut Self>) -> Option<Pin<&mut T>>;
core/src/ptr/non_null.rs:123:5                              core::mem::NonNull<T>                                       unsafe fn as_uninit_ref<'a>(&self) -> &'a MaybeUninit<T>;
core/src/ptr/non_null.rs:314:5                              core::mem::NonNull<T>                                       unsafe fn as_ref<'a>(&self) -> &'a T;
core/src/ptr/non_null.rs:522:5                              core::mem::NonNull<[T]>                                     unsafe fn as_uninit_slice<'a>(&self) -> &'a [MaybeUninit<T>];
core/src/ptr/non_null.rs:583:5                              core::mem::NonNull<[T]>                                     unsafe fn as_uninit_slice_mut<'a>(&self) -> &'a mut [MaybeUninit<T>];
core/src/ptr/unique.rs:115:5                                core::mem::Unique<T>                                        unsafe fn as_ref(&self) -> &T;
core/src/slice/iter.rs:128:5                                core::slice::Iter<'a, T>                                    fn as_slice(&self) -> &'a [T];
core/src/slice/iter.rs:301:5                                core::slice::IterMut<'a, T>                                 fn as_slice(&self) -> &[T];
core/src/str/iter.rs:113:5                                  core::str::Chars<'a>                                        fn as_str(&self) -> &'a str;
core/src/str/iter.rs:189:5                                  core::str::CharIndices<'a>                                  fn as_str(&self) -> &'a str;
core/src/str/iter.rs:1251:5                                 core::str::SplitWhitespace<'a>                              fn as_str(&self) -> &'a str;
core/src/str/iter.rs:1306:5                                 core::str::SplitAsciiWhitespace<'a>                         fn as_str(&self) -> &'a str;
core/src/str/mod.rs:234:5                                   str                                                         const fn as_bytes(&self) -> &[u8];
core/src/str/mod.rs:307:5                                   str                                                         const fn as_ptr(&self) -> *const u8;
core/src/time.rs:332:5                                      core::time::Duration                                        const fn as_secs(&self) -> u64;
core/src/time.rs:415:5                                      core::time::Duration                                        const fn as_millis(&self) -> u128;
core/src/time.rs:432:5                                      core::time::Duration                                        const fn as_micros(&self) -> u128;
core/src/time.rs:449:5                                      core::time::Duration                                        const fn as_nanos(&self) -> u128;
core/src/time.rs:659:5                                      core::time::Duration                                        const fn as_secs_f64(&self) -> f64;
core/src/time.rs:677:5                                      core::time::Duration                                        const fn as_secs_f32(&self) -> f32;
std/src/ffi/c_str.rs:300:5                                  std::ffi:FromVecWithNulError                                fn as_bytes(&self) -> &[u8];
std/src/ffi/c_str.rs:617:5                                  std::ffi::CString                                           fn as_bytes(&self) -> &[u8];
std/src/ffi/c_str.rs:636:5                                  std::ffi::CString                                           fn as_bytes_with_nul(&self) -> &[u8];
std/src/ffi/c_str.rs:654:5                                  std::ffi::CString                                           fn as_c_str(&self) -> &CStr;
std/src/ffi/c_str.rs:1307:5                                 std::ffi::CStr                                              const fn as_ptr(&self) -> *const c_char;
std/src/ffi/os_str.rs:140:5                                 std::ffi::OsString                                          fn as_os_str(&self) -> &OsStr;
std/src/os/unix/net/addr.rs:195:5                           std::os::unix::net::SocketAddr                              fn as_pathname(&self) -> Option<&Path>;
std/src/path.rs:431:5                                       std::path::PrefixComponent<'a>                              fn as_os_str(&self) -> &'a OsStr;
std/src/path.rs:679:5                                       std::path::Components<'a>                                   fn as_path(&self) -> &'a Path;
std/src/path.rs:824:5                                       std::path::Iter<'a>                                         fn as_path(&self) -> &'a Path;
std/src/path.rs:1189:5                                      std::path::PathBuf                                          fn as_path(&self) -> &Path;
std/src/path.rs:1922:5                                      std::path::Path                                             fn as_os_str(&self) -> &OsStr;
std/src/thread/mod.rs:1035:5                                std::thread::ThreadId                                       fn as_u64(&self) -> NonZeroU64;

core/src/ops/range.rs:747:5                                 core::ops::Bound<&T>                                        fn cloned(self) -> Bound<T>;
core/src/option.rs:1453:5                                   core::option::Option<&T>                                    const fn copied(self) -> Option<T>;
core/src/option.rs:1496:5                                   core::option::Option<&T>                                    fn cloned(self) -> Option<T>;
core/src/pin.rs:710:5                                       core::pin::Pin<&'a T>                                       const fn get_ref(self) -> &'a T;
```

# Expensive constructors

```rust
alloc/src/collections/binary_heap.rs:386:5                  alloc::collections::binary_heap::BinaryHeap<T>              fn with_capacity(capacity: usize) -> BinaryHeap<T>;
alloc/src/collections/vec_deque/mod.rs:493:5                alloc::collections::vec_deque::VecDeque<T>                  fn with_capacity(capacity: usize) -> VecDeque<T>;
alloc/src/raw_vec.rs:91:5                                   alloc::raw_vec::RawVec<T, Global>                           fn with_capacity(capacity: usize) -> Self;
alloc/src/raw_vec.rs:98:5                                   alloc::raw_vec::RawVec<T, Global>                           fn with_capacity_zeroed(capacity: usize) -> Self;
alloc/src/string.rs:425:5                                   alloc::string::String                                       fn with_capacity(capacity: usize) -> String;
alloc/src/vec/mod.rs:467:5                                  alloc::vec::Vec<T>                                          fn with_capacity(capacity: usize) -> Self;
std/src/collections/hash/map.rs:244:5                       std::collections::hash_map::HashMap<K, V>                   fn with_capacity(capacity: usize) -> HashMap<K, V, RandomState>;
std/src/collections/hash/set.rs:148:5                       std::collections::hash_set::HashSet<T>                      fn with_capacity(capacity: usize) -> HashSet<T, RandomState>;
std/src/ffi/os_str.rs:203:5                                 std::ffi::OsString                                          fn with_capacity(capacity: usize) -> OsString;
std/src/path.rs:1173:5                                      std::path::PathBuf                                          fn with_capacity(capacity: usize) -> PathBuf;

std/src/backtrace.rs:291:5                                  std::backtrace::Backtrace                                   fn capture() -> Backtrace;
std/src/backtrace.rs:309:5                                  std::backtrace::Backtrace                                   fn force_capture() -> Backtrace;
std/src/backtrace.rs:315:5                                  std::backtrace::Backtrace                                   const fn disabled() -> Backtrace;
std/src/env.rs:117:1                                        std::env                                                    fn vars() -> Vars;
std/src/env.rs:144:1                                        std::env                                                    fn vars_os() -> VarsOs;
std/src/env.rs:568:1                                        std::env                                                    fn home_dir() -> Option<PathBuf>;
std/src/env.rs:607:1                                        std::env                                                    fn temp_dir() -> PathBuf;
std/src/env.rs:747:1                                        std::env                                                    fn args() -> Args;
std/src/env.rs:782:1                                        std::env                                                    fn args_os() -> ArgsOs;
```

# Cheap constructors

```rust
alloc/src/str.rs:593:1                                      alloc::str                                                  unsafe fn from_boxed_utf8_unchecked(v: Box<[u8]>) -> Box<str>;
alloc/src/string.rs:765:5                                   alloc::string::String                                       unsafe fn from_utf8_unchecked(bytes: Vec<u8>) -> String;
core/src/alloc/layout.rs:98:5                               core::alloc::Layout                                         const unsafe fn from_size_align_unchecked(size: usize, align: usize) -> Self;
core/src/char/convert.rs:53:1                               core::char                                                  fn from_u32(i: u32) -> Option<char>;
core/src/char/convert.rs:92:1                               core::char                                                  unsafe fn from_u32_unchecked(i: u32) -> char;
core/src/char/convert.rs:323:1                              core::char                                                  fn from_digit(num: u32, radix: u32) -> Option<char>;
core/src/char/methods.rs:140:5                              char                                                        fn from_u32(i: u32) -> Option<char>;
core/src/char/methods.rs:181:5                              char                                                        unsafe fn from_u32_unchecked(i: u32) -> char;
core/src/char/methods.rs:237:5                              char                                                        fn from_digit(num: u32, radix: u32) -> Option<char>;
core/src/num/f32.rs:790:5                                   core::num::f32                                              const fn from_bits(v: u32) -> Self;
core/src/num/f32.rs:868:5                                   core::num::f32                                              const fn from_be_bytes(bytes: [u8; 4]) -> Self;
core/src/num/f32.rs:883:5                                   core::num::f32                                              const fn from_le_bytes(bytes: [u8; 4]) -> Self;
core/src/num/f32.rs:909:5                                   core::num::f32                                              const fn from_ne_bytes(bytes: [u8; 4]) -> Self;
core/src/num/f64.rs:804:5                                   core::num::f64                                              const fn from_bits(v: u64) -> Self;
core/src/num/f64.rs:882:5                                   core::num::f64                                              const fn from_be_bytes(bytes: [u8; 8]) -> Self;
core/src/num/f64.rs:897:5                                   core::num::f64                                              const fn from_le_bytes(bytes: [u8; 8]) -> Self;
core/src/num/f64.rs:923:5                                   core::num::f64                                              const fn from_ne_bytes(bytes: [u8; 8]) -> Self;
core/src/num/int_macros.rs:286:9                            $Int                                                        const fn from_be(x: Self) -> Self;
core/src/num/int_macros.rs:286:9                            $Int                                                        const fn from_be(x: Self) -> Self;
core/src/num/int_macros.rs:317:9                            $Int                                                        const fn from_le(x: Self) -> Self;
core/src/num/int_macros.rs:317:9                            $Int                                                        const fn from_le(x: Self) -> Self;
core/src/num/int_macros.rs:2434:9                           $Int                                                        const fn from_be_bytes(bytes: [u8; mem::size_of::<Self>()]) -> Self;
core/src/num/int_macros.rs:2464:9                           $Int                                                        const fn from_le_bytes(bytes: [u8; mem::size_of::<Self>()]) -> Self;
core/src/num/int_macros.rs:2507:9                           $Int                                                        const fn from_ne_bytes(bytes: [u8; mem::size_of::<Self>()]) -> Self;
core/src/num/saturating.rs:648:13                           core::num::Saturating<$Int>                                 const fn from_be(x: Self) -> Self;
core/src/num/saturating.rs:675:13                           core::num::Saturating<$Int>                                 const fn from_le(x: Self) -> Self;
core/src/num/uint_macros.rs:289:9                           $Int                                                        const fn from_be(x: Self) -> Self;
core/src/num/uint_macros.rs:321:9                           $Int                                                        const fn from_le(x: Self) -> Self;
core/src/num/uint_macros.rs:2182:9                          $Int                                                        const fn from_be_bytes(bytes: [u8; mem::size_of::<Self>()]) -> Self;
core/src/num/uint_macros.rs:2212:9                          $Int                                                        const fn from_le_bytes(bytes: [u8; mem::size_of::<Self>()]) -> Self;
core/src/num/uint_macros.rs:2255:9                          $Int                                                        const fn from_ne_bytes(bytes: [u8; mem::size_of::<Self>()]) -> Self;
core/src/num/wrapping.rs:642:13                             core::num::Wrapping<$Int>                                   const fn from_be(x: Self) -> Self;
core/src/num/wrapping.rs:669:13                             core::num::Wrapping<$Int>                                   const fn from_le(x: Self) -> Self;
core/src/str/converts.rs:160:1                              core::str                                                   const unsafe fn from_utf8_unchecked(v: &[u8]) -> &str;
core/src/str/lossy.rs:15:5                                  core::str::lossy::Utf8Lossy                                 fn from_str(s: &str) -> &Utf8Lossy;
core/src/str/lossy.rs:19:5                                  core::str::lossy::Utf8Lossy                                 fn from_bytes(bytes: &[u8]) -> &Utf8Lossy;
core/src/task/wake.rs:162:5                                 core::task::Context<'a>                                     fn from_waker(waker: &'a Waker) -> Self;
core/src/task/wake.rs:255:5                                 core::task::Waker                                           unsafe fn from_raw(waker: RawWaker) -> Waker;
core/src/time.rs:208:5                                      core::time::Duration                                        const fn from_secs(secs: u64) -> Duration;
core/src/time.rs:227:5                                      core::time::Duration                                        const fn from_millis(millis: u64) -> Duration;
core/src/time.rs:249:5                                      core::time::Duration                                        const fn from_micros(micros: u64) -> Duration;
core/src/time.rs:271:5                                      core::time::Duration                                        const fn from_nanos(nanos: u64) -> Duration;
core/src/time.rs:697:5                                      core::time::Duration                                        const fn from_secs_f64(secs: f64) -> Duration;
core/src/time.rs:758:5                                      core::time::Duration                                        const fn from_secs_f32(secs: f32) -> Duration;
std/src/ffi/c_str.rs:429:5                                  std::ffi::CString                                           unsafe fn from_vec_unchecked(mut v: Vec<u8>) -> CString;
std/src/ffi/c_str.rs:705:5                                  std::ffi::CString                                           unsafe fn from_vec_with_nul_unchecked(v: Vec<u8>) -> Self;
std/src/ffi/c_str.rs:1166:5                                 std::ffi::CStr                                              unsafe fn from_ptr<'a>(ptr: *const c_char) -> &'a CStr;
std/src/ffi/c_str.rs:1249:5                                 std::ffi::CStr                                              const unsafe fn from_bytes_with_nul_unchecked(bytes: &[u8]) -> &CStr;
std/src/io/error.rs:477:5                                   std::io::Error                                              fn from_raw_os_error(code: i32) -> Error;
std/src/io/stdio.rs:304:1                                   std::io                                                     fn stdin() -> Stdin;
std/src/io/stdio.rs:674:1                                   std::io                                                     fn stdout() -> Stdout;
std/src/io/stdio.rs:953:1                                   std::io                                                     fn stderr() -> Stderr;
std/src/time.rs:243:5                                       std::time::Instant                                          fn now() -> Instant;
std/src/time.rs:296:5                                       std::time::Instant                                          fn duration_since(&self, earlier: Instant) -> Duration;
std/src/time.rs:316:5                                       std::time::Instant                                          fn checked_duration_since(&self, earlier: Instant) -> Option<Duration>;
std/src/time.rs:336:5                                       std::time::Instant                                          fn saturating_duration_since(&self, earlier: Instant) -> Duration;
std/src/time.rs:360:5                                       std::time::Instant                                          fn elapsed(&self) -> Duration;
std/src/time.rs:466:5                                       std::time::SystemTime                                       fn now() -> SystemTime;
std/src/time.rs:634:5                                       std::time::SystemTimeError                                  fn duration(&self) -> Duration;
```

# Constructors

```rust
alloc/src/collections/binary_heap.rs:367:5                  alloc::collections::binary_heap::BinaryHeap<T>              fn new() -> BinaryHeap<T>;
alloc/src/collections/btree/map.rs:505:5                    alloc::collections::btree_map::BTreeMap<K, V>               const fn new() -> BTreeMap<K, V>;
alloc/src/collections/btree/set.rs:251:5                    alloc::collections::btree_set::BTreeSet<T>                  const fn new() -> BTreeSet<T>;
alloc/src/collections/linked_list.rs:420:5                  alloc::collections::linked_list::LinkedList<T>              const fn new() -> Self;
alloc/src/collections/vec_deque/mod.rs:478:5                alloc::collections::vec_deque::VecDeque<T>                  fn new() -> VecDeque<T>;
alloc/src/raw_vec.rs:72:5                                   alloc::raw_vec::RawVec<T, Global>                           const fn new() -> Self;
alloc/src/rc.rs:2047:5                                      alloc::rc::Weak<T>                                          fn new() -> Weak<T>;
alloc/src/string.rs:381:5                                   alloc::string::String                                       const fn new() -> String;
alloc/src/sync.rs:1681:5                                    alloc::sync::Weak<T>                                        fn new() -> Weak<T>;
alloc/src/vec/mod.rs:423:5                                  alloc::vec::Vec<T>                                          const fn new() -> Self;
core/src/hash/sip.rs:160:5                                  core::hash::SipHasher                                       fn new() -> SipHasher;
core/src/lazy.rs:86:5                                       core::lazy::Lazy                                            const fn new() -> OnceCell<T>;
core/src/num/nonzero.rs:63:17                               core::num::NonZero$Int                                      const fn new(n: $Int) -> Option<Self>;
core/src/sync/atomic.rs:293:5                               core::sync::atomic::AtomicBool                              const fn new(v: bool) -> AtomicBool;
core/src/sync/atomic.rs:1395:13                             core::sync::atomic::Atomic$int_type                         const fn new(v: $int_type) -> Self;
core/src/task/wake.rs:42:5                                  core::task::RawWaker                                        const fn new(data: *const (), vtable: &'static RawWakerVTable) -> RawWaker;
core/src/time.rs:184:5                                      core::time::Duration                                        const fn new(secs: u64, nanos: u32) -> Duration;
std/src/collections/hash/map.rs:227:5                       std::collections::hash_map::HashMap<K, V>                   fn new() -> HashMap<K, V, RandomState>;
std/src/collections/hash/map.rs:2895:5                      std::collections::hash_map::RandomState                     fn new() -> RandomState;
std/src/collections/hash/map.rs:2946:5                      std::collections::hash_map::DefaultHasher                   fn new() -> DefaultHasher;
std/src/collections/hash/set.rs:130:5                       std::collections::hash_set::HashSet<T>                      fn new() -> HashSet<T, RandomState>;
std/src/ffi/os_str.rs:123:5                                 std::ffi::OsString                                          fn new() -> OsString;
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
std/src/sync/barrier.rs:83:5                                std::sync::Barrier                                          fn new(n: usize) -> Barrier;
std/src/sync/condvar.rs:124:5                               std::sync::Condvar                                          fn new() -> Condvar;
std/src/sync/once.rs:189:5                                  std::sync::Once                                             const fn new() -> Once;
std/src/thread/mod.rs:289:5                                 std::thread::Builder                                        fn new() -> Builder;
core/src/alloc/layout.rs:123:5                              core::alloc::Layout                                         const fn new<T>() -> Self;

alloc/src/boxed.rs:215:5                                    alloc::boxed::Box                                           fn new_uninit() -> Box<mem::MaybeUninit<T>>;
alloc/src/boxed.rs:240:5                                    alloc::boxed::Box                                           fn new_zeroed() -> Box<mem::MaybeUninit<T>>;
alloc/src/boxed.rs:564:5                                    alloc::boxed::Box                                           fn new_uninit_slice(len: usize) -> Box<[mem::MaybeUninit<T>]>;
alloc/src/boxed.rs:588:5                                    alloc::boxed::Box                                           fn new_zeroed_slice(len: usize) -> Box<[mem::MaybeUninit<T>]>;
alloc/src/rc.rs:455:5                                       alloc::rc::Rc<T>                                            fn new_uninit() -> Rc<mem::MaybeUninit<T>>;
alloc/src/rc.rs:487:5                                       alloc::rc::Rc<T>                                            fn new_zeroed() -> Rc<mem::MaybeUninit<T>>;
alloc/src/rc.rs:661:5                                       alloc::rc::Rc<T>                                            fn new_uninit_slice(len: usize) -> Rc<[mem::MaybeUninit<T>]>;
alloc/src/rc.rs:687:5                                       alloc::rc::Rc<T>                                            fn new_zeroed_slice(len: usize) -> Rc<[mem::MaybeUninit<T>]>;
alloc/src/sync.rs:451:5                                     alloc::sync::Arc<T>                                         fn new_uninit() -> Arc<mem::MaybeUninit<T>>;
alloc/src/sync.rs:483:5                                     alloc::sync::Arc<T>                                         fn new_zeroed() -> Arc<mem::MaybeUninit<T>>;
alloc/src/sync.rs:665:5                                     alloc::sync::Arc<[T]>                                       fn new_uninit_slice(len: usize) -> Arc<[mem::MaybeUninit<T>]>;
alloc/src/sync.rs:691:5                                     alloc::sync::Arc<[T]>                                       fn new_zeroed_slice(len: usize) -> Arc<[mem::MaybeUninit<T>]>;
core/src/hash/sip.rs:171:5                                  core::hash::SipHasher                                       fn new_with_keys(key0: u64, key1: u64) -> SipHasher;
core/src/num/nonzero.rs:54:17                               core::num::NonZero$Int                                      const unsafe fn new_unchecked(n: $Int) -> Self;

core/src/mem/maybe_uninit.rs:317:5                          core::mem::MaybeUninit<T>                                   const fn uninit() -> MaybeUninit<T>;
core/src/mem/maybe_uninit.rs:353:5                          core::mem::MaybeUninit<T>                                   const fn uninit_array<const LEN: usize>() -> [Self; LEN];
core/src/mem/maybe_uninit.rs:396:5                          core::mem::MaybeUninit<T>                                   fn zeroed() -> MaybeUninit<T>;
```

# Pure functions

```rust
core/src/char/methods.rs:697:5                              char                                                        fn is_alphabetic(self) -> bool;
core/src/char/methods.rs:729:5                              char                                                        fn is_lowercase(self) -> bool;
core/src/char/methods.rs:761:5                              char                                                        fn is_uppercase(self) -> bool;
core/src/char/methods.rs:789:5                              char                                                        fn is_whitespace(self) -> bool;
core/src/char/methods.rs:817:5                              char                                                        fn is_alphanumeric(self) -> bool;
core/src/char/methods.rs:842:5                              char                                                        fn is_control(self) -> bool;
core/src/char/methods.rs:886:5                              char                                                        fn is_numeric(self) -> bool;
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
core/src/num/f64.rs:689:5                                   core::num::f64                                              fn max(self, other: f64) -> f64;
core/src/num/f64.rs:705:5                                   core::num::f64                                              fn min(self, other: f64) -> f64;
core/src/num/int_macros.rs:2318:9                           $Int                                                        const fn is_positive(self) -> bool;
core/src/num/int_macros.rs:2334:9                           $Int                                                        const fn is_negative(self) -> bool;
core/src/num/nonzero.rs:883:17                              core::num::NonZero$Int                                      const fn is_power_of_two(self) -> bool;
core/src/num/saturating.rs:852:13                           core::num::Saturating<$Int>                                 const fn is_positive(self) -> bool;
core/src/num/saturating.rs:872:13                           core::num::Saturating<$Int>                                 const fn is_negative(self) -> bool;
core/src/num/saturating.rs:930:13                           core::num::Saturating<$Int>                                 fn is_power_of_two(self) -> bool;
core/src/num/uint_macros.rs:1506:9                          $Int                                                        const fn abs_diff(self, other: Self) -> Self;
core/src/num/uint_macros.rs:1894:9                          $Int                                                        const fn unstable_div_floor(self, rhs: Self) -> Self;
core/src/num/uint_macros.rs:1915:9                          $Int                                                        const fn unstable_div_ceil(self, rhs: Self) -> Self;
core/src/num/uint_macros.rs:1993:9                          $Int                                                        const fn is_power_of_two(self) -> bool;
core/src/num/uint_macros.rs:2269:9                          $Int                                                        const fn min_value();
core/src/num/uint_macros.rs:2280:9                          $Int                                                        const fn max_value();
core/src/num/wrapping.rs:849:13                             core::num::Wrapping<$Int>                                   const fn is_positive(self) -> bool;
core/src/num/wrapping.rs:869:13                             core::num::Wrapping<$Int>                                   const fn is_negative(self) -> bool;
core/src/num/wrapping.rs:916:13                             core::num::Wrapping<$Int>                                   fn is_power_of_two(self) -> bool;
core/src/char/methods.rs:283:5                              char                                                        fn is_digit(self, radix: u32) -> bool;
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
core/src/str/mod.rs:193:5                                   str                                                         fn is_char_boundary(&self, index: usize) -> bool;
core/src/time.rs:297:5                                      core::time::Duration                                        const fn is_zero(&self) -> bool;

core/src/char/methods.rs:382:5                              char                                                        fn escape_unicode(self) -> EscapeUnicode;
core/src/char/methods.rs:458:5                              char                                                        fn escape_debug(self) -> EscapeDebug;
core/src/char/methods.rs:512:5                              char                                                        fn escape_default(self) -> EscapeDefault;
core/src/char/methods.rs:572:5                              char                                                        const fn len_utf8(self) -> usize;
core/src/char/methods.rs:598:5                              char                                                        const fn len_utf16(self) -> usize;
core/src/mem/mod.rs:303:1                                   core::mem                                                   const fn size_of<T>() -> usize;
core/src/mem/mod.rs:402:1                                   core::mem                                                   fn min_align_of<T>() -> usize;
core/src/mem/mod.rs:447:1                                   core::mem                                                   const fn align_of<T>() -> usize;
core/src/mem/mod.rs:577:1                                   core::mem                                                   const fn needs_drop<T>() -> bool;
core/src/num/f32.rs:675:5                                   core::num::f32                                              fn max(self, other: f32) -> f32;
core/src/num/f32.rs:691:5                                   core::num::f32                                              fn min(self, other: f32) -> f32;
core/src/num/int_macros.rs:2521:9                           $Int                                                        const fn min_value() -> Self;
core/src/num/int_macros.rs:2534:9                           $Int                                                        const fn max_value() -> Self;
core/src/num/f32.rs:566:5                                   core::num::f32                                              const fn classify(self) -> FpCategory;
core/src/num/f32.rs:626:5                                   core::num::f32                                              fn recip(self) -> f32;
core/src/num/f32.rs:717:5                                   core::num::f32                                              unsafe fn to_int_unchecked<Int>(self) -> Int;
core/src/num/f32.rs:746:5                                   core::num::f32                                              const fn to_bits(self) -> u32;
core/src/num/f32.rs:808:5                                   core::num::f32                                              const fn to_be_bytes(self) -> [u8; 4];
core/src/num/f32.rs:824:5                                   core::num::f32                                              const fn to_le_bytes(self) -> [u8; 4];
core/src/num/f32.rs:853:5                                   core::num::f32                                              const fn to_ne_bytes(self) -> [u8; 4];
core/src/num/f64.rs:565:5                                   core::num::f64                                              const fn classify(self) -> FpCategory;
core/src/num/f64.rs:639:5                                   core::num::f64                                              fn recip(self) -> f64;
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
core/src/num/int_macros.rs:117:9                            $Int                                                        const fn leading_zeros(self) -> u32;
core/src/num/int_macros.rs:135:9                            $Int                                                        const fn trailing_zeros(self) -> u32;
core/src/num/int_macros.rs:135:9                            $Int                                                        const fn trailing_zeros(self) -> u32;
core/src/num/int_macros.rs:153:9                            $Int                                                        const fn leading_ones(self) -> u32;
core/src/num/int_macros.rs:153:9                            $Int                                                        const fn leading_ones(self) -> u32;
core/src/num/int_macros.rs:171:9                            $Int                                                        const fn trailing_ones(self) -> u32;
core/src/num/int_macros.rs:171:9                            $Int                                                        const fn trailing_ones(self) -> u32;
core/src/num/int_macros.rs:240:9                            $Int                                                        const fn swap_bytes(self) -> Self;
core/src/num/int_macros.rs:240:9                            $Int                                                        const fn swap_bytes(self) -> Self;
core/src/num/int_macros.rs:348:9                            $Int                                                        const fn to_be(self) -> Self;
core/src/num/int_macros.rs:348:9                            $Int                                                        const fn to_be(self) -> Self;
core/src/num/int_macros.rs:379:9                            $Int                                                        const fn to_le(self) -> Self;
core/src/num/int_macros.rs:379:9                            $Int                                                        const fn to_le(self) -> Self;
core/src/num/int_macros.rs:649:9                            $Int                                                        const fn checked_neg(self) -> Option<Self>;
core/src/num/int_macros.rs:649:9                            $Int                                                        const fn checked_neg(self) -> Option<Self>;
core/src/num/int_macros.rs:761:9                            $Int                                                        const fn checked_abs(self) -> Option<Self>;
core/src/num/int_macros.rs:761:9                            $Int                                                        const fn checked_abs(self) -> Option<Self>;
core/src/num/int_macros.rs:867:9                            $Int                                                        const fn saturating_neg(self) -> Self;
core/src/num/int_macros.rs:867:9                            $Int                                                        const fn saturating_neg(self) -> Self;
core/src/num/int_macros.rs:888:9                            $Int                                                        const fn saturating_abs(self) -> Self;
core/src/num/int_macros.rs:888:9                            $Int                                                        const fn saturating_abs(self) -> Self;
core/src/num/int_macros.rs:1174:9                           $Int                                                        const fn wrapping_neg(self) -> Self;
core/src/num/int_macros.rs:1174:9                           $Int                                                        const fn wrapping_neg(self) -> Self;
core/src/num/int_macros.rs:1257:9                           $Int                                                        const fn wrapping_abs(self) -> Self;
core/src/num/int_macros.rs:1257:9                           $Int                                                        const fn wrapping_abs(self) -> Self;
core/src/num/int_macros.rs:1595:9                           $Int                                                        const fn overflowing_neg(self) -> (Self, bool);
core/src/num/int_macros.rs:1669:9                           $Int                                                        const fn overflowing_abs(self) -> (Self, bool);
core/src/num/int_macros.rs:2227:9                           $Int                                                        const fn abs(self) -> Self;
core/src/num/int_macros.rs:2296:9                           $Int                                                        const fn signum(self) -> Self;
core/src/num/int_macros.rs:2350:9                           $Int                                                        const fn to_be_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/int_macros.rs:2368:9                           $Int                                                        const fn to_le_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/int_macros.rs:2402:9                           $Int                                                        const fn to_ne_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/nonzero.rs:76:17                               core::num::NonZero$Int                                      const fn get(self) -> $Int;
core/src/num/nonzero.rs:202:17                              core::num::NonZero$Int                                      const fn leading_zeros(self) -> u32;
core/src/num/nonzero.rs:224:17                              core::num::NonZero$Int                                      const fn trailing_zeros(self) -> u32;
core/src/num/nonzero.rs:414:17                              core::num::NonZero$Int                                      const fn checked_next_power_of_two(self) -> Option<$Ty>;
core/src/num/nonzero.rs:464:17                              core::num::NonZero$Int                                      const fn abs(self) -> $Ty;
core/src/num/nonzero.rs:494:17                              core::num::NonZero$Int                                      const fn checked_abs(self) -> Option<$Ty>;
core/src/num/nonzero.rs:528:17                              core::num::NonZero$Int                                      const fn overflowing_abs(self) -> ($Ty, bool);
core/src/num/nonzero.rs:566:17                              core::num::NonZero$Int                                      const fn saturating_abs(self) -> $Ty;
core/src/num/nonzero.rs:599:17                              core::num::NonZero$Int                                      const fn wrapping_abs(self) -> $Ty;
core/src/num/nonzero.rs:632:17                              core::num::NonZero$Int                                      const fn unsigned_abs(self) -> $Uty;
core/src/num/saturating.rs:478:13                           core::num::Saturating<$Int>                                 const fn count_ones(self) -> u32;
core/src/num/saturating.rs:496:13                           core::num::Saturating<$Int>                                 const fn count_zeros(self) -> u32;
core/src/num/saturating.rs:516:13                           core::num::Saturating<$Int>                                 const fn trailing_zeros(self) -> u32;
core/src/num/saturating.rs:592:13                           core::num::Saturating<$Int>                                 const fn swap_bytes(self) -> Self;
core/src/num/saturating.rs:702:13                           core::num::Saturating<$Int>                                 const fn to_be(self) -> Self;
core/src/num/saturating.rs:729:13                           core::num::Saturating<$Int>                                 const fn to_le(self) -> Self;
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
core/src/num/uint_macros.rs:1679:9                          $Int                                                        const fn overflowing_neg(self) -> (Self, bool);
core/src/num/uint_macros.rs:2038:9                          $Int                                                        const fn next_power_of_two(self) -> Self;
core/src/num/uint_macros.rs:2058:9                          $Int                                                        const fn checked_next_power_of_two(self) -> Option<Self>;
core/src/num/uint_macros.rs:2080:9                          $Int                                                        const fn wrapping_next_power_of_two(self) -> Self;
core/src/num/uint_macros.rs:2098:9                          $Int                                                        const fn to_be_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/uint_macros.rs:2116:9                          $Int                                                        const fn to_le_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/uint_macros.rs:2150:9                          $Int                                                        const fn to_ne_bytes(self) -> [u8; mem::size_of::<Self>()];
core/src/num/wrapping.rs:473:13                             core::num::Wrapping<$Int>                                   const fn count_ones(self) -> u32;
core/src/num/wrapping.rs:491:13                             core::num::Wrapping<$Int>                                   const fn count_zeros(self) -> u32;
core/src/num/wrapping.rs:511:13                             core::num::Wrapping<$Int>                                   const fn trailing_zeros(self) -> u32;
core/src/num/wrapping.rs:587:13                             core::num::Wrapping<$Int>                                   const fn swap_bytes(self) -> Self;
core/src/num/wrapping.rs:696:13                             core::num::Wrapping<$Int>                                   const fn to_be(self) -> Self;
core/src/num/wrapping.rs:723:13                             core::num::Wrapping<$Int>                                   const fn to_le(self) -> Self;
core/src/num/wrapping.rs:779:13                             core::num::Wrapping<$Int>                                   const fn leading_zeros(self) -> u32;
core/src/num/wrapping.rs:805:13                             core::num::Wrapping<$Int>                                   fn abs(self) -> Wrapping<$t>;
core/src/num/wrapping.rs:829:13                             core::num::Wrapping<$Int>                                   fn signum(self) -> Wrapping<$t>;
core/src/num/wrapping.rs:897:13                             core::num::Wrapping<$Int>                                   const fn leading_zeros(self) -> u32;
core/src/num/wrapping.rs:940:13                             core::num::Wrapping<$Int>                                   fn next_power_of_two(self) -> Self;
std/src/f32.rs:713:5                                        f32                                                         fn sin_cos(self) -> (f32, f32);
std/src/f64.rs:715:5                                        f64                                                         fn sin_cos(self) -> (f64, f64);
```

# Getters

```rust
alloc/src/collections/binary_heap.rs:1049:5                 alloc::collections::binary_heap::BinaryHeap<T>              fn len(&self) -> usize;
alloc/src/collections/binary_heap.rs:1072:5                 alloc::collections::binary_heap::BinaryHeap<T>              fn is_empty(&self) -> bool;
alloc/src/collections/btree/map.rs:2207:5                   alloc::collections::btree_map::BTreeMap<K, V>               const fn len(&self) -> usize;
alloc/src/collections/btree/map.rs:2227:5                   alloc::collections::btree_map::BTreeMap<K, V>               const fn is_empty(&self) -> bool;
alloc/src/collections/btree/set.rs:1035:5                   alloc::collections::btree_set::BTreeSet<T>                  const fn len(&self) -> usize;
alloc/src/collections/btree/set.rs:1053:5                   alloc::collections::btree_set::BTreeSet<T>                  const fn is_empty(&self) -> bool;
alloc/src/collections/linked_list.rs:580:5                  alloc::collections::linked_list::LinkedList<T>              fn is_empty(&self) -> bool;
alloc/src/collections/linked_list.rs:606:5                  alloc::collections::linked_list::LinkedList<T>              fn len(&self) -> usize;
alloc/src/string.rs:1539:5                                  alloc::string::String                                       fn len(&self) -> usize;
alloc/src/string.rs:1558:5                                  alloc::string::String                                       fn is_empty(&self) -> bool;
core/src/ptr/non_null.rs:442:5                              core::mem::NonNull<[T]>                                     const fn len(self) -> usize;
core/src/str/mod.rs:144:5                                   str                                                         const fn len(&self) -> usize;
core/src/str/mod.rs:164:5                                   str                                                         const fn is_empty(&self) -> bool;
std/src/ffi/os_str.rs:663:5                                 std::ffi::OsStr                                             fn is_empty(&self) -> bool;
std/src/ffi/os_str.rs:694:5                                 std::ffi::OsStr                                             fn len(&self) -> usize;
std/src/fs.rs:1059:5                                        std::fs::MetaData                                           fn len(&self) -> u64;
std/src/os/unix/net/ancillary.rs:434:5                      std::os::unix::net::SocketAncillary<'a>                     fn is_empty(&self) -> bool;
std/src/os/unix/net/ancillary.rs:440:5                      std::os::unix::net::SocketAncillary<'a>                     fn len(&self) -> usize;

std/src/fs.rs:986:5                                         std::fs::MetaData                                           fn is_dir(&self) -> bool;
std/src/fs.rs:1014:5                                        std::fs::MetaData                                           fn is_file(&self) -> bool;
std/src/fs.rs:1040:5                                        std::fs::MetaData                                           fn is_symlink(&self) -> bool;
std/src/fs.rs:1287:5                                        std::fs::FileType                                           fn is_dir(&self) -> bool;
std/src/fs.rs:1319:5                                        std::fs::FileType                                           fn is_file(&self) -> bool;
std/src/fs.rs:1354:5                                        std::fs::FileType                                           fn is_symlink(&self) -> bool;
std/src/net/addr.rs:236:5                                   std::net::SocketAddr                                        const fn is_ipv4(&self) -> bool;
std/src/net/addr.rs:257:5                                   std::net::SocketAddr                                        const fn is_ipv6(&self) -> bool;
std/src/net/ip.rs:237:5                                     std::net::IpAddr                                            const fn is_unspecified(&self) -> bool;
std/src/net/ip.rs:260:5                                     std::net::IpAddr                                            const fn is_loopback(&self) -> bool;
std/src/net/ip.rs:285:5                                     std::net::IpAddr                                            const fn is_global(&self) -> bool;
std/src/net/ip.rs:308:5                                     std::net::IpAddr                                            const fn is_multicast(&self) -> bool;
std/src/net/ip.rs:336:5                                     std::net::IpAddr                                            const fn is_documentation(&self) -> bool;
std/src/net/ip.rs:360:5                                     std::net::IpAddr                                            const fn is_benchmarking(&self) -> bool;
std/src/net/ip.rs:383:5                                     std::net::IpAddr                                            const fn is_ipv4(&self) -> bool;
std/src/net/ip.rs:403:5                                     std::net::IpAddr                                            const fn is_ipv6(&self) -> bool;
std/src/net/ip.rs:530:5                                     std::net::Ipv4Addr                                          const fn is_unspecified(&self) -> bool;
std/src/net/ip.rs:551:5                                     std::net::Ipv4Addr                                          const fn is_loopback(&self) -> bool;
std/src/net/ip.rs:581:5                                     std::net::Ipv4Addr                                          const fn is_private(&self) -> bool;
std/src/net/ip.rs:608:5                                     std::net::Ipv4Addr                                          const fn is_link_local(&self) -> bool;
std/src/net/ip.rs:683:5                                     std::net::Ipv4Addr                                          const fn is_global(&self) -> bool;
std/src/net/ip.rs:723:5                                     std::net::Ipv4Addr                                          const fn is_shared(&self) -> bool;
std/src/net/ip.rs:748:5                                     std::net::Ipv4Addr                                          const fn is_benchmarking(&self) -> bool;
std/src/net/ip.rs:782:5                                     std::net::Ipv4Addr                                          const fn is_reserved(&self) -> bool;
std/src/net/ip.rs:805:5                                     std::net::Ipv4Addr                                          const fn is_multicast(&self) -> bool;
std/src/net/ip.rs:826:5                                     std::net::Ipv4Addr                                          const fn is_broadcast(&self) -> bool;
std/src/net/ip.rs:853:5                                     std::net::Ipv4Addr                                          const fn is_documentation(&self) -> bool;
std/src/net/ip.rs:1293:5                                    std::net::Ipv6Addr                                          const fn is_unspecified(&self) -> bool;
std/src/net/ip.rs:1316:5                                    std::net::Ipv6Addr                                          const fn is_loopback(&self) -> bool;
std/src/net/ip.rs:1342:5                                    std::net::Ipv6Addr                                          const fn is_global(&self) -> bool;
std/src/net/ip.rs:1369:5                                    std::net::Ipv6Addr                                          const fn is_unique_local(&self) -> bool;
std/src/net/ip.rs:1397:5                                    std::net::Ipv6Addr                                          const fn is_unicast(&self) -> bool;
std/src/net/ip.rs:1448:5                                    std::net::Ipv6Addr                                          const fn is_unicast_link_local(&self) -> bool;
std/src/net/ip.rs:1472:5                                    std::net::Ipv6Addr                                          const fn is_documentation(&self) -> bool;
std/src/net/ip.rs:1494:5                                    std::net::Ipv6Addr                                          const fn is_benchmarking(&self) -> bool;
std/src/net/ip.rs:1531:5                                    std::net::Ipv6Addr                                          const fn is_unicast_global(&self) -> bool;
std/src/net/ip.rs:1592:5                                    std::net::Ipv6Addr                                          const fn is_multicast(&self) -> bool;
std/src/os/unix/net/addr.rs:160:5                           std::os::unix::net::SocketAddr                              fn is_unnamed(&self) -> bool;
std/src/path.rs:219:5                                       std::path::Prefix<'a>                                       fn is_verbatim(&self) -> bool;
std/src/path.rs:251:1                                       std::path                                                   fn is_separator(c: char) -> bool;
std/src/path.rs:2010:5                                      std::path::Path                                             fn is_absolute(&self) -> bool;
std/src/path.rs:2034:5                                      std::path::Path                                             fn is_relative(&self) -> bool;
std/src/path.rs:2696:5                                      std::path::Path                                             fn is_file(&self) -> bool;
std/src/path.rs:2722:5                                      std::path::Path                                             fn is_dir(&self) -> bool;
std/src/path.rs:2748:5                                      std::path::Path                                             fn is_symlink(&self) -> bool;
std/src/sync/barrier.rs:169:5                               std::sync::BarrierWaitResult                                fn is_leader(&self) -> bool;

alloc/src/collections/binary_heap.rs:833:5                  alloc::collections::binary_heap::BinaryHeap<T>              fn iter(&self) -> Iter<'_, T>;
alloc/src/collections/binary_heap.rs:878:5                  alloc::collections::binary_heap::BinaryHeap<T>              fn peek(&self) -> Option<&T>;
alloc/src/collections/binary_heap.rs:895:5                  alloc::collections::binary_heap::BinaryHeap<T>              fn capacity(&self) -> usize;
alloc/src/collections/btree/map.rs:2081:5                   alloc::collections::btree_map::BTreeMap<K, V>               fn iter(&self) -> Iter<'_, K, V>;
alloc/src/collections/btree/map.rs:2140:5                   alloc::collections::btree_map::BTreeMap<K, V>               fn keys(&self) -> Keys<'_, K, V>;
alloc/src/collections/btree/map.rs:2161:5                   alloc::collections::btree_map::BTreeMap<K, V>               fn values(&self) -> Values<'_, K, V>;
alloc/src/collections/btree/map/entry.rs:351:5              alloc::collections::btree_map::OccupiedEntry<'a, K, V>      fn key(&self) -> &K;
alloc/src/collections/btree/map/entry.rs:395:5              alloc::collections::btree_map::OccupiedEntry<'a, K, V>      fn get(&self) -> &V;
alloc/src/collections/btree/set.rs:668:5                    alloc::collections::btree_set::BTreeSet<T>                  fn first(&self) -> Option<&T>;
alloc/src/collections/btree/set.rs:694:5                    alloc::collections::btree_set::BTreeSet<T>                  fn last(&self) -> Option<&T>;
alloc/src/collections/btree/set.rs:1017:5                   alloc::collections::btree_set::BTreeSet<T>                  fn iter(&self) -> Iter<'_, T>;
alloc/src/collections/linked_list.rs:494:5                  alloc::collections::linked_list::LinkedList<T>              fn iter(&self) -> Iter<'_, T>;
alloc/src/collections/linked_list.rs:681:5                  alloc::collections::linked_list::LinkedList<T>              fn front(&self) -> Option<&T>;
alloc/src/collections/linked_list.rs:731:5                  alloc::collections::linked_list::LinkedList<T>              fn back(&self) -> Option<&T>;
core/src/fmt/mod.rs:1626:5                                  core::fmt::Formatter<'a>                                    fn flags(&self) -> u32;
core/src/fmt/mod.rs:1658:5                                  core::fmt::Formatter<'a>                                    fn fill(&self) -> char;
core/src/fmt/mod.rs:1694:5                                  core::fmt::Formatter<'a>                                    fn align(&self) -> Option<Alignment>;
core/src/fmt/mod.rs:1728:5                                  core::fmt::Formatter<'a>                                    fn width(&self) -> Option<usize>;
core/src/fmt/mod.rs:1758:5                                  core::fmt::Formatter<'a>                                    fn precision(&self) -> Option<usize>;
core/src/fmt/mod.rs:1788:5                                  core::fmt::Formatter<'a>                                    fn sign_plus(&self) -> bool;
core/src/fmt/mod.rs:1816:5                                  core::fmt::Formatter<'a>                                    fn sign_minus(&self) -> bool;
core/src/fmt/mod.rs:1843:5                                  core::fmt::Formatter<'a>                                    fn alternate(&self) -> bool;
core/src/fmt/mod.rs:1868:5                                  core::fmt::Formatter<'a>                                    fn sign_aware_zero_pad(&self) -> bool;
core/src/panic/location.rs:85:5                             core::panic::Location<'a>                                   const fn caller() -> &'static Location<'static>;
core/src/panic/location.rs:123:5                            core::panic::Location<'a>                                   fn file(&self) -> &str;
core/src/panic/location.rs:145:5                            core::panic::Location<'a>                                   fn line(&self) -> u32;
core/src/panic/location.rs:167:5                            core::panic::Location<'a>                                   fn column(&self) -> u32;
core/src/panic/panic_info.rs:85:5                           core::panic::PanicInfo<'a>                                  fn payload(&self) -> &(dyn Any + Send);
core/src/panic/panic_info.rs:93:5                           core::panic::PanicInfo<'a>                                  fn message(&self) -> Option<&fmt::Arguments<'_>>;
core/src/panic/panic_info.rs:122:5                          core::panic::PanicInfo<'a>                                  fn location(&self) -> Option<&Location<'_>>;
core/src/time.rs:354:5                                      core::time::Duration                                        const fn subsec_millis(&self) -> u32;
core/src/time.rs:376:5                                      core::time::Duration                                        const fn subsec_micros(&self) -> u32;
core/src/time.rs:398:5                                      core::time::Duration                                        const fn subsec_nanos(&self) -> u32;
std/src/fs.rs:964:5                                         std::fs::MetaData                                           fn file_type(&self) -> FileType;
std/src/fs.rs:1078:5                                        std::fs::MetaData                                           fn permissions(&self) -> Permissions;
std/src/fs.rs:1225:5                                        std::fs::Permissions                                        fn readonly(&self) -> bool;
std/src/fs.rs:1416:5                                        std::fs::DirEntry                                           fn path(&self) -> PathBuf;
std/src/fs.rs:1511:5                                        std::fs::DirEntry                                           fn file_name(&self) -> OsString;
std/src/net/addr.rs:153:5                                   std::net::SocketAddr                                        const fn ip(&self) -> IpAddr;
std/src/net/addr.rs:193:5                                   std::net::SocketAddr                                        const fn port(&self) -> u16;
std/src/net/addr.rs:298:5                                   std::net::SocketAddrV4                                      const fn ip(&self) -> &Ipv4Addr;
std/src/net/addr.rs:332:5                                   std::net::SocketAddrV4                                      const fn port(&self) -> u16;
std/src/net/addr.rs:396:5                                   std::net::SocketAddrV6                                      const fn ip(&self) -> &Ipv6Addr;
std/src/net/addr.rs:428:5                                   std::net::SocketAddrV6                                      const fn port(&self) -> u16;
std/src/net/addr.rs:470:5                                   std::net::SocketAddrV6                                      const fn flowinfo(&self) -> u32;
std/src/net/addr.rs:509:5                                   std::net::SocketAddrV6                                      const fn scope_id(&self) -> u32;
std/src/net/ip.rs:507:5                                     std::net::Ipv4Addr                                          const fn octets(&self) -> [u8; 4];
std/src/net/ip.rs:1257:5                                    std::net::Ipv6Addr                                          const fn segments(&self) -> [u16; 8];
std/src/net/ip.rs:1558:5                                    std::net::Ipv6Addr                                          const fn multicast_scope(&self) -> Option<Ipv6MulticastScope>;
std/src/net/ip.rs:1701:5                                    std::net::Ipv6Addr                                          const fn octets(&self) -> [u8; 16];
std/src/os/unix/net/ancillary.rs:428:5                      std::os::unix::net::SocketAncillary<'a>                     fn capacity(&self) -> usize;
std/src/os/unix/net/ancillary.rs:446:5                      std::os::unix::net::SocketAncillary<'a>                     fn messages(&self) -> Messages<'_>;
std/src/os/unix/net/ancillary.rs:474:5                      std::os::unix::net::SocketAncillary<'a>                     fn truncated(&self) -> bool;
std/src/path.rs:2060:5                                      std::path::Path                                             fn has_root(&self) -> bool;
std/src/path.rs:2488:5                                      std::path::Path                                             fn iter(&self) -> Iter<'_>;
std/src/path.rs:2638:5                                      std::path::Path                                             fn exists(&self) -> bool;

std/src/os/unix/net/ancillary.rs:204:5                      std::os::unix::net::SocketCred                              fn get_pid(&self) -> libc::pid_t;
std/src/os/unix/net/ancillary.rs:216:5                      std::os::unix::net::SocketCred                              fn get_uid(&self) -> libc::uid_t;
std/src/os/unix/net/ancillary.rs:228:5                      std::os::unix::net::SocketCred                              fn get_gid(&self) -> libc::gid_t;
```
