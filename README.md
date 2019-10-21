# Zero to git

## What I'm going to talk about in this Tutorial
- What is version control
- Why do we need it?
- Local git workflow
- Remote repositories
- Branches, merging them and pull requests

## What is version control.
google's generic dictionary defines it as:
"the task of keeping a software system consisting of many versions and configurations well organized."

## That looked like vague Russian! What is actually? Why do we need it?
- What is it?
    -  version control is normally a software program that tells you exactly what version of your software you are running.
- Do you remember group projects before google docs? where we would send our final report to the group that was named: stupid_project-1.0-FINAL.docx
    - Do you remember when steve and anne (who doesn't do work) would send it back to you with the file names (because they didn't finish their work):
        - stupid_project-1.1-FINAL.docx
        - stupid_project-1.0b-FINAL.docx
    - Then you took the time to see what they did and put into a new version that you called
        - stupid_project-2.0-FINAL.docx
    - And the process would repeat.
    - Version control is a program attempting to solve that problem.

- Why do we need it?
    - We want everyone to agree on the current version so we won't have to deal with the above problem.
    - As well we don't want to delete our brilliant unicorn code!
    - Another reason why we need it is that it gives us a record of everything that's been written in our software project.
    - As well it allows us to have a "Source of Truth" which is the version we all agree on.


## Okay I know what it is... How do we get started doing this? Are we going to use something to do this?
- We're going to use a program called GIT
- Git is used by a lot of software languages and programs to do version control, not only python.
    - This is just a great way to manage the version of files.

    - Honestly most of the large companies would be using GIT nowadays.

## How does this relate to fortunato?
- Since you're a unicorn with fortunato you're going to be ramping up your team so we want to ensure that steve and anne don't send you shoddy versions.


## Now that we kind of know what it does, let's get it installed!

- How to install Git!
- For windows and mac installation, please refer to Atlassian's guide:
https://www.atlassian.com/git/tutorials/install-git
- Since our servers will be using linux we're also going to use it as our development environment (Your VM)
- Installing on (Ubuntu) linux
    - Open a terminal!
    - type in the following commands:
```
sudo apt update
sudo apt install git
```
Note: update updates your packages
install just installs git!

## Now I have Git! How does one Git? Is dan a Git? (yes to the last question)
- Here's how we're going to tackle the above questions.
- Local workflow (useful for working alone!)
    - initialize a "folder" to track
    - talk about what is the staging area.
- Commands we use for "local" Git
    - `git init`
    - `git add <file-name-here>`
    - `git commit -m "<short description of what you did>"`
- Remote workflow (adding on to the above)
    - github! (and other stuff)
- Commands we'll learn for dealing with remote repositories (what code is called when it's remote.)
    - `git remote add origin`
    - `git push -u origin master`
    - `git fetch`
    - `git pull`
    - `git branch (this is tough)`
    - `git merge`

## Local workflow (which means git only on your computer.)
- here we're going to learn the meat of the idea of git.
- what we'll learn
    - some terminology
    - `git init`
    - `git status`
    - `git add <file_name>`
    - `git commit`
    - `git diff`
    - review and do it again!

## things you need to know and understand.
- untracked files
    - files that aren't being tracked at all (haven't been added to the staging area whatsoever)
- working directory
    - this is where you work!
- staging area
    - you can think of this as the "ready to commit area"
    - another way you can think of this is as a "pre save area"
- commit log
    - These are the checkpoints of your saved stuff

## Commands for Local workflow!
- How to call them.
- What they do.
- When to use it!

## Git init
- think of this as "git initialize"
- When to use it?
    - When starting a project that you haven't used version control on.
- What does this do?
    - creates a .git folder in your "working directory" and keeps all of the internal tracking data for git.
- Let's do something with it! 
    - Create a folder (`mkdir ready-to-git`)
    - Go into that folder (`cd ready-to-git`)
    - `git init`

## Git status
- This is your best friend! Use this Constantly.
- What does this do?
    - Give you information about your repository
    - What branch you're on, what commit you're on (coming into)
- When to use this?
    - All the time!
    - Any time you're confused, or your want to see changes, or you're breathing and not thinking.
- Let's do something with it!
    - Make a file (nano README.md) don't add anything to it.
    - `git status`
        - should show the file that's it.
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_status.png)
## Git add \<file-name>
- Adding stuff to the staging (ready to be committed) area!
- What does this do?
    - this adds the changes you've made to begin to be tracked to the "ready to be committed " staging area.
    - moves untracked (new) files to the staging area to be tracked!
