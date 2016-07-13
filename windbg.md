
# windbg

[Common WinDbg Commands (Thematically Grouped)](http://windbg.info/doc/1-common-cmds.html)

### Setting Up Dump Workspace

Not sure if there is an easy way but if you're going to work on a specific dump for a while, it helps to set up the workspace.

    load dump
    set symbol path
    set source path
    set image path
    save workspace
    reload dump

### Automatically Anaylze Dump

    !analyze -v

### Debug Symol Loading

    !sym noisy
    .reload

### Set Symbol Path to Microsoft Symbol Server

    .symfix

### Force Reload of Mismatched Symbols

    .reload -i someprog.exe

### Print Summary of Heap Sizes

    !heap -s

### Print Stats for a Particular Heap

    !heap -stat -h <handle>

### Show All Allocations of a Given Sizes

    !heap -flt s <size>

### Show Details of a Single Allocations

    !heap -p -a <allocation>

### Find Address with Matching Text

    s -[1]a 0 L?7fffffff "12345"
    s -[1]a 0 L?7fffffff 31 32 33 34 35

### Find Matching Memory and Show Block Information for Each

    .foreach ($obj {s -[1]a 0 L?7fffffff "12345"}) {!heap -p -a $obj}

### Find Matching Memory and Dump Bytes for Each    

    .foreach ($obj {s -[1]a 0 L?7fffffff "12345"}) {db $obj}

### Breakpoint main

    bp main

### List Breakpoints

    bl

### Clear All Breakpoints

    bc *

### List Modules

    lm
    
### List Settings for Image

    gflags /i someprog.exe

### Enable User Mode Stack Trace Database

    gflags /i someprog.exe +ust

### TODO

    ~
    ~*
    k
    !address summary
    !address  
    !heap -s -v
    x/v *
    
