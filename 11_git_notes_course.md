## Git Notes from [LinkedInLearning Course](https://www.linkedin.com/learning/8-git-commands-you-should-know-16027523?u=78611978) by [Ronnie Sheer](https://www.linkedin.com/learning/instructors/ronnie-sheer?u=78611978)

### Stashing

```
git diff                        # shows edits
git stash                       # stashes code
git stash pop                   # removed code from stash
git stash save "edit"           # save a stash named "edit"
git stash list                  # shows stashes w/ index 
git stash apply 0               # applies stashed state with index 0
```

### Staging changes

```
git status                      # shows current state
git commit -am                  # add files & commit at the same time                
                                # less granular control
git add -p                      # accept selectively which
                                # changes you wish
                                # to commit interactively
                                # (type y/n & enter to accept
                                # or decline, respectively)
```

### Mistakes & Fixes

#### Be careful where you push
```
git push                        # quicker
git push <remote> <branch>      # safer
```

#### Undo a commit - NOT pushed
```
git commit -am "something"
git reset --soft HEAD~1         # one commit back
git status                      # now back to staged
```

### Challenge: Rename a commit & move it to another branch
```
git add .
git commit -m "something"

git log                         # shows changes
git reset --soft HEAD~1         # undo commit
git checkout -b new-branch      # create new branch
git commit -m "something again" # redo commit with new name
git checkout -d                 # go back to previous banch
```

### Pre-commit and Pythong
[Check it here](https://pre-commit.com/)

### Amend, Revert
1. Amend: quickly modify a commit before pushing
```
git commit --amend -m "foo bar"
```
2. Revert: creates a new commit where we can undo our action
```
git revert <commit hash>    # optionally edit commit message
git log                     # shows the new state without
                            # losing the erroneous commit
```