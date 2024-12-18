# H4. The `core.` files wll be helpful in finding the answer.

What is the content of the `core.[number]` files?

See 'Open question 2: reading the `core.` files.

## 'Open question 2: reading the `core.` files

- [Kevin Ushey](https://forum.posit.co/t/core-dump-from-rstudio/3155/2)
    - Useless
- [sqlite DB core dump](https://forum.posit.co/t/rstudio-core-dump-when-querying-sqlite-db/8921/1)
    - Not useful
    - !!!May be locale
- [RStudio 'core' folder](https://github.com/rstudio/rstudio/tree/main/src/cpp/core)

They are in the `core_files` folder

Do:

```bash
cd core_files
interactive -A sens2017625 -n 2 -t 2:00:00
module load R_packages/4.3.1
module load RStudio/2023.12.1-402
gdb rstudio core.7641
```

Results: is not a core dump ...?

```
[richel@sens2017625-b9 core_files]$ gdb rstudio core.7641
GNU gdb (GDB) Red Hat Enterprise Linux 7.6.1-120.el7
Copyright (C) 2013 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.  Type "show copying"
and "show warranty" for details.
This GDB was configured as "x86_64-redhat-linux-gnu".
For bug reporting instructions, please see:
<http://www.gnu.org/software/gdb/bugs/>...
Reading symbols from /sw/apps/RStudio/2023.12.1-402/rackham/rstudio...
warning: Unable to open "librpm.so.3" (/sw/apps/xz/5.2.6/bianca/lib/liblzma.so.5: version `XZ_5.1.2alpha' not found (required by /lib64/librpmio.so.3)), missing debuginfos notifications will not be displayed
Missing separate debuginfo for /sw/apps/RStudio/2023.12.1-402/rackham/rstudio
Try: yum --enablerepo='*debug*' install /usr/lib/debug/.build-id/c9/a5c4e4a9489e5a017327ea9770a718fb9a8e66.debug
(no debugging symbols found)...done.
"/castor/project/home/richel/core_files/core.7641" is not a core dump: File truncated
(gdb) bt
No stack.
(gdb)
```

The core files are truncated.
According to [https://docs.oracle.com/cd/E19205-01/819-5257/blabs/index.html](https://docs.oracle.com/cd/E19205-01/819-5257/blabs/index.html),
these are useless.
