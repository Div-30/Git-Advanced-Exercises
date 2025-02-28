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
