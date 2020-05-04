# tslide-presentations
A repo to house/keep tslide presentations.

## Some quick preliminaries

For vim, setup a (plugin manager)[https://github.com/junegunn/vim-plug] and (here)[https://github.com/junegunn/vim-plug/wiki/tips#automatic-installation]. Basically, in your `.vimrc`. do

```
if empty(glob('~/.vim/autoload/plug.vim'))
  silent !curl -fLo ~/.vim/autoload/plug.vim --create-dirs
    \ https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
  autocmd VimEnter * PlugInstall --sync | source $MYVIMRC
endif
```
