# Work In Progress (WIP) option for git

Keep your work in progress in a dedicated branch where you can mess up all
you want. Each file change gets its own commit to allow for easier
rebase/cherry-pick. 

`git wip` create a new branch prefixed with `wip/` if not already done to keep
the mess in a dedicated and easy to identify branch.

## Usage
```
% git wip
```

## Saving Work In Progress

```
$ git branch
* master

$ git wip
M       README.md
Switched to branch 'wip/master'
[wip/master 6b3f206] [wip] README.md
 1 file changed, 2 insertions(+), 2 deletions(-)

[change in some file...]

$ git wip
[wip/master 840b762] [wip] README.md
 1 file changed, 12 insertions(+) 

$ git log master..wip/master
commit 840b762d92585dbd3b5dee20f5f58528523e6882 (HEAD -> wip/master)
Author: John <john@example.com>
Date:   Tue Sep 2 09:59:59 2025 +0200

    [wip] README.md

commit 6b3f206c829096d9e45951121156aeb54a508a4f
Author: John <john@example.com>
Date:   Tue Sep 2 09:57:32 2025 +0200

    [wip] README.md

```
Now you can:
* rebase/squash to prepare your commits in an appropriate manner
* cherry pick commits to your original branch
* push this work in progress to some remote to continue on another device
