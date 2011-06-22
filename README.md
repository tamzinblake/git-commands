## git-commands ##

These are some git commands I like to have around, written for the unix shell

They both invoke `git status` as a cheap way to die if you're not in a git repository.

## git rebase-all ##

Rebases all of your local branches on master.  Skips any local branches that track a remote branch, as well as any branches whose names begin with `z_` (sleepy branches).

If any of them have conflicts, it stops so you can fix them and do a `git rebase--continue`, after which you can run `git rebase-all` again to continue.

## git deploy ##

Intended to be used after a local branch is rebased and ready to be fast-forward merged onto master and pushed.

Usage:
  `git deploy branch`

where `branch` is the name of the branch to merge.

Does a quick pull of master and rebase to insist that the merge is fast-forward no matter what, then does the fast-forward merge onto master and pushes.
