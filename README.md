# ideamvimrc

## References

- [How to open WebStorm from the terminal on MacOS](https://medium.com/@lucymarmitchell/how-to-open-webstorm-from-the-terminal-on-macos-b3de2f82b874)

## IntelliJ IDEA

### Plugins

#### IdeaVim 

Allows to use *vim* in editor

> Also includes extensions
- [vim-easymotion](https://github.com/easymotion/vim-easymotion)	 
- [vim-surround](https://github.com/tpope/vim-surround)	 

### Files

Copy files to root path directly (or write to files if exist)

```shell
cp vimrc.txt ~/.vimrc
cp ideavimrc.txt ~/.ideavimrc
```

#### `~/.vimrc`

For basic `vim` mode (even wihtout editor, e.g. terminal)

> Shortcuts for location, selection, insertion and so on.

#### `~/.ideavimrc`

For IdeaVim settings (also source `~/.vimrc` in file)

> Shortcuts for setting extensions and actions in editor.

## Git

### Files

#### `~/.gitconfig`

Git aliases for common commands.

Append the aliases to your global config (keeps your existing `[user]` and other settings):

```shell
cat .gitconfig >> ~/.gitconfig
```

Or include the file instead of copying it, so updates in this repo apply automatically:

```shell
git config --global include.path "$(pwd)/.gitconfig"
```

> Check that the aliases loaded: `git config --get-regexp ^alias\.`

### Aliases

| Alias | Command | Description |
| --- | --- | --- |
| `st` | `status` | Show working tree status |
| `ss` | `status -s` | Show short status |
| `ad` | `add` | Stage changes |
| `unstage` | `restore --staged .` | Unstage all staged changes |
| `cm` | `commit` | Commit |
| `cmm` | `commit -m` | Commit with message, e.g. `git cmm "feat: ..."` |
| `cma` | `commit --amend` | Amend the last commit |
| `rs` | `reset` | Reset current HEAD |
| `co` | `checkout` | Checkout branch or files |
| `cob` | `checkout -b` | Create and checkout a new branch |
| `sw` | `switch` | Switch branches |
| `br` | `branch` | List, create or delete branches |
| `mg` | `merge` | Merge branches |
| `df` | `diff` | Show changes |
| `ft` | `fetch` | Fetch from remote |
| `pl` | `pull` | Pull from remote |
| `ps` | `push` | Push to remote |
| `l` | `log --oneline --graph` | One-line graph of current branch |
| `la` | `log --oneline --graph --all` | One-line graph of all branches |
| `adog` | `log --all --decorate --oneline --graph` | Decorated one-line graph of all branches |
| `ls` | `log --graph --pretty=format:"%h <%an> %ar %s"` | Graph with hash, author, relative date and subject |
| `lg` | `log --pretty=format:'%an committed %h'` | Author and hash of each commit |

