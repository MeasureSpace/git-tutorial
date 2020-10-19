# git-tutorial

Git is a version control system. Using git, you can trace your code change history and better collaborate with others.

## Git workflow introduction

When working with git, it's always safe to have your own branch and do your personal work within it simply because the master branch may connect to the production system directly and you don't want some small bugs to affect all your users. After everything is tested, you can merge your own branch with the
master branch.

The following picture shows the basic workflow of using git. In your local desktop, typically you need to create two branches - one is the local master branch and the other one is the local feature branch. After your have a new feature developed, you may want to push the feature branch to remote repo and create a pull request to merge the remote feature branch with the remote master branch.

![git_workflow](https://raw.githubusercontent.com/MeasureSpace/git-tutorial/main/git.png)

## Basic usage

Here is an example of how to do that.

```bash
#Clone the master branch
$git clone [your_master_branch_address]
# Setup repo username and email (add --global for global setting)
$git config [--global] user.name [Your git user name]
$git config [--global] user.email [Your git user email]
# Create and switch to your local feature branch
$git checkout -b [name_of_your_feature_branch]
# Check all local branches
$git branch
# Make some changes and check git status
$git status
# Stage your changes
$git add .
# Commit your changes
$git commit -m "I made some changes"
# push changes to your remote feature branch
$git push origin [name_of_your_feature_branch]
```
## Merge feature branch with latest master branch
Another situation is that when you were working on your branch, your colleagues have already finished their part and committed new changes to the master branch. To make sure your working branch contains the latest code from master branch, a typical practice is to first update your local master branch and then merge your master branch with your local feature branch.

```bash
# Swith to master branch
$git checkout master
# Pull latest code from master branch
$git pull origin master
# Switch to feature branch (assume feature is your local working branch name)
$git checkout feature
# Merge master branch
$git merge master
# Push back to remote feature branch
$git push origin feature
```

## YouTube tutorial

Click the following image, and it will take you to YouTube for more detailed tutorial.

[!]()

References:

* [stackoverflow](https://stackoverflow.com/questions/5601931/what-is-the-best-and-safest-way-to-merge-a-git-branch-into-master)
* [Kunena-Forum](https://github.com/Kunena/Kunena-Forum/wiki/Create-a-new-branch-with-git-and-manage-branches)
* [Basic git commands](https://confluence.atlassian.com/bitbucketserver/basic-git-commands-776639767.html)
* [How to merge other's branch into mine?](http://stackoverflow.com/questions/11582894/how-do-i-merge-another-developers-branch-into-mine)
