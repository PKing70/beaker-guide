---
layout: default
title: Hello Beaker
parent: Get Started
nav_order: 12
---

# Your First Beaker Experiment 

Beaker manages experiments as Docker containers combined with additional metadata to make your code and data easy to share and replicate. To show you how to do this with "real" code and data, this tutorial will show you how to train a Python Pytorch model using LeCun's MNIST dataset of images of handwritten digits.

Don't worry if you don't know about Python, Pytorch, or MNIST data; you won't need to here. This exercise simply shows you how to run a full experiment with Beaker in a way that should be easy to understand. You should be able to apply these steps and concepts to your own code, data, and experiments.

## Set Up Python and Pytorch

If not yet done, install [Python](https://www.python.org/downloads/) and [Pytorch (and Torchvision)](https://pytorch.org/get-started/locally/).

After installing, you can verify your configuration by enting `python` from your Terminal shell:

    ```bash
    $ python
    Python 3.7.2 (default, Dec 29 2018, 00:00:04) 
    [Clang 4.0.1 (tags/RELEASE_401/final)] :: Anaconda, Inc. on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>> 
    ```
Which shows your Python version, date, and so on, if successfully configured.

From the Python prompt (`>>>`, above) you can verify your Pytorch installation too:

    ```bash
    >>> import torch; print(torch.__version__)
    1.0.0
    ```
    
Which shows your Pytorch/Torchvision version, if successfully configured.

Finally, if you are new to Python for this tutorial, know you quit the Python shell (`>>>`) and return to your Terminal shell by pressing `control+d`.


