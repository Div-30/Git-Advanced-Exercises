# PART 1 CHALLENGES

## Challenge 1: Missing File Fix

### Evaluating the current status of my repository:
```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
(use "git push" to publish your local commits)

Changes not staged for commit:
(use "git add/rm <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
deleted:    index.html

Untracked files:
(use "git add <file>..." to include in what will be committed)
test4.md

no changes added to commit (use "git add" and/or "git commit -a")

```

### staging and adding the [test4.md](http://test4.md/) file and updating the commit message:

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add [test4.md](http://test4.md/)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Added [test4.md](http://test4.md/) file"

[main 5dbdd2a] Added [test4.md](http://test4.md/) file
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 [test4.md](http://test4.md/)

```

## Challenge 2: Editing Commit History

This challenge focuses on refining commit messages to ensure they remain clear and accurate throughout a project's history. For instance, we updated the commit message from the vague "Create another file" to the more precise "Create second file," better reflecting the action taken.

## Challenge 3: **Keeping History Tidy - Squashing Commits**

This challenge introduces the concept of squashing, a Git technique that consolidates multiple commits into a single, streamlined entry for a tidier project history. In this task, we merge the "Create second file" commit into the "Create initial file" commit, reducing clutter while preserving all changes.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git rebase -i HEAD~5
[detached HEAD 18a1f97] chore: Create initial file and second file
Date: Wed Feb 26 11:31:42 2025 +0200
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 [test1.md](http://test1.md/)
create mode 100644 [test2.md](http://test2.md/)
Successfully rebased and updated refs/heads/main.
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log
```

## Challenge 4: **Splitting a Commit**

This challenge explores the use of git reset to refine a project’s commit history by splitting a single commit into multiple, distinct ones for improved clarity and tracking.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % touch test5 test6

gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add test5 test6

gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Create test 5 and test 6"
[main 6e83c59] Create test 5 and test 6
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test5
create mode 100644 test6
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git reset --soft HEAD^
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git reset
Unstaged changes after reset:
D       index.html
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add test5
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Create Test 5"
[main 0bbe208] Create Test 5
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test5
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add test6

gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Create Test 6"
[main cdbe2c8] Create Test 6
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test6

```

## Challenge 5: **Advanced Squashing**

This challenge involves using Git’s interactive rebasing with the squash command to combine the last two commits, "Create test 5" and "Create test 6" into a single commit named "Create test 5 and test 6."

```
PS C:\Users\Divin Paul\Documents\Git-Advanced-Exercises\Git-Advanced-Exercises> git rebase -i HEAD~2
[detached HEAD ecf3f41] Create test 5 and test 6
Date: Mon Mar 3 11:46:33 2025 +0200
2 files changed, 2 insertions(+)
create mode 100644 test5.md
create mode 100644 test6.md
Successfully rebased and updated refs/heads/main.
PS C:\Users\Divin Paul\Documents\Git-Advanced-Exercises\Git-Advanced-Exercises> git log --oneline
ecf3f41 (HEAD -> main) Create test 5 and test 6
cfb443d Update README.md
50fe6ee Update README.md
3ec5ec8 Update README.md
766049f Create README.md
fe60d0f Delete index.html
5dbdd2a Added test4.md file
399cc9d chore: Create third and fourth files
e0dab20 chore: Create another file
6f96695 chore: Create initial file
ed3f4a6 Initial commit
```

## Challenge 6: **Dropping a Commit**

This challenge revolves around mastering the use of git rebase -i, a powerful Git command that allows you to interactively modify your commit history.

```
PS C:\Users\Divin Paul\Documents\Git-Advanced-Exercises\Git-Advanced-Exercises> git rebase -i ecf3f41
Successfully rebased and updated refs/heads/main.
PS C:\Users\Divin Paul\Documents\Git-Advanced-Exercises\Git-Advanced-Exercises> git log --oneline     
1018f50 (HEAD -> main) Update README.md
56e1ec1 Update README.md
ecf3f41 Create test 5 and test 6
cfb443d Update README.md
50fe6ee Update README.md
3ec5ec8 Update README.md
766049f Create README.md
fe60d0f Delete index.html
5dbdd2a Added test4.md file
399cc9d chore: Create third and fourth files
e0dab20 chore: Create another file
6f96695 chore: Create initial file
ed3f4a6 Initial commit

```
## Challenge 7: **Reordering Commits**

This challenge focuses on mastering git rebase -i to manipulate Git commit history. It’s about exploring how to rearrange commits in a repository using interactive rebase.
The goal is to understand and apply this command to reorder commits effectively.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git rebase -i HEAD~3    
Successfully rebased and updated refs/heads/main.
```

## Challenge 8: **Cherry-Picking Commits**

The "Cherry-Picking Commits" challenge involves creating a branch called ft/branch, adding a file test5.md, and committing it with the message "Implemented test 5". And then switch back to the main branch and use git cherry-pick to selectively apply that specific commit to main.
```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout -b ft/branch
Switched to a new branch 'ft/branch'
gymtwiyubake@Twiyubakes-iMac Git-Advanced % echo "This is test 5 content" > test5.md
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add test5.md
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Implemented test 5"
[ft/branch 09b1bcc] Implemented test 5
1 file changed, 1 insertion(+)
create mode 100644 test5.md
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 6 and 20 different commits each, respectively.
(use "git pull" to merge the remote branch into yours)
```

## Challenge 9: **Visualizing Commit History (Bonus)**

This challenge i explored using tools like git log --graph or a graphical Git client that can help visualize your commit history.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log --graph
* commit 230264b224f66c485257b78f36d88f526f72c02b (HEAD -> main)
| Author: Div-30 <divinpaul88@gmail.com>
| Date:   Tue Mar 4 11:03:43 2025 +0200
| 
|     Implemented test 5
| 
* commit 8d09434f4dd1711f47e3a6c97d7f1802ffdcffb6
| Author: Div-30 <divinpaul88@gmail.com>
| Date:   Tue Mar 4 10:45:11 2025 +0200
| 
|     Updating
| 
* commit cdbe2c8bc02c43ceb018447e2a2c8d8e262b8287
| Author: Div-30 <divinpaul88@gmail.com>
| Date:   Fri Feb 28 14:52:02 2025 +0200
| 
|     Create Test 6
| 
* commit 0bbe20866cd357a9a78b7d6ce253cec9c76267ca
| Author: Div-30 <divinpaul88@gmail.com>
| Date:   Fri Feb 28 14:51:45 2025 +0200
| 
|     Create Test 5
| 
* commit 01fa30f039469b33f99f0b7639d408f40c9a6396
| Author: Div-30 <divinpaul88@gmail.com>
| Date:   Wed Feb 26 11:35:25 2025 +0200
| 
|     Added test4.md file
| 
* commit 12f42671409bb12c077c77531358dbf41cfe79ab
| Author: Div-30 <divinpaul88@gmail.com>
| Date:   Wed Feb 26 11:32:15 2025 +0200
| 
|     chore: Create third and fourth files
| 
* commit 18a1f97a2549ed90a0207b700258e96e2930846e
| Author: Div-30 <divinpaul88@gmail.com>
| Date:   Wed Feb 26 11:31:42 2025 +0200
| 
|     chore: Create initial file and second file
| 
* commit ed3f4a6e0ceb96a1539ca644c608ddee15cbd77b
  Author: Div-30 <divinpaul88@gmail.com>
```

## Challenge 10: **Checking Out Detached HEAD**

The "Understanding Reflogs (Bonus)" challenge involves learning how Git reflogs track the history of branch and HEAD updates in the repository.


# PART 2 CHALLENGES

## Challenge 1: **Feature Branch Creation**
This challenge involves creating a new Git branch named ft/new-feature to work on a specific feature in isolation. You start by ensuring your repository has an initial commit on the main branch, then use git checkout -b ft/new-feature to create and switch to the new branch.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout -b feature-branch
Switched to a new branch 'feature-branch'
```

## Challenge 2: **Working on the Feature Branch**
This challenge involves working on a Git feature branch.
I created a file named feature.txt, added content, and committed it with a descriptive message.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % touch feature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add feature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git status
On branch feature-branch
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   feature.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html

gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Implemented core functionality for new feature"
[feature-branch 1456f8a] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log --oneline
1456f8a (HEAD -> feature-branch) Implemented core functionality for new feature
230264b (main) Implemented test 5
8d09434 Updating
cdbe2c8 Create Test 6
0bbe208 Create Test 5
01fa30f Added test4.md file
12f4267 chore: Create third and fourth files
18a1f97 chore: Create initial file and second file
ed3f4a6 Initial commit
```

## Challenge 3: **Switching Back and Making More Changes**
This challenge focuses on switching between Git branches during development.You  can switch to the main branch and create a readme.txt file with introductory content.The task ends with committing the changes using the message "Updated project readme."

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 7 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git branch
  feature-branch
  ft/branch
* main
gymtwiyubake@Twiyubakes-iMac Git-Advanced % touch readme.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add readme.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git status
On branch main
Your branch and 'origin/main' have diverged,
and have 7 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   readme.txt

gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "updated project readme"
[main d78fbd4] updated project readme
 1 file changed, 3 insertions(+)
 create mode 100644 readme.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log --oneline
d78fbd4 (HEAD -> main) updated project readme
230264b Implemented test 5
8d09434 Updating
cdbe2c8 Create Test 6
0bbe208 Create Test 5
01fa30f Added test4.md file
12f4267 chore: Create third and fourth files
18a1f97 chore: Create initial file and second file
ed3f4a6 Initial commit
```


  ## Challenge 4: **Local vs. Remote Branches**

  This challenge introduces the concept of local and remote branches in Git. Local branches exist on your machine, while remote branches are stored on a platform like GitHub.You learn to push a local branch to a remote repository using git push.You also practice pulling remote changes to 
  your local branch with git pull.

   ## Challenge 5: **Branch Deletion**

   This challenge teaches you to clean up a Git repository by deleting a feature branch.
   You start by merging the ft/new-feature branch (or ft/branch in your case) into main.
   Then, you delete the branch locally using git branch -d after ensuring its changes are integrated.

   ```
git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
gymtwiyubake@Twiyubakes-iMac Git-Advanced % echo "Some feature content" > feature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add feature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Added feature content"
[ft/new-feature 1628e3a] Added feature content
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 8 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git merge ft/new-feature
Updating d78fbd4..1628e3a
Fast-forward
 feature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git branch
  feature-branch
  ft/branch
  ft/new-feature
* main
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git branch -d ft/new-feature
Deleted branch ft/new-feature (was 1628e3a).
   ```

   ## Challenge 6: **Creating a Branch from a Commit**

   This challenge is about creating a Git branch from a specific point in my commit history. I  used git checkout -b ft/new-branch-from-commit with a commit hash to start the branch ft/new-branch-from-commit.

```
   gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log --oneline
1c79e1f (HEAD -> main) Test commit 1
1628e3a Added feature content
d78fbd4 updated project readme
230264b Implemented test 5
8d09434 Updating
cdbe2c8 Create Test 6
0bbe208 Create Test 5
01fa30f Added test4.md file
12f4267 chore: Create third and fourth files
18a1f97 chore: Create initial file and second file
ed3f4a6 Initial commit
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout -b ft/new-branch-from-commit d78fbd4
Switched to a new branch 'ft/new-branch-from-commit'
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git branch
  feature-branch
  ft/branch
* ft/new-branch-from-commit
  main
```

## Challenge 7: **Branch Merging**
This challenge involves integrating a feature branch into the main branch using Git. You merge ft/new-branch-from-commit into main with git merge, ensuring all changes are combined.

```
git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'
gymtwiyubake@Twiyubakes-iMac Git-Advanced % echo "New feature work" > newfeature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add newfeature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Added new feature content
dquote> 
dquote> '
dquote> "
[ft/new-branch-from-commit 61f5057] Added new feature content
 1 file changed, 1 insertion(+)
 create mode 100644 newfeature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 10 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git merge ft/new-branch-from-commit
Merge made by the 'ort' strategy.
 newfeature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 newfeature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log --oneline --graph
*   c6c398d (HEAD -> main) Merge branch 'ft/new-branch-from-commit'
|\  
| * 61f5057 (ft/new-branch-from-commit) Added new feature content
* | 1c79e1f Test commit 1
* | 1628e3a Added feature content
|/  
* d78fbd4 updated project readme
* 230264b Implemented test 5
* 8d09434 Updating
* cdbe2c8 Create Test 6
* 0bbe208 Create Test 5
* 01fa30f Added test4.md file
* 12f4267 chore: Create third and fourth files
* 18a1f97 chore: Create initial file and second file
* ed3f4a6 Initial commit
```

## Challenge 7: **Branch Merging**

This challenge introduces rebasing as a way to integrate a feature branch into main in Git. You rebase ft/new-branch-from-commit onto main using git rebase, placing its commits on top of main’s latest commit.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git merge ft/new-branch-from-commit
Merge made by the 'ort' strategy.
 newfeature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 newfeature.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log --oneline --graph
*   c6c398d (HEAD -> main) Merge branch 'ft/new-branch-from-commit'
|\  
| * 61f5057 (ft/new-branch-from-commit) Added new feature content
* | 1c79e1f Test commit 1
* | 1628e3a Added feature content
|/  
* d78fbd4 updated project readme
* 230264b Implemented test 5
* 8d09434 Updating
* cdbe2c8 Create Test 6
* 0bbe208 Create Test 5
* 01fa30f Added test4.md file
* 12f4267 chore: Create third and fourth files
* 18a1f97 chore: Create initial file and second file
* ed3f4a6 Initial commit
```

## Challenge 8: **Branch Rebasing**

This challenge introduces rebasing as a way to integrate a feature branch into main in Git. You rebase ft/new-branch-from-commit onto main using git rebase, placing its commits on top of main’s latest commit.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log --oneline --graph
*   c6c398d (HEAD -> ft/new-branch-from-commit, main) Merge branch 'ft/new-branch-from-commit'
|\  
| * 61f5057 Added new feature content
* | 1c79e1f Test commit 1
* | 1628e3a Added feature content
|/  
* d78fbd4 updated project readme
* 230264b Implemented test 5
* 8d09434 Updating
* cdbe2c8 Create Test 6
* 0bbe208 Create Test 5
* 01fa30f Added test4.md file
* 12f4267 chore: Create third and fourth files
* 18a1f97 chore: Create initial file and second file
* ed3f4a6 Initial commit
```

## Challenge 9: **Renaming Branches**

This challenge focuses on renaming a Git branch to improve its descriptiveness.You use git branch -m ft/new-branch-from-commit ft/improved-branch-name to change the branch name.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git branch
  feature-branch
  ft/branch
* ft/new-branch-from-commit
  main
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git branch -m ft/new-branch-from-commit ft/improved-branch-name
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git branch
  feature-branch
  ft/branch
* ft/improved-branch-name
  main
```

## Challenge 10: **Checking Out Detached HEAD**

This challenge explores the concept of a detached HEAD in Git, where HEAD points to a commit instead of a branch. You use git checkout <commit-hash> to detach HEAD and work at a specific point in history.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log --oneline
c6c398d (HEAD -> ft/improved-branch-name, main) Merge branch 'ft/new-branch-from-commit'
61f5057 Added new feature content
1c79e1f Test commit 1
1628e3a Added feature content
d78fbd4 updated project readme
230264b Implemented test 5
8d09434 Updating
cdbe2c8 Create Test 6
0bbe208 Create Test 5
01fa30f Added test4.md file
12f4267 chore: Create third and fourth files
18a1f97 chore: Create initial file and second file
ed3f4a6 Initial commit
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout 1c79e1f 
Note: switching to '1c79e1f'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 1c79e1f Test commit 1
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git branch
* (HEAD detached at 1c79e1f)
  feature-branch
  ft/branch
  ft/improved-branch-name
  main
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log --oneline
1c79e1f (HEAD) Test commit 1
1628e3a Added feature content
d78fbd4 updated project readme
230264b Implemented test 5
8d09434 Updating
cdbe2c8 Create Test 6
0bbe208 Create Test 5
01fa30f Added test4.md file
12f4267 chore: Create third and fourth files
18a1f97 chore: Create initial file and second file
ed3f4a6 Initial commit
```

# PART 3 CHALLENGES

## Challenge 1: **Stashing Changes**

This challenge involves using git stash to temporarily save uncommitted changes on the main branch.It simulates needing to pause work for an urgent task without losing your progress.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout main
Previous HEAD position was 1c79e1f Test commit 1
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 12 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % echo "Work in progress" > file.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add file.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % echo "More work" > another.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git status 
On branch main
Your branch and 'origin/main' have diverged,
and have 12 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   file.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        another.txt

gymtwiyubake@Twiyubakes-iMac Git-Advanced % git stash
Saved working directory and index state WIP on main: c6c398d Merge branch 'ft/new-branch-from-commit'
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git status
On branch main
Your branch and 'origin/main' have diverged,
and have 12 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        another.txt

nothing added to commit but untracked files present (use "git add" to track)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git stash list
stash@{0}: WIP on main: c6c398d Merge branch 'ft/new-branch-from-commit'
```

## Challenge 2: **Retrieving Stashed Changes**

This challenge focuses on retrieving previously stashed changes to resume work on the main branch.You use git stash pop to apply the most recent stash and remove it from the stash stack.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git stash pop
On branch main
Your branch and 'origin/main' have diverged,
and have 12 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   file.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        another.txt

Dropped refs/stash@{0} (f7b450bcbfa611ea2a9d3d51142afefc95d5fe48)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git status
On branch main
Your branch and 'origin/main' have diverged,
and have 12 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   file.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        another.txt

gymtwiyubake@Twiyubakes-iMac Git-Advanced % git stash list
gymtwiyubake@Twiyubakes-iMac Git-Advanced % 
```

## Challenge 3: **Branch Merging Conflicts (Continued)**
This challenge involves simulating and resolving a merge conflict between main and a feature branch in Git. I created conflicting changes in the same file on both branches and merged and manually fixed the conflicts.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout -b ft/conflict-branch
Switched to a new branch 'ft/conflict-branch'
gymtwiyubake@Twiyubakes-iMac Git-Advanced % echo "Feature branch version" > conflict.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add conflict.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Added feature branch change"
[ft/conflict-branch d32b57a] Added feature branch change
 2 files changed, 2 insertions(+)
 create mode 100644 conflict.txt
 create mode 100644 file.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout main 
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 12 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % echo "Main branch version" > conflict.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add conflict.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Added main branch change"
[main 1546465] Added main branch change
 1 file changed, 1 insertion(+)
 create mode 100644 conflict.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git merge ft/conflict.txt
merge: ft/conflict.txt - not something we can merge
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git merge ft/conflic-branch 
merge: ft/conflic-branch - not something we can merge
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git merge ft/conflict-branch
Auto-merging conflict.txt
CONFLICT (add/add): Merge conflict in conflict.txt
Automatic merge failed; fix conflicts and then commit the result.
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git status
On branch main
Your branch and 'origin/main' have diverged,
and have 13 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:
        new file:   file.txt

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both added:      conflict.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        another.txt

gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add conflict.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit
[main 2c890ba] Merge branch 'ft/conflict-branch'
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log --oneline --graph
*   2c890ba (HEAD -> main) Merge branch 'ft/conflict-branch'
|\  
| * d32b57a (ft/conflict-branch) Added feature branch change
* | 1546465 Added main branch change
|/  
*   c6c398d (ft/improved-branch-name) Merge branch 'ft/new-branch-from-commit'
|\  
| * 61f5057 Added new feature content
* | 1c79e1f Test commit 1
* | 1628e3a Added feature content
|/  
* d78fbd4 updated project readme
* 230264b Implemented test 5
* 8d09434 Updating
* cdbe2c8 Create Test 6
* 0bbe208 Create Test 5
* 01fa30f Added test4.md file
* 12f4267 chore: Create third and fourth files
* 18a1f97 chore: Create initial file and second file
* ed3f4a6 Initial commit
```

## Challenge 4: **Resolving Merge Conflicts with a Merge Tool**
This challenge explores using git mergetool to resolve merge conflicts visually and efficiently. You simulate or handle a conflict, then launch a merge tool to compare and edit conflicting files.
```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git config --global merge.tool meld
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout main
Already on 'main'
Your branch and 'origin/main' have diverged,
and have 15 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % echo "Main version" > conflict.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add conflict.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Main change"
[main 315f4cd] Main change
 1 file changed, 1 insertion(+), 1 deletion(-)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout -b ft/conflict-branch
fatal: a branch named 'ft/conflict-branch' already exists
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout conflict-branch
error: pathspec 'conflict-branch' did not match any file(s) known to git
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout ft/conflict-branch
Switched to branch 'ft/conflict-branch'
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add conflict.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Feature change"
[ft/conflict-branch b43d000] Feature change
 1 file changed, 1 insertion(+), 1 deletion(-)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 16 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git merge ft/conflict-branch
Auto-merging conflict.txt
CONFLICT (content): Merge conflict in conflict.txt
Automatic merge failed; fix conflicts and then commit the result.
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git mergetool
Merging:
conflict.txt

Normal merge conflict for 'conflict.txt':
  {local}: modified file
  {remote}: modified file
The merge tool meld is not available as 'meld'
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit
U       conflict.txt
error: Committing is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add conflict.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit
[main 0104c15] Merge branch 'ft/conflict-branch'
```

## Challenge 5: **Understanding Detached HEAD State**
This challenge involves detaching HEAD state in Git, where HEAD points to a commit instead of a branch.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout 315f4cd
Note: switching to '315f4cd'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 315f4cd Main change
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git branch
* (HEAD detached at 315f4cd)
  feature-branch
  ft/branch
  ft/conflict-branch
  ft/improved-branch-name
  main
gymtwiyubake@Twiyubakes-iMac Git-Advanced % echo "detached work" > temp.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add temp.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "detached commit"
[detached HEAD 56513b0] detached commit
 1 file changed, 1 insertion(+)
 create mode 100644 temp.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout main
Warning: you are leaving 1 commit behind, not connected to
any of your branches:

  56513b0 detached commit

If you want to keep it by creating a new branch, this may be a good time
to do so with:

 git branch <new-branch-name> 56513b0

Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 18 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout -b ft/detached-work  #
fatal: '#' is not a commit and a branch 'ft/detached-work' cannot be created from it
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout -b ft/detached-work   
Switched to a new branch 'ft/detached-work'
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log--oneline 
git: 'log--oneline' is not a git command. See 'git --help'.
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log --oneline
0104c15 (HEAD -> ft/detached-work, main) Merge branch 'ft/conflict-branch'
b43d000 (ft/conflict-branch) Feature change
315f4cd Main change
2c890ba Merge branch 'ft/conflict-branch'
1546465 Added main branch change
d32b57a Added feature branch change
c6c398d (ft/improved-branch-name) Merge branch 'ft/new-branch-from-commit'
61f5057 Added new feature content
1c79e1f Test commit 1
1628e3a Added feature content
d78fbd4 updated project readme
230264b Implemented test 5
8d09434 Updating
cdbe2c8 Create Test 6
0bbe208 Create Test 5
01fa30f Added test4.md file
12f4267 chore: Create third and fourth files
18a1f97 chore: Create initial file and second file
ed3f4a6 Initial commit

```

## Challenge 6: **Ignoring Files/Directories**
This challenge is about creating a .gitignore file to specify the exclusions.

```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % touch .gitignore
gymtwiyubake@Twiyubakes-iMac Git-Advanced % echo "/tmp" >> .gitignore
gymtwiyubake@Twiyubakes-iMac Git-Advanced % mkdir tmp 
gymtwiyubake@Twiyubakes-iMac Git-Advanced % touch tmp.txt
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git status
On branch ft/detached-work
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        another.txt
        conflict_BACKUP_2824.txt
        conflict_BASE_2824.txt
        conflict_LOCAL_2824.txt
        conflict_REMOTE_2824.txt
        tmp.txt

nothing added to commit but untracked files present (use "git add" to track)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add .gitignore
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Added /tmp to .gitignore"
[ft/detached-work 9618a3b] Added /tmp to .gitignore
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore
```

## Challenge 7: **Working with Tags**
This challenge involves how to use Git tags, which mark important points in the repository's history.
```
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 18 and 20 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git tag v1.0
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git tag
v1.0
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git push origin v1.0
Enumerating objects: 52, done.
Counting objects: 100% (52/52), done.
Delta compression using up to 8 threads
Compressing objects: 100% (40/40), done.
Writing objects: 100% (52/52), 4.41 KiB | 4.41 MiB/s, done.
Total 52 (delta 18), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (18/18), done.
To https://github.com/Div-30/Git-Advanced-Exercises.git
 * [new tag]         v1.0 -> v1.0
```
