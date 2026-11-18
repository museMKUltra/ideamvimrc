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

### Usage

Most shortcuts start with `z`. Several replace Vim's built-in `z` commands (e.g. folding with `zo`, `zc`, `zf`, `zd`).

Modes: `n` = Normal, `i` = Insert, `v` = Visual.

#### `~/.vimrc`

##### Settings

| Option | Description |
| --- | --- |
| `number` / `relativenumber` | Show the current line number and relative numbers for other lines |
| `clipboard=unnamed` | Yank and paste use the system clipboard |
| `hlsearch` / `incsearch` | Highlight matches, and search as you type |
| `ignorecase` | Search ignores case |

##### General

| Key | Modes | Description |
| --- | --- | --- |
| `zx` | i, v | Return to Normal mode (`<Esc>`) |
| `U` | n, v | Redo |

##### Location

| Key | Modes | Description |
| --- | --- | --- |
| `zh` | n, i, v | Go to the first non-blank character of the line |
| `zl` | n, i, v | Go to the end of the line |
| `zy` | n, i, v | Jump to the matching bracket (`%`) |
| `zt` | i | Scroll so the current line is at the top |
| `zb` | i | Scroll so the current line is at the bottom |
| `zz` | i | Type a literal `z` |

##### Selection

| Key | Modes | Description |
| --- | --- | --- |
| `z-` | n, i, v | Select the left side of an assignment (the part before `=`) |
| `z=` | n, i, v | Select the right side of an assignment (after `= `, up to `;`) |
| `z/` | n, i, v | Select from the first non-blank character to the end of the line |
| `z?` | n, i, v | Select from the second word up to `;`, e.g. the value in `return value;` |
| `z\` | n, i | Select whole lines from a line ending with a bracket to its matching bracket |
| `z\` | v | Extend the selection to the matching bracket |
| `z\|` | n, i | Select only the lines inside a block, without the bracket lines |
| `z\|` | v | Leave Visual mode, move down one line and jump to the matching bracket |

##### Insertion

| Key | Modes | Description |
| --- | --- | --- |
| `zs` | n, i | Insert `this` |
| `z;` | n, i, v | Add `;` to the end of the line |
| `z.` | n, i, v | Insert `=>` |
| `z,` | n, i, v | Insert `->` |
| `z<Space>` | n, i, v | Insert a space before the cursor and stay in Insert mode |

#### `~/.ideavimrc`

Includes every `~/.vimrc` shortcut above, plus:

##### Config

| Key | Modes | Description |
| --- | --- | --- |
| `zq` | n, v | Reload `~/.ideavimrc` |

##### Extensions

| Key | Modes | Extension | Description |
| --- | --- | --- | --- |
| `zg` | n, i, v | easymotion | Jump to a character in either direction (type a character, then the hint label) |
| `z'` `z"` `` z` `` | v | surround | Wrap the selection in quotes or backticks |
| `z(` `z[` `z{` `z<` | v | surround | Wrap the selection in brackets, with no inner spaces |
| `z>` | v | surround | Wrap the selection in a tag (prompts for the tag name) |

##### Multiple cursors

| Key | Modes | Description |
| --- | --- | --- |
| `<Space>` | v | Add the next occurrence of the selection |
| `<S-Tab>` | v | Remove the last added occurrence |
| `<S-Space>` | v | Select all occurrences |

##### IDE actions

| Key | Modes | Action | Description |
| --- | --- | --- | --- |
| `za` | n, v | `SurroundWith` | Surround with (if, try/catch, ...) |
| `zd` | n, v | `CodeCompletion` | Basic code completion |
| `zu` | n, v | `GotoNextError` | Go to the next error |
| `zi` | n, v | `ShowIntentionActions` | Show intention actions / quick fixes |
| `ze` | n, v | `FileStructurePopup` | File structure popup |
| `zw` | n, v | `ActivateTerminalToolWindow` | Open the terminal |
| `zk` | n, v | `MethodUp` | Go to the previous method |
| `zj` | n, v | `MethodDown` | Go to the next method |
| `zr` | n, v | `RenameElement` | Rename |
| `zc` | n, v | `IntroduceConstant` | Extract constant |
| `zv` | n, v | `IntroduceVariable` | Extract variable |
| `zf` | n, v | `IntroduceField` | Extract field |
| `zp` | n, v | `IntroduceParameter` | Extract parameter |
| `zm` | n, v | `ExtractMethod` | Extract method |
| `zn` | n, v | `Inline` | Inline |
| `zo` | n, v, i | `OptimizeImports` + `ReformatCode` + `RearrangeCode` | Clean up the file: optimize imports, reformat, rearrange |

## VS Code

Brings the same `z` shortcuts to VS Code.

### Extensions

