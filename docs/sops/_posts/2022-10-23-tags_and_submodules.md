---
layout: post-toc
title: How to use tags and gitmodules (submodules)
about: This will help you stay sane while trying to work with Max.
tags: git instructions gitmodules submodules packages matlab
category: sops
---

## What is this? ##
Max has a tendency to push a lot of changes to the remote repos because that's how he develops on one device or another, and since it's often the case that you can't keep working on just one device (particularly if there is some important machine that is in high-demand, and therefore less accessible, but which must be accessed ultimately to run code and conduct the related experiments), there is a tendency for there to be lots of small pushes to the remotes. This generally works fine with side-branches, but for any of the **`MATLAB`** repositories--particularly the [`package` style repositories](https://github.com/Neuro-Mechatronics-Interfaces#matlab), this can pose a problem for others that use a shared repo but are on a side branch potentially with submodule versions that are "out-of-date" (even if they aren't that far behind). 

To avoid causing problems when submodules, which must be updated, are updated, Max is implementing a tagging strategy. This SOP explains what the tags indicate, and how best to make use of the tags to save time particularly when working on any codebase that Max might touch.

### Tag Conventions ###
The tags basically follow the recommend GitHub semantic veresioning tag specifications:
> Tagging Specification (SemVerTag) This sub-specification SHOULD be used if you use a version control system (Git, Mercurial, SVN, etc) to store your code. Using this system allows automated tools to inspect your package and determine SemVer compliance and released versions. When tagging releases in a version control system, the tag for a version MUST be "vX.Y.Z" e.g. "v3.1.0".  

If you like these kind of things, then you may enjoy reading up on [Semantic Versioning 2.0.0](https://semver.org/). The short summary (from their site):
> Given a version number `MAJOR.MINOR.PATCH`, increment the:
> 1. `MAJOR` version when you make incompatible API changes
> 2. `MINOR` version when you add functionality in a backwards compatible manner
> 3. `PATCH` version when you make backwards compatible bug fixes

### OK, but really, what does that mean? ###
In practice, `MAJOR` version changes very infrequently. `PATCH` is the most-frequent change--and in the `submodules` it will typically occur with things like bugfixes or other minor tweaks in functionality. In practice, any time I do things like:
* Add a new function file
* Change input arguments to an existing function, in a way that might break old code
* Change the order or number of output arguments from an existing function, in a way that might break old code
* Change a table's columns, or some other data structure, ina  way that might break old code  
`...`
* `<Do something with the code>` which might break old code
I try to increment the `MINOR` version.  

When there have been a significant number of `MINOR` version changes, or the codebase overall has changed enough that it is ready for a "new" iteration of some experiment for example, this may also be an appropriate time to change the `MAJOR` version (I think this is different than the intended use of `SemVer` but that is generally how my scheme goes at any rate).

## How do I tag stuff? ##
Try to get in the habit of tagging; any time you are going to make a `git push`, to the remote, consider first tagging the commit and potentially even annotating that tag. For example, tagging a change to `changed_file.m` with `v1.3.7` would look like: 
```(git)
git add changed_file.m
git commit -m "Fixes a bug where it deletes all my files."
git tag -a v1.3.7 -m "v1.3.7 Fixes critical error where it wipes my data. Please update."
```

### How can tags help me work with Max? ###
If there is some current version of code that you're collaborating on and you know it's the weekend so Max is going to put in 20 hours or so before you've checked your email again, there is a possibility that a bunch of changes will happen in the code. To make your life easier, consider keeping a record for yourself of any `gitmodule` submodule packages (for example, in `MATLAB` repos specifically the `+plot` package and `+io` and `+utils` packages tend be where this kind of changes can happen). Keeping a running record of the tags associated with your branch makes it easier to go in and then using for example a GUI like `GitKraken`, check which version the `submodule` is on. If you see that the package has moved beyond where your records indicate the tag should be, just double-click the tagged version you want from the remote, and it will automatically put you back to the correct version of the package.