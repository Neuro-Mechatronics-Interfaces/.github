# NML GitHub #

This GitHub Organization hosts code that is developed and maintained by the members of the Neuro-Mechatronics Lab (**[NML](https://www.meche.engineering.cmu.edu/faculty/neuromechatronics-lab.html)**) at Carnegie Mellon University.  

## Contents ##
- [Repos](#repos)
  + Add `MATLAB` packages from [this table](#matlab). 
  + User Interfaces
     * [DS8R](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__ds8r) | (Stimulus Isolator Controller)
     * [2TMSi MATLAB Streaming](https://github.com/Neuro-Mechatronics-Interfaces/2TMSi_MATLAB_Interface) | (Realtime streams/recording with the squiggles etc)
     * [LSL GUI for TMSi MATLAB](https://github.com/Neuro-Mechatronics-Interfaces/TMSi_MATLAB_LSL) | (Can connect to realtime streams any time someone runs 2TMSi interface, as long as both computers are connected to NML Wifi router)
     * [MUExplorer](https://github.com/Neuro-Mechatronics-Interfaces/MUExplorer) | Interactive manual selection of MUAP waveforms - complementary with DEMUSE toolkit import/export format.
     * [Decomposition Export](https://github.com/Neuro-Mechatronics-Interfaces/Decomposition-Export) | See examples for how to export your TMSi `.poly5` data to `.mat` file format compatible with `DEMUSE`.
     * [Text Entry Prompter](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__typewriter) | Simple MATLAB GUI that lets you prompt subjects using a pre-curated list of simple phrases for text entry.
- [Contributing](#contributing)

---
## External Links ##
* [Lab Wiki](https://nml-wiki.org)
* Various WTF Links:
  + [Click-Hold-Release (CHR) Tasks](https://chr.nml.wtf)
  + [Fitts' Grid Tasks](https://fitts-task.nml.wtf)
  + [Simulations of varying utility](https://sims.nml.wtf)

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
| **[+tdk](https://github.com/Neuro-Mechatronics-Interfaces/matlab_package__tdk)** | [Max Murphy](https://github.com/m053m716) | This repository contains a MATLAB `mex` interface to the TDK vibrotactors. |
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

