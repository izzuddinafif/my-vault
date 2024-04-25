#git #gitlab 

[YouTube Video](https://www.youtube.com/watch?v=NK2BrGpA9wI&ab_channel=CameronMcKenzie)
# What is Git and GitLab?
Git is a distributed version control system that track changes in any set of computer files[^1] . GitLab is basically git that is hosted on servers in the cloud, but it extends the features of git with other features,  such as branch protections, workflows, etc.
## Basic Git commands learned:
In the first part of the video, I learned about git and its commands. Here are some basic commands:

```sh
git clone https://blabla.com/username/repo.git # clone a remote repository
git remote add remote_name(usually origin) remote_url # add a remote repo
git add . # add all files in working directory to staging phase to track their changes
git add filename # stage changes made to a file
git commit -m "commit message" # comm it staged changes 
git commit -a # commit all unstaged changes, won't work on new files
git pull # pull changes from repo
git push # push commits to repo
git fetch # fetch changes from repo
git merge # merge changes after fetching
git status # show changes
git log --oneline # show the log in one line
git checkout somecommithash # checkout to a previous commit in a detached HEAD state
git log --all --decorate --oneline --graph # git "log a dog"
```

And I also learned about some more advanced commands:

```sh
git reflog # simpler full log
git reset --hard commithash # remove all files and changes after a selected commit
git revert commithash # undo changes made by selected previous commit by creating a new commit that does the opposite of the selected commit
git cherry-pick commithash # pick a commit from one branch and apply it to other branch or same branch (re-applying prevous change)
```

## Isolated Development/Branching with Git and GitLab
One of the advantages of git and gitlab is that people can experiment and collaborate on something independently using the concept of branching. It allows people to do whatever they want to a repo and request to merge it to main repo (pull request), or just delete it if they want and nobody is the wiser.  We can do it both in git or gitlab. Remember that you ==**can't create a new branch before having any commits.**==

### Merge
Merging is the process used in Git to integrate changes from one branch into another. It combines the histories of the merged branches, preserving the context of the branch as a separate entity in the history. Here are some essential commands for Merging in git:

```sh
git switch -c branchname # create a branch at current (condition of) repo and switch to it
git branch branchname # create a new branch 
git merge branchname # merge the "branchname" branch into current branch
git branch -d branchname # --delete a branch
```

In gitlab, you usuallly would create a merge request (or pull request in github) to inform admin about your new branch that you want to merge into main branch. After inspection by admin, they can either accept or deny your merge request.

### Rebase
**Rebase** is a command in Git that allows you to take all the changes that were committed on one branch and replay them on a different base, typically the current head of another branch. This process is used to adjust the point at which a branch diverges from another branch, essentially "moving" the entire branch to start from a new base. so its basically creating a whole new commit history with elements of both branches present in it.


```sh
git rebase
```

You can rebase a merge request from the GitLab UI, but there are some prerequisites
- There are no merge conflicts
- You have the Developer role for the source project
- The fork allows commits from members of the upstream project 

### Squash
Squashing" refers to the process of combining multiple commits into one or a few cohesive commits. This technique is particularly useful in maintaining a clean, understandable commit history, especially before merging a feature branch into the main branch. Squashing is commonly performed as part of an interactive rebase, but can also be done during a merge, particularly with a pull request.

```sh
git rebase -i selectedcommithash # open interactive window to squash/pick commits occured after the selected commit
```

### Resolving merge conflict
A merge conflict in Git occurs when two branches have changed the same part of the same file, and then those branches are merged together. Git is unable to automatically resolve these changes, and the conflict must be manually resolved by the user.

### Stash
`git stash` is a powerful feature in Git that allows you to temporarily save changes that you've made to your working directory without having to commit them. This is particularly useful when you need to quickly switch contexts and work on something else, but you're not ready to make a commit. 

```sh
git stash push
git stash list
git stash apply # apply change from the stash without removing it, not like pop
git stash pop
git stash clear
```

[^1]: https://en.wikipedia.org/wiki/Git