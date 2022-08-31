# Git Guidelines
When co-working on git, each member should follow some standards. Each of them is specified below.

## Git branching strategy
When working with git, we will use the following branching strategy
![Branching Strategy](https://nvie.com/img/merge-without-ff@2x.png)

On each project we will be using the `develop` branch. Here any member can submit a pull request and with minimum 3 approvals, it can be merged. However, the `develop` branch will not be the release version. The stable versions will be on `master` or `main` and only the repository admins will have permissions to merge commits into this branch. 

## Workflow

When a developer has been assigned a task, this person should create a branch from the `develop` branch and start working on it. 
![Feature branches](https://buddy.works/blog/images/feature-branch.png)

## Creating a branch

When a user desires to create a branch for a specific task, it should be created from `develop`. By not paying attention to this part, when opening a Pull Request, that branch may have conflicts and some important changes may be lost, if it would get merged.

## Merging changes

When merging changes, the responsible person needs to check 2 important things:
- merging that branch with `develop`, before pushing the changes
- resolve any conflicts if there are, with the parent branch

## Branch naming strategy

Each task from Trello will have a tag. Some tag examples may be `feature`, `bug`, `documentation`, etc. When creating a branch for a task, the responsible person should use the following naming pattern: `tag/name-of-the-task`. The name of the task will always be separated using the dash character.
Example:
```
git checkout develop
git checkout -b feature/create-git-readme-repository
```
After the changes have been commited, the user will push that branch and create a Pull Request on Github.

## Commit naming strategy

Each commit message will follow this naming convention:
`tag: some message about what has been done in this task`
Example
```
git add .
git commit -m "feature: add a button for the website's navbar"
```

## Full commit example
Firstly, when the task has been assigned, run the following commands pattern
```
git checkout develop
git checkout -b tag/task-name`
```
After the changes have been made, create the commit
```
cd (project root folder)
git add .
git commit -m "tag: what has been done"
git checkout develop
git pull
git checkout -
git merge develop
git push
```

This way all the changes from `develop` will be syncronized and therefore the chances to appear major merge problems will be pretty low.

### Good luck and have fun
