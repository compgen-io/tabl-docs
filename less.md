---
title: "tabl less"
permalink: /less
layout: home
#nav_gap: true
nav_order: 5
subsite_nav: true

---

# tabl less

This command lets you view a delimited text file in a TUI paging environment. It operates very similarly to the less command. You can scroll through rows and columns. 

One unique feature is that the header values are always displayed as the top line. This way, you can keep track of the meaning for column, even if you are at the end of the file. Also, when scrolling, you can also set certain columns to be "sticky". This means that those columns are always shown, even if you are currently looking at columns further to the right.

## Usage

`$ tabl less [filename] {options}`  
    
*If `filename` is not given, stdin is assumed. Use `-` to explicitly read from stdin.*
## Options

* `--min`           -- the minimum width for a column
* `--max`           -- the maximum width for a column  
*(by default, the width is auto determined)*

## Common options
* `--csv`            -- the file is a CSV file
* `--no-header`      -- the file doesn't contain a header row
* `--header-comment` -- the header is the last commented line (not common, but used sometimes in bioinformatics, eg. VCF format)

## Example

    $ tabl less iris.txt

![tabl less](/assets/img/tabl-less.png)

## In-program commands

    ?                 Show the help text
    q,Ctrl-C,ESC      Quit the program
    /                 Search
    m,Enter           Mark a line
    x                 Select "sticky" columns
                      To select sticky columns, use 
                      arrow keys and hit space to toggle on/off.
                      Hit ESC to exit "sticky-select" mode.
    

Navigation

    h,left-arrow      Move left a column  
    j,down-arrow      Move down a row
    k,up-arrow        Move up a row  
    l,right-arrow     Move right a column  
    
    space             Move down a page
    b                 Move up a page

    

