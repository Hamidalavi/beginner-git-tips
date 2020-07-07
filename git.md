# Hamid Alavi's Git tips

- `git init` = create git file (repository)
- `git status` = see status of git

## Add to stage

- `git add` [**file**] = add file to stage list
- `git add` -A = add all files to stage list
  - if you modify a file, you must add to stage that file again
  - you can can also use wild-card (like \*)

## Reset

- `git reset` [**file**] = reset file

## Commit

- `git commit` = open a editor to send commit comments
- `git commit -m` '**message**' = commit all thing in stage list

## Restore

- `git restore --staged` [**file**] = removes file from stage list
- `git checkout --` [**file**] = retore file content from last commited (if file is broke or have bug)

## Config

- `git config --global user.email` "**you@example.com**" = specify email for user
- `git config --global user.name` "**Your Name**" = specify name for user

## Git Log

- `git log` = shows all logs (activity)

## Difference

- `git diff HEAD` = shows difference of current version compared to the last version (modified)
  - -- is last state
  - ++ is current state
  - @@ -[oldline(s)] +[newline(s)] @@

- `git diff --staged` = shows difference of current version compared to the last version in stage list(modified)

## Branches

- `git branch` = shows all branchs
- `git branch` [**name**] = creates new branch
- `git branch -d` [**brnach**] = deletes a branch
- `git checkout` [**branch**] = change branch
- `git merge` [**branch**] = merge all changes to master branch
- `git rm` [**file**] = removes file from git and current directory
- `git clone` [**address**] = get git project from server (download)

## Remote

- `git remote add origin` [**address**] = add remote
- `git remote -v` = verbose mode of remote (shows remote and it's state)
- `git remote set-url origin` [**address**] = change remote url

## Push/Pull

- `git push origin master` = send changes to origin via remote (commit into server)
- `git push -u origin master` = send changes to origin via remote
- `git pull origin master` = get changes from origin (contribute)
