### New GitHub repo from existing project from local directory

1. In the directory containing the project:
```bash
$ git init
$ git add .
$ git commit 
```
2. On GitHub, create new repo
3. 
```bash
$ git remote add origin git@github.com:username/new_repo
$ git push -u origin main
```