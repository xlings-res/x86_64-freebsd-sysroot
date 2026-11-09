# x86_64-freebsd-sysroot

Release storage for `xim:x86_64-freebsd-sysroot`: the FreeBSD base system (amd64) a program for
`x86_64-freebsd` is compiled and linked against -- `usr/include`, the shared
libraries, the dynamic loader, crt objects and the static archives of the C
library, the C++ run-time and the compiler run-time -- with libc++'s std module
sources generated from the official libcxx source release of the base's libc++
version (FreeBSD installs none).

The payload is target code and host-independent: one archive serves every host.
It is a base package (mcpp design 2026-11-10 E5): the package root is the
sysroot, and `mcpp.toml` at the root states the layers it supplies
(`provides`) and where they stand (`[build]`).

    x86_64-freebsd-sysroot-<ver>/
      mcpp.toml  PROVENANCE.md
      lib/  libexec/  usr/          the sysroot
      usr/share/libc++/v1/          std.cppm, std.compat.cppm

Assembled from the official `base.txz` distribution set (download.freebsd.org)
by `openxlings/xim-pkgindex`: `.agents/tools/build-freebsd-sysroot.py`.
PROVENANCE.md in the archive names the upstream set and its sha256.
