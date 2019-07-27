Theme: Zurich
autoscale: true
footer: Copyright Ⓒ Eric Jiang 2018 - 2019 | Adapated from "Gitting Started at Hackathons" tech talk

## Introduction to Git

### Eric Jiang (@lorderikir)


---

# Hi, I'm **Eric Jiang** 👋 <br/><br/>

- Currently Software Engineer, Digital Transformation, eSolutions.
- I founded MonPlan 
- I also maintain other apps like GeckoDM and MARIE.js
- Also have worked at Localz too where I worked on the React Native Core App


---

# So, I love writing code & also love working in teams 

_But what if there was a way that I could remember how the code look liked throughout its entire development lifecycle, for example if something went wrong and I want to go back to a previous version?_

In comes [Git](https://git-scm.com/)

---

# First of all, what is Git?

![right 50%](https://i.redd.it/05b6u19pseoz.png)


---

# Git

> Git is a version control system for tracking changes in computer files and coordinating work on those files among multiple people
> -- [Git-SCM Website](https://git-scm.com/)

_Also if you want to go into Software Development at some companies, you are bound to use Git or some kind of version control like SVN/Mecurial_

---

# How Git Works

![inline](https://tudip.com/wp-content/uploads/2017/12/GitWorkflow.png)



---

# Some Terminology

## **Repository** 
> The Git repository is stored in the same directory as the project itself, in a subdirectory called .git. Note differences from central-repository systems like CVS or Subversion:

* There is only one .git directory, in the root directory of the project.
* The repository is stored in files alongside the project. There is no central server repository.



---
# Some Terminology

## **Commit** 
> The git commit command captures a snapshot of the project's currently staged changes

* A reference to some changes to a file (removals or deletitions in files, creation/moving/deletition of files)

- Imagine the commit as a _save_ of the changes to the file(s)

- A commit also contains the Commit Title/Name, and Commit Description


---
# Some Terminology

## **Branches** 
> A branch in Git is simply a lightweight movable pointer to one of these commits. The default branch name in Git is master

![inline](https://git-scm.com/figures/18333fig0304-tn.png)



---

# Git File Lifecycle

![inline](https://git-scm.com/figures/18333fig0201-tn.png)



---
# Some Basic Commands

| Command      | Description                            |
| ------------ | -------------------------------------- |
| `git clone`  | Clones a repository locally            |
| `git add`    | Stages changes to file(s) for a commit |
| `git commit` | Creates a commit (set of changes)      |
| `git push`   | Push changes to the hosted repo        |



---

# Using Git within teams

Well, working with teams 👪 may be hard. There are generally two ways you can work off a repository.

* Using Branches
* Using Forks

- Open Source projects tend to use Forks, while:
- a lot of companies internally uses what is known as GitFlow which uses branches!

---

# Use Branches 🌳 for Versioning Control (GitFlow)

1.  Make a branch with the feature, bug, hotfix you are working on.
2.  Every time you commit and push up
3.  Make a Pull Request
4.  Merge the pull request

One of the best workflows is known as _GitFlow_

---

# In GitFlow, our Branches follow some naming conventions...

* `master`: branch is the key branch, typically for our production/public-facing version
* `develop`: _unstable_, most of the PRs should go here
* `staging`: this branch is occassionally but not always used, this matches our QA/Testing environment
* `feature/\*`, `fix/\*`, etc.: are 'for purpose' branches, these branches are for development

_This slide has been adapted from my [CI-CD talk](https://github.com/lorderikir/cicd-techtalk)_


---

# So we know that development is done incrementally



---

# Imagine we using Git within our practices

And one of my team-mates, has found a bug within one of our buttons.



---

# So, he creates a new branch to fix the bug

![inline](assets/git/step1.png)

```shell
# update our develop branch
git checkout develop
git pull
# we create a new branch
git branch fix/contact-button
# we make the new branch the new working branch
git checkout fix/contact-button
```



---
# He fixes the code and stages the change in commits

![inline](assets/git/step2.png)

```
git add .
git commit -m "new commit"
git push
```



---

# He fixes the code and stages the change in commits

![inline](assets/git/step2a.png)

```
git add .
git commit -m "new commit"
git push
```



---

# He then makes a PR into my develop or master branch

![inline](assets/git/step3.png)

## Where we discuss his proposed changes



---

![inline](assets/pullrequest.png)



---

# We then merge the Changes

![inline](assets/git/step4.png)

---

# This would also work for...

* Upgrades to the codebase
* Refactoring our legacy code
* Upgrading frameworks to newer versions



---

# Why is using GitFlow important?

* We seperate production code and our 'work-in-progress' (WIP) code.
* We have a clearer understanding of what each developer is working on
* We can branch off WIP branches and merge changes in
* Relatively easier (not always) to fix merge conflicts
* Some CI/CD tools only run off branches (not PRs)
* We can set our CI/CD to deployment so that it can deploy off branches (i.e. `develop` to _dev_, `master` to _staging_ or _qat_ and `deploy` to _prod_)



---

# Key notes 🗒️

* Version Control over Development is really important as it helps keep 'backups' and you can see the changes
  * You can always see who pushed out the broken code with `git blame` 😈
* Git is always useful as you can always revert broken code or changes
* Branching and forking is basically the same,
  * when working we typically use branches over forks as we can solve merge conflicts more easily (and locally)



---

# Please DO NOT ever `git push --force`

![inline](assets/gitpushforcememe.png)



---

# Key things to look 🔭 out for.

* Merge conflicts are always the hardest part
* Be careful of `git merge` and `git rebase` commands. Always `merge` don't `rebase`
  * This is because rebase always applies your changes last (assumes you are always correct)
  * When merging between branches and fixing conflicts always work with a team-mate



---

![inline](http://i.bittwiddlers.org/LD6.jpg)



---

# Got it? `¯\_(ツ)_/¯`

## So now let's try and fork some branches instead 

1. Go to [https://github.com](https://github.com) to create an account if you don't have one
2. Go to [https://github.com/lorderikir/git-example](https://github.com/lorderikir/git-example) to play around


---

## Step 1 - Create a Fork of this Repository under your GitHub Account


![inline](https://camo.githubusercontent.com/134a4a65bac8799402bdda836a69656511cefd18/68747470733a2f2f63646e2d7374642e64707263646e2e6e65742f66696c65732f6163635f3630393938372f444c48447a4f)


---
## Step 2 - Edit the file in your fork by clicking the pencil icon and add your name to the list

![inline](https://camo.githubusercontent.com/ae4eabdf698ebee96369c449f54e30ca785f1a73/68747470733a2f2f63646e2d7374642e64707263646e2e6e65742f66696c65732f6163635f3630393938372f6b694f545958)

---

## Step 3 - Edit the file and commit your changes

![inline](https://camo.githubusercontent.com/99d779e5b9d35a7e3bd59ae6fa77ea4fb609d9c9/68747470733a2f2f63646e2d7374642e64707263646e2e6e65742f66696c65732f6163635f3630393938372f4c6c32457547)

---


## Step 4 - Submit a Pull Request (PR)

![inline](https://camo.githubusercontent.com/05abe83f12928e50f0ee894011e3ebde02dbf367/68747470733a2f2f63646e2d7374642e64707263646e2e6e65742f66696c65732f6163635f3630393938372f737478545932)


---

## So merge conflicts, what are they and how do we resolve them?

---

# Merge Conflicts
- essentially, when we are merging changes to code and _Git_ sees different changes on the **same** file
- this most likely happens when someone already committed to the branch from earlier on, and hasn't applied their changes on to the branch that we are using
- therefore, the Git history (of our changes) 'diverges' as each commit is a different hash

---

# Here's one of the best and easiest ways to resolve a conflict

1. We go to the target branch and pull down the latest changes
2. We then 'checkout' our current working branch and create a new branch off the working branch 
3. We then attempt to merge our target branch into our new branch
4. Resolve Conflicts (by choosing the right pieces of code you want), VSCode makes this really easier
5. Merge the new branch into our current branch
6. Merge the current branch into the target branch


---

# This is the current state of the branches

![inline](https://i.imgur.com/7ou081C.png)



---
We go to the target branch and pull down the latest changes

[.code-highlight: 1,2]
```
git checkout develop
git pull
git checkout feature/awesome-feature
git checkout mergconf/feat-develop
# ...
```

![inline](https://i.imgur.com/jD0ioV9.png)



---
We then 'checkout' our current working branch and create a new branch off the working branch 

[.code-highlight: 3]
```
git pull
git checkout feature/awesome-feature
git checkout mergconf/feat-develop
git merge develop
# ...
```

![inline](https://i.imgur.com/s1rWJu4.png)



---

We then attempt to merge our target branch into our new branch

[.code-highlight: 3]
```
git pull
git checkout feature/awesome-feature
git checkout mergconf/feat-develop
git merge develop
# ...
```
![inline](https://i.imgur.com/BN2poNJ.png)



---

Resolve Conflicts (by choosing the right pieces of code you want), VSCode makes this really easier

![inline](https://code.visualstudio.com/assets/docs/editor/versioncontrol/merge-conflict.png)


---

Here's how the state of the branches are:

![inline](https://i.imgur.com/qDC4szs.png)



---

Merge the new branch into our current branch


[.code-highlight: 1,2]
```
git checkout feature/awesome-feature #get to current working branch
git merge mergconf/feat-develop
git push # push to repo
```

![inline](https://i.imgur.com/a8TmzRe.png)



---

Push changes to repository

[.code-highlight: 3]
```
git checkout feature/awesome-feature #get to current working branch
git merge mergconf/feat-develop
git push # push to repo
```

![inline](https://i.imgur.com/Prsy165.png)




---

# Our Conflicts would have been solved now! 🎆



---
# Questions? <br/><br/> 🤔 🎤 📣

---
# Thank You!!

You can follow me on my social accounts:
- Twitter: [@lorderikir](https://twitter.com/lorderikir)
- GitHub: [@lorderikir](https://github.com/lorderikir)
