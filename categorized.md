# Discarded guard

```rust
std/src/io/stdio.rs:489:5                                   std::io::Stdin                                              fn split(self, byte: u8) -> Split<StdinLock<'static>>;
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

# Conversions

```rust
alloc/src/collections/binary_heap.rs:514:5                  alloc::collections::binary_heap::BinaryHeap<T>              fn into_sorted_vec(mut self) -> Vec<T>;
alloc/src/str.rs:247:5                                      str                                                         fn into_boxed_bytes(self: Box<str>) -> Box<[u8]>;
alloc/src/str.rs:484:5                                      str                                                         fn into_string(self: Box<str>) -> String;
alloc/src/sync.rs:801:5                                     alloc::sync::Arc<T>                                         fn into_raw(this: Self) -> *const T;
std/src/ffi/c_str.rs:1441:5                                 std::ffi::CStr                                              fn into_c_string(self: Box<CStr>) -> CString;
std/src/ffi/os_str.rs:700:5                                 std::ffi::OsStr                                             fn into_os_string(self: Box<OsStr>) -> OsString;
std/src/path.rs:2755:5                                      std::path::Path                                             fn into_path_buf(self: Box<Path>) -> PathBuf;
std/src/process.rs:1617:5                                   std::process::ExitStatusError                               fn into_status(&self) -> ExitStatus;

