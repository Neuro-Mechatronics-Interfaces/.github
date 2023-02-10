---
layout: post-toc
title: Setup your SSH credentials
about: How to configure your credential manager for the NML GitHub.
tags: git instructions ssh
lastUpdated: 2022-06-26
category: tutorials
---

## 1. Install git ##
To contribute/use code from repositories on the NML GitHub organization, the easiest authentication strategy for use with `git` is to create an SSH key and associate it to your GitHub account. You will need to download `git` to do any of this; the necessary keygen (openSSH) tools will subsequently be available in `git bash` that comes with the `git` download.   

In Windows (versions <11) you should be able to start a `git bash` terminal in your repository folder (or where you want to clone the repo) by right-clicking and selecting `Git Bash Here` from the context menu. In Windows 11, you can do the same thing but have to click the `More Options...` context menu at the bottom and then you will see the `Git Bash Here` option.

## 2. SSH setup ##
Platform-specific instructions for generating SSH keys and starting the SSH-agent that will "remember" your credentials in subsequent `git bash` sessions are provided by GitHub **[here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)**. Follow all the steps in that guide first. **It is recommended to add a passphrase to the generated SSH key!**  

Next, you need to add the key to your GitHub account. Step-by-step instructions that are platform-specific are provided by GitHub **[here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)**. Follow all the steps in that guide to associate the public key to your GitHub account.  

Once you have completed these steps, you should be able to use `git` commands with this and other `Neuro-Mechatronics-Interfaces` organization repositories that you have access to via the `Weberlab` team.  

## 3. Setup local repo ##
With `git` installed and your `ssh` credentials ready, you should now be able to clone this repository. Navigate to where you want this repository to go (as a folder) right-click and click `Git Bash Here` then enter:  
```(git)
git clone --recurse-submodules git@github.com:Neuro-Mechatronics-Interfaces/NHP_Center_Out.git
```
If you set up a `passphrase` in the `SSH` step, then you should be prompted for that `passphrase` before it will clone. You will now see a folder called `NHP_Center_Out` inside the folder where you opened the `git bash` terminal. The `--recurse-submodules` option just adds in submodules that Max created so that if he updates code related to this project while working on a different project, he doesn't forget to update it here (or, can create branches to avoid breaking things here if there are conflicts in another version for a different project).  

To avoid overwriting code that others are working on, please create a side branch. Max already made some example side branch but basically the format is `dev/<initials>` (e.g. Jonathan commits on `dev/JS`). To create and use a side branch, in `git bash` use the following command (replacing `MM` with your initials): 
```(git)
git checkout -b dev/MM
```

Now, when you `git commit` and `git push` to the remote repository, you will avoid overwriting changes on `main`. This is useful for collaborative work to avoid destroying each others analysis pipelines for example. If you have a really cool change that you think everybody should have, use the tools on the web interface to submit a pull request from your side branch (`dev/<initials>`) into `main` and assign @m053m716 as a reviewer. Maybe also send Max an email--once he sees the pull request and approves it will be merged into `main` and then anyone using `main` can see what you've added. 

By convention, it is good practice before you start coding to use `git fetch` to see if there have been recent changes on `main`. If you notice changes, you will want to `rebase` onto `main` so that your side branch stems from the current version of `main`. If you get too far behind `main`, then you may be working with deprecated code so keep that in mind if you plan on using the code here for development. Also, if you are planning on actively contributing/developing code in this repo please just let Max know so he isn't constantly squashing/forcing pushes to `main` (which is basically just done to keep the commit structure tidy). Thanks!


