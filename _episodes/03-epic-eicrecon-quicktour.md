---
title: "Quick Tour of the epic and eicrecon repositories"
teaching: 15
exercises: 0
questions:
- "Where does some relevant code live, and what does it look like?"
objectives:
- "Explore a few key repositories."
keypoints:
- "The [epic repository])(https://github.com/eic/epic) contains the detector geometry descriptions. The [eicrecon repository](https://github.com/eic/eicrecon/) handles digitization, reconstruction, and pre-analysis such as jet-finding."
---

A deep, interactive dive into either package would exceed the time frame of this tutorial. Some of it will be covered in the following tutorials. While build times, especially for eicrecon on a Silicon Mac are somewhat prohibitive, you know now how to do it. For any interactive work later today, it is strongly recommended to use eic-shell either on an intel machine, or at least start the build right now. Note that only the initial build will take that long, changes to a few files generally don't trigger the rebuild of an entire package.

Detector geometry is handled by the `epic` package. Sub-detector cml filese are in `epic/compact`, their corresponding C++ (Geant4) implementations in `epic/src`

Configurations (like bruycecanyon, craterlake, customized ones for special purposes are in the `epic` top level directory, but instead of making changes here, add to or edit the YAML files in `epic/configurations`, rebuilding the package will auto-generate the composite configurations.





{% include links.md %}

