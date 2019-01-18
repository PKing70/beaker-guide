---
layout: default
title: Installing
nav_order: 10
---

# Installing

There are a few different ways to install Beaker:

- Download a
[release](https://github.com/allenai/beaker/releases) and extract it to your path:

    ```bash
    tar -xvzf beaker_*.tar.gz -C /usr/local/bin
    ```

- Apple macOS users can install Beaker through [Homebrew](https://brew.sh/) with a custom tap:

    ```bash
    brew tap allenai/homebrew-beaker https://github.com/allenai/homebrew-beaker.git
    brew install beaker
    ```

- Google [Go](https://golang.org/) developers can install Beaker from source using standard tools:

    ```bash
    go get -u github.com/allenai/beaker/...
    ```

## Getting Started

1. Create an account at [beaker-pub.allenai.org](https://beaker-pub.allenai.org)
   and follow the instructions in your [account settings](https://beaker-pub.allenai.org/user).

   These instructions will guide you through installing and configuring the
   Beaker CLI. See [below](#install-beaker-cli) for more options.
   
   Request "Scientist" or higher credentials from a Beaker admin to get authorization
   to create experiments.

2. Run your first experiment. The following example
   [counts words](https://beaker-pub.allenai.org/bp/bp_qbjvcda1sed7) in the text
   of [Moby Dick](https://beaker-pub.allenai.org/ds/ds_1hz9k6sgxi0a).

    ```bash
    beaker experiment run \
      --name wordcount-moby \
      --blueprint examples/wordcount \
      --source examples/moby:/input \
      --result-path /output
    ```


