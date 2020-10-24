# lib32-gdbm-patched
This is the gentoo patched version of lib32-gdbm package from aur repository. For Arch and Arch based distro.

patched following the comment made by gebau00a:
````
gebau00a commented on 2020-06-08 15:21
GDBM will not compile due to double definitions, see https://bugs.gentoo.org/705898 for details. Bug happens only on gcc 10.

Very dirty fast hack is to change CFLAGS in the build file to CFLAGS='-fcommon' (dirty workaround from https://wiki.gentoo.org/wiki/Gcc_10_porting_notes/fno_common)

Better would be to implement the patch from Gentoo
````

Here's the getoo patch: https://bugs.gentoo.org/705898

aur links: https://aur.archlinux.org/packages/lib32-gdbm/
