# **SETUP** 
```
git config --global user.name "[firstname lastname]"
```

 * Sets/changes username in order to identify user that tries to commit on remote. 
Current username can be checked with the command `git config --global user.name`
   - `git config --global user.name "matejkovacc"`


```
git config --global user.email [valid-email]
```
+ Sets/changes email in order to identify user that tries to commit on remote. Current email can be checked with command 
    - `git config --global user.email "matej.kovack@gmail.com"`
****
# **SETUP AND INIT**
```
git init
```
+ Creates empty repo in specified directory. 
  
```
git clone [URL]
```
+ Clones repository located at URL onto local machine. Original repo can be located on the local files or on remote. 
    - `git clone https://github.com/matejkovacc/first-task.git`



****
# **STAGE AND SNAPSHOT**

```
git  status
```
+ List which files are staged, unstaged and untracked

```
git add [file]
```
+ Stage all changes in file for the next commit. 
    - `git add README.md`

```
git add .
```
+ Stage all changes in **all** files for the next commit. 
  
```
git commit
```
+ Changes made in repository saved as commit
  
```
git commit -m [descriptive message]
```
+ Commit staged content as a new commit snapshot
    - `git commit -m "Message written in GitBash"`
  
```
git reset
```
+ reset staging area to match most recent commit, 
but leave the working directory unchanged



****
# **BRANCH AND MERGE**
```
git branch
```
+ List all of the branches in repo

```
git branch [branch-name]
```
+ Create a new branch in the current commit
    - git branch "master"

```
git branch -u
```
```
git checkout
```
+ Switch to another branch
    - `git checkout main`
  
```
git checkout -b myfeature develop
```
+ Switched to a new branch "myfeature"
  
```
git checkout -b [name of new branch]
```
+ Create and checkout new branch
    - `git checkout -b anonymous`

```
git log
```
+ Show all commits in the current branch's history
  
```
git merge [branch]
```
+ Merge `[branch]` into the current branch

```
git branch [name of the branch] -d
```
+ Deletes the branch
    - `git branch cheatsheet -d`

```
git branch -m [branch 1][branch2]
```
+ `branch1` takes the name of `branch2`

```
git checkout bugFix; git merge main
```
+ Main branch merged into bugFix branch



****
# **SYNCING**
```
git fetch
```
+ Download commits, files and refs from a remote repository into local repo. Does not update main branch
+  našo lokalno predstavitev oddaljenega repozitorija uskladi z dejanskim stanjem na oddaljenem repozitoriju
      +  `git fetch first-task`

```
git push  [remote][branch]
```
+ Upload local repository content to a remote repository
    - `git push first-task master`
  
+ Pojdi na branch poimenovan "main" na mojem repozitoriju, zgrabi vse commite in nato pojdi na branch "main" na oddaljenem repotu poimenovanem "origin". Postavi vse commite, ki manjkajo na branch in me obvesti, ko končaš

```
git push --set upstream origin
```
+ upstream is another branch name, associated with a regular branch

```
git pull [remote]
```
+ Fetch and download content from remote repository.  Merges and fetches at the same time. It updates local repository to match the content
+ Odgovoren za nalaganje sprememb na določen oddaljen repozitorij
    - `git pull first-task`

```
git fakeTeamwork
```
+ modifies git state
    - `git fakeTeamwork foo 3`

`git pull --rebase`
+ work rebased on new commits from remote repository

****
# **REWRITE HISTORY**
```
git rebase
```
+ Move a sequence of commits to a new base commit
    + git rebase bugFix
```
git rebase -i [base]
```
+ rebase current branch onto base. 
```
git revert
```
+ create new commit that undoes all of the changes made in "commit", then apply it to the current branch

```
git commit --amend
```
+ Replace the last commit with the staged changes and last commit combined

****

# **TREE HIERARCHY**
```
git checkout HEAD^
```
+ moves active branch for one commit up
```
git branch -f main HEAD~3
``` 
```
git branch -f main C6
```
+ moves main on C6
```
git checkout HEAD^2/git checkout HEAD~2
```
+ moves active branch for two commits up





```
git cherry-pick [commit]
```
+ integrate selected, individual commits from any branch into current HEAD branch
    - `git cherry-pick HEAD`


****
#**TAGS**
```
git tag v1 C1
```
+ commit C1 has assigned tag v1
```
git describe
```
+ finds the most recent tag reachable from a commit

```
git reset --hard o/main
```
```
git checkout -b feature C2
```



```
git push origin main:newBranch
```

```
git fetch origin foo:main 
git push origin :foo
git fetch origin :bar
git pull origin main:side
```