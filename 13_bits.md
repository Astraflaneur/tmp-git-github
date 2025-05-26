## Bits & Tips
1. *Your branch and origin have diverged and X and Y different commits each respectively*
```
git fetch origin branchName
git reset --hard origin/branchName
```
2. When merge develop to master: NOT SQUASH (keep history of what was merged for PROD)

3. Tags:
```
git fetch --tags (brings tags)
git tag (displays all)
git checkout tags/v1.0 -b v1.0 (creates local branch for this tag)
```