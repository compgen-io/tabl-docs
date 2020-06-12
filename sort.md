---
title: "tabl sort"
permalink: /sort
layout: home
#nav_gap: true
nav_order: 7
subsite_nav: true

---

# tabl sort

Sorts the given file based on the values for each column. Columns can be sorted in text mode (default) or numeric mode. The order can be ascending (default) or descending.

This is implemented as a merge sort with temporary files.

## Usage

`$ tabl sort [filename] {options}`  
    
*If `filename` is not given, stdin is assumed. Use `-` to explicitly read from stdin.*

## Options

* `-k`, `--key`  -- the columns to sort by  
This argument can be used more than one. The value is a comma separated list of column names or indexes. A numeric column is specified by adding `:n` to the end of the argument. Descending sorting (reverse) is specified by adding `:r` to the argument. `:rn` does both. 

  Examples:

  `-k 1-2` -- sort by columns 1 and 2

  `-k 1,3` -- sort by columns 1 and 3

  `-k "Gene name",3` -- sort by the column named "Gene name" and then column 3

  `-k 1:n -k 2:rn` -- sort first by column 1 (numeric) and then column 2 (reversed and numeric)


## Common options
* `--csv`            -- the file is a CSV file (and the output will be a CSV file)
* `--no-header`      -- the file doesn't contain a header row
* `--header-comment` -- the header is the last commented line (not common, but used sometimes in bioinformatics, eg. VCF format)
* `--show-comments`  -- display any comment lines in place

## Example

    $ tabl sort -k 4-5:n -k class iris.txt | tabl view | head
    class           | sepal_length    | sepal_width    | petal_length    | petal_width    
    ================+=================+================+=================+================
    Iris-setosa     | 4.6             | 3.6            | 1.0             | 0.2            
    Iris-setosa     | 4.3             | 3.0            | 1.1             | 0.1            
    Iris-setosa     | 5.0             | 3.2            | 1.2             | 0.2            
    Iris-setosa     | 5.8             | 4.0            | 1.2             | 0.2            
    Iris-setosa     | 4.4             | 3.2            | 1.3             | 0.2            
    Iris-setosa     | 4.7             | 3.2            | 1.3             | 0.2            
    Iris-setosa     | 4.4             | 3.0            | 1.3             | 0.2            
    Iris-setosa     | 5.5             | 3.5            | 1.3             | 0.2            

*(piped through `tabl view` for visualization)*
