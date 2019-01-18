---
layout: default
title: Command Line Interface
nav_order: 40
---

# CLI

usage: beaker [<flags>] <command> [<args> ...]

Beaker is a lab assistant to run and view experiments.

Flags:
  -h, --help     Show context-sensitive help (also try --help-long and
                 --help-man).
  -v, --version  Show application version.
      --debug    Print verbose stack traces on error.

Commands:
  help [<command>...]
    Show help.

  alpha [<flags>]
    Alpha commands with limited support

  blueprint [<flags>]
    Manage blueprints

  dataset [<flags>]
    Manage datasets

  experiment [<flags>]
    Manage experiments

  group [<flags>]
    Manage groups

  task [<flags>]
    Manage tasks

  configure
    Configure Beaker options

  version
    Print the Beaker version
