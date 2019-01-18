---
layout: default
title: Your First Experiment
parent: Examples
nav_order: 40
---
# Your First Experiment

First, create an account at [beaker-pub.allenai.org](https://beaker-pub.allenai.org) and follow the instructions in your [account settings](https://beaker-pub.allenai.org/user).

These instructions will guide you through installing and configuring the Beaker CLI. See [Installing](#) for more options.
   
Request "Scientist" or higher credentials from a Beaker admin to get authorization to create experiments.

## Counting words

The following example [counts words](https://beaker-pub.allenai.org/bp/bp_qbjvcda1sed7) in the text of [Moby Dick](https://beaker-pub.allenai.org/ds/ds_1hz9k6sgxi0a).

```bash
beaker experiment run \
  --name wordcount-moby \
  --blueprint examples/wordcount \
  --source examples/moby:/input \
  --result-path /output
```
