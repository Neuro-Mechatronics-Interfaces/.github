---
layout: post
title: Adding a Repo
about: How to initially set up an NML GitHub repository.
tags: git documentation instructions
category: tutorials
---

## Check you are in the right tutorial first ## 
If you know about `git` and feel good about contributing, but you're not sure about contributing to _these_ repos because you're worried you will break something--**don't be scared!** If you're not breaking _some_ code then you are probably doing things  wrong anyways. If you follow these steps, you can learn by working with the code without worrying about breaking others' code. Also, if your first thought when looking at the code in `step 1` is _"where exactly do I enter this?"_ then please **[start here instead](https://code.nml.wtf/tutorials/2022/06/26/credentials.html)**. 

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
