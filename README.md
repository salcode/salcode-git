# salcode Git Configuration

## Git Aliases

### `git can-ff-merge [branch]`

Alias to check if merging `[branch]` into the current branch can be done as a fast-forward merge. (i.e. checks if current branch is an ancestor of `[branch]`). Note: This command supports using a single dash (`-`) to represent [the previous branch](https://salferrarello.com/git-previous-branch/).

See [Check If We Can Do a Git Fast-Forward Merge](https://salferrarello.com/check-can-do-git-fast-forward-merge/).

### `git d-b`

Alias for `git branch --delete @{-1}` to delete the previous branch.

See [Git Previous Branch](https://salferrarello.com/git-previous-branch/).

### `git dgone`

Alias to delete local branches that are gone on the remote. This combines `git fetch --prune` with processing the branches looking for those marked `[gone]`.

### `git drb`

Alias for `git push origin --delete $(git rev-parse --abbrev-ref HEAD)` to delete the remote branch with the same name as the current branch from the remote **origin**.

See [Deleting Remote Branches](https://git-scm.com/book/en/v2/Git-Branching-Remote-Branches#_delete_branches).

### `git is-up-to-date-with [branch]`

Alias to check if the current branch is up to date with `[branch]` (i.e. could we fast-forward merge our current branch into `[branch]`). Note: This command supports using a single dash (`-`) to represent [the previous branch](https://salferrarello.com/git-previous-branch/).

See [Is Git Branch Up to Date](https://salferrarello.com/is-git-branch-up-to-date/).

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

### `git rhu` (and `git frhu`)

Alias for `git reset --hard @{upstream}` to discard local changes and reset the branch to match the upstream (`@{upstream}`) branch.

`git frhu` does the same thing but performs a `git fetch` first to ensure we have the latest version of the upstream branch.

See [Replace Local Git Branch with Branch on GitHub](https://salferrarello.com/replace-local-git-branch-with-branch-on-github)

### `git shnpfb`

Alias for `git show --no-patch --format='%B'`, which gets the commit message from a commit.

### `git track-origin-same-branch-name`

Alias for `git branch --set-upstream-to=origin/$(git rev-parse --abbrev-ref HEAD)`.

See [There is no tracking information for the current branch](https://salferrarello.com/there-is-no-tracking-information-for-the-current-branch/).

## Configuration

### branch.sort

Set `branch.sort = -committerdate` to display the branches in descending order by commiter date (i.e. the most recent at the top).

### checkout.defaultRemote

Set `checkout.defaultRemote = origin` to avoid the error "matched multiple remote tracking branches" when running `git checkout`. With this setting, Git uses the remote `origin` when doing a `git checkout` (unless a different remote is explicitly defined).

See [Git matched multiple remote tracking branches](https://salferrarello.com/git-matched-multiple-remote-tracking-branches/).

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

### tag.sort

Set `tag.sort = -version:refname` to display tags sorted by version number with the highest version first.

See [Sort Git Tags by Version](https://salferrarello.com/sort-git-tags-by-version/).

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
