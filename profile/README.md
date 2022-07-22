# NML GitHub #

This GitHub Organization hosts code that is developed and maintained by the members of the Neuro-Mechatronics Lab (**[NML](https://www.meche.engineering.cmu.edu/faculty/neuromechatronics-lab.html)**) at Carnegie Mellon University.  

## Contents ##
- [Contents](#contents)
- [A Note From Max](#a-note-from-max)
- [Contributing](#contributing)
- [Resources](#resources)
  * [NML](#nml)
  * [Version Control](#version-control)
  * [IDEs](#ides)
  * [CAD](#cad)
  * [Graphics](#graphics)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>

---

## A Note From [Max](murphylab.net) ##
I started this GitHub organization when I joined NML in Spring 2021, because I generally am familiar with GitHub and kept my code in a GitHub Organization that stayed with the [lab where I did my dissertation research](https://github.com/Cortical-Plasticity-Lab). It's still not clear to me whether most code will end up here, on GitLab, on Google Drive, or on an internal server like raptor. However, I mostly use this organization to keep my own code that I develop while at NML documented and distributable within our team (and amongst collaborators). I had initially created some "GitHub Teams" to try and compartmentalize access to the different repos because there was initially some indication that human subjects research (and associated code) might be housed here. It looks like this is not an issue, but the Teams have persisted and at this point I'm moving away from using them. I think by now everyone should have access to what they need, **but please let me know** if you do not have access to a repo that you would like to use, and I will add you as quickly as I can!

--- 

## Contributing ##
If you are not familiar with `git` or version-control in general, it's recommended to familiarize yourself (it is a lot easier than you would think) by going **[here](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)**.

Please refer to **[this guide](https://code.nml.wtf/tutorials/2022/06/25/contributing.html)** for how to contribute your own code.

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