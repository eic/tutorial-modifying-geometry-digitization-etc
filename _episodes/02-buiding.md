---
title: "Building an ePIC Package"
teaching: 15
exercises: 0
questions:
- "How can I modify and build parts of the ePIC software stack inside `eic-shell`?"
objectives:
- "Download and build a package, set up the environment to use it."
keypoints:
- "Any downloaded ePIC software package can be installed using `build.sh`"
---

Begin by obtaining the code of the repository you want to compile:
```
git clone git@github.com:eic/afterburner.git
```

Installing is now as easy as:
```
./build.sh afterburner
```

It is instructive to follow the steps that thisw script takes:




Note: You most likely will want to develop




#### Homework:
Explore this directory and familiarize yourself with the documentation. There are many helpers in here to run simulations, visualize gemetries etc. But in this tutorial, we will focus exclusively on `build.sh`



{% include links.md %}

