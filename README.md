# salcode Git Configuration

## Git Aliases

### `git can-ff-merge [branch]`

Alias to check if merging `[branch]` into the current branch can be done as a fast-forward merge. (i.e. checks if current branch is an ancestor of `[branch]`)

See [Check If We Can Do a Git Fast-Forward Merge](https://salferrarello.com/check-can-do-git-fast-forward-merge/).

### `git d-b`

Alias for `git branch --delete @{-1}` to delete the previous branch.

See [Git Previous Branch](https://salferrarello.com/git-previous-branch/).

### `git drb`

Alias for `git push origin --delete $(git rev-parse --abbrev-ref HEAD)` to delete the remote branch with the same name as the current branch from the remote **origin**.

See [Deleting Remote Branches](https://git-scm.com/book/en/v2/Git-Branching-Remote-Branches#_delete_branches).

### `git lg`

Decorated version of `git log --oneline --graph`.

See [Improve Git Log](https://salferrarello.com/improve-git-log/).

### `git open-pr-github [targetBranch]`

Alias to open a GitHub URL for the current repo to create a pull request from the current branch into the `[targetBranch]`. If the `[targetBranch]` is not provided, the PR will target the default branch on the repo.

Note: This requires the upstream reference is defined for the current branch, so using `git push --set-upstream` (or `git push -u`) when pushing the branch is necessary.

See [Git Alias Open Pull Request on GitHub](https://salferrarello.com/git-alias-open-pull-request-github/).

### `git please`

Alias for `git push --force-with-lease`.

See [Never use git push force](https://salferrarello.com/never-git-push-force/).

### `git recover-rejected-commit`

Alias to create a commit and pre-fill the commit message with the most recent commit message entered. This is useful to recover a commit message when commit validation fails.

See [Recover failed Git commit message](https://salferrarello.com/recover-failed-git-commit-message/)

### `git track-origin-same-branch-name`

Alias for `git branch --set-upstream-to=origin/$(git rev-parse --abbrev-ref HEAD)`.

See [There is no tracking information for the current branch](https://salferrarello.com/there-is-no-tracking-information-for-the-current-branch/).

## Configuration

### blame.ignoreRevsFile

Set `blame.ignoreRevsFile = .git-blame-ignore-revs` to ignore any commits listed in the optional repo file `.git-blame-ignore-revs` when doing a `git blame`.

Additionally set `blame.markIgnoredLines = true` to "Mark lines that have a commit skipped using --ignore-rev with a `?`."

And set `blame.markUnblamableLines = true` to "Mark lines that were added in a skipped commit with a `*`."

See [A better git blame with --ignore-rev](https://michaelheap.com/git-ignore-rev/)

**Note**: This only works on Git version `2.23` (released 2019-08-16) or greater.

### commit.verbose

Set `commit.verbose = true` to display the changes in the comments of the commit.

See [Git Preview Changes in Commit Message](https://salferrarello.com/git-preview-changes-in-commit-message/).

### push.autoSetupRemote

Set `push.autoSetupRemote = true` to configure Git to treat `git push` as if it were `git push --set-upstream`. This helps with the "There is no tracking information for the current branch." message that can occur on `git pull` because now the tracking information is automatically set when you do a `git push`.

See [Git autoSetupRemote Prevents "no tracking information" Error](https://salferrarello.com/git-autosetupremote-prevent-no-tracking-information).

**Note**: This only works on Git version `2.38` (released 2022-10-03) or greater.

### push.default

Set `push.default = current` to define the behavior of `git push`

> push the current branch to update a branch with the same name on the receiving end

See Git config [push.default](https://git-scm.com/docs/git-config#Documentation/git-config.txt-pushdefault) and [Git push default – difference between simple, matching, current, etc.](https://rakhesh.com/coding/git-push-default/)

### rebase.autosquash

Set `rebase.autosquash = true` to move fixup commits to the appropriate position (and mark them fixup) when doing an interactive rebase.

See [Autosquashing Git Commits](https://thoughtbot.com/blog/autosquashing-git-commits)

## Installation

- Clone this repo into a location (e.g. `~/salcode-git`)  
```
git clone https://github.com/salcode/salcode-git.git ~/salcode-git
```
- Modify your default Git config file (`~/.gitconfig`) to include the config from this project. e.g. add  
```
[include]
  path = ~/salcode-git/gitconfig
```
