## git-merge-pr: apply GitHub pull requests from command-line

## Usage

	git merge-pr [PRNUM][@REMOTE] [GIT-AM FLAGS...]

`git merge-pr` will fetch the patch corresponding to pull request
number PRNUM of REMOTE repository (defaults to your upstream) and
applies it on top of the current tree, rewriting the commit message of
the newest patch to close the pull request upon push (can be disabled
by setting `merge-pr.autoclose` to false).

Without PRNUM, all open pull requests of REMOTE will be listed.

Useful `git am` flags:

* `--signoff`
* `--3way`
* `--interactive`

## Why rebasing pull requests is preferable to merging them

* Keeps a linear history without merge bubbles.
* Properly keeps author and committer name as well as author and commit date.
* Conflicts can easily be dealt with in an ad-hoc fashion.
* Interactive mode allows for on-the-fly cherry picking.

## Requirements

* Git 2.8.0 or newer
* wget
* jq (only for listing pull requests)

## Copyright

git-merge-pr is in the public domain.

To the extent possible under law,
Leah Neukirchen <leah@vuxu.org>
has waived all copyright and related or
neighboring rights to this work.

http://creativecommons.org/publicdomain/zero/1.0/
