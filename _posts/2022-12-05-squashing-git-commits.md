---
tags: [git]
---
If last X commits need to be squashed, then the git command will be `git rebase -i head~X`. So, for squashing
2 commits\:
> git rebase -i head~2

1. You will be presented with a list of commits in the default editor e.g vim with the oldest commit at the top. In vim, below is how the rebase commits will appear, with the older commit at top and newer commit below it.
![vim commit log for rebase](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Screenshot+2022-12-08+at+7.37.57+AM.png)
2. Change flag to `s` or `f` depending on whether a squash or fixup is needed. A squash will 
group all the selected commit messages under the oldest commit. A fixup on the other hand will
make the commit messages go away but retain the commit. Below is the how a fixup(flag `f`) will look like:
![fixup commit](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Screenshot+2022-12-08+at+7.39.06+AM.png)
3. Save and exit. Below is how the `fixed up` commits look like, the fixed up commit message has gone away.
![after fixup applied](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Screenshot+2022-12-08+at+7.39.51+AM.png)

> git push \-\-force origin master