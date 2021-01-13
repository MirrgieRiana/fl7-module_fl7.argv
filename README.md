
# Name

fl7.argv - Very simple ARGV parser.

# Synopsys

```
$ fl7 'USE(MODULE(FILE; "fl7.argv")).parse("Usage: args..."; ARGV[1; ]) => JSON >> 2' -a A1 +abc -a A2 file1 -b B1 --abc ABC1 -a A3 +a --abc=ABC2 file2
```

prints

```
{
  "a": [
    "A1",
    true,
    "A2",
    "A3",
    true
  ],
  "b": [
    true,
    "B1"
  ],
  "c": [
    true
  ],
  "_": [
    "file1",
    "file2"
  ],
  "abc": [
    "ABC1",
    "ABC2"
  ]
}
```

# Installing

## 1. Install fluorite-7

https://github.com/MirrgieRiana/fluorite-7

## 2. Install this module

```
$ fl7m pull 'https://raw.githubusercontent.com/MirrgieRiana/fl7-module_fl7.argv/main/module.json?'
```

# Usage

## `_.parse(usage; list_arg)` function

- `usage`: a parse error message as a strings
- `list_arg`: set the `ARGV[1; ]` as an array of strings
- Returns: an object whose value is an array of parsed arguments
