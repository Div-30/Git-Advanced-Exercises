# PART 1 CHALLENGES

## Challenge 1: Missing File Fix

### Evaluating the current status of my repository:
`gymtwiyubake@Twiyubakes-iMac Git-Advanced % git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
(use "git push" to publish your local commits)`

`Changes not staged for commit:
(use "git add/rm <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
deleted:    index.html`

`Untracked files:
(use "git add <file>..." to include in what will be committed)
[test4.md](http://test4.md/)`

`no changes added to commit (use "git add" and/or "git commit -a")`

### staging and adding the [test4.md](http://test4.md/) file and updating the commit message:

`gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add [test4.md](http://test4.md/)
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Added [test4.md](http://test4.md/) file"`

`[main 5dbdd2a] Added [test4.md](http://test4.md/) file
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 [test4.md](http://test4.md/)`

## Challenge 2: Editing Commit History

This challenge focuses on refining commit messages to ensure they remain clear and accurate throughout a project's history. For instance, we updated the commit message from the vague "Create another file" to the more precise "Create second file," better reflecting the action taken.

## Challenge 3: **Keeping History Tidy - Squashing Commits**

This challenge introduces the concept of squashing, a Git technique that consolidates multiple commits into a single, streamlined entry for a tidier project history. In this task, we merge the "Create second file" commit into the "Create initial file" commit, reducing clutter while preserving all changes.

`gymtwiyubake@Twiyubakes-iMac Git-Advanced % git rebase -i HEAD~5
[detached HEAD 18a1f97] chore: Create initial file and second file
Date: Wed Feb 26 11:31:42 2025 +0200
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 [test1.md](http://test1.md/)
create mode 100644 [test2.md](http://test2.md/)
Successfully rebased and updated refs/heads/main.
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git log`

## Challenge 4: **Splitting a Commit**

This challenge explores the use of git reset to refine a project’s commit history by splitting a single commit into multiple, distinct ones for improved clarity and tracking.

`gymtwiyubake@Twiyubakes-iMac Git-Advanced % touch test5 test6`

`gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add test5 test6`

`gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Create test 5 and test 6"
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
gymtwiyubake@Twiyubakes-iMac Git-Advanced % git add test6`

`gymtwiyubake@Twiyubakes-iMac Git-Advanced % git commit -m "Create Test 6"
[main cdbe2c8] Create Test 6
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test6`

## Challenge 5: **Advanced Squashing**

This challenge involves using Git’s interactive rebasing with the squash command to combine the last two commits, "Create test 5" and "Create test 6" into a single commit named "Create test 5 and test 6."

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
