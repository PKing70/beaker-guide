---
layout: default
title: Your First Beaker Experiment
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

```python
>>> import torch; print(torch.__version__)
1.0.0
```
    
Which shows your Pytorch/Torchvision version, if successfully configured.

Finally, if you are new to Python for this tutorial, know you quit the Python shell (`>>>`) and return to your Terminal shell by pressing `control+d`.

## Get an existing experiment

For this tutorial, you should use the code from https://github.com/beaker/mnist-example. 

1. Clone https://github.com/beaker/mnist-example
2. Download your dataset from from [here](https://beaker.org/ds/ds_kf6v919aq7hk/details) to /data directory. The *dataset* used with experiments are the files, or directories of files, referenced by the code of the experiment. For this experiment, download the four MNIST source files (`/t10k-images-idx3-ubyte`...).

## Run the experiment

1. Set the python path:
```bash
export PYTHONPATH=.
```
2. Set the EPOCH environment variable, required by this experiment:
```bash
EPOCH=10
```
3. From your local mnist-example directory, run the main program in Python, using the path to the data director to which you downloaded the dataset above:
```bash
python beaker_pytorch/main.py \
    --data-dir /path/to/data \
    --output-dir /tmp/output \
```

## Build the Docker image 

1. Build the docker image:
```bash
docker build -t mnist .
```
## Create the Beaker blueprint

All of the above steps represent the creation and running of an experiment without Beaker. Next, you will use Beaker to create a blueprint that represents this experiment, and pushes it to Beaker.org for management and reuse.

```bash
beaker blueprint create -n mnist mnist
```
You can have only one Beaker blueprint called mnist. If necessary, change this name to something unique such as mnist2.

Now, run the experiment using Beaker:
```bash
beaker experiment run -f spec.yml
```
## What happened?

Check out your experiment at the URL provided from the command line. 

You should see A B C.

You can now rerun this experiment easily, by ...

The experiment that was already defined for you on Beaker.org was just run again, by your command. You can see its latest status at

This demonstrates how Beaker facilitates experiment replication.

Next, Your dataset

The *dataset* used with experiments are the files, or directories of files, referenced by the code of the experiment. For this experiment, download the four MNIST files (`/t10k-images-idx3-ubyte` and so on) from [here](https://beaker.org/ds/ds_kf6v919aq7hk/details) to a local directory.

## Your blueprint

The specification that defines your Beaker experiment is your *blueprint*. For this experiment, download the MNIST blueprint  in YAML format from ... at Beaker.




