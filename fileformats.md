---
title: "File formats"
permalink: /formats
layout: home
#nav_gap: true
nav_order: 3
subsite_nav: true

---

# Supported file formats

Tabl supports two types of delimited text files: tab-delimited and comma-separated. These are two fairly simple formats, but tabl supports a few variants of each type.

## Tab delimited

Tab delimited text files are plain text files that have one record for each line. The individual data values are separated by tab characters (`\t` - not spaces). This means that a cell can contain any value except for tabs (`\t`), newlines (`\n`), or carriage returns (`\r`). 

There is normally a header line that describes the data each column contains. This can be optionally omitted. 


## Comma separated


## Compression

Tabl will transparently handle files that have been gzip compressed. This is determined by the file contents, not by the file extension. You still need to specify `--csv` for CSV files, but other than that, the compression support is automatic. 