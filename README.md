# tslide-presentations
A repo to house/keep tslide presentations.

## Some quick preliminaries

For vim, setup a [plugin manager](https://github.com/junegunn/vim-plug) and [here](https://github.com/junegunn/vim-plug/wiki/tips#automatic-installation). Basically, in your `.vimrc`. do

```
if empty(glob('~/.vim/autoload/plug.vim'))
  silent !curl -fLo ~/.vim/autoload/plug.vim --create-dirs
    \ https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
  autocmd VimEnter * PlugInstall --sync | source $MYVIMRC
endif
if empty(glob('~/.vim/autoload/plug.vim'))
  silent !curl -fLo ~/.vim/autoload/plug.vim --create-dirs
    \ https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
  autocmd VimEnter * PlugInstall --sync | source $MYVIMRC
endif

" Plugins will be downloaded under the specified directory.
call plug#begin('~/.vim/plugged')

" Declare the list of plugins.
Plug 'tpope/vim-sensible'
Plug 'junegunn/seoul256.vim'
Plug 'hjson/vim-hjson'

" List ends here. Plugins become visible to Vim after this call.
call plug#end()


```
