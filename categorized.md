# Misleading

```rust
std/src/net/ip.rs:423:5                                     std::net::IpAddr                                            const fn to_canonical(&self) -> IpAddr;
std/src/net/ip.rs:1683:5                                    std::net::Ipv6Addr                                          const fn to_canonical(&self) -> IpAddr;

alloc/src/rc.rs:2226:5                                      alloc::rc::Weak<T>                                          fn upgrade(&self) -> Option<Rc<T>>;
alloc/src/sync.rs:894:5                                     alloc::sync::Arc<T>                                         fn downgrade(this: &Self) -> Weak<T>;
alloc/src/sync.rs:1856:5                                    alloc::sync::Weak<T>                                        fn upgrade(&self) -> Option<Arc<T>>;
core/src/alloc/layout.rs:115:5                              core::alloc::Layout                                         const fn align(&self) -> usize;
core/src/alloc/layout.rs:264:5                              core::alloc::Layout                                         fn pad_to_align(&self) -> Layout;
std/src/path.rs:2510:5                                      std::path::Path                                             fn display(&self) -> Display<'_>;

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
std/src/io/stdio.rs:467:5                                   std::io::Stdin                                              fn lines(self) -> Lines<StdinLock<'static>>;
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

# Pure functions

```rust
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
core/src/num/f64.rs:565:5                                   core::num::f64                                              const fn classify(self) -> FpCategory;
core/src/num/f64.rs:639:5                                   core::num::f64                                              fn recip(self) -> f64;
core/src/num/f64.rs:689:5                                   core::num::f64                                              fn max(self, other: f64) -> f64;
core/src/num/f64.rs:705:5                                   core::num::f64                                              fn min(self, other: f64) -> f64;
core/src/num/uint_macros.rs:2269:9                          $Int                                                        const fn min_value();
core/src/num/uint_macros.rs:2280:9                          $Int                                                        const fn max_value();
core/src/num/nonzero.rs:76:17                               core::num::NonZero$Int                                      const fn get(self) -> $Int;
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
