
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

[How can I change a file's encoding with vim?](http://stackoverflow.com/questions/778069/how-can-i-change-a-files-encoding-with-vim)
[Convert DOS line endings to Linux line endings in vim](http://stackoverflow.com/questions/82726/convert-dos-line-endings-to-linux-line-endings-in-vim)    

### Change Line Ending with dos2unix

    dos2unix somefile

### Vi

[Vi Cheat Sheet](http://www.lagmonster.org/docs/vi.html)

### Run Script But Include Environment Changes In Current Shell

#### Current directory
    . somescript
#### Another directory
    . ../somedir/somescript

### Print the Environment of a Running Process

See man proc 5...

    strings /proc/<pid>/environ

### Ignore Case in Filenames When Using diff

    diff --ignore-file-name-case dir1 dir2

### See Files With Spaces in the Name

    find . -printf "[%p]\n"
    [.]
    [./x  ]
    [./x   ]
    [./x ]
    [./x]

### Find Directories in a Tree 

    find . -type d

### Touch All Files in a Directory

    find . -type f -exec touch {} \;

### Print SHA1 Hash of All Files in a Directory

    find . -type f -exec sha1sum {}

### Find Files With a Given Name in Directory Tree

    find . -type f -name "*.log"

### Copy Only Executables

    find fromdir -perm /a+x -exec cp {} todir \;       

### Change Directories to 755

    find somedir -type d -exec chmod 755 {} \;

### Change Files to 644

    find somedir -type f -exec chmod 644 {} \;     

### List Symbols of an Object File

    nm someexecutable
    nm somesharedobject

### List Shared Library Dependencies

    ldd someexecutable
    ldd somesharedobject
 
### List Mounted File Systems

    mount

### List Space Available on Each Mount

    df -h

### List Space Taken Up By Immediate Subdirectories

    du --max-depth=1 -h

### Show IP Address of Each Interface

    ifconfig -a

### Show Memory Map of a Process

    pmap <pid>

### Show Stack of a Running Process

    pstack <pid>

### Show Tree of Running Processes

    pstree

### Show Files Open By a Process

    lsof -a -p <pid>

### Generate a Timestamp

    date +%Y%m%d

### Date Calculations

    date --date="30 days ago" +%Y%m%d

### Check the Number of Command Line Arguments

    if [ $# -eq 0 ];
    then
        echo 'No arguments passed. Please pass the full path of the log directory ' >> $scriptdir/sysout/logarchive-$Today.out
        exit 1
    fi

### Uppercase a Value

    $(echo `hostname -s` | tr [:lower:] [:upper:])

### Extract Range of Bytes From Output

    ls -la | cut --bytes 16-30

### List Files in Reverse Order

    ls -lrt

### List Files with Numeric uid/gid

    ls -lan

### List Files with their Inodes

    ls -lia

### List Permissions Down a Path

    namei -m /aaa/bbb/ccc/ddd/eee

### Using Backticks to Execute a Command

    echo `pwd`

### Show SELinux Status

    sestatus

### Show Security Context of Files

    ls -Z

### Show Security Data for Processes

    ps axZ

### Generate Policy From Denied Audit Operations

    audit2allow



### TODO

top
vmstat
mpstat
lsof
prstat
sar
truss
dtrace
iostat
locale
locale -a
audit2why
perf
strace
script
dd