core/src/ops/range.rs:747:5                                 core::ops::Bound<&T>                                        fn cloned(self) -> Bound<T>;
core/src/option.rs:1453:5                                   core::option::Option<&T>                                    const fn copied(self) -> Option<T>;
core/src/option.rs:1496:5                                   core::option::Option<&T>                                    fn cloned(self) -> Option<T>;
core/src/pin.rs:710:5                                       core::pin::Pin<&'a T>                                       const fn get_ref(self) -> &'a T;
```

# Constructors

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

# Uncategorized

```rust
alloc/src/alloc.rs:85:1                                         alloc::alloc                                                unsafe fn alloc(layout: Layout) -> *mut u8;
alloc/src/alloc.rs:154:1                                        alloc::alloc                                                unsafe fn alloc_zeroed(layout: Layout) -> *mut u8;
alloc/src/collections/linked_list.rs:532:5                      alloc::collections::linked_list::LinkedList<T>              fn cursor_front(&self) -> Cursor<'_, T>;
alloc/src/collections/linked_list.rs:550:5                      alloc::collections::linked_list::LinkedList<T>              fn cursor_back(&self) -> Cursor<'_, T>;
alloc/src/collections/linked_list.rs:1181:5                     alloc::collections::linked_list::Cursor<'a, T>              fn index(&self) -> Option<usize>;
alloc/src/collections/linked_list.rs:1235:5                     alloc::collections::linked_list::Cursor<'a, T>              fn current(&self) -> Option<&'a T>;
alloc/src/collections/linked_list.rs:1245:5                     alloc::collections::linked_list::Cursor<'a, T>              fn peek_next(&self) -> Option<&'a T>;
alloc/src/collections/linked_list.rs:1261:5                     alloc::collections::linked_list::Cursor<'a, T>              fn peek_prev(&self) -> Option<&'a T>;
alloc/src/collections/linked_list.rs:1274:5                     alloc::collections::linked_list::Cursor<'a, T>              fn front(&self) -> Option<&'a T>;
alloc/src/collections/linked_list.rs:1281:5                     alloc::collections::linked_list::Cursor<'a, T>              fn back(&self) -> Option<&'a T>;
alloc/src/collections/linked_list.rs:1292:5                     alloc::collections::linked_list::CursorMut<'a, T>           fn index(&self) -> Option<usize>;
alloc/src/collections/linked_list.rs:1633:5                     alloc::collections::linked_list::CursorMut<'a, T>           fn front(&self) -> Option<&T>;
alloc/src/collections/linked_list.rs:1647:5                     alloc::collections::linked_list::CursorMut<'a, T>           fn back(&self) -> Option<&T>;
alloc/src/collections/mod.rs:73:5                               alloc::colletions::TryReserveError                          fn kind(&self) -> TryReserveErrorKind;
alloc/src/fmt.rs:576:1                                          alloc::fmt                                                  fn format(args: Arguments<'_>) -> string::String;
alloc/src/rc.rs:2240:5                                          alloc::rc::Weak<T>                                          fn strong_count(&self) -> usize;
alloc/src/rc.rs:2248:5                                          alloc::rc::Weak<T>                                          fn weak_count(&self) -> usize;
alloc/src/rc.rs:2318:5                                          alloc::rc::Weak<T>                                          fn ptr_eq(&self, other: &Self) -> bool;
alloc/src/str.rs:511:5                                          str                                                         fn repeat(&self, n: usize) -> String;
alloc/src/string.rs:895:5                                       alloc::string::String                                       fn capacity(&self) -> usize;
alloc/src/string.rs:1815:5                                      alloc::string::FromUtf8Error                                fn utf8_error(&self) -> Utf8Error;
alloc/src/sync.rs:947:5                                         alloc::sync::Arc<T>                                         fn weak_count(this: &Self) -> usize;
alloc/src/sync.rs:976:5                                         alloc::sync::Arc<T>                                         fn strong_count(this: &Self) -> usize;
alloc/src/sync.rs:1091:5                                        alloc::sync::Arc<T>                                         fn ptr_eq(this: &Self, other: &Self) -> bool;
alloc/src/sync.rs:1893:5                                        alloc::sync::Weak<T>                                        fn strong_count(&self) -> usize;
alloc/src/sync.rs:1909:5                                        alloc::sync::Weak<T>                                        fn weak_count(&self) -> usize;
alloc/src/sync.rs:1988:5                                        alloc::sync::Weak<T>                                        fn ptr_eq(&self, other: &Self) -> bool;
alloc/src/vec/drain.rs:63:5                                     alloc::vec::Drain<'a, T, A>                                 fn allocator(&self) -> &A;
core/src/alloc/layout.rs:107:5                                  core::alloc::Layout                                         const fn size(&self) -> usize;
core/src/alloc/layout.rs:187:5                                  core::alloc::Layout                                         const fn dangling(&self) -> NonNull<u8>;
core/src/any.rs:463:5                                           core::any::TypeId                                           const fn of<T: ?Sized + 'static>() -> TypeId;
core/src/any.rs:497:1                                           core::any                                                   const fn type_name<T: ?Sized>() -> &'static str;
core/src/ascii.rs:91:1                                          core::ascii                                                 fn escape_default(c: u8) -> EscapeDefault;
core/src/cell.rs:1337:5                                         core::cell::Ref<'b, T>                                      fn clone(orig: &Ref<'b, T>) -> Ref<'b, T>;
core/src/char/decode.rs:132:5                                   core::char::DecodeUtf16Error                                fn unpaired_surrogate(&self) -> u16;
core/src/char/methods.rs:1152:5                                 char                                                        const fn eq_ignore_ascii_case(&self, other: &char) -> bool;
core/src/default.rs:159:1                                       core::default::Default                                      fn default<T: Default>() -> T;
core/src/future/mod.rs:94:1                                     core::future                                                unsafe fn get_context<'a, 'b>(cx: ResumeTy) -> &'a mut Context<'b>;
core/src/iter/sources/empty.rs:21:1                             core::iter                                                  const fn empty<T>() -> Empty<T>;
core/src/mem/mod.rs:626:1                                       core::mem                                                   unsafe fn zeroed<T>() -> T;
core/src/mem/mod.rs:662:1                                       core::mem                                                   unsafe fn uninitialized<T>() -> T;
core/src/mem/mod.rs:1056:1                                      core::mem                                                   const fn variant_count<T>() -> usize;
core/src/num/error.rs:118:5                                     core::num::ParseIntError                                    fn kind(&self) -> &IntErrorKind;
core/src/num/f32.rs:959:5                                       core::num::f32                                              fn total_cmp(&self, other: &Self) -> crate::cmp::Ordering;
core/src/num/f64.rs:973:5                                       core::num::f64                                              fn total_cmp(&self, other: &Self) -> crate::cmp::Ordering;
core/src/num/mod.rs:338:5                                       u8                                                          const fn eq_ignore_ascii_case(&self, other: &u8) -> bool;
core/src/num/saturating.rs:757:13                               core::num::Saturating<$Int>                                 fn pow(self, exp: u32) -> Self;
core/src/num/wrapping.rs:751:13                                 core::num::Wrapping<$Int>                                   fn pow(self, exp: u32) -> Self;
core/src/panic/location.rs:179:5                                core::panic::Location<'a>                                   const fn internal_constructor(file: &'a str, line: u32, col: u32) -> Self;
core/src/panic/panic_info.rs:44:5                               core::panic::PanicInfo<'a>                                  fn internal_constructor(message: Option<&'a fmt::Arguments<'a>>, location: &'a Location<'a>) -> Self;
core/src/ptr/mod.rs:211:1                                       core::mem                                                   const fn null<T>() -> *const T;
core/src/ptr/mod.rs:230:1                                       core::mem                                                   const fn null_mut<T>() -> *mut T;
core/src/ptr/non_null.rs:87:5                                   core::mem::NonNull<T>                                       const fn dangling() -> Self;
core/src/ptr/non_null.rs:418:5                                  core::mem::NonNull<[T]>                                     const fn slice_from_raw_parts(data: NonNull<T>, len: usize) -> Self;
core/src/ptr/unique.rs:72:5                                     core::mem::Unique<T>                                        const fn dangling() -> Self;
core/src/slice/iter.rs:1715:5                                   core::slice::ChunksExact<'a, T>                             fn remainder(&self) -> &'a [T];
core/src/slice/iter.rs:2143:5                                   core::slice::ArrayChunks<'a, T, N>                          fn remainder(&self) -> &'a [T];
core/src/slice/iter.rs:2717:5                                   core::slice::RChunksExact<'a, T>                            fn remainder(&self) -> &'a [T];
core/src/str/error.rs:76:5                                      core::str::Utf8Error                                        fn valid_up_to(&self) -> usize;
core/src/str/error.rs:97:5                                      core::str::Utf8Error                                        fn error_len(&self) -> Option<usize>;
core/src/str/iter.rs:213:5                                      core::str::CharIndices<'a>                                  fn offset(&self) -> usize;
core/src/str/mod.rs:497:5                                       str                                                         unsafe fn slice_unchecked(&self, begin: usize, end: usize) -> &str;
core/src/str/mod.rs:569:5                                       str                                                         fn split_at(&self, mid: usize) -> (&str, &str);
core/src/str/mod.rs:760:5                                       str                                                         fn bytes(&self) -> Bytes<'_>;
core/src/str/validations.rs:255:1                               core::str                                                   fn utf8_char_width(b: u8) -> usize;
core/src/task/wake.rs:169:5                                     core::task::Context<'a>                                     fn waker(&self) -> &'a Waker;
core/src/task/wake.rs:244:5                                     core::task::Waker                                           fn will_wake(&self, other: &Waker) -> bool;
std/src/collections/hash/map.rs:1709:5                          std::collections::hash_map::RawOccupiedEntryMut<'a, K, V>   fn key(&self) -> &K;
std/src/collections/hash/map.rs:1731:5                          std::collections::hash_map::RawOccupiedEntryMut<'a, K, V>   fn get(&self) -> &V;
std/src/ffi/c_str.rs:1006:5                                     std::ffi::NulError                                          fn nul_position(&self) -> usize;
std/src/ffi/c_str.rs:1102:5                                     std::ffi::IntoStringError                                   fn utf8_error(&self) -> Utf8Error;
std/src/ffi/os_str.rs:240:5                                     std::ffi::OsString                                          fn capacity(&self) -> usize;
std/src/fs.rs:389:5                                             std::fs::File                                               fn with_options() -> OpenOptions;
std/src/io/error.rs:446:5                                       std::io::Error                                              fn last_os_error() -> Error;
std/src/io/error.rs:512:5                                       std::io::Error                                              fn raw_os_error(&self) -> Option<i32>;
std/src/io/error.rs:550:5                                       std::io::Error                                              fn get_ref(&self) -> Option<&(dyn error::Error + Send + Sync + 'static)>;
std/src/io/error.rs:690:5                                       std::io::Error                                              fn kind(&self) -> ErrorKind;
std/src/io/mod.rs:1302:5                                        std::io::Initializer                                        fn zeroing() -> Initializer;
std/src/io/mod.rs:1316:5                                        std::io::Initializer                                        unsafe fn nop() -> Initializer;
std/src/io/mod.rs:1323:5                                        std::io::Initializer                                        fn should_initialize(&self) -> bool;
std/src/io/util.rs:37:1                                         std::io                                                     const fn empty() -> Empty;
std/src/io/util.rs:117:1                                        std::io                                                     const fn repeat(byte: u8) -> Repeat;
std/src/io/util.rs:197:1                                        std::io                                                     const fn sink() -> Sink;
std/src/net/tcp.rs:856:5                                        std::net::TcpListener                                       fn incoming(&self) -> Incoming<'_>;
std/src/os/unix/net/listener.rs:236:5                           std::os::unix::net::UnixListener                            fn incoming(&self) -> Incoming<'_>;
std/src/os/unix/process.rs:440:1                                std::os::unix::process                                      fn parent_id() -> u32;
std/src/panicking.rs:164:1                                      std::panicking                                              fn take_hook() -> Box<dyn Fn(&PanicInfo<'_>) + 'static + Sync + Send>;
std/src/panicking.rs:287:5                                      std::panicking::panic_count                                 fn get_count() -> usize;
std/src/panicking.rs:293:5                                      std::panicking::panic_count                                 fn count_is_zero() -> bool;
std/src/path.rs:424:5                                           std::path::PrefixComponent<'a>                              fn kind(&self) -> Prefix<'a>;
std/src/path.rs:1449:5                                          std::path::PathBuf                                          fn capacity(&self) -> usize;
std/src/process.rs:953:5                                        std::process::Command                                       fn get_program(&self) -> &OsStr;
std/src/process.rs:976:5                                        std::process::Command                                       fn get_args(&self) -> CommandArgs<'_>;
std/src/process.rs:1008:5                                       std::process::Command                                       fn get_envs(&self) -> CommandEnvs<'_>;
std/src/process.rs:1029:5                                       std::process::Command                                       fn get_current_dir(&self) -> Option<&Path>;
std/src/process.rs:1191:5                                       std::process::Stdio                                         fn piped() -> Stdio;
std/src/process.rs:1230:5                                       std::process::Stdio                                         fn inherit() -> Stdio;
std/src/process.rs:1269:5                                       std::process::Stdio                                         fn null() -> Stdio;
std/src/process.rs:1470:5                                       std::process::ExitStatus                                    fn success(&self) -> bool;
std/src/process.rs:1501:5                                       std::process::ExitStatus                                    fn code(&self) -> Option<i32>;
std/src/process.rs:1612:5                                       std::process::ExitStatusError                               fn code_nonzero(&self) -> Option<NonZeroI32>;
std/src/process.rs:1726:5                                       std::process::Child                                         fn id(&self) -> u32;
std/src/process.rs:1996:1                                       std::process                                                fn id() -> u32;
std/src/sync/condvar.rs:65:5                                    std::sync::WaitTimeoutResult                                fn timed_out(&self) -> bool;
std/src/sync/mpsc/mod.rs:711:1                                  std::sync::mpsc                                             fn channel<T>() -> (Sender<T>, Receiver<T>);
std/src/sync/mpsc/mod.rs:759:1                                  std::sync::mpsc                                             fn sync_channel<T>(bound: usize) -> (SyncSender<T>, Receiver<T>);
std/src/thread/mod.rs:653:1                                     std::thread                                                 fn current() -> Thread;
std/src/thread/mod.rs:741:1                                     std::thread                                                 fn panicking() -> bool;
std/src/thread/mod.rs:1133:5                                    std::thread::Thread                                         fn id(&self) -> ThreadId;
std/src/thread/mod.rs:1175:5                                    std::thread::Thread                                         fn name(&self) -> Option<&str>;
std/src/thread/mod.rs:1362:5                                    std::thread::JoinHandle<T>                                  fn thread(&self) -> &Thread;
```
