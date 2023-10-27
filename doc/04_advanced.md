# 4. GIT Advanced

[Link back to readme](../README.md)

## Temporarily saving changes (stash)

### Question 1

What is stash used for?

- [ ] To backup changes.
- [ ] To backup commits.
- [x] **To clean working tree and temporarily save the changes.**
- [ ] To send a commit to team.

### Question 2

What command can you use to apply the third newest stash to your current working tree without destroying the stash?

`git stash apply stash@{2}`

## Inspecting the history of a single file (blame)

### Question 1

What is blame used for?

- [ ] To collect error statistics
- [x] **To find out who made which change**
- [ ] To locate copy-paste code
- [ ] To improve code quality

### Question 2

What command do you use to find out who did changes to index.js lines 5-15 and when?

`git blame -L 5,15 index.js`

### Question 1

What is reflog used for?

- [x] **To help with restoring deleted commits**
- [ ] To look at references in remote repository
- [x] **To look at the reference history in local repository**
- [ ] To interactively help with creating commits

### Question 2

How do you maintain reflog?

- [ ] By regularly running git reflog expire
- [ ] By going through reflog and deleting old ones with git reflog delete
- [ ] By removing branch specific files regularly
- [x] **By doing nothing. Git will take care of it.**

### Question 3

What command can you use to get reflog from release branch that is over five days and six hours old?

`git reflog release@{5.days.6.hours.ago}`

## Rebase

### Question 1

What is rebase used for?

- [ ] As a helper tool to create a merge commit
- [x] **To rewrite version history**
- [ ] To clean public branches
- [x] **To move changes without merge commits**

### Question 2

What’s the difference between merge and rebase?

- [ ] Merge does not create a commit
- [x] **Rebase does not create a commit**
- [x] **Rebase changes the starting commit of a branch**
- [ ] No real differences, they do the same thing

### Question 3

What command can you use to start an interactive merge from your current branch to main?

`git rebase -i main`

## Creating good version history

### Question 1

What do you use rebase and merge for?

- [x] **Rebase is used to rewrite version history in local branch**
- [ ] Rebase is used to rewrite version history in main branch
- [x] **Rebase is used to synchronize changes from remote branches to your own branch**
- [x] **Merge is used to synchronize changes to main**

### Question 2

What does the subject line in commit message tell us?

- [ ] Who made the changes
- [ ] How were the changes made
- [ ] Why were the changes made
- [x] **What changes were made**

### Question 3

What can you find from the body of a commit message?

- [x] **Why was the change made**
- [x] **How was the change made**
- [ ] Which lines were changed
- [x] **Alternative solutions which were considered**

## Different Git workflows

### Question 1

Which of the following statements are true?

- [ ] Forking workflow is great increasing productivity of small teams
- [x] Forking workflow is good for open source projects
- [ ] You’ll end up using less branches with Gitflow
- [x] In forking workflow each developer has two remote repositories. One for pull and the other for push.
- [x] Gitflow is created to support making regular releases
- [ ] In Gitflow you’ll merge new features to main branch
- [ ] In forking workflow each developer has write access to the official repository
- [x] In Gitflow you’ll merge new features to develop branch

### Question 2

Who can benefit from forking workflow?

- [x] Open source projects
- [x] Big corporations where one person chooses features for the next release
- [ ] Small teams
- [ ] Teams with regular releases

### Question 3

What kinds of teams can benefit from Gitflow?

- [ ] New teams
- [x] Teams with regular releases
- [ ] Teams with lacking Git knowledge
- [ ] Teams who focus on prototyping

## Advanced exercises

### Rebase

#### Initializing a repository

