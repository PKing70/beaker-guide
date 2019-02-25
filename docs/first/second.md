---
layout: default
title: Create Your Blueprint
parent: Get Started
nav_order: 14  
---

# Create Your Own Blueprint 

In this step, you'll use existing experiment code, data, and a Docker file. To this, you'll define your own Beaker blueprint, to define and manage the experiment you will run. This example continues with the MNIST dataset of the prior example. 

Don't worry if you don't know much about Python, Pytorch, or MNIST data; you won't need to here. This exercise simply shows you how to run a full experiment with Beaker in a way that should be easy to understand. You should be able to apply these steps and concepts to your own code, data, and experiments.

This example assumes you've successfully completed [Beaker and Docker installation](install.md), and you've set up your [Beaker.org](https://www.beaker.org) account and can run experiments as shown in [Your First Experiment](first.md).

## Set Up Python and Pytorch

If you don't already have them set up, install [Python](https://www.python.org/downloads/) and [Pytorch (and Torchvision)](https://pytorch.org/get-started/locally/).

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

All of this code simple represents the actual experiment codebase and dataset running locally, as you might do without Beaker. You are simply producing locally what the prior experiment did for you within the Beaker cloud.

The next step is to put this experiment into a Docker image. 

## Build the Docker image 

To build the docker image from the existing Dockerfile (which you cloned from Github), from the command line run:
```bash
docker build -t mymnist .
```
You should see the Docker steps complete, and conclude successfully with a message such as:
```
Successfully tagged mymnist:latest
$ 
```
In later examples, we'll show you how to set up your own Dockerfile but for this step, just use the provided Dockerfile that you cloned from Github.

## Create the Beaker blueprint

Now you have a Docker image of a complete experiment codebase and dataset. Next, create a Beaker blueprint to represent this experiment and push it to Beaker.org for management and reuse.

```bash
beaker blueprint create -n <mymnist> mnist
```
Note can have only one Beaker blueprint called mnist. So if you must because you've created an mnist blueprint previously, change <mnist> to something unique such as mnist2.

If you successfully create the blueprint, you should see output such as:
```
Pushing mymnist as mnist (bp_8ugouwgec4gn)...
<...preparing, waiting, etc...>
The push refers to repository [gcr.io/ai2-beaker-core/public/bhq49ga41h4qcklhc79g]
latest: digest: sha256:569de2a77ba779dbfddf6cc897f7abb17ef674239021b5f05e63e596aa7db5c3 size: 3058
Done.
$
```

Notice that each blueprint is assigned a unique ID, in addition to the name we chose. Any object,
including blueprints, can be referred to by its name or ID. Like any object, a blueprint can be
renamed, but its ID is guaranteed to remain stable. The following two commands are equivalent:

```bash
beaker blueprint inspect mymnist
beaker blueprint inspect bp_8ugouwgec4gn
```

Either should produce CLI output such as:

```bash
[
    {
        "id": "bp_8ugouwgec4gn",
        "user": {
            "id": "<your_user_id>",
            "name": "<your_user_name>",
            "display_name": ""
        },
        "name": "mymnist",
        "created": "2019-02-25T19:51:00.116911Z",
        "committed": "2019-02-25T19:51:05.103003Z",
        "original_tag": "mnist"
    }
]
```

## Pulling a Blueprint

You can pull a blueprint to your local machine at any time with `beaker blueprint pull`.

```
▶ beaker blueprint pull mymnist
Pulling gcr.io/ai2-beaker-core/public/bduufrl06q5ner2l0440 ...
latest: Pulling from ai2-beaker-core/public/bduufrl06q5ner2l0440
Digest: sha256:4c70545c15cca8d30b3adfd004a708fcdec910f162fa825861fe138200f80e19
Status: Downloaded newer image for gcr.io/ai2-beaker-core/public/bduufrl06q5ner2l0440:latest
Done.
```

In order to avoid accidentally overwriting your local images, this command assigns Beaker's random
internally assigned tag  `gcr.io/ai2-beaker-core/public/bduufrl06q5ner2l0440` by default. To assign
a more human-friendly tag, set it with an additional argument:

```
▶ beaker blueprint pull mymnist friendly-name
```

## Cleanup

To clean up, simply `docker image rm` any images created above.

Because blueprints are immutable, they can't be deleted. It will be possible to archive them in the
near future.

Next, we'll go through creating your own experiment spec.

