---
layout: default
title: Beaker experiment
parent: Command Line Interface
nav_order: 56
---

# Beaker experiment

```
usage: beaker experiment [<flags>] <command> [<args> ...]

Manage experiments

Flags:
  -h, --help     Show context-sensitive help (also try --help-long and
                 --help-man).
  -v, --version  Show application version.
      --debug    Print verbose stack traces on error.
      --addr="https://beaker-pub.allenai.org"  
                 Address of the Beaker service.

Subcommands:
  create [<flags>]
    Create a new experiment

  inspect <experiment>...
    Display detailed information about one or more experiments

  rename [<flags>] <experiment> <new-name>
    Rename an experiment

  run --result-path=PATH [<flags>] [<arg>...]
    Run an experiment

  stop <experiment>...
    Stop one or more running experiments
 ```
