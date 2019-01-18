---
layout: default
title: Command Line Interface
nav_order: 40
has_children: true
permalink: /docs/cli
---

# CLI

To list available commands, from the Terminal either run `docker` or `docker help`.

```bash
$ beaker

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
```

You can modify the beaker command behavior using environment variables or command-line options. 

## Help Text

To list the help on any command just execute the command, followed by the --help option.

```bash
$ beaker configure --help
usage: beaker configure <command> [<args> ...]

Configure Beaker options

Flags:
  -h, --help     Show context-sensitive help (also try --help-long and
                 --help-man).
  -v, --version  Show application version.
      --debug    Print verbose stack traces on error.

Subcommands:
  interactive*
    Interactive configuration

  test
    Test the configuration
```

## beaker (base command)

## beaker commands

| Command        | Description           |
| ------------- |-------------| 
| beaker blueprint      | this is it | 
| beaker configure      | this is it      | 
| beaker dataset | this is it      | 
| beaker experiment | this is it      | 
| beaker group | this is it      | 
| beaker help | this is it      | 
| beaker versions | this is it      | 
| beaker task | this is it      | 





