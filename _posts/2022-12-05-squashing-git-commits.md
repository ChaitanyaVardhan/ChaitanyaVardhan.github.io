---
tags: [git]
---
> git rebase -i head~2

1. You will be presented with a list of commits in the default editor e.g vim with the oldest commit at the top
2. Change flag to s or f depending on whether a squash or fixup is needed. A squash will 
group all the selected commit messages under the oldest commit. A fixup on the other hand will
make the commit messages go away.
3. Save and exit.

> git push \-\-force origin master