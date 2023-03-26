## Git Cheatsheet

### Install git
* ```git config --global user.name "myname"```
* ```git config --global user.email "my@email.com"```

### Set up git for current directory
* ```git init```

### Update repo with any changes to staged files
* ```git commit -am "some commit message"```

### Check what files in current directory are NOT staged/added to repo
* ```git status```

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
