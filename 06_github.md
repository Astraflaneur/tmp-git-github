GitHub isn't git! GitHub is a [site](https://github.com/)!

## GitHub's features
- `fork` = copy a repo to your GitHub account
- `clone` = copy at your PC:<br>
`git clone`<br>`git @ github.com/UserName/git-repo.git`<br>`cd git-repo`
- Your PC repo has the site repo as its remote
- Each repo copy has it's own commits/branches/history (some may be common)
- Each remote has its own URL & name

## Commands
- `git remote` = shows repo's remotes
- `git remote add <name> <url>`
- `git remote rm <name>`

## Origin
Origin = repo's copy to our GitHub (automatically made when cloning)<br>
If you want to publish your code: `git push origin master` = sends master's local commits to remote's master named origin
If you want to get your code: `git pull origin master` = brings commits at our local master from remote's master named origin

## Outdated
If someone else pushed in the meantime when we're working locally, we can't overwrite their work.

    
    push conflict: A-B-C-D
                       |
                       E

Can't merge E,D because split => `git pull` or `git pull -rebase` (the second keeps E only locally and D is our last state)

## Hub
[A set of extra commands that expand git specifically for GitHub](https://github.com/github/hub)