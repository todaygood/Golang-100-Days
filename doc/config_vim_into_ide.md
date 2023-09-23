# Config vim to Golang-IDE in linux 

根据 https://my.oschina.net/u/3287304/blog/1559952

1. upgrade vim  to 8.0 latest

[root@cloud-sz-kolla-b13-01 yum.repos.d]# cat vim.repo 

[vim-latest]
name=vim 
baseurl=http://mirror.ghettoforge.org/distributions/gf/el/7/plus/x86_64/
enabled=1
skip_if_unavailable=1
gpgcheck=0

yum install -y cmake vim 

vim安装完成后查看，然后查看vim版本号中的python是否支持,
[root@cloud-sz-kolla-b13-01 ~]# vim --version |grep python 
+cryptv          +linebreak       +python/dyn      +vreplace
+cscope          +lispindent      -python3         +wildignore

+python表示支持python插件编写。


2. modify .vimrc for plugin  

```conf
"""""""""""""""""""""""""""""""""" vundle needed begin """""""""""""""""""""""""""""""""""""
set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" golang
Plugin 'fatih/vim-go'
Plugin 'Valloric/YouCompleteMe'
Plugin 'majutsushi/tagbar'
"Plugin 'scrooloose/nerdtree'
"Plugin 'ludovicchabant/vim-gutentags'
"Plugin 'vim-php/tagbar-phpctags.vim'
Plugin 'ctrlpvim/ctrlp.vim'

" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required
" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line
"""""""""""""""""""""""""""""""""" vundle needed end """""""""""""""""""""""""""""""""""""
```
加入到.vimrc开头处，在命令行vim，进入命令模式
:PluginInstall 
安装插件



3. Install go-tool 

cd $GOPATH 

go get -u -v golang.org/x/tools/...

注意，需要翻墙。

4. vim-go插件安装
vim 进入命令模式

:GoInstallBinar
安装完成后，你的vim基本就ok了ies


此时，你的vim就可以关键字显示，代码自动提示补全了,还有以下命令可用：

:colorscheme molakai 切换到molakai 配色，隔一段时间换一下，感觉会不一样
:TagbarToggle 显示tag window
:NERDTreeToggle  显示文件directory 

[我的vimrc](https://github.com/todaygood/my-backup/blob/master/vimrc_for_go_python)

如有更多的功能需求，可参见[这个vimrc](https://github.com/1046102779/goide/blob/master/.vimrc)

# Refer docs 

[vim-as-ide](https://github.com/yangyangwithgnu/use_vim_as_ide)
[config-vim-for-golang](https://github.com/Unknwon/wuwen.org/issues/7)






# Issue 

https://github.com/todaygood/go_repo/issues/6

https://github.com/todaygood/go_repo/issues/5




