---
layout: page
title: Documentation
permalink: docs
---

## Documentation ##
This page contains links to automatically-generated documentation produced using [`doxygen`](https://doxygen.nl/download.html). Specifically, any code written in a compiled language like `c` should include `doxygen` style `docstrings` (which are easily produced using tools like GPT-3.5+).  
* [Repos](#repos)
* [Contributing](#contributing)

---

### Repos ###
#### Applications ####
* [`NHP State Server`]({{site.baseurl}}/docs/StateServer/html/index.html) - This is the main workhorse for running the NHP wrist task. 
* [`NHP Wrist Renderer`]({{site.baseurl}}/docs/NHP_Wrist_Center_Out/html/index.html) - Compiled c application for rendering the cursor and targets.  
* [`NHP Task Controller`]({{site.baseurl}}/docs/TaskController/html/index.html) - Application for controlling the server/task/parameters.  
* [`NHP Rewarder`]({{site.baseurl}}/docs/Rewarder/html/index.html) - Application for controlling reward delivery.  

#### Libraries ####
* [`DataStructures`]({{site.baseurl}}/docs/DataStructures/html/index.html) - Compiled c-library with common data structures for the NHP wrist center-out and other tasks.  
* [`LogUtilities`]({{site.baseurl}}/docs/LogUtilities/html/index.html) - Compiled c-library with some useful logging utility functions.  
* [`MathUtilities`]({{site.baseurl}}/docs/MathUtilities/html/index.html) - Compiled c-library for some useful math functions that might be shared across repos.  
* [`NetworkUtilities`]({{site.baseurl}}/docs/NetworkUtilities/html/index.html) - Compiled c-library for some useful math functions that might be shared across repos.  
* [`SoundSynth`]({{site.baseurl}}/docs/SoundSynth/html/index.html) - Compiled c-library with some compiled applications for synthesizing sinusoidal tones and playback on Windows devices.  
* [`TaskParameters`]({{site.baseurl}}/docs/TaskParameters/html/index.html) - Compiled c-library with basic functions and data structure definitions for handling parameters. 
* [`TimingUtilities`]({{site.baseurl}}/docs/TimingUtilities/html/index.html) - Compiled c-library with basic utility functions for timing with higher precision than time.h. 

### Contributing ###
If you are contributing code and would like to use Doxygen to help maintain the documentation, then follow these steps:  
1. Download `doxygen` for your operating system/distribution and follow the installation instructions. On Windows, make sure you add the `bin` folder (by default: `C:/Program Files/doxygen/bin`) to the `PATH` environment variable so you can call `doxygen` from a terminal.  
2. If you are modifying code in an existing repo, you will notice that the repo should have a `Doxyfile` in the root folder of the repository.  If you are creating a new repo, copy an existing repository structure and use its `Doxyfile` as a template. You should be able to more-or-less leave the `Doxyfile` alone unless you want to make significant changes to the template repo organization; the key thing to make sure you change are the `OUTPUT_DIRECTORY`, `PROJECT_NAME` and `PROJECT_VERSION` variables in the Doxyfile. Your `OUTPUT_DIRECTORY` should be `OUTPUT_DIRECTORY = "$(NML_DOXY_DOCS_REPOSITORY)/<PROJECT_NAME>"` i.e. `OUTPUT_DIRECTORY = "$(NML_DOXY_DOCS_REPOSITORY)/StateServer"` for the `StateServer` repository.  
3. Critically, before calling `doxygen` to generate documentation, you need to set the `NML_DOXY_DOCS_DIRECTORY` environment variable. To set this variable, you need to have the `.github` repository cloned from the Neuro-Mechatronics-Lab Github organization. Wherever that repo lives on your local machine, there is a sub-folder `docs` and within that sub-folder there is another sub-folder `docs`. Your `$NML_DOXY_DOCS_REPOSITORY` will be the full string: `<.github folder>/docs/docs`. Note: I have not tested this using '\' on Windows, please use '/' just to be safe.  
4. Once you have configured everything, then in a terminal where you can confirm the `NML_DOXY_DOCS_DIRECTORY` (i.e. using `echo $(NML_DOXY_DOCS_DIRECTORY)` for UNIX-style bash or `echo %NML_DOXY_DOCS_DIRECTORY%` for Windows terminal), you should run `doxygen` from the repository root for which you wish to generate documentation.  
5. If you are adding documentation for a repo that does not exist in the list below, then in your `.github` local repository, edit the `index.md` file in `~/.github/docs/docs/index.md` to add the link to the list, following the path structure of other links in the list.  