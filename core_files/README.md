# Core files

```text
richel@richel-N141CU:~/GitHubs/ticket_304069/core_files$ file core.7641 
core.7641: ELF 64-bit LSB core file, x86-64, version 1 (SYSV), can't read elf program headers at 10200
```

richel@richel-N141CU:~/GitHubs/ticket_304069/core_files$ file -Pelf_phnum=10000 core.7641 
core.7641: ELF 64-bit LSB core file, x86-64, version 1 (SYSV), can't read elf program headers at 10200


```
richel@richel-N141CU:~/GitHubs/ticket_304069/core_files$ readelf -Wa core.7641
ELF Header:
  Magic:   7f 45 4c 46 02 01 01 00 00 00 00 00 00 00 00 00 
  Class:                             ELF64
  Data:                              2's complement, little endian
  Version:                           1 (current)
  OS/ABI:                            UNIX - System V
  ABI Version:                       0
  Type:                              CORE (Core file)
  Machine:                           Advanced Micro Devices X86-64
  Version:                           0x1
  Entry point address:               0x0
  Start of program headers:          64 (bytes into file)
  Start of section headers:          0 (bytes into file)
  Flags:                             0x0
  Size of this header:               64 (bytes)
  Size of program headers:           56 (bytes)
  Number of program headers:         854
  Size of section headers:           0 (bytes)
  Number of section headers:         0
  Section header string table index: 0

There are no sections in this file.

There are no section groups in this file.
readelf: Error: Too many program headers - 0x356 - the file is not that big

There is no dynamic section in this file.

There are no relocations in this file.
No processor specific unwind information to decode

Dynamic symbol information is not available for displaying symbols.

No version information found in this file.
readelf: Error: Too many program headers - 0x356 - the file is not that big
```


```
richel@richel-N141CU:~/GitHubs/ticket_304069/core_files$ readelf --program-headers core.7641

Elf file type is CORE (Core file)
Entry point 0x0
There are 854 program headers, starting at offset 64
readelf: Error: Too many program headers - 0x356 - the file is not that big
```

To get some proper output, run with `gdb`:

```bash
gdb rstudio core.7641
```