1. Create a _NEW_ repository for yourself
2. Add a new remote repository for your repository [https://course-gitlab.tuni.fi/git-course/advanced-rebase.git](https://course-gitlab.tuni.fi/git-course/advanced-rebase.git)
3. Fetch the history from the remote repository and merge it to yours. You might have to use --allow-unrelated-histories flag

> **Attention**
>
> Automated tests verify that your log history is only two commits long. You’ll have to create a new repository in order to pass the tests.

#### Exercise

Repository contains two branches _main_ and _devel_. Developers have barely been able to keep _main_ nice and clean but _devel_ is starting to look pretty horrible. As you might have guessed your job is to clean up the history in _devel_. Because the changes are pretty small you’ll want to have them in a single commit with message _Add prints_. You must be able to add these changes to _main_ by fast-forwarding. In the end your _main_ must have all the changes made in _devel_ and the history must be two commits long.

```shell
cd ~/git
mkdir hello_git_cource_advanced
cd hello_git_cource_advanced
git init -b main
git remote add origin https://github.com/mmmkoo/hello_git_course_advanced.git
git remote add advanced-rebase https://course-gitlab.tuni.fi/git-course/advanced-rebase.git
git fetch advanced-rebase
git merge advanced-rebase/master --allow-unrelated-histories
git checkout devel
git remote remove advanced-rebase
git merge-base devel main
# 426381dde6077e7d6bc82b232f3f07542f435b7d
git rebase -i 426381d
git checkout main
git merge --ff devel
git push --set-upstream origin main
```

### Log & Blame

#### Initializing the exercise

Clone repository [https://course-gitlab.tuni.fi/git-course/advanced-blame](https://course-gitlab.tuni.fi/git-course/advanced-blame)

#### Exercise

The different ways of "cheating" through this exercise are countless. The goal of this exercise is to learn how to use git log and git blame from command line. It’s possible to get the anwers from GUI or just by looking at every log event. You should try to add different filters to git log because it will come in handy in the future.

You’ve cloned a remote repository. With this clone you’ve also received every event made in the repository. You’ll have to find answers to questions by using git log and git blame.

You can open up the documentation by typing `git log --help` or `git blame --help`.

```shell
cd ~/git
git clone https://course-gitlab.tuni.fi/git-course/advanced-blame advanced_blame
cd advanced_blame
# Question 1
git log --reverse
# Question 2
git log --after="2020-01-15 00:00" --before="2020-01-15 23:59" --author=Jalo
# Question 3
# git log --reverse --follow -- TODO
# The correct answer can be found by simply:
git log TODO
# Question 4
git diff --find-renames
# Returns nothing
git log --reverse
# Get 1a54e416ee43519815d16927af40abf129c874a4
git diff --name-status -C 1a54e416ee43519815d16927af40abf129c874a4 HEAD
# Question 5
git log --all -i --grep='Merge branch'
# Question 6
git blame -L 29,34 -- lorem.ipsum
# Question 7
# Find where Question is mentioned in commit changes and see the first one in the log:
git log -SQuestion
# Question 8
git show 9afe1d6
```

##### Question 1

Who made the first commit?

- [ ] Teppo Testaaja
- [x] Teemu Teekkari
- [ ] Jalo Javascript
- [ ] Pertti Python

##### Question 2

How many commits did Jalo Javascript do in 15.01.2020?

- [ ] 0
- [ ] 2
- [x] 3
- [ ] 5

##### Question 3

Who created file TODO and when?

- [ ] 15.1.2020 Teemu Teekkari
- [ ] 16.1.2020 Jalo Javascript
- [ ] 15.1.2020 Pertti Python
- [x] 16.1.2020 Teppo Testaaja

##### Question 4

How many files have been renamed?

- [ ] 0
- [x] 1
- [ ] 2
- [ ] 3

##### Question 5

How many merge commits are there in _main_?

- [x] 2
- [ ] 3
- [ ] 4
- [ ] 5

##### Question 6

Who made the latest changes to lorem.ipsum lines 29-34?

- [x] Teppo Testaaja
- [ ] Teemu Teekkari
- [ ] Jalo Javascript
- [ ] Pertti Python

##### Question 7

Who added a file with class Question?

- [ ] Teppo Testaaja
- [ ] Teemu Teekkari
- [ ] Jalo Javascript
- [x] Pertti Python

##### Question 8

Which of the following statements are correct regarding the latest commit (9afe1d6f9aaa85b3655088c27bf261616ccc0fca) Teemu Teekkari made?

- [ ] 39 lines were removed
- [x] 39 lines were added
- [ ] No changes to any lines. A file was renamed.
- [ ] models.py was changed
- [ ] TODO was changed
- [x] lorem.ipsum was changed
- [x] Change was made 16.1.2020 klo 9:33
- [ ] Change was made 16.1.2020 klo 9:35
- [ ] Change was made 15.1.2020 klo 9:35
