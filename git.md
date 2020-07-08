# Hamid Alavi's Git tips

## Please fix tips if i wrote wrong. thanks so mush for contributing :)

- `git init` = create git file (repository)
- `git status` = see status of git

## Help

- `git help` [**text**] = get help from git
  - press `q` to guit from help mode

## Add to Stage

- `git add` [**file**] = add file to stage list
- `git add -A` = add all files to stage list
  - you can also use `git add .` add all files in current directory to track list
  - if you modify a file, you must add to stage that file again
  - you can can also use wild-card (like \*)

## Commit

- `git commit` = open a editor to send commit comments
- `git commit -m` (or --message) '**message**' = commit all things in stage list
- `git commit -S -m` '**message**' = commit all things in stage list and signature them

## Restore

- `git restore` [**file**] = restore last commit from working tree
- `git restore --staged` (or -S) [**file**] = restore last commit from stage
- `git restore --source` [**commitID**] [**file**] = restore file to specific commit id
- `git checkout` --[**file**] = extracts the file from the last commit and replaces the current file

## Reset

- `git reset` [**file**] = reset file

## Config

- `git config --global -l` (or --list) = shows list of user configurations
- `git config --global user.email` "**you@example.com**" = specify email for user
  - use `git config --global user.email` for just showing user's email
- `git config --global user.name` "**Your Name**" = specify name for user
  - use `git config --global user.name` for just showing user's name
- `git config --global user.signingKey` = shows owner signin key
- `git config --global user.signingkey` [**key**] = set signing keys for git
  - example: git config --global user.signingkey xxxxxxxxxxxxxxxxx

## Git Log

- `git log` = shows git logs (history of commits)
  -press `q` to quit log mode
- `git log --oneline` = displays git logs by one line
- `git log --oneline --all` = displays git logs by one line on all branch

## Difference

- `git diff HEAD` = shows difference of current version (commit) compared to the last version (modified)
  - -- is last state
  - ++ is current state
  - @@ -[oldline(s)] +[newline(s)] @@

- `git diff --staged` = shows difference of current version (stage) compared to the last version (modified)

## Branches

- `git branch` = shows all branchs
- `git branch` [**name**] = creates new branch
- `git branch -d` [**brnach**] = deletes a branch
- `git checkout` [**branch**] = change branch
- `git merge` [**branch**] = merge all changes to master (main) branch
- `git rm` [**file**] = removes file from git and current directory

## Cloning

- `git clone` [**address**] = get git project from server (download)

## Remote

- `git remote add origin` [**address**] = add remote
- `git remote -v` = verbose mode of remote (shows remote and it's state)
- `git remote set-url origin` [**address**] = change remote url

## Push/Pull

- `git push origin master` = send changes to origin via remote (commit into server)
- `git push -u origin master` = send changes to origin via remote
- `git push` = like above command. but saved last push command
- `git push origin` [**tagName**] = send tag to origin via remote
  - you can also use `git push origin --tags` command for push all tags
- `git pull origin master` = get changes from origin (contribute)

## Show Changes

- `git show` = shows information about the last commit
- `git show` [**commitID**] = displays changes of specific commit (whats happend in that commit)
  - press `q` to quit show mode
- `git show` [**tagName**] = shows changes of specific tag (whats happend in that commit)(show information of that tag)

## Tag

- `git tag -a [**annotation**] -m` '**message**' = makes a tag for the repository (annotation)
  - example: git tag v1.0 -m 'creating first tag'
- `git tag -a [**annotation**] [**commitID**] -m` '**message**' = makes tag for the specific commit of repository (annotation)(use for release versions)
  - example: git tag v1.1 1692d9f31f0d9ba647ecdffb38b40c47a8f4cf66
- `git tag -s [**tagName**] -m` '**message**' = makes a tag for the repository with signature (signing key)
- `git tag -l` [**tagName**] = lists tags by name
- `git tag -v` [**tagName**] = shows tag information (tagger, date, type, signature and etc.)

## Key and Hash

- pretty good privacy (pgp) = using for keys
  - use gpg for usage
- `gpg --list-keys` = shows all keys
  - if for first time, automatically create necessary files
- `gpg --gen-key` = generating a key
- `gpg --list-secret-keys` = list of secret keys
- `gpg --list-secret-keys --keyid-format LONG` = list of secret keys as long format key id

## Blame

- `git blame` [**file**] = shows writer of all lines of code or content (history)
- `git blame` [**file**] -L[n] = shows writer of that line and above of code or content
  - example: git blame hamid.html L5
    - output: ^xxxxxx (Hamid Alavi 2020-07-07 05:34:19 +0430  5) ....
- `git blame` [**file**] -L[n],[n] = shows writer of between of n lines of code or content

## Binary Search Commit

- `git bisect start` = you have started the wizard and it won't end until you type git bisect reset
- `git bisect reset` = ends process of bisect
- `git bisect good` = if that version works correctly you should type **good**
- `git bisect bad` = if that version is broken, you should type **bad**
