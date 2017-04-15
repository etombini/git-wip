# Work In Progress (WIP) option for git

Keep your work in progress in a remote branch in order to make it available to all your workstations. 

## Usage
```
% git wip
Usage: git wip [get|push]
```

## Saving Work In Progress

```
% git branch -a
* master
  remotes/origin/master

% echo "some new stuff, but not done for real" >> test.txt

% git wip push
[...]

% git branch -a
  master
* wip-1492044696
  remotes/origin/master
  remotes/origin/wip-1492044696
```

Note: all previous WIP (`remotes/origin/wip-... `) stored on the remote server are deleted, local WIP is kept to allow rebasing.

## Getting Last Version Of Work In Progress

Current WIP is an old one (no fetch or no pull done yet)

```
% git branch -a
  master
* wip-1492043628
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
  remotes/origin/wip-1492043628 (<- does not exist anymore on the remote server)

```

Getting the latest WIP

```
% git wip get

% git branch -a
  master
  wip-1492043628
* wip-1492044696
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
  remotes/origin/wip-1492044696
```
Previous WIP is kept locally (`wip-1492043628`).


