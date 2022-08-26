# salcode Git Configuration

## Git Aliases

### `git d-b`

Alias for `git branch --delete @{-1}` to delete the previous branch.

See [Git Previous Branch](https://salferrarello.com/git-previous-branch/).

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

## Configuration

### commit.verbose

Set `commit.verbose = true` to display the changes in the comments of the commit.

See [Git Preview Changes in Commit Message](https://salferrarello.com/git-preview-changes-in-commit-message/).

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
