# salcode Git Configuration

## Git Aliases

### `git d-b`

Alias for `git branch --delete @{-1}` to delete the previous branch.

See [Git Previous Branch](https://salferrarello.com/git-previous-branch/).

### `git drb`

Alias for `git push origin --delete $(git branch --show-current)` to delete the remote branch with the same name as the current branch from the remote **origin**.

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

### `git track-origin-same-branch-name`

Alias for `git branch --set-upstream-to=origin/$(git branch --show-current)`.

See [There is no tracking information for the current branch](https://salferrarello.com/there-is-no-tracking-information-for-the-current-branch/).

## Configuration

### commit.verbose

Set `commit.verbose = true` to display the changes in the comments of the commit.

See [Git Preview Changes in Commit Message](https://salferrarello.com/git-preview-changes-in-commit-message/).

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
