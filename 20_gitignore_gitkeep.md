## How to Use .gitignore and .gitkeep?

### `.gitignore`
- In Git, the `.gitignore` file is used to specify which files or directories the change tracking process should ignore.
- [Here](https://github.com/github/gitignore/tree/main) you can find ready-made `.gitignore` templates for various technologies and languages.

### `.gitkeep`
- Not a standard Git element
- Used to keep track of directories that we wish to keep track of, even if they are empty.

### How to keep empty directories using `.gitignore`
```
# Ignore everything in this directory
*
# But do not ignore this .gitignore file
!.gitignore
```

[Source](https://dev.to/ritaly/git-lesson-how-to-use-gitignore-and-gitkeep-5edm)