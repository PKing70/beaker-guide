---
layout: default
title: Beaker dataset
parent: Command Line Interface
nav_order: 54
---

# Beaker dataset

```
usage: beaker dataset [<flags>] <command> [<args> ...]

Manage datasets

Flags:
  -h, --help     Show context-sensitive help (also try --help-long and
                 --help-man).
  -v, --version  Show application version.
      --debug    Print verbose stack traces on error.
      --addr="https://beaker-pub.allenai.org"  
                 Address of the Beaker service.

Subcommands:
  create [<flags>] <source>
    Create a new dataset

  fetch --output=OUTPUT <dataset>
    Fetch an existing dataset

  rename [<flags>] <dataset> <new-name>
    Rename an dataset

  stream-file [<flags>] <dataset> [<file>]
    Stream a single file from an existing dataset to stdout

  inspect [<flags>] <dataset>...
    Display detailed information about one or more datasets
 ```
