---
layout: post
title: Contributing
about: How to contribute to an NML GitHub repository.
tags: git instructions
category: tutorials
---

If you know about `git` and feel good about contributing, but you're not sure about contributing to _these_ repos because you're worried you will break something--**don't be scared!** If you're not breaking _some_ code then you are probably doing things  wrong anyways. If you follow these steps, you can learn by working with the code without worrying about breaking others' code. Also, if your first thought when looking at the code in `step 1` is _"where exactly do I enter this?"_ then please **[start here instead](https://code.nml.wtf/tutorials/2022/06/26/credentials.html)**. 

1. **[Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository#cloning-a-repository)** the `main` branch to your local device:
```(git)
git clone --recurse-submodules git@github.com:Neuro-Mechatronics-Interfaces/NHP_Center_Out.git 
```
  + _Note 1:_ you will want to replace `NHP_Center_Out` with the name of the desired repository.
  + _Note 2:_ if you have not yet set up `git` and **[configured a credential manager](https://code.nml.wtf/tutorials/2022/06/26/credentials.html)**, please do that first.
2. Make a **[Branch](https://git-scm.com/docs/git-branch)** on your local device:
```(git)
git checkout -b dev/MM
```
  + _Note 3:_ replace `MM` with your initials.
3. Now you can make some changes to the code. If you are like me, then maybe you have already pulled the code, you got excited and made some changes trying to figure out how it works, and only now you are reading this document. That's okay, thanks for reading this document! Here's what to do if you made changes on `main` without switching to a side branch first:
  ```(git)
  
  ```

_{{ page.date | date: "%Y-%m-%d"}}: WIP (sorry)_
