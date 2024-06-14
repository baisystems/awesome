# Awesome Git & GitHub

## rebase vs merge

When integrating changes from the main branch into your feature branch, you have two options: merging or rebasing. Let’s explore the differences between these approaches:

### Merge:
- Merging creates a new merge commit that combines the histories of both branches.
- It’s a non-destructive operation, meaning the existing branches remain unchanged.
- The feature branch will have an extraneous merge commit each time you incorporate upstream changes.
- If the main branch is very active, this can clutter your feature branch’s history.
- However, it’s straightforward and doesn’t alter the original commits.
- To merge the main branch into your feature branch, use:
    - git checkout feature
    - git merge main

### Rebase:
- Rebasing moves the entire feature branch to begin on the tip of the main branch.
- It re-writes the project history by creating brand new commits for each original commit.
- The benefit is a cleaner project history:
    - No unnecessary merge commits.
    - A linear project history, making navigation easier.
- To rebase your feature branch onto the main branch, use:
    - git checkout feature
    - git rebase main

## squash commits
```
$ git rebase -i <commit-sha>
$ git push -f origin <branch-nanme>
```
Note: When edit commits, leave the first commit as `pick`, change the rest commits as `squash`.

## amend a commit (avoid the need to squash all commits later)
```
$ git commit --amend
$ git push -f origin <branch-nanme>
```
Note: must do a force push at the end to overwrite the previous commit.
