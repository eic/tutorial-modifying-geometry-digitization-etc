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

Note: You most likely will want to develop packages like epic, eicrecon, ... Due to current technical issues, full compilation from scratch of these in the docker version of eic-shell on a Silicon Mac takes 15+ minutes, too much for this tutorial.
 
 
It is instructive to follow the steps that this script takes:
```
# ./build.sh afterburner
CMAKE COMMANDS:
========================================

[ generate buildsystem ]
cmake -S afterburner/cpp -B afterburner/build -DHEPMC3_ROOTIO=ON -DCMAKE_INSTALL_PREFIX=/Users/eickolja/eic/drich-dev/prefix

[ build ]
cmake --build afterburner/build -j4

[ install ]
cmake --install afterburner/build

========================================
```
This tells you almost everything the script does, and in fact if you make changes to a file or two, it can make sense to use these commands directly instead of running through the makefile generation step again.
```
[Add std::cout<<"Hello world 1" << std::endl; to afterburner/cpp/abconv/main.cc]
time ./build.sh afterburner
```
Then try
```
[Change "Hello world 1" to "Hello world 2"]
time cmake --build afterburner/build -j4 && cmake --install afterburner/build
```

Also, note in the above the appearance of `-DHEPMC3_ROOTIO=ON`. By default, `build.sh` can build anything that relies on the "cmake, make, make install" paradigm, but for some named packages, options can be added and changed by default, explore `build.sh` to learn more!


Finally, it is sometimes necessary, and it never hurts, to update the environment again, and we can learn from its output as well.
```
source environ.sh
```


#### Homework:
Install any of epic, EICrecon, etc. Make a change, recompile, see what happens! Suggestions: Add simple text output, change the parameters of a detector subsystem and look for the consequences of such a change, like overlaps. Some packages:
```
git clone git@github.com:eic/epic.git
git clone git@github.com:eic/irt.git
git clone git@github.com:eic/EDM4eic.git
git clone git@github.com:eic/EICrecon.git
```
You can also explore how this works with external packages, such as:
```
git clone https://github.com/AIDASoft/DD4hep.git
git clone https://github.com/eic/EDM4eic
```
Some repositories have changed capitalization over time, you may need to rename them for `build.sh` to pick them up. Please report/file an issue/contact the Mattermost helpdesk, if you come across such instances.




{% include links.md %}

