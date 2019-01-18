---
layout: default
title: Beaker blueprint
parent: Command Line Interface
nav_order: 50
---

# Beaker blueprint

```
usage: beaker blueprint [<flags>] <command> [<args> ...]

Manage blueprints

Flags:
  -h, --help     Show context-sensitive help (also try --help-long and
                 --help-man).
  -v, --version  Show application version.
      --debug    Print verbose stack traces on error.
      --addr="https://beaker-pub.allenai.org"  
                 Address of the Beaker service.

Subcommands:
  create [<flags>] <image>
    Create a new blueprint

  inspect <blueprint>...
    Display detailed information about one or more blueprints

  rename [<flags>] <blueprint> <new-name>
    Rename an blueprint

  pull [<flags>] <blueprint> [<tag>]
    Pull the blueprint's Docker image
```
