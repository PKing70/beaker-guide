---
layout: default
title: Installing
nav_order: 10
---

# Installing

There are a few different ways to install Beaker:

- Download a
[release](https://github.com/allenai/beaker/releases) and extract it:

    ```bash
    tar -xvzf beaker_*.tar.gz -C /usr/local/bin
    ```
    
    Place the binary executable in your PATH (e.g., /usr/local/bin/ or ~/bin)

- Apple macOS users can install Beaker through [Homebrew](https://brew.sh/) with a custom tap:

    ```bash
    brew tap allenai/homebrew-beaker https://github.com/allenai/homebrew-beaker.git
    brew install beaker
    ```

- Google [Go](https://golang.org/) developers can install Beaker from source using standard tools:

    ```bash
    go get -u github.com/allenai/beaker/...
    ```




