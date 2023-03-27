## Git Cheatsheet

### Clone Remote to Local
* ```git clone https:github.com/sandynomike/reponame.git```
* Make changes to local file

### Push Local Repo to GitHub -- assumes remote repo exists
* ```git push``` Use current remote (origin) and local (main) branch names
* ```git push origin main``` Specifty remote and local branch names

### Pull Remote GitHub Repo to Local Repo -- assumes local repos exists
* ```git pull origin main```

### Get new files from remote repo but download files that would overwrite local files
* ```git fetch```
* ```git fetch origin main```

### Create GitHub Repo from Local
* ```gh repo create```

### Install git
* ```git config --global user.name "myname"```
* ```git config --global user.email "my@email.com"```

### Set up git for current directory
* ```git init -b main```
* ```git add . && git commit "Initial Commit"```

### Update repo with any changes to staged files
* ```git commit -am "some commit message"```

### Check what files in current directory are NOT staged/added to repo
* ```git status```

### Review previous commits
* ```git log```

### Check Remote associated with this repo
* ```git remote -v```

### Update Remote associated with this repo
* ```git remote set-url origin https:/github/sandynomike/newRepoName.git```

### Check what files are tracked, don't go into directories
* ```git ls-tree --full-tree --name-only head```

### Check what files are tracked, recurse into directories
* ```git ls-tree --full-tree --name-only -r head```

### Add (stage) file or files
* ```git add filename.abc``` Commit a single file
* ```git add file1.abc file2.abc file3.abc``` Commit multiple files
* ```git add .``` Commit all files in this directory
* ```git add --all``` Commit all files in this directory
* ```git add -A``` Commit all files in this directory

### Remove (unstage) file
* ```git rm filename.abc```

### Commit changes to repo<br>
* ```git commit -m "Commit message"``` Commit currently staged files to repo
* ```git commit -am "Commit message"``` Commit any files to repo that have been changed since last commit
