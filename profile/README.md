# NML GitHub #

This GitHub Organization hosts code that is developed and maintained by the members of the Neuro-Mechatronics Lab (**[NML](https://www.meche.engineering.cmu.edu/faculty/neuromechatronics-lab.html)**) at Carnegie Mellon University.  

## Contents ##
- [A Note From Max](#a-note-from-max)
- [Repos](#repos)
  + [MATLAB](#matlab)
- [Contributing](#contributing)
- [Resources](#resources)
  * [NML](#nml)
  * [Version Control](#version-control)
  * [IDEs](#ides)
  * [CAD](#cad)
  * [Graphics](#graphics)

---

## Repos ##  
This README is a continual _work-in-progress_. Please add a brief snippet and link where you feel is appropriate, if you add any repository to this organization. This is typically better to do when you are just starting a project, as that is a good time to outline documentation for how you think the code should be organized anyways.  

### MATLAB ###
I've tried to start moving any MATLAB "packages" (folders led with `+` e.g. `+plot`, which effectively creates a namespace for functions in those folders e.g. `plot.data()` for function `data.m` in the `+plot` folder).  
Any such code repositories in this GitHub organization should start with the name convention `matlab_package__` and should be initialized as a `gitmodule` with the folder name specified at the top-level of that repo (e.g. `+opx` for `matlab_package__opx`). Note that there are a couple of older repos from when I was just starting off, which do not follow this convention but to avoid making everyone's lives miserable I haven't gone back and changed the repo name.   

|   Name                                                     |  Maintainer                                                         | Description                                                                                          |
| ---------------------------------------------------------- | ------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **[+bd](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__bd)** | [Max Murphy](https://github.com/m053m716) | MATLAB package for handling behavioral metadata such as trial success rate, trajectory curvature, etc...   |
| **[+buf](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__circle_buffer)** | [Max Murphy](https://github.com/m053m716) | MATLAB package for efficient circle buffer using compiled mex functions. About twice as fast as MATLAB 2024 circshift. | 
| **[+circ](https://github.com/m053m716/-circ)**           | Adapted by Max from [Philipp Berens](berens@tuebingen.mpg.de) (MATLAB FEX originally)                        | Statistics package for distributions on circles.              |
| **[+ckc](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__ckc)** | multiple | MATLAB package for organizing data for CKC, primarily meant to have pre-processing and CKC reader functions. |
| **[+cm](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__cm)**           | [Max Murphy](https://github.com/m053m716)                        | Colormaps for MATLAB projects scattered throughout this organization's repos.              |
| **[+charts](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__charts)**           | [Max Murphy](https://github.com/m053m716)                        | MATLAB chart-classes (primarily for use with HD surface-EMG datasets).              |
| **[+cursor](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__cursor)** | [Max Murphy](https://github.com/m053m716) | MATLAB class for viewing/polling/logging Joystick cursor. |
| **[+default](https://github.com/m053m716/Matlab-Defaults)**           | [Max Murphy](https://github.com/m053m716)                        | Max's favorite default overrides for MATLAB built-ins such as `figure`.                      |
| **[+digilent](https://github.com/Neuro-Mechatronics-Interfaces/Digilent_Snippet_Parsing)** | [Max Murphy](https://github.com/m053m716) | Parsing/processing for csv snippets collected using the Digilent Analog Discovery 2 in Oscilloscope mode using the Waveforms software. |
| **[+ds8r](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__ds8r)** | [Jonathan Shulgach](https://github.com/Jshulgach) & [Max Murphy](https://github.com/m053m716) | MATLAB package gitmodule for running multiple DS8R via DAQ. | 
| **[+enum](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__enum)** | [Max Murphy](https://github.com/m053m716) | Enumeration classes commonly used by Max. |
| **[+error](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__error)** | [Max Murphy](https://github.com/m053m716) | MATLAB package gitmodule for error-handling that raises "standard" MATLAB exceptions. |
| **[+gui](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__gui)** | [Max Murphy](https://github.com/m053m716) | "Light-weight" GUIs (not .mlapp applications) for data curation (and presumably other purposes). |
| **[+io](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__io)** | [Max Murphy](https://github.com/m053m716) | Class with "loader" or "reader" functions (particularly useful for repos that access `raptor`). |
| **[+intan](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__intan)** | [Max Murphy](https://github.com/m053m716) | Code for running the Intan RHX interface via TCP. |
| **[+mats](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__mats)** | Adapted by Max from [Mats et al. 2021 JNE](https://kilthub.cmu.edu/articles/dataset/Simulation_files_for_current_field_computation_in_layer-homogeneous_media_applied_to_skull-transparent_currents/13281518/1) (and elsewhere)    | MATLAB package containing Mats' mystical field visualization tools.      |
| **[+opx](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__opx)** | Adapted by Max from [Plexon](https://plexon.com/software-downloads/#software-downloads-SDKs) | MATLAB package gitmodule for working with OmniPlex (Plexon). | 
| **[+plot](https://github.com/Neuro-Mechatronics-Interfaces/MATLAB_Data_Plots)**           | [Max Murphy](https://github.com/m053m716)                        | MATLAB package for different types of NML data plots.                    |
| **[+sounds](https://github.com/m053m716/-sounds)**           | [Max Murphy](https://github.com/m053m716)                        | Package with sound files (if initialized repo with Git-LFS) and function to play them.                |
| **[+TMSiSAGA](https://github.com/Neuro-Mechatronics-Interfaces/TMSi_SAGA)** | Adapted by Max from [TMSi](https://info.tmsi.com/software-tmsi-polybench) | This repository contains code for the MATLAB and Python APIs compatible with Windows 10 v2.0.0 drivers and beyond for use with the TMSi SAGA data recorder. | 
| **[+tdk](https://github.com/Neuro-Mechatronisc-Interfaces/matlab_package__tdk)** | [Max Murphy](https://github.com/m053m716) | This repository contains a MATLAB `mex` interface to the TDK vibrotactors. |
| **[+typewriter](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__typewriter)** | [Max Murphy](https://github.com/m053m716) | This repository contains code with a simple, configurable interface to prompt someone to type common phrases (Mackenzie & Soukeroff 2003) while measuring their words per minute. |
| **[+utils](https://github.com/Neuro-Mechatronics-Interfaces/NHP_MATLAB_Utilities)** | [Max Murphy](https://github.com/m053m716)   | Package with generic matlab utility functions, like parameter parsing from varargin, etc.             | 

### ROS2 ###
Different ROS2 nodes (probably in Python3) that let task-devices communicate with other environments, such as Unity.  

|   Name                                                     |  Maintainer                                                         | Description                                                                                          |
| ---------------------------------------------------------- | ------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **[NML Bag](https://github.com/ricmua/nml_bag)**           | [Andrew Whitford](https://github.com/ricmua)                        | A simple Python package for working with ROS2 bag files.                                             |
| **[Force Dimension ROS2 package](https://github.com/ricmua/ros_force_dimension)** | [Andrew Whitford](https://github.com/ricmua) | A ROS2 package for interfacing with Force Dimension haptics robots.                                  |
| **[ROS2 Data Agent](https://github.com/Neuro-Mechatronics-Interfaces/ROS2_Data_Agent)** | [Jonathan Shulgach](https://github.com/Jshulgach) | Code for a multipurpose file explorer specializing in reading ROS2 topic data from '.bag' or '.db3' files. |
| **[ROS2 Reward Dispenser](https://github.com/Neuro-Mechatronics-Interfaces/ROS2_Reward_Dispenser)**           | [Jonathan Shulgach](https://github.com/Jshulgach)                        | A ROS2 package with Arduino sketches to operate a water reward system using serial commands. LED matrix display and loadcell measuring scale supported.                                            |

---

## Contributing ##

### Using git ###
If you are not familiar with `git` or version-control in general, it's recommended to familiarize yourself (it is a lot easier than you would think) by going **[here](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)**.

### Contributing code ###
Please refer to **[this guide](https://code.nml.wtf/tutorials/2022/06/25/contributing.html)** for how to contribute your own code.

### Documenting contributions ###
Please refer to **[this guide](https://code.nml.wtf/tutorials/2023/02/10/adding-a-repo.html)** for how to document your code contributions. **If you add a repo to this GitHub organization, _please_ follow these instructions when setting it up!**

---

## Resources ##
I've added links to some general and code-specific resources that I've found helpful.

### NML ###
* [Lab "wiki"](https://sites.google.com/andrew.cmu.edu/nml-wiki/)
  + More of an internal lab webpage since it's technically *not* a wiki (sorry Doug).
* [Lab manual](https://docs.google.com/document/d/16vjhJS-PAJfaK7ePl2iu_n1GC_jEd4QehurmFKuI0No/edit?usp=sharing)
  + This is a helpful document that was primarily compiled by [Ashley](https://ashleydalrymple.com/).
* [Lab onboarding](https://docs.google.com/document/d/1sjAKbXGcvK6zEjVtAKwhtRyCwtew3JxEYqOH46v00SU/edit)
  + This onboarding document continues to evolve as students/staff join.
* [Raptor](http://128.2.244.66/doc/)
  + [Andrew](https://www.cs.cmu.edu/~awhitfor/) put together documentation and internally-hosted repos here.

### Version Control ###
* [git](https://git-scm.com)
  + Start here if you are new to **[VCS](https://en.wikipedia.org/wiki/Version_control)** and git in general.
* [GitKraken](https://www.gitkraken.com/)
  + This is my favorite GitHub desktop graphical interface.
  + It is pretty useful for tracking projects with multiple developers and branches.

### IDEs ###
* [Arduino](https://www.arduino.cc/en/software)
  + My favorite tool for flashing code onto microcontrollers.
  + Also, see this [tutorial](https://learn.sparkfun.com/tutorials/how-to-install-ch340-drivers/all) for CH34X drivers (in case you use cheap alternatives off Amazon like me, and always forget how to install...)
* [Thonny](https://thonny.org/)
  + Anaconda and PyCharm are both nice, but they are too big. Thonny is a light-weight IDE for Python that works right away on every platform I've ever tried (including running [MicroPython](https://micropython.org/) or [CircuitPython](https://circuitpython.org/) on [Pi Pico](https://www.raspberrypi.com/products/raspberry-pi-pico/), etc.)
    - Incidentally, [this](https://eshop.wiznet.io/shop/module/w5100s-evb-pico/) is my favorite evaluation board that uses the RP2040 chipset. It has a hardwired TCP/IP controller that makes it easy to network on a local ethernet switch.
* [Notepad++](https://notepad-plus-plus.org/downloads/)
  + This is a small text editor that opens everything.
  + Also I will fight you if you tell me this is not an IDE.

### CAD ###
* [OpenSCAD](https://openscad.org/downloads.html)
  + This is a free, light-weight CAD tool.
  + Also, check-out all the [free model libraries](https://github.com/nophead/NopSCADlib) others have shared!
    - (Although, note that they do use GPL-3.0 license, if you care about that kind of stuff.)
* [3D Slicer](https://download.slicer.org/)
  + Really nice tool for visualizing/segmenting MRI image datasets (i.e. `.dcm` or `.nifti`, etc.)
* [PrusaSlicer](https://www.prusa3d.com/page/prusaslicer_424/)
  + This is what I use to slice `.stl` files to get the `.gcode` for [using my 3D-printer](https://sites.google.com/andrew.cmu.edu/nml-wiki/documentation/administrative/equipment/3d-printing?authuser=0), which anybody in NML can use if they want.

### Graphics ###
* [Inkscape](https://inkscape.org/release)
  + This is a free tool that you can use instead of Adobe PhotoShop.
  + Also, check out this helpful [Inkscape Tutorial](https://drive.google.com/file/d/1CRXf0ffctcGFzVo-XWRsYJNRVkoJU13I/view?usp=sharing) by [Ashley](https://ashleydalrymple.com/)!
* [GIMP](https://www.gimp.org/downloads/)
  + This is also free, you can use it instead of Adobe Illustrator.