- [Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim) (`vscodevim.vim`): required
- [Go to Next/Previous Member](https://marketplace.visualstudio.com/items?itemName=mishkinf.goto-next-previous-member): for `zk` / `zj`
- [im-select](https://github.com/daipeihust/im-select) (optional): switches the input method automatically when you leave Insert mode

### Files

Copy both files into your VS Code user folder. If you already have these files, merge the contents instead of overwriting them.

| OS | Folder |
| --- | --- |
| Windows | `%APPDATA%\Code\User\` |
| macOS | `~/Library/Application Support/Code/User/` |
| Linux | `~/.config/Code/User/` |

```shell
# macOS example
cp settings.json keybindings.json ~/Library/Application\ Support/Code/User/
```

> You can also open them from the Command Palette (`Ctrl+Shift+P`): **Preferences: Open User Settings (JSON)** and **Preferences: Open Keyboard Shortcuts (JSON)**.

#### `settings.json`

Vim options and every `z` mapping.

#### `keybindings.json`

VS Code shortcuts that VSCodeVim can't map by itself (`Shift+Space`, `Shift+Tab` in Visual mode).

### Usage

#### Settings

| Setting | Description |
| --- | --- |
| `editor.lineNumbers: relative` | Relative line numbers (`set number relativenumber`) |
| `vim.useSystemClipboard` | Yank and paste use the system clipboard (`set clipboard=unnamed`) |
| `vim.hlsearch` / `vim.incsearch` | Highlight matches, and search as you type |
| `vim.ignorecase` (`smartcase` off) | Search always ignores case |
| `vim.easymotion` / `vim.surround` | Turn on the easymotion and surround emulation |
| `vim.timeout: 300` | How long (ms) Insert mode waits after `z` for the second key |
| `vim.autoSwitchInputMethod.*` | Switch to English (`1033`) when leaving Insert mode, using `C:\tools\im-select.exe`. Change the path and code for your machine |
| `window.autoDetectColorScheme` | Follow the OS light/dark theme |

#### Ctrl keys

`vim.useCtrlKeys` is on, and `vim.handleKeys` decides who gets each key:

| Goes to | Keys |
| --- | --- |
| VS Code | `Ctrl` + `A` `C` `X` `V` `Z` `Y` `F` `H` `G` `L` `N` `P` `T` `W` `B` `J` `K` |
| Vim | `Ctrl` + `D` `U` `O` `I` `R` `E` `Q` |

> `Ctrl+V` pastes, so use `Ctrl+Q` for Visual Block mode.

#### Shortcuts

The General, Location, Selection and Insertion shortcuts work the same as in `~/.vimrc`, except:

- In Visual mode, only `zx`, `zh`, `zl`, `zy`, `z\` and `z|` work. The selection (`z-` `z=` `z/` `z?`) and insertion (`z;` `z.` `z,` `z<Space>`) shortcuts work in Normal and Insert mode only.
- `zy` also works after an operator, e.g. `dzy` deletes to the matching bracket.
- `zq` (reload config) doesn't exist. VS Code reloads `settings.json` when you save it.

##### Extensions

| Key | Modes | Extension | Description |
| --- | --- | --- | --- |
| `zg` | n, i | easymotion | Jump to a character (type a character, then the hint label) |
| `z'` `z"` `` z` `` | v | surround | Wrap the selection in quotes or backticks |
| `z(` `z[` `z{` `z<` | v | surround | Wrap the selection in brackets, with no inner spaces |
| `z>` | v | surround | Wrap the selection in a tag (prompts for the tag name) |

##### Multiple cursors

| Key | Modes | Command | Description |
| --- | --- | --- | --- |
| `<Space>` | v | `editor.action.addSelectionToNextFindMatch` | Add the next occurrence of the selection |
| `<S-Tab>` | v | `cursorUndo` | Remove the last added occurrence (`keybindings.json`) |
| `<S-Space>` | v | `editor.action.selectHighlights` | Select all occurrences (`keybindings.json`) |

##### IDE actions

| Key | Modes | Command | Description |
| --- | --- | --- | --- |
| `za` | n, i, v | `editor.action.surroundWithSnippet` | Surround with a snippet |
| `zd` | n, i | `editor.action.triggerSuggest` | Code completion |
| `zu` | n, i | `editor.action.marker.next` | Go to the next error |
| `zi` | n, i | `editor.action.quickFix` | Quick fix |
| `ze` | n, i | `workbench.action.gotoSymbol` | Go to a symbol in the file |
| `zw` | n, i | `workbench.action.terminal.toggleTerminal` | Toggle the terminal |
| `zk` | n, i | `gotoNextPreviousMember.previousMember` | Go to the previous member |
| `zj` | n, i | `gotoNextPreviousMember.nextMember` | Go to the next member |
| `zr` | n, i, v | `editor.action.rename` | Rename |
| `zc` | n, v | `refactor.extract.constant` | Extract constant |
| `zv` | n, v | `refactor.extract.variable` | Extract variable |
| `zf` | n, v | `refactor.extract.field` | Extract field |
| `zp` | n, v | `editor.action.refactor` | Open the Refactor menu (VS Code has no "extract parameter") |
| `zm` | n, v | `refactor.extract.function` | Extract function |
| `zn` | n, v | `refactor.inline` | Inline |
| `zo` | n, i | `editor.action.organizeImports` + `editor.action.formatDocument` | Clean up the file: organize imports, then format |

> The extract and inline commands only work when the language extension supports that refactoring.

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

