
# Solaris Commands

(I need to retest some of these...)

### View Limits on Running Process

    plimit <pid>

### Show Instruction Set Architecture

    isainfo -v

### Invalidate DNS Cache 

    nscd -i hosts

### Calculate Hash For File

    digest -a md4 somefile
    digest -a sha1 somefile

### Determine if Daemon is Running

    /usr/bin/svcs ssh	

### List Summary Disk Usage for Current Directory

    du -s $(ls)

### Show Process Memory Size Sorted by Resident Set Size

    prstat -s rss	

### Show Top Processes by Memory Consumption

    ps -eo pid,pmem,vsz,rss,comm | sort -rnk2 | head

### List Processes Sorted by Memory

    top
    (hit M)

### List Address Space for Process

    ls -lh /proc/19792/as
    for pid in `pgrep someprocessname`; do ls -lh /proc/$pid/as; done

### Extract Record from File

    dd if=inputfile of=outputfile bs=454 iseek=5 count=1 
    dd if=inputfile of=outputfile bs=65536 skip=14170 count=1

### TODO

    prtdiag
    prtconf
    swap -l
    top
    mdb
    bdx
    psrinfo -v
    prtconf
    prtdiag -v
    lsofg -p
    gcore
    pstack <pid>
    pstack <corefile>
    ipcs -m -a
    ipcrm -m 4608
    ipcrm -M 0x5efaa728
    sysdef
    sar
    iostat
    vmstat
    mpstat
    lockstat -gkIW sleep 60
    /usr/ucb/ps aux
    prstat -avm
    prstat -vL
    sar -u 10 5
    prstat -amL
    apptrace
    mount -F tmpfs -o size=20000m swap /mountpoint
    a=$(ramdiskadm -a bigdisk 20g)
    newfs $a
    mount $a /mountpoint
    eject cdrom

    gdb
    break main
    break CLASS:meth

    tell gdb to not stop on SIGILL which is used on Solaris to emulate instructions not supported by the current processor
    handle SIGILL noprint
    handle SIGILL nostop
