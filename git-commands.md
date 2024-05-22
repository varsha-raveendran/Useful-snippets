# Git Notes

Ref: 
* Git & GitHub Crash Course For Beginners [https://www.youtube.com/watch?v=SWYqp7iY_Tc]
* Udemy: GitHub Ultimate: Master Git and GitHub - Beginner to Expert

# Concepts
-----------------------
* Decentralized and distributed version control system
* Quasi-hidden .git folder
* Git versions files and not folders
* Snapshots are commits; commits are changed on a branch 


# Basics
---------------------
* New file -> Working copy --> Add to Index --> Commit to tree
* Index: a staging area between working directory and repository. [Ref:
  [Link](https://shafiul.github.io/gitbook/1_the_git_index.html#:~:text=The%20Git%20index%20is%20used,is%20in%20your%20working%20directory.)]
* -- is used to separate file names from command options
* git help <command>

## Initialization
```
git init # .git folder created
```
## Add to staging area
```
git add <file> # Add to Index (Staging Area) 
git status # Check status of working tree
```

## Check changes
```
git log # list all the commits with its SHA1 identifier
git log --oneline --graph --decorate --all # format
git show # lists recent commit + diff
git ls-files # lists tracked files
```

## Git Aliases
```
git config --global alias.hist "log --oneline --graph --decorate --all" # creates an alias "hist" to git log
git config --global --list # to check if alias is created
git hist # to use the created alias
git hist -- LICENSE.md # to use created alias for only 1 file
```

## Commit files
```
git commit # commit changes in Index
git commit -am # add modified files and commit with message
```

## Recovering from mistakes
```
git reset HEAD <file to be unstaged> # after commit, default mode: mixed, resets the index to the state it was previously
git checkout -- <file> # reverts all changes

```
## Rename and Delete files
```
git mv <old_name> <new_name> # renames and adds to index
git rm <file> 
git rm --cached <file> # Remove from staging area; with --cached it doesn't remove from disk else it does by default

# ext to git
mv <old> <new>
git add -u # update
git add -A # updates all modifications in the working dir

rm <file>
git add -u # stages deleted file
```

## Push changes
```
git push #to remote
git pull
git clone
```

## Excluding files
```
touch .gitignore
```

## Compare differences
```
git diff <commit id> HEAD
git difftool <commit id> HEAD # opens a ui
git diff # shows recent changes in working dir
git difftool
```

# Branching
----------------------
```
git branch <name>

```

# Remote
-----------------------
```
git remote add origin <link>
git push -u origin master
```

# Merge
-----------------------
* Merging takes contents of source branch and integrates them with target branch. 
* Only the target branch is changed. The source branch history remains the same
Ref: freecodecamp
```
git checkout feature
git merge master
```

OR
```
git merge master feature
```

# Rebase
-----------------------
```
git pull --rebase origin master
git push origin master
```
# Set remote
-----------------------
```
git remote -v
git remote set-url origin <git/https>
```
