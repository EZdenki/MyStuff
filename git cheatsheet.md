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