- When to use it?
    - When you're ready to commit your changes, or you want to track your changes from the staging area.
    - When you've created a new file and you want to track the changes from nothing.

- Note,
    - if you've already "git add"[ed] a file, additional changes will be in your working directory and not the staging area!
    - if you want to remove files from the "ready to be committed area" use "git reset"

- Let's do something with it!
    - Add the file into the staging area! (`git add README.md`)
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_add.png)

## Git commit -m "\<What you did in this chunk stuff>"
- Save stuff (ready to be committed) a "checkpoint"
- What does this do?
    - Saves your staged (ready to be committed) changes
    - Gives it a hash (just a reference so that you can go back in time to that commit when you need to.)
- When to use it?
    - When you're ready to save stuff!

- Note:
    - Good practice is to do one thing per commit. How do you know this? If you use the word "and" in your commit message.

- Let's Do Something with It!
    - `git status`
        - you should see README.md in the "Changes to be committed" area!
    - `git commit -m "Initial Commit"`
    - `git status`
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_commit.png)

## Git log
- shows your saved history!
- What does this do?
    - shows all of your commits.
    - HEAD shows you where you are on the changes.
- When to use it?
    - When you don't know if you have the most current commit
    - When you want to see your saved history!

- Let's do something with it!
    - `git log` in the terminal
    - you should see your commit!
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_log.png)

## Git Diff <maybe a file?>
- What does this do.
    - This shows the difference from your staging (ready to be committed area) and if you don't have that it'll show the differences from your last commit ("save")

- When should you use this?
    - When you're ready to put something into the staging (ready to be committed area)
    - this will show

- Let's do something with it!
    - open your README.md
    - add the following lines.
```
        ## Ready To Git!
        Just a project to learn how to use git!

        # Intro
        TODO!
```
    - Save the file.
    - write `git diff` in the terminal.
    - now you should see the changes!
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_diff.png)

## Local workflow review 
- Let's save these changes through the process we've created.
    (Remember to git status often)
1. Let's see what's up
    - `git status`
2. Let's add this to the staging (ready to be commited area)
    - `git add README.md`
3. Let's commit (save to the log)
    - `git commit -m "Add titles to README"`
4. See your commit (save) log
    - `git log`
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_local_workflow_review.png)

## Remote Workflow!
- we want to work with other people on fortunato!
- What we'll learn
    - Where are these remote things? what can I use?
    - Setting up a remote repo with github.
    - `git remote add <name of remote> <url to remote>`
    - `git push <name of remote>`


## Remote Repositories
- They're not on our computer. They should be the "source of truth" of your code.
- Github, Gitlab, and Bitbucket are all awesome remote providers.
- Don't host it yourself unless you need to. It's a pain.
- Sign up for github! as we'll be using this.
- If you want private repositories, go to bitbucket (that's what I use but there are a lot more awesome ones.)

## Setting up a remote repository with github.
- Sign in to github (once you've signed up)
    - Please remember your password.
    - Please make it the same as your banking password and send it to me with your mothers maiden name.
- Click "Create new Repository" and enter the information as it looks like in the picture.
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_create_remote_github_repo.png)
- Once you have created it, it gives you instructions. We're going to take a look at the url.
    - Mine looks like this: `https://github.com/dgmouris/ready-to-git.git`
    - we're going to use https, because ssh is confusing to start with.

## git remote add \<name of remote> \<url to remote>
- What does this do?
    - This allows us to "connect" our current repo, which we've been working on locally, to our github.
- When to use it?
    - when connecting to a remote repo (or fork will not cover that today.)
- Let's do something with it!
    - `git remote add origin https://github.com/dgmouris/ready-to-git.git`
    - to see our remotes we can use `git remote -v` this shows
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_add_remote_repo.png)

## git push \<name of remote>
- What does this do?
    - Allows us to "upload our changes" to the remote repository.
- When to use it?
    - When you want your changes pushed up to be reviewed (will talk about this later *look at branches and merges.)
    - When you just want to push your changes up.
- Let's do something with it!
    - git push origin master
    - Go to the repository on github and you should see your code there!
        - go to your github home page.
        - click on your repo name (mine is ready-to-git)
    - Congrats! That's pretty cool! Right? I'm writing this alone and looking for acknowledgement that isn't there...
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_push.png)

## git fetch
- What does this do?
    - Allows us to "download"
- When to use this?
    - When someone else has added something to the repository that you don't have locally.
- Let's do this!
    - `git fetch`
    - We're not going to see anything different.
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_fetch.png)

## git pull
- What does this do?
    - Git fetch doesn't do all the work. You have to move your head forward to the most recent commit!
