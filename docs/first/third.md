---
layout: default
title: Create your Experiment
parent: Get Started
nav_order: 16  
---

# Create Your Own Experiment

In this example, you'll run your experiment from the CLI and also create a corresponding experiment spec. 

https://beaker-pub.allenai.org/ex/ex_lhqimp6vaffk

beaker experiment create \
    --blueprint mymnist \
    --env EPOCH=50 \
    --source mymnist-dataset:/data \
    --result-path /output
    
Experiment ex_lhqimp6vaffk submitted. See progress at https://beaker-pub.allenai.org/ex/ex_lhqimp6vaffk


