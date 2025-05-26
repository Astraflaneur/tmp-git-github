## **An Introduction to Git & GitHub**

<div align="center">  
  <img src="./asset/git-logo-color.png" width="200" height="100">  
  <br><br>

 **Understanding Version Control in Practice**

*Git "Gud"* with <br>
**Sagar Prakash Barad** <br>
School of Physical Sciences <br>
NISER Bhubaneswar

</div>

### 🔹 Why do we need Git:

> In research, development, and collaboration, understanding your changes and controlling your codebase is essential.
> Git isn’t just a backup tool, it’s a tool to manage your project with calrity.

---


## 🔹 **Git Basics** & 🔸 **Staging Area**

<div align="center">  
  <img src="./asset/basic-usage.svg" >  
  <br><br>
</div>


<table style="width:100%">
  <tr>
    <td style="vertical-align:top; width:50%">

### 🧩 Git Overview

* Git is a **Version Control System**.
* Tracks and manages changes across files and time.

#### 📁 File States:

* **Committed**: saved in the Git database.
* **Modified**: changed but not yet staged.
* **Staged**: marked for the next commit via `git add`.

#### 🆔 Commits:

* Each commit has a **unique hash ID**.
* Minimum 4-character prefix if unique in repo.

</td>

<td style="vertical-align:top; width:50%">


### 🗂️ Special Git Files

* **`.gitignore`**:

  * Located at the root of the repo.
  * Tells Git what to ignore.
  * Supports file names, extensions (`*.pyc`), and paths.
  * Keeps unnecessary or sensitive files out of version control.


### 🧷 Staging Area

* Virtual space where changes go after `git add`.
* Allows precise control over **what gets committed**.

</td>
</tr>
</table>

---

## Commands
### Install:<br>
`sudo apt-get install git`
### Set up:<br>
- `git config --global user.name "User Name"` <br>
- `git config --global user.email "email@email.com"`
### Create a New Project:<br>
- `mkdir project`<br>
- `cd project`<br>
- `git init` *(initialise empty git repo in my folder (based on path) aka .git folder)* <br>
- `ls -la` *(check my folder)*
### Check "world status":<br>
`git status`
### Help for each command
`git help <command>`
### Add files
- `git add .` = add all on current branch
- `git add -p <param=file>` = add part of file to staging area, ask for each change (if no param => all files) so we have more control and cleaner commits.
*After any `git add`, we need a `git commit`, either a file or a pattern (e.g. `*.txt`)<br>*
### Delete a file
- `git rm <filename>` = deletes a file, updates git and then commit!<br>
- `git rm --cached <filename>"` = delete a previously tracked file
### Move a file
`git mv <old path> <new path>` *should be followed by:*<br>
`git rm <old path>`<br>
`git add <new path>`
### Check difference
- `git diff`= displays what will be added if i `git add`, so what changed in the folder and hasn't been updated yet
- `git diff <filename>` = displays the alterations of a file (the modified and the commited versions of it)
- `git diff --staged` = displays what has already been added and thus what changed will be recorded
- `git diff HEAD` = displays changes since last commit
### Display history
`git-log` = displays the history, the chronologival order of commits (based on their IDs), who did them, what was their description<br>
`git show <id>` = displays what the <id> commit did = `git log` + `git diff`
  
### Make an [alias](https://medium.com/the-lazy-developer/five-life-changing-git-aliases-e4211c090017)
- `git config --global alias.<aliasname> "command(s)"`
<br>e.g.:<br>
`git config --global alias.lg "log --color --graph --pretty=format: '%(red%h%(green(%cr)%((bold blue)<%an>%(reset' --abbrev -commit"`
- `git config --list` - displays our aliases
### Make archive
`git archive --format=zip -o latest.zip HEAD`
### Revert to old commit
`git log`<br>
`git checkout <commit hex id>`
### Cancel not staged changes
`git checkout` = it copies staging area (usually last commit) to out working copy
### Reset
`git reset` - remove all that exists in my staging area by copying them from the most recent commit (basically undoes `git add`)
### Copy a commit to another branch
`git cherry-pick <commit>` = we copy a commit from a point of the graph, we put it on active branch (therefore creating a copy of the selected commit) - new ID, same changes and description!
### Copy changes to new commit
`git revert <commit>` = inverted add/deletes etc. It cancels the commit that has already happened.
### Tags
- `git tag -a <tag>` = adds tag to last commit of current branch
- `git tag -a <tag> <commit>` = add tag to selected commit
- `git tag` = shows all tags in repo
- `git tag -d <tag>` = deletes a tag
### Publish tags
`git push <remote> <tag>` = publishes tag in remote
`git fetch --tags <remote>` = brings all tags from remote
### Serial list of changes
- `git reflog` = all the changes
- `git reflog <branch>` = changes on our branch
- `git reflog --date=relative` = displays changes relative to time
### Prune stale references
 - `git fetch -p`