- When to use this?
    - When you do a git fetch to get yourself to the most recent commit
- Let's do something with it!
    - `git fetch` (because you're downloading your stuff.)
    - `git log` (shows your commits)
    - `git pull` (moves it forward!)
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_pull.png)

## Working with others (and your past self.)
- Since you'll be deploying and using versions of your code, a good way to add new code to a repository is by making a branch.
- branches are good ways to kind of segment your work (feature, hotfix)
- This is one of the more complex parts of git, so if you have questions please reach out afterwards and it's okay if you don't get it yet.

## git branch \<branch-name>
- You always want your master "branch" to be stable! (normally production)
- This is a way to separate old code from new code and then get it back in.
- What does this do?
    - this creates a new commit (save) section
    - you can view all of your branches when you type -a instead of a branch name
- When to use this?
    - When you're doing anything new, like creating a new feature or something.
    - When you're fixing something!

## git checkout \<branch name>
- What does this do?
    - this allows you to go into your newly created lane! 
- When to use this?
    - When we have to change what section of code we're working on.

- Let's do something! (draw on the board.)
    - If you look at your remote repository our title sizes are wrong!
    - `git branch`
        - shows our branches
    - `git branch fix-title-sizes`
        - this creates the branch
    - `git branch`
        - this lists our new created branch!
    - `git checkout fix-title-sizes`
        - this puts you on the new branch!
    - `git branch`
        - shows that you're on the new branch!
    - `git log`
        - shows that you have kept all of the changes from the previous branch because you have branched off from the last commit checkpoint!
        Note:
        - you can shortcut creating a branch by adding the -b parameter before the branch name.
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_branch_checkout.png)

## Let's create the change, commit it, and push it up! Like you would on a team! 
- this is basically a review of everything except merging which we'll talk about next!
- Let's do it!
    - `git status`
        - make sure you're one the right branch!
    - open your README.md and make the change
        ```
        # Ready To Git!
        Just a project to learn how to use git!

        ## Intro
        TODO!
        ```
    - `git diff`
        - shows your changes!
    - `git add README.md`
        - add it to the ready to be committed area!
    - `git commit -m "Fix title sizing"`
        - commit it to your save log!
    - `git log!`
        - take a look at your save log!
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_do_the_full_process.png)

## git merge / pull (merge) requests.
- this is a really important concept so I saved the best for last!
- What does this do?
    - this puts all of the commits that you did in your branch and puts them back into the mainline!
    - you can do this locally by doing `git merge <other branch>` when you're on the branch that you want all the changes merged on.
    - show the diagram!
    - we're going to do this on Github! This is exciting!
- When to use this?
    - when you're done with the fix, or feature, and it's done being reviewed (you'll see soon)
- Let's do it! 
    - `git push --set-upstream origin fix-title-sizes`
    - go to github.
    - click on compare and pull request.
- Here you'll be able to see your changes and deletions!
- Click on create pull request!
- Here you can do a lot of cool stuff:
    - like add reviewers
    - assign people, so that people can help you our with your code!
    - Add comments to help people out!
- press git merge and this will put all of your changes into the master branch!
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_push_a_new_branch.png) 
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_create_pull_request_on_github.png) 
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_create_pull_request_on_github_1.png)

## One last time let's get our changes from git
- `git checkout master`
- `git log`
    - we don't have the most recent change
- `git fetch`
    - download the changes
- `git log`
    - we're behind the current change! our head is not on the most current commit!
- `git pull`
    - we'll put it up!
- `git log`
    - we're here!
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_final_review_1.png)
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_final_review_2.png)
![alt text](https://github.com/dgmouris/zero_to_git/blob/master/images/how_to_git_final_review_3.png)

## Random tidbits and some stuff we're not covering.
- merge conflicts
    - this is one of the hardest things in git, we're not going to go over it today.
    - if you've come into one of these we have a lot of people here that can help you out with it!
- gitignore.
    - this just adds patterns for files that you don't want tracked.
    - A good way to not check-in files that are sensitive.
- git hooks.
    - are programs/scripts that are executed on a particular event, normally: merge, commit, push.
    - they are a great way to ensure that your tests all pass before you make a commit.
- forks!
    - this is a relatively complex topic that we're not going to cover today.
    - You'll need to learn this if you want to contribute to open source.
    - it's kind of like next level branching for repositories so more people can work together!
- git rebase
    - fast forwarding branches on commits.

## Thank you!
We've covered a lot! In the interest of time, please reach out to me afterwards as Andrew has another presentation to help us with fortunato!

