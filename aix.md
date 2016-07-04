
# AIX Commands

(I need to retest some of these...)

### Tar Z Equivalent

    gunzip -dc some.tar.gz | tar -xf -

### List Log Files

    alog -L

### View Specific Log

    alog -o -t boot

### View Error Reports

    errpt

### View Specific Error Report

    errpt -a -j BFE4C025

### Convert DOS to UNIX Using AWK

    awk '{ sub("\r$", ""); print }' dos.txt > aix.txt

    [DOS to AIX conversion](https://www.ibm.com/developerworks/community/blogs/powermeup/entry/dos_to_aix_conversion13?lang=en)

### Get SIDS of Each Shared Memory Object

    ipcs -mS

### Get Process IDs Attached to a Shared Memory Object

    svmon -S 0x30170

### Reboot System

    shutdown -Fr

### Power Off System

    shutdown -F

### Show Process Memory Info

    svmon -P <pid>

### List Files in an Archive

    ar t

### Dump Dependencies

    dump -Hv someexecutable

### List Shared Libraries in Memory

    genkld

### Unload Shared Libraries in Memory

    slibclean

### List Loaded Objects for Each Process

    genld -lfind . -type d

### Links

    [IBM AIX commands you should not leave home without ](http://www.ibm.com/developerworks/aix/library/au-aix_cmds/)

### TODO

smitty
svmon
bootinfo -r
lsattr -El sys0
topas
swap -s
swap -l
ipcs
ipcrm
procstack <pid>
lslpp -l | grep xlC
snapcore
lsps -a
topas -P
rpm -qa	
svmon -P -O summary=basic,unit=MB,sortentity=pgsp
vmo -h lru_file_repage
vmstat -v
svmon -G
vmo -L
pagesize -a
ps aux
ps -kelf
lsattr -El sys0| grep -i core
lsdev -C -c adapter
lscfg -v -l ent0
svmon -P <pid>
find . -inum 811011 -exec ls -l {} \;
procfiles -n <pid>
netstat -Aan
kdb
(0)> sockinfo 70593de4 tcpcb
rmsock f100050000b05bb8 tcpcb

dbx
thread
thread current
where
dbx -I
stop CLASS:meth
run -f
cont
where
up
dump
file somefile.cpp
list <lineno>
stop at <lineno>
run -test
