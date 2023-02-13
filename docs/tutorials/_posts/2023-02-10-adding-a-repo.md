---
layout: post-toc
title: Adding a Repo
about: How to initially set up an NML GitHub repository.
tags: git documentation instructions
hidden: false
lastUpdated: 2023-02-10
category: tutorials
---

## Check you are in the right tutorial first ## 
If you're completely new to `git`, or if you've used it before but don't know what setting up `ssh` credentials means, please **[start here instead](https://code.nml.wtf/tutorials/2022/06/26/credentials.html)**. 

## Creating a GitHub repo ##
Basically there are a couple of places you should set up links to your repo, so that in the future we can find it and it just helps everything stay a little more organized. My typical process goes:
1. Create the GitHub remote repository before anything else. 
  + Navigate to the [GitHub NML homepage](https://github.com/Neuro-Mechatronics-Interfaces) in your web browser. 
    - Notice all the general documentation here. This all exists in the `README` for the [`.github`](https://github.com/Neuro-Mechatronics-Interfaces/.github/tree/main/profile#readme) repository. We will come back to this.
  + Click the [`Repositories` tab](https://github.com/orgs/Neuro-Mechatronics-Interfaces/repositories).
  + Click the green `New repository` button at the top-right (as of this writing) above the list of repos. You can also search for repos here (and in the next steps you can make it easier to search your repo by adding a few things). 
  + Now, create your repository. Generally it is easiest to create a `public` repository but if you're self-conscious and don't think you'll be collaborating with others (or you have top-secret super-awesome code and want to limit who can get to it) then make your repo `private`. 
    - I typically do not initialize with README, .gitignore, or License at this stage but feel free to do whatever you want. If you leave it blank here, conveniently, GitHub will prompt you with how to initialize the repository locally so that is usually what I do.
    - For naming, the one convention I've been using is for repos that will be packages in MATLAB (folders starting with `+`), in the `Description (optional)` field I make sure to include what that package name should be (since the GitHub convention won't allow the repo to be named starting with `+` symbol). I also like to name those `matlab_package__<name>` to make it clear that this is a package to be added as a submodule.
2. Great, now you have a GitHub remote repository on the NML organization home page and you can link to it. Before we forget that link, please copy the home page link and go back to that [`README`](https://github.com/Neuro-Mechatronics-Interfaces/.github/tree/main/profile#readme) I just mentioned. **Please**, quickly add a link and short description of your repo in a relevant section based on how the `README` looks (I trust you will figure out where to put it that's relevant, feel free to create new headers or whatever you want). You can do this in a couple of ways.
    - (Maybe easiest). Since you are on the page (from the link above), just go ahead and click the little pencil icon at the top right of the `README.md` section. This will allow you to edit the file directly through the web interface. The file is in markdown syntax, and if you don't know how to use that it's very easy so just [check here for conventions](https://www.markdownguide.org/basic-syntax/). 
	- (The way I do it). I have a local version of the `.github` repo cloned. If you do it this way, **always fetch from the remote first and make sure your `main` is current before you start making changes!!!** Then when you are done making changes on your local version of `README.md` (the one in the `profile` folder), you will use `git add` to stage, `git commit` to commit, and `git push` to push your changes back to the remote. If those sound foreign, please check the tutorial on [how to contribute](https://code.nml.wtf/tutorials/2022/06/25/contributing.html). 
3. Now, clone or initialize your local version of the repository you've created on the NML GitHub organization, and go to the local version of the repository you've just created. Before you do any coding or anything else, either create `README.md` at the top level of your local repository, or open up the `README.md` that was initialized from GitHub. **Please fill this out with a little more information regarding what your repository is and how you plan to structure it, etc.** Doing it now will save you headaches later, and can also help you plan and structure how you will set up the code project and organization. So just take a little time and thought at this stage and write it out like you are reminding future you one year from now that it's okay they forgot everything because here is how it works.  

So yeah, that's basically it and it's really not a very cumbersome process. Once you see how easy it is, and the major convenience of using GitHub to organize and distribute project code, I suspect you will create more repos too.  

## Advanced: add WTF documentation ##
This is not really advanced, just extra. In the same `.github` repo that you may have cloned earlier (or via the NML GitHub organization web interface), you can go into the [`docs` folder](https://github.com/Neuro-Mechatronics-Interfaces/.github/tree/main/docs) (located at the repository root level). You will notice that this contains all the files used to generate this `WTF` website. So, let's say you have created a repo for processing EMG, then what would be super cool of you would be to go into the `examples/_posts` and copy one of the existing `.md` files, then mimic the syntax of that file to create your own `examples` post. Note that the IEEE-8601 format `YYYY-MM-DD` is required at the start of the filename, since that is used by `jekyll` when building the web application to create the link names for the generated html.  

If you add any posts (`examples`, `sops`, or `tutorials`) to the `WTF` page in this way Max will find you and buy you a beer (or boba, or whatever, basically he owes you one). 

### Wait, examples, sops, and tutorials? ###
Yes, that's right. The `WTF` documentation is broken down into these three categories. "But Max, what goes where?" you ask...

#### Examples ####
As mentioned above, this would be where you show off how awesome you are at doing some kind of coding. I don't know maybe you want to brag about the amazing hand gestures you created in Blender? That really sick new physics collider for your Unity haptic integration module?? A parameters interface you wrote in Python??? Yeah, all of that stuff can go in Examples.

#### Tutorials ####
But Max, isn't a Tutorial just a glorified example? Yes, yes it is. The difference in this case is the `WTF` Tutorial is more general, so it should be things like I don't know, "how do I add a repository to the GitHub?" 

#### SOPS ####
This is a bit of a misnomer but it's in the spirit of "we're a lab." These are similar to tutorials, but it's more like, "please do it this way (or you will cause problems for everyone)" and less of "consider doing it this way."

### But what about the API I wrote for <thing>? ###  
Sorry, that doesn't go here. If you'd like to add your code to the GitHub organization, please feel free to do so (and contact Max with your GitHub account info if you need to be added as an administrator on the GitHub page). The relevant API documentation for <thing> should go in the `README.md` at the root level of your code repo. If you have a real API (i.e. the documentation requires more than one `README.md` file in the project root), you should consider adding a `wiki` to your repo using the convenient `Wiki` tab associated to every repository on GitHub, then linking to that wiki from the `README.md` (which will populate the landing page of your GitHub code repo any time somebody navigates there via web browser). If you've added these things to your project and still would like to add more documentation (bless your heart), please consider adding to the `Examples` section using the same post format as other files there, as learning code by example is often an effective way of sharing the relevant "how to" enough to help someone else get their experiments up and running.   