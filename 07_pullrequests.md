## Intro to PRs
If you want to push to a repo which isn't yours (after forking, cloning, branching, changing and committing our work), we request a pull from the repo's owner (usually at master) so we publish our changes:
- `git push origin feature`
- [create pull request (PR)](https://help.github.com/en/articles/creating-a-pull-request) at repo's owner's GitHub
- Finally, the repo's owner merges, after reviewing them (push anew etc).

## Group Workflow
We have a central repo, the developers fork and do their work.<br>
Latest code = master of central repo.<br>
**NO-ONE PUSHES TO ANY MASTER**: for each change, each person pushes to their fork, PRs to master of control repo, the group reviews and then they merge.<br>
Additionally, each member adds to the central repo an extra remote named 'upstream' (so now each member has 2 remotes: `origin` - their own and `upstream` - central).<br>
From upstream master: everyone pulls to local master & pushes to origin master => Syncing master PRs (All: local & remote).<br>
Each member is a [contributor](https://help.github.com/en/articles/inviting-collaborators-to-a-personal-repository) to the central repo therefore can merge.