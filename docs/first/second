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

1. Clone https://github.com/beaker/mnist-example. An easy way to do this is to click **Clone or download** from the GitHub page and download the ZIP to `/Downloads`, so that you have the files in `/Downloads/mnist-example-master`.

2. Download your dataset from from [here](https://beaker.org/ds/ds_kf6v919aq7hk/details) to a /data subdirectory of the location which you cloned `mnist-example` (for example, `/Downloads/mnist-example-master/data`. The *dataset* used with experiments are the files, or directories of files, referenced by the code of the experiment. For this experiment, download the four MNIST source files (`/t10k-images-idx3-ubyte`...).

## Run the experiment

1. Export the python path:
```bash
export PYTHONPATH=.
```

2. Set and exportthe EPOCH environment variable, required by this experiment:
```bash
EPOCH=10
export EPOCH
```

3. From your local `mnist-example-master` directory, run the main program in Python:
```bash
python beaker_pytorch/main.py
```
You should see the experiment run, then conclude with a message such as:
```bash
Test set: Average loss: 0.2057, Accuracy: 9405/10000 (94%)
$
```
By default, this experiment puts its results in an `/output` folder, in `metrics.json`.

All of this code simple represents an actual running experiment codebase and dataset, as you might have without Beaker. The next step is to put this experiment into a Docker image. 

## Build the Docker image 

To build the docker image, from the command line run:
```bash
docker build -t mnist .
```
You should see the Docker steps complete, and conclude successfully with a message such as:
```
Successfully tagged mnist:latest
$ 
```

## Create the Beaker blueprint

Now you have a Docker image of a complete experiment codebase and dataset. Next, create a Beaker blueprint to represent this experiment and push it to Beaker.org for management and reuse.

```bash
beaker blueprint create -n <mnist> mnist
```
Note can have only one Beaker blueprint called mnist. So if you must because you've created an mnist blueprint previously, change <mnist> to something unique such as mnist2.

If you successfully create the blueprint, you should see a message such as:
```
latest: digest: sha256:569de2a77ba779dbfddf6cc897f7abb17ef674239021b5f05e63e596aa7db5c3 size: 3058
Done.
$
```

Now, you can run the experiment using Beaker:
```bash
beaker experiment create -f spec.yml
```
## What happened?

Check out your experiment at the URL provided from the command line. 

You should see A B C.

You can now rerun this experiment easily, by ...
