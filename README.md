# GitProLearning
 As a fresh starter in software development industry, I find it super helper to learn Git. And I found this incredibly helpful material online at [GitPro](https://git-scm.com/book/en/v2). I will only cover the very basics from chapter 1-3. The remaining parts will be referred when needed in work. I have summarized my personal experience in this medium post here [medium](https://jl4730.medium.com/git-101-to-new-users-from-creating-a-new-repo-to-push-275e42955d8a)
 
# Chapter 1 Getting Started
Git has three main states that your files can reside in: modified, staged, and committed:
- Modified means that you have changed the file but have not committed it to your database yet.
- Staged means that you have marked a modified file in its current version to go into your nextcommit snapshot.
- Committed means that the data is safely stored in your local database.

# Chapter 2 Git Basics
Common flow:
```
cd /Users/user/my_project
git clone https://xxxxxxxxxxxxxxxxxxxx
git add what's changed
git commit -m 'Initial project version'
```
Use `git status` to check status. Often, you’ll have a class of files that you don’t want Git to automatically add or even show you as being untracked. In such cases, you can create a file listing patterns to match them named `.gitignore`.
`git log` lists the commits made in that repository in reverse chronological order.

At any stage, you may want to undo something. Here, we’ll review a few basic tools for undoing changes that you’ve made. One of the common undos takes place when you commit too early and possibly forget to add some files, or you mess up your commit message. If you want to redo that commit, make the additional changes you forgot, stage them, and commit again using the `--amend` option:
```
$ git commit -m 'Initial commit'
$ git add forgotten_file
$ git commit --amend
$ git push origin master
```
You end up with a single commit — the second commit replaces the results of the first.

# Chapter 3 Git Branching
```
$ git checkout master
Switched to branch 'master'
$ git merge testing
```
Occasionally, this process doesn’t go smoothly. If you changed the same part of the same file differently in the two branches you’re merging, Git won’t be able to merge them cleanly. The `git branch` command can help manage branches.  To see the last commit on each branch, you can run `git branch -v`. To synchronize your work with a given remote, you run a `git fetch <remote>` command. 
```
git rebase
git push --force
```
In general the way to get the best of both worlds is to rebase local changes you’ve made but haven’t shared yet before you push them in order to clean up your story, but never rebase anything you’ve pushed somewhere.
