---
layout: default
title: Beaker group
parent: Command Line Interface
nav_order: 58
---

# Beaker group

```
usage: beaker group [<flags>] <command> [<args> ...]

Manage groups

Flags:
  -h, --help     Show context-sensitive help (also try --help-long and
                 --help-man).
  -v, --version  Show application version.
      --debug    Print verbose stack traces on error.
      --addr="https://beaker-pub.allenai.org"  
                 Address of the Beaker service.

Subcommands:
  add [<flags>] <group> <experiment>...
    Add experiments to an existing group

  create --name=NAME [<flags>] [<experiment>...]
    Create a new experiment group

  delete [<flags>] <group>
    Delete an experiment group

  inspect [<flags>] <group>...
    Display detailed information about one or more groups

  remove [<flags>] <group> <experiment>...
    Remove experiments from an existing group

  rename [<flags>] <group> <new-name>
    Rename an group
```
