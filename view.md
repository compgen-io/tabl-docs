---
title: "tabl view"
permalink: /view
layout: home
#nav_gap: true
nav_order: 7
subsite_nav: true

---

# tabl view

This command formats a tab-delimited file and displays it in equally spaced columns.

## Usage

`$ tabl view [filename] {options}`  
    
*If `filename` is not given, stdin is assumed. Use `-` to explicitly read from stdin.*

## Options
* `--show-linenum`  -- also include the line number in the output
* `--min`           -- the minimum width for a column
* `--max`           -- the maximum width for a column  
*(by default, the width is auto determined)*

## Common options
* `--csv`            -- the file is a CSV file
* `--no-header`      -- the file doesn't contain a header row
* `--header-comment` -- the header is the last commented line (not common, but used sometimes in bioinformatics, eg. VCF format)
* `--show-comments`  -- display any comment lines in place

## Example

    $ tabl view iris.txt

    class           | sepal_length    | sepal_width    | petal_length    | petal_width    
    ================+=================+================+=================+================
    Iris-setosa     | 5.1             | 3.5            | 1.4             | 0.2            
    Iris-setosa     | 4.9             | 3.0            | 1.4             | 0.2            
    Iris-setosa     | 4.7             | 3.2            | 1.3             | 0.2            
    Iris-setosa     | 4.6             | 3.1            | 1.5             | 0.2            
    Iris-setosa     | 5.0             | 3.6            | 1.4             | 0.2            
    Iris-setosa     | 5.4             | 3.9            | 1.7             | 0.4            
    Iris-setosa     | 4.6             | 3.4            | 1.4             | 0.3            
    Iris-setosa     | 5.0             | 3.4            | 1.5             | 0.2            
