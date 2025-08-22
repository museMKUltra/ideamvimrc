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

