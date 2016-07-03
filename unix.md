
# Miscellaneous Unix Commands

### Determine File Type

    file somefile
    somefile: Little-endian UTF-16 Unicode text, with CRLF, CR line terminators

### Dump File As Hex

    hexdump somefile

### Change File Encoding, Line Ending, Byte Order Mark with Vim

    vi somefile
    :set ff=unix
    :set fileencoding=utf-8
    :set nobomb
    :wq   


