Conflicts can't be automatically merged! Git has changed our file, merges what it can, but the rest is left on us:<br>
Open an editor and look for lines like so: `<<<<<`, `=====`, `>>>>>`<br>
These mark our conflict areas, where we keep all we need and discard what we don't.<br>
Afterwards, we `git add` each file, `git commit` (therefore merge) and all is OK!