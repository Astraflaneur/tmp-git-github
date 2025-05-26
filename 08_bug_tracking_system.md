## GitHub Issues
Each issue:
- has a unique ID
- is a bug or a task (open/resolved)
- has a description
- has commits

Issues can be opened even by users who are not the repo's owners.
*Note: GitHub allows references to links*

When we locate a bug on a commit, we backtrack to a previous commit where there was no bug and try to find what caused it in the between commits (current=HEAD), or (see (\*)).

### Commands
- `git commit -m "Refactor code for issue #765`<br>
`git commit -m "Closes #765`<br>
or from PR description (similarly)
- `git checkout <commit>` = state detached head can't commit, we need to checkout again into a branch (and check code for some time)
- `git checkout <commit> <file>` = changes file's contains and brings them into commited state (no new commit/no stage)
- (\*)`git bisect`: <br>`git bisect start`<br>`git bisect bad` (HEAD is buggy)<br>`git bisect good <commit>` (<commit> is a known bug free commit).<br>
    *Basically it asks for each commit if the bug exists, we reply with `bisect good/bad`*<br>
   We stop it by using `git bisect reset` (last one). [Check here too](https://git-scm.com/docs/git-bisect).
- `git blame <file>` = marks a file as the culprit<br>