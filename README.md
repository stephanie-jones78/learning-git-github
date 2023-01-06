
# Learning Git and Github
>[LinkedIn Course](https://www.linkedin.com/learning-login/share?forceAccount=false&redirect=https%3A%2F%2Fwww.linkedin.com%2Flearning%2Flearning-git-and-github-14213624%3Ftrk%3Dshare_ent_url%26shareId%3DdvujaFZBS%252BGLk%252FgY2blIrg%253D%253D)

>[This podcast episode](https://podcasts.google.com/u/1/feed/aHR0cHM6Ly9hbmNob3IuZm0vcy81MTA5Mzc2NC9wb2RjYXN0L3Jzcw/episode/OWUwZDhlYmYtMmZkMC00YzcwLWI4NjMtMGI0MWE0ZjY4ZmVj?sa=X&ved=0CAUQkfYCahcKEwjojIW7zK_8AhUAAAAAHQAAAAAQLA) on CI/CD and CI/CT Pipelines inspired me wanting to reaquaint and dive deeper into git fundamentals.
## Version Control
Version control allows us to document the history of a project over time and gives us the ability to jump back and forth through time.

## Git Setup
Configuring GIT
```
# git config commands
git config --global user.name #your github “Your Name”
git config --global user.email #github email “Your Email”
```

Initializing Project Folder
```
# initialize local git repository
	# Creates an empty .git folder in local repository
	# This is where git stores all the project information
git init
```

Each Git branch is like an alternate reality that allows you to create alternate *versions* of a project. Essentially, it is a copy of a project that you can work on without changing the original. You can then syncronize branches or go back and forth between them.
- Head is the actual reality
- Main (Master)

## Git Environments
- Working (*last commit status*)
- Staging (*add command - changes queued prior to commit*)
- Commit (*new log entry with hash*)

Staging Files
```# temporarily store files for later commit
git add filename
git add --all
git add -A
git add .
```

Committing Files to History
```# creates a version checkpoint 
git commit -m ‘Your comment’
```
*A Git hash is unique identifier for a commit.*

Reviewing Commit History
```
git log

# viewing condensed version (without scroll)
git log --online
```

Getting File State
```
git status 
```

Restoring File to a Previous State
```git restore filename
git restore --state (staged) filename
git restore . # restores current directory
git checkout . # older version of restore command
```

## Ignoring Files
Files that are not tracked by git or uploaded to GitHub. Create a `.gitignore` file at the root level of project folder with files or file patterns you want to ignore.
```
.DS_Store
.vscode/authentication.js
node_modules
notes/ 
**/*-todo.md
```
*Git doesn't track empty folders*

Creating global ignore file with a `config` variable that captures ignore settings for any new project
```
git config --global core.excludesfile [file]
```

## Deleting, Renaming, and Moving Files
```
# deleting files managed by git
    # also moves deletion event into staging
    # take care of git add 
git rm filename

# renaming files
git mv oldfilename newfilename

# moving files 
git mv oldpath/filename newpath/filename
```

## Differences
Showing the difference between files
```
git diff

# look at a specific hash's diff
git diff hash

# escape diff scroll
q
```
It is difficult to view when there are a lot of changes. In that case better to use VS Code's ***Source Control*** feature.

## Changing History
Amending is when you 
```
git commit amend
git commit -am 'New commit msg'
git commit amend --no-edit
```

Test text