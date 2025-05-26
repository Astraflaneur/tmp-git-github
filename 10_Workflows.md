## Basic Git Workflow
- edit file (e.g. vim)
- `git add <filename>`
- `git status`
- `git commit -m "Explain what happened"`

## `master` Workflow
- `git remote add origin <giturl>`
- `git checkout master`
- `git pull upstream master`
- `git push origin master`
- `git checkout -b feature`
- `vim && git add && git commit // git add .   , git commit -m "msg"`
- `git push origin feature`
- `hub pull-request -b upstream:master`

## Workflow Overview
- `git init`
- `git commit`
- `git commit`
- `git checkout -b bugfix`
- `git commit`
- `git checkout master`
- `git checkout -b bname`
- `git commit`
- `git commit`
- `git checkout master`
- `git branch -D bname`
- `git chckout -b feature`
...

## Branch Workflow
- `git checkout master`
- `git checkout -b parent2`
- `vim && git add && git commit` (as needed)
- `git checkout master`
- `git merge parent2`
- `git branch -d parent2`

## Merge Workflow
- `git checkout master`
- `git pull upstream master`
- `git push origin master`
- `git checkout feature`
- `git merge master`
- `git push origin feature`
- `hub pull-request`

## Rebase Workflow
- `git checkout master`
- `git pull upstream master`
- `git push origin master`
- `git checkout feature`
- `git rebase master`
- `git push origin feature`
- `hub pull-request`

## Master - Develop Workflow
- `git checkout develop`
- `git pull upstream develop`
- `git push origin develop`
- `git checkout -b feature`
- changes...
- `git push origin feature`
- `hub pull-request -b upstream:develop`

## Release Workflow
- `git checkout master`
- `git pull upstream develop`
- `git push origin develop`
- `git checkout master`
- `git pull upstream master`
- `git merge develop`
- `git tag -a v2.0`
- `git push origin master`
- `git push origin v2.0`
- `git push upstream master, v2.0`
