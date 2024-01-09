---
title: "Introduction"
teaching: 5
exercises: 0
questions:
- "How can I set easily set up eic-shell to developp and compile parts of the ePIC software stack`?"
objectives:
- "Download the drich-dev environment."
keypoints:
- "All our packaes are in public repositories. The `drich-dev` environment provides helpers to streamline building and setting the PATHs just right."
---
As usual, we start with
```
./eic-shell
source /opt/detector/epic-nightly/setup.sh
```

Now download `drich-dev`:
```
git clone https://github.com/eic/drich-dev.git
```
Reminder: If you expect to contribute to a repository, you must have developer privileges, for the most part by being a member of the EIC organization and becoming a member of the ePIC devs team. In that case, it is beneficial to upload your ssh credentials to github and use the ssh clone interface by replacing `https://github.com/`with `git@github.com:`, i.e.
```
git clone git@github.com:eic/drich-dev.git
```
To do so using the docker version, it is for this version best to issue git commands from outside eic-shell so that your credentials are known.

Now just initialize the environment and we are ready to install a repository from scratch in the next lesson:
```
cd drich-dev
source environ.sh
```

Some parameters you can set:
* $BUILD_NPROC controls the number of parallel threads during building. By default it will use as many threads as there are cores, while memory-hungry builds may be done on a single thread.
* $EIC_SHELL_PREFIX is the local installation location for all built modules, byt default `./prefix`


#### Homework:
Explore this directory and familiarize yourself with the documentation. There are many helpers in here to run simulations, visualize gemetries etc. But in this tutorial, we will focus exclusively on `build.sh`



{% include links.md %}

