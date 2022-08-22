# salcode Git Configuration

## Git Aliases

### `git lg`

Decorated version of `git log --oneline --graph`.

See [Improve Git Log](https://salferrarello.com/improve-git-log/).

### `git please`

Alias for `git push --force-with-lease`.

See [Never use git push force](https://salferrarello.com/never-git-push-force/).

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
