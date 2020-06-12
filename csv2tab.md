---
title: "tabl csv2tab"
permalink: /csv2tab
layout: home
#nav_gap: true
nav_order: 4
subsite_nav: true

---

# tabl csv2tab

Converts CSV files to tab-delimited text files.

## Usage

`$ tabl csv2tab [filename] {options}`  
    
*If `filename` is not given, stdin is assumed. Use `-` to explicitly read from stdin.*

## Common options
* `--show-comments`  -- include comments in the output

## Example

    $ tabl view iris.csv | head