# Questions
## How many `git add <filename>` do I need?

| Times | What it does |
| ------ | ------ |
| 1 | Tracks `<filename>` |
| 2 | Makes `<filename>` staged |
| 3 | If modified again after staged, we need a thrid `git add` to stage it again |

## What does `git commit` do?
- commit a file = create a snapshot of the current world state (files, folders & their contents)
- contains an explanatory message
- automatically stores metadata (creator, date etc)
- has a unique (hex) id number
<br> *e.g.: `git commit -m "Added README file`*

## Combinations
- `git commit -a` = `git add` + `git commit` (not desirable due to lack of control)
- `git pull` = `git fetch` + `git merge` (very useful)

---

## What is a branch?
It is a version of our code. Branches have a name and are pointing to a commit (there's a different history+past commits depending on our branch, but some commits may be common).
<br>
One branche per feature (the smaller the better) so changes happen to the branch, not the master workflow until the final merge. Afterwards, we merge and delete the branch.

## Commands
- `git branch <name>` = creates the branch, it's an exact duplicate of our current/previous branch (they point to the same commit)
- `git branch` = returns my current branch
- `git checkout <name>` = changes current (`HEAD`), `<name>` points to `HEAD` now
- `git branch -d <name>` = deletes this branch (**NOT** the commits also)
- `git checkout -b <name>` = creates a new branch and makes this new branch as our current working one = `git branch <name>` + `git checkout <name>`
- `git merge <branch>` = merges <branch>'s history with my current branch + try to merge changes in files from both the branches => 2 parents in new commit. *(Afterwards we find the most recent parent of those two parents => commits of the new branch = commits of parent1 + commits of parent2 => updates master, master in new commit - see schema (1))*

*schema (1)*
![branch](https://user-images.githubusercontent.com/19435096/66163182-62b38500-e638-11e9-96a8-bc81d9ca43a4.jpg)

*Note: If you make a branch on terminal and want it to show on GitHub, you need to `git push origin branchname` first!*
*Note2: After being done with a branch, `git checkout <productionbranch>`, and then `git merge <tesbranch>` and then `git branch -d <testbranch>` (you can delete the testbranch from GitHub's UX)*
#

### Master Branch
- Our default branch after a `git init` command.
- (For most projects) it has a 'current' code
- Usually we create a new branch as a copy of master

#
## References to parental nodes
| Symbol  | Meaning                                            |
|----|------------------------------------------------------------|
| ~  | 1 commit behind                                            |
| ^  | the first commited parent                                  |
| ~2 | commit's grandpa (2 commits back based on `^` (if merged)) |
| ^2 | second parent from merge                                   |

e.g. `192a812~2` = 2 commits before commit #192a812, or `HEAD^2`

## Rewriting History
We can change our commits' sequence, description and changes, but: **you should not rewrite a history in commits that others may pull** <br>
`git commit --amend` = changes most recent commit, add to it the staged stuff.<br>
`git commit --amend --no-edit` = [check here](https://dev.to/lt0mm/comment/eo8)

## Back Merging
When I work on a branch, it is possible that some changes might have happened on master => we need `git merge master` and resolve the conflicts. Or...
- `git rebase` = like `merge` but better, it happens between two branches and changes the base where a branch has been made, rewrites its history (clean). Followed by a clean `pull request`. Generally we merge only for final pull request on each branch.
- `git rebase -i` = dynamic: changes the sequence of commit applies changes, fixes multiple commits or can break a commit to many.
- `git reset <commit>` (usually `git reset HEAD`) = returns current branchto <commit>, cancels in between changes.

**Not for published commits!!**

- `git push --force-with-lease` or `git push --force` = if I change history, git denies pushing w/o it.