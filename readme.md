-- link for git and github chaiCode documentation
https://docs.chaicode.com/youtube/chai-aur-git/introduction/

--we can track files accordingly
--so if we want to track folder "one" we have to initialize git in it

--so cd one then git init
--this will start git to track one folder
-- before initializing git first check using git status that is it already tracking or not
-- now this make it working directory

-- touch : for creating file
-- mkdir : for creating folder

-- for push folder in staging area we use git add
-- git add 1.txt
-- git add . (for adding all unStage files)

-- use "git rm --cached <file>..." to unstage

-- git commit : for send changes from staging area to repo
-- git log : will show you your repo history
-- we can use --online flag with git log to show only commit messages

-- git original editor is vim which is very hard to use
-- so we set vs code terminal as editor using command
-- git config --global core.editor "code --wait"
-- install code command in vs code
-- now a file open write message and save and close file

-- if we don't wanna track any file put it into gitignore

-- if we wanna keep emptyFolder we make .gitkeep file in that folder so by using that we can keep empty folder too in our repo

-- git branch : give all branches
-- head : pointer point to current branch
-- git branch <branch name> : will create new branch
-- git switch <branch name> : switch to new branch
-- git switch -c <branch name> : create and switch to a new branch
-- git checkout : similar to switch

-- merging
-- git merge <branch name> : merge branches
-- if there is any merge conflict , you have to resolve them choosing
-- 1. Accept current 2. Accept incoming 3. Accept both
-- then you have to add and commit again

-- git branch -m <old-name> <new-name> : rename branch
-- git branch -d <branch-name> : delete branch

-- git diff --staged : This command shows the changes between your last commit and the staging area
-- git diff <branch-name-one> <branch-name-two> : This command compares the difference between two branches.
-- Another way to compare the difference between two branches is to use the following command:
-- git diff branch-name-one..branch-name-two

-- Comparing Specific Commits: git diff <commit-hash-one> <commit-hash-two>

-- Conflicting changes will not allow you to switch branches without committing the changes
-- git stash : This command saves your changes in a temporary location. It is like a stack of changes that you can access later
-- Naming the stash : git stash save "work in progress on X feature"
-- View the stash list : git stash list
-- Apply the Most Recent Stash : git stash apply
-- Apply Specific Stash : git stash apply stash@{0}
-- Applying and Drop a Stash :git stash pop
-- Drop the stash : git stash drop
-- Applying stash to a specific branch : git stash apply stash@{0} <branch-name>
-- Clearing the stash : git stash clear

-- Git Tags : Tags are a way to mark a specific point in your repository.
-- Creating a Tag : git tag <tag-name>

-- Managing History

-- A merge commit is a commit that combines two or more commits into one. It is created when you merge two or more branches into a single branch
-- Some people like to use rebase over the merge command because it allows you to keep the commit history cleaner
-- Ensure you are on the branch you want to rebase
git checkout feature-branch
git rebase main

-- If there are any conflicts, you will need to resolve them manually similar to merge conflict
git add <resolved-files>
git rebase --continue

git reflog : Git reflog is a command that shows you the history of your commits
git reset --hard <commit-hash> : Recover lost commits or changes
git reset --hard HEAD@{1} : you can use HEAD@{n} to reset to the nth commit before the one you want to reset to.

## Publish Code to Remote Repository

Remote URL Setting
You can check the remote url setting by running the following command:
git remote -v

You can add a remote repository by running the following command:
git remote add origin <remote-url>
origin is the name of the remote repository.

## Pushing Code

git push remote-name branch-name
git push origin main

## Setup an upstream remote

Setting up an upstream remote is useful when you want to keep your local repository up to date with the remote repository. It allows you to fetch and merge changes from the remote repository into your local repository.

-- This will allow you to run future commands like git pull and git push without specifying the remote name.

git remote add upstream <remote-url>
or
git remote add -u <remote-url>
or
git push -u origin main

git fetch <remote-name> : To fetch code from a remote repository
git pull origin main : To pull code from a remote repository
