## Backlog

An ordered list of work items (features, fixes, technical tasks)
that need to be built, prioritized from most to least important.
It is a living document — it grows and changes throughout the project.

## Branch protection

A set of rules that restricts changes to a branch. In this project,
changes to `main` are only allowed through a pull request.

## Pull request

A request to merge the changes of one branch into another branch,
allowing review before the merge.

## Merge commit

A commit that joins the histories of two branches. It has two
parent commits.

## Fast-forward

A merge in which the target branch has no new commits, so Git
just moves its pointer forward without creating a merge commit.

## Staging

The step where changes are marked with `git add` to be included
in the next commit. Staged files are ready to commit; tracked
files are simply those Git already knows about.
