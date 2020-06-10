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

Tab delimited text files are plain text files that have one record for each line. The individual data values are separated by tab characters (`\t` - not spaces). This means that a cell can contain any value except for tabs (`\t`), newlines (`\n`), or carriage returns (`\r`). Tab-delimited elements do not support quoting.

There is normally a header line that describes the data each column contains. This is optional however, so tabl will support files missing this header. Another variation is where the header is actually the last commented line. This isn't terribly common, but does happen with some bioinformatics file formats. Tabl will also support these types of files. In both cases, there is a command-line flag that can be passed to let tabl know to take this variant into account.

Tab-delimited text files are the default format for tabl.

## Comma separated (CSV)

Comma-separated value files are text files where the individual data values are separated by the `,` character. Rows are separated by the carriage return/newline combination `\r\n`. The comma delimiter makes it easy to include whitespace (tab-characters) in the value. However, it also means that the value can not contain the `,` character. To get around this, CSV elements can also be quoted. If the element is surrounded by double-quotes (`"`), then any extra whitespace characters (including newlines) or commas included. If a double-quote is part of the element, then it needs to be included as two double-quotes (`""`). If used, the double-quotes must be present at the start and the end of the element.

In order to tell tabl that a data files is a CSV file, you can pass the `--csv` flag to any of the commands.

For more information, see [RFC 4180](https://tools.ietf.org/html/rfc4180).

## Comments

All files can contain comments anywhere within their body. Comment lines are denoted by the `#` character. All comment lines must start with that character. These lines can be either ignored (default) or included in `tabl view` or `tabl export` with a command-line flag (`--show-comments`).


## Compression

Tabl will transparently handle files that have been gzip compressed. This is determined by the file contents, not by the file extension. You still need to specify `--csv` for CSV files, but other than that, the compression support is automatic. Gzip is currently the only compression method that is transparently handled. Other methods can be used, but they need to be decompressed and piped to tabl through `stdin`.

Example:

    $ bunzip2 -c file.txt.bz2 | tabl view -