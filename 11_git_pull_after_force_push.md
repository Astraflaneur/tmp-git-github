# `git pull` after remote forced update
[Source](https://www.scivision.dev/git-pull-after-force-push/)

```bash
# Erase local changes in feat1 and match the remote Git repo.
git switch feat1
git pull --rebase

# To preserve work in feat1
git switch feat1
git fetch
git reset origin/feat1 --soft
```