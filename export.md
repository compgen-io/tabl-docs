---
title: "tabl export"
permalink: /export
layout: home
#nav_gap: true
nav_order: 5
subsite_nav: true

---

# tabl export

This command returns only selected columns from the delimited text file.

## Usage

`$ tabl export [columns] [filename] {options}`  
    
*If `filename` is not given, stdin is assumed. Use `-` to explicitly read from stdin.*

`columns` is a comma-separated list of the columns to include. The value can be the name of the column (header value), the column number (1-based index), or a range of columns (ex `1-3`). If the name of the column contains spaces, the name can be quoted as well.  Extra qu

*Note: because of how the shell works with quoted arguments, column names that contain spaces will always need to be quoted, even if they aren't quoted in the input file. Column names that contains a comma or quotes in the name will likely need to be surrounded in single quotes and double quotes. *

 Example of quoting for the column named `"final,header"`:
 
    bin/tabl export "first header",'"final,header"' examples/test.csv --csv


## Common options
* `--csv`            -- the file is a CSV file (and the output will be a CSV file)
* `--no-header`      -- the file doesn't contain a header row
* `--header-comment` -- the header is the last commented line (not common, but used sometimes in bioinformatics, eg. VCF format)
* `--show-comments`  -- display any comment lines in place

## Example

    $ tabl export class,4-5 iris.txt | tabl view | head
    class           | petal_length    | petal_width    
    ================+=================+================
    Iris-setosa     | 1.4             | 0.2            
    Iris-setosa     | 1.4             | 0.2            
    Iris-setosa     | 1.3             | 0.2            
    Iris-setosa     | 1.5             | 0.2            
    Iris-setosa     | 1.4             | 0.2            
    Iris-setosa     | 1.7             | 0.4            
    Iris-setosa     | 1.4             | 0.3            
    Iris-setosa     | 1.5             | 0.2            

*(piped through `tabl view` for visualization)*

