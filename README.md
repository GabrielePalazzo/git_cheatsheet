# Git

## Push / pull changes

Clone existing repository to local folder:
```
git clone https://github.com/username/repository_name
```

Pull remote changes to local repository:
```
git pull
```

Check local repository status (files changed, current branch, ...):
```
git status
```

### Commit workflow

Typical commit workflow:
 - Add modified / new files:
  - All files (use caution, check git status before doing it): `git add *` (or `git add .`)
  - Selected files: `git add filename1 filename2`
 - Remove files we want to delete from the repository (on Unix this also removes files from local directory): `git rm --cached filename1 filename2`
   - without `--cached` the command also deletes the files from the filesystem
 - Create commit: `git commit -m "Brief commit description"`
 - Push changes to remote repository: `git push -u origin main`

## Branches and branching

### Create branch

Check existing branches (active branch is highlighted):
```git branch```

Create new branch:
```git branch branchname```
Note: `git branch` still shows that we are on the main branch.

Change local active branch:
```
git checkout branchname
```

Create new branch (**from HEAD**) and switch to that branch in one line:
```
git checkout -b branchname
```
Create new branch from another branch and switch to that branch in one line:
```
git checkout -b branchname existingbranch
```

Push changes to branchname to remote repository:
```
git push -u origin branchname
```

### Merge branches (can also be done on github via browser)

We want to merge branchname to main.

Switch to main:
```
git checkout main
```

Merge the two branches:
```
git merge branchname
```

Push changes:
```
git push -u origin main
```


### Delete branch

Delete existing branch:
```
git branch -d branchname
```

Push changes:
```
git push origin --delete branchname
```

### Update local repository

Update local repository after pull requests / branch changes
```
git fetch --all --prune
```
