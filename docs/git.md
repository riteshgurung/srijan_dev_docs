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
* Use git commit --amend in case you want to add/modify something to your last commit
* [Refer](http://chris.beams.io/posts/git-commit/) for more
* In case your commit message does not follow above points it is likely that the pull request might get rejected and you
might have to make changes in your commit messages. Please read [this](https://help.github.com/articles/changing-a-commit-message/)
to understand the process of changing git commit messages

## Git Workflows

### Git Workflow 1

### Git Workflow 2

## Other important points to consinder











