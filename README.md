
<a href="https://github.com/MirrgieRiana/fl7-module_fl7.argv/actions?query=workflow%3ATest"><img src="https://github.com/MirrgieRiana/fl7-module_fl7.argv/workflows/Test/badge.svg"></a>

# Name

fl7.argv - Very simple ARGV parser.

# Synopsys

```
$ fl7 'USE(MODULE(FILE; "fl7.argv")).parse("Usage: args..."; ARGV[1; ]) => JSON >> 2' -a A1 +abc -a A2 file1 -b B1 --abc ABC1 -a A3 +a ++def --abc=ABC2 file2 -- +X --
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
    "file2",
    "+X",
    "--"
  ],
  "abc": [
    "ABC1",
    "ABC2"
  ],
  "def": [
    true
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

## `_.parse([usage[; list_arg]])` function

- `usage`: a parse error message as a strings (default: "Argument Error")
- `list_arg`: set the `[ARGS]` as an array of strings (default: `[ARGS]`)
- Returns: an object whose value is an array of parsed arguments
