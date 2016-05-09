# Git Workflow

## Introduction
This document highlights Git workflow which team at Srijan should use. It also contains conventions for naming
branches and remotes. We will introduce two workflows in this document. It is suggested to use the Workflow 1
(Github's fork based workflow) unless there is a special need to use Workflow 2.

## Branch name conventions
Both the workflow would follow per feature branch branching concept, so it is crucial to follow a similar branching
name convention.

It is assumed that your project uses some ticketing tool(Jira etc) to run sprints and each team member is assigned
tickets in the sprint to develop/fix. Since we would be following per feature branch which should follow following
naming convetion and please use lowercase to name your feature branches.

```
<ticket-number>-<description-of-the-ticket>
```

*Example*

* Ticket no. Assigned: Dev-123
* User story: As an authenticated user I should be able to view my organization's logo instead of site logo when I
navigate to my organization page.

Considering the above example the branch name could be
```
dev-123-logo-authenticated-users-for-org
```

## Git commit messages
* Start your git commit message with the ticket number of the feature you are working. Example ```Dev-123: added template
for logo"
* Git commit messages should highlight the work which you are saving in that particular commit. Please avoid generic
commit messages like "added css"
* Git commit messages should not contain any typos
* Use ```git commit --amend``` in case you want to add/modify something to your last commit
* [Refer](http://chris.beams.io/posts/git-commit/) for more
* In case your commit message does not follow above points it is likely that the pull request might get rejected and you
might have to make changes in your commit messages. Please read [this](https://help.github.com/articles/changing-a-commit-message/)
to understand the process of changing git commit messages

## Git Workflows

### Git Workflow 1

#### Architecture
* Each project would have an upstream repository hosted on Srijan account.
* [https://github.com/srijanaravali/srijan_dev_docs](https://github.com/srijanaravali/srijan_dev_docs) is an example of upstream remote which we would be using as an example in this document.

#### Steps
* Create a fork
![Screenshot](images/fork.png)
* This would create(clone) the upstream repo to your personal github account
![Screenshot](images/forked_repo.png)
* Clone the forked repo ```git clone git@github.com:AshishThakur/srijan_dev_docs.git```
* Add upstream repo as a new remote named upstream ```git remote add upstream git@github.com:srijanaravali/srijan_dev_docs.git```
* It is important to follow similar conventions; while you clone your repo needs to be named as *origin* and the srijan repo needs
to be added a new remote named *upstream*. In case you have confusions regarding remote, please read about how remotes work in git.
* In case you have correctly followed the above steps ```git remote -v``` should give following output
```
Ashishs-MacBook-Pro:srijan_dev_docs ashish$ git remote -v
origin  git@github.com:AshishThakur/srijan_dev_docs.git (fetch)
origin  git@github.com:AshishThakur/srijan_dev_docs.git (push)
upstream        git@github.com:srijanaravali/srijan_dev_docs.git (fetch)
upstream        git@github.com:srijanaravali/srijan_dev_docs.git (push)
```
Note above my forked repo is named as *origin* and the srijanaravali/srijan_dev_docs is named as *upstream*

### Git Workflow 2

## Other important points to consinder











