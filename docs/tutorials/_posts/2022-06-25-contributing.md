---
layout: post
title: Contributing
about: How to contribute to an NML GitHub repository.
tags: git instructions
category: tutorials
---

## Check you are in the right tutorial first ## 
If you know about `git` and feel good about contributing, but you're not sure about contributing to _these_ repos because you're worried you will break something--**don't be scared!** If you're not breaking _some_ code then you are probably doing things  wrong anyways. If you follow these steps, you can learn by working with the code without worrying about breaking others' code. Also, if your first thought when looking at the code in `step 1` in the [example pull request](#example-pull-request) below, is _"where exactly do I enter this?"_ then please **[start here instead](https://code.nml.wtf/tutorials/2022/06/26/credentials.html)**. 

## Example Pull Request ##  
Let's say that you want to interact with the [`programming club`](#https://github.com/Neuro-Mechatronics-Interfaces/programming_club) repo to practice using `git`. Try the steps below:  

1. **[Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository#cloning-a-repository)** the `main` branch to your local device:
```(git)
git clone --recurse-submodules git@github.com:Neuro-Mechatronics-Interfaces/programming_club.git 
```
  + _Note:_ if you have not yet set up `git` and **[configured a credential manager](https://code.nml.wtf/tutorials/2022/06/26/credentials.html)**, please do that first.
2. Make a **[Branch](https://git-scm.com/docs/git-branch)** on your local device:
```(git)
cd programming_club # Only necessary if you aren't already in the repo you just cloned.
git checkout -b dev/MM # Replace dev/MM with dev/<YOUR INITIALS> to create your own branch
git status # This should tell you that you are on your new branch and that your local repo is current.
```
3. Now you can make some changes to the code. If you are like me, then maybe you have already pulled the code, you got excited and made some changes trying to figure out how it works, and only now you are reading this document. That's okay, thanks for reading this document! [Here's what to do if you made changes on `main` without switching to a side branch first](#help-i-made-changes-on-main-before-branching). If you didn't do that, good job, make some example changes by adding your own new text file with some contents by echoing text from the git terminal into the text file (this is just for demonstrative purposes).
```(git)
echo "*.asv" > .gitignore # (we do not care about version-control for MATLAB autosave files)
echo "My ignored contribution." > 000_Git_Practice/MM_test_ignored.asv # (replace MM with your initials)
echo "My awesome additions!" > 000_Git_Practice/MM_test_file.txt # (replace MM with your initials)
```
4. Now, check the status of your repo. You should see both `.gitignore` and your new `<INITIALS>_test_file.txt` in red, but not `<INITIALS>_test_ignored.asv`. The .gitignore file has been updated to ignore anything that ends with `.asv`, so `<INITIALS>_test_ignored.asv` does not appear.
```(git)
git status
```
5. Before we commit the changes to `.gitignore` and `.txt` file, we must first `stage` them. Do this using `add`. 
```(git)
git add .gitignore 000_Git_Practice/MM_test_file.txt # replace MM with your initials
```
6. Now when you check the status, the files should be listed in green.
```(git)
git status
```
7. You can now `commit` your changes, which allows you to `push` them to the remote. The pattern is always `add` > `commit` > `push`, with the final (optional) component (for collaborations) being to submit a `pull request` (we'll get to those things next). When you `commit`, it is good practice to include a short message describing the changes you've just made.  
```(git)
git commit -m "I made an awesome text file with real changes."
```
8. Now, when you check the status, you will notice that nothing is outstanding- you are "up-to-date" in terms of all changes being committed and registered with version-control. At this point, you could continue developing if you did not want to `push` to remote just yet (for example maybe this is an intermediate step and you just wanted to `commit` a small change in case you want to [revert to this commit](#help-i-committed-changes-i-do-not-want) later).
```(git)
git status # Should say "nothing to commit, working tree clean"
```
9. It is also good practice to `tag` your commits and annotate what the tags mean. Ideally, your tag should make use of the `semver` [versioning scheme](https://semver.org/). The `tag` is a good way to keep track of what the most-current "ID" of the code base _should_ be, since otherwise you have to refer to some weird string of seemingly arbitrary numbers and letters (the commit `hash`). Because this is an example tutorial that exists at a specific stage of the `programming_club` repository, your tag will depend on the latest sub-version of the `v1.1.x` repo tag. On the GitHub page, check the tags to find the latest tag starting with `v1.1`, and increment the patch version by 1 on your tag (i.e. the next tag after my `v1.1.0` should be `v1.1.1`; it is okay to use double-digits since these are treated like strings, so `v1.1.10` is after `v1.1.9`, for example). 
```(git)
git tag -a v1.1.0 -m "MM initial tag in version with semver tag-incrementing exercise."  # replace v1.1.0 with your tag, and replace MM
```
10. Push your changes to the corresponding origin branch. Note that you only need to link this branch the first time (when you have created it). All subsequent `push` should **not** include `-u` option, this is only to set the first one "upstream" in order to create that branch on the remote. Adding the `--tags` flag will also push the `tag` you've just created to the remote, so that others can see it.
```(git)
git push -u origin dev/MM --tags # replace MM with your initials
```
11. Now you are ready to issue a `pull request` on GitHub, which is probably one of the best features of having code on GitHub in my opinion. However, although `git` ships with `git request-pull`, misleadingly this is not actually the `pull request` that you want to use. I almost always make pull requests through the GitHub webpage just because I've found that to be easiest, but you can use `git` GUIs (I like [`GitKraken`](https://gitkraken.com), although I pay out-of-pocket for the professional version which might be required for the GitHub integrations--it still has lots of other good free features so I encourage others to check it out). You can also download and use tools like [`GitHub CLI`](https://cli.github.com).
We will look at a couple of ways of doing it in this tutorial.
  i. To use `GitHub CLI`, you should open a new terminal (**not git bash terminal**, but a standard windows command terminal should work) in the `programming_club` repo folder. Follow these steps: 
    + Login using the following command and following the web browser authentication via https: 
```(git)
gh auth login -h GitHub.com
``` 
	+ Replacing `MM` where relevant, create your pull request into `main` and request Max (`m053m716`) as the reviewer.
```(git)
gh pr create --title "MM pull request" --body "This used GitHub CLI" --base main --reviewer m053m716
```
  ii. Use the GitHub web interface directly, by navigating to the [GitHub org repo web page](https://github.com/Neuro-Mechatronics-Interfaces/programming_club) (log in), then click the `Pull requests` link near the top left (it's between links for `Issues` and `Actions`). Click the green `New Pull Request` button at the top right, then fill in the relevant fields (you will submit a pull request from `dev/<INITIALS>` into `main`, and optionally request `m053m716` or whomever you want to ping as a reviewer). You can add more detailed comments and formatting to the pull request in this interface using markdown syntax. 
12. Now you wait. In a "real" scenario, the reviewer might request you to make some changes to your code once they review the code, or they might just pull and merge it. You can configure how/whether GitHub will notify you of this in your account settings. Also, if you set up your own repos for your own collaborations, you can set the permissions so that it's a requirement (or not needed) for a third-party reviewer to approve the pull request before it goes into `main` (or whatever branch you want). 
  + I wouldn't go too crazy with this. Keep it simple. One side-branch per collaborator where they develop, and everyone always `rebases` from `main`...that leads to the next point..
13. Hopefully the `pull request` process lets you see why it is important to try and keep your side branches current from `main`, so that you are always submitting a relatively recent feature request to be pulled back into `main`. Otherwise what can happen is you have some old stale feature branch you were going to work on last summer and forgot about, then you finally got back to it but by now `main` has gone 40 commits ahead and you have no idea how to reconcile all these changes. Rather than create a huge headache for the reviewer, it is the better thing to do this part yourself, so go through the pain of `rebase` to get current with the most-recent `main`, and then submit your pull request. 
  + Wondering about `rebase`? Check out the [`git practice`](https://github.com/Neuro-Mechatronics-Interfaces/programming_club/tree/main/000_Git_Practice) session from programming club to get an idea of why `rebase` is helpful. You can read more about `rebase` in the [`git-scm`](https://git-scm.com/book/en/v2/Git-Branching-Rebasing) documentation. 
  + Because of how important this can be, and how confusing multi-person collaborations can get if this practice is *not* followed, this is the **primary reason why I recommend using a graphical tool like GitKraken when you try to rebase, rather than doing it from the command line**. This is because `rebase` typically goes hand-in-hand with `merge conflicts` which means you will want some kind of editor that can detect conflicts (`GitKraken` can do this, but other tools exist like [`kdiff3`](https://kdiff3.sourceforge.net/) which I have had success with in the past, and I think [`geanie`](https://www.geany.org/) can also do `diff` operations). 

## Common Mistakes ##
Below are some mistakes that I tend too make more frequently than I'd like, so I often find myself hunting down the syntax for some of these commands.  

### Help I made changes on main before branching ###
If you haven't committed your changes yet, you can try this; otherwise, do **[this](#help-i-committed-changes-i-do-not-want)** first.
```(git)
git stash
git checkout -b dev/MM
git stash pop
```
 * _Note:_ again, replace `dev/MM` with `dev/<your initials>`.   
As long as you have not already committed your changes to `main`, those steps should work. 

### Help I committed changes I do not want ###
I broke up the code blocks so you do not copy/paste everything at once, as you will have to input the correct commit hash. Step 1 is to get that hash, using the following command (works in Windows 10 bash, you'll have to look it up if on a different OS):  
```(git)
git rev-parse HEAD^1 | clip # this will put the current commit hash into your clipboard, change "1" if you want to go back more than 1 commit.
```
Step 2 is to use that commit ID to revert your changes. I followed the answer suggested on **[this StackOverflow thread](https://stackoverflow.com/a/21718540/15434437)**, where there is more information in case this doesn't work for you (it's suggested that if you need to revert after a commit involving `merge` that this will cause an error and you'll have to do it a different way).
```(git)
git revert --no-commit 0766c053..HEAD
```
Make sure you paste the value from your clipboard where `0766c053` is in the example above.  