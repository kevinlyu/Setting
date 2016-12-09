##Vim 設定
macos 本身就有內建 vim 版本，但版本關係可能會無法使用 Vundle   
另外 macos 本身無法將內建版本刪除 ，
所以直接安裝其他版本在指定的目錄下比較方便  
最快速的方式就是使用homebrew去安裝，也可以自行從vim官網下載編譯  
使用brew安裝 vim :  

`brew install vim`  

設定bash設定檔：

```
alias vim="/usr/local/bin/vim"    
alias vimdiff="/usr/local/bin/vimdiff"      
alias vimtutor="/usr/local/bin/vimtutor"
```

###colors
vim 本身的 scheme 稍嫌不足, 這邊改用 [solarized](http://ethanschoonover.com/solarized)	
從官網下載後, 放入`~/.vim/colors`下, 若沒有colors, 自行創建  
對`~/.vimrc`做設定：

```
syntax enable	
syntax on		
set nu 	
set t_Co=256	
set background=dark	
colorscheme solarized
```  	
另外設定`~/.bash_profile` ：

`export TERM=xterm-256color`

##Vundle
Vundle 為 vim  知名套件管理(Vim 目前最新版似乎已經內建套件管理)

直接對`~/.vimrc`設定就能安裝：	

```
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
		Plugin 'gmarik/vundle'
		Plugin 'https://github.com/Valloric/YouCompleteMe.git'
call vundle#end()
```	

##YouCompleteMe
YouCompleteMe 是 Vim 套件中很方便的的套件, 支援許多語言
在 coding 上真的是超好用的套件！

安裝 YouCompleteMe, 需要先安裝Cmake：
#####For mac 
`brew install Cmake`
#####For ubuntu 
`sudo apt-get install build-essential cmake`

另外 ubuntu 還必須安裝 python dev 套件：

` sudo apt-get install python-dev

同樣對`~/.vimrc`做設定 :

`Plugin 'Valloric/YouCompleteMe'`

 bundle 安裝完後, 還需要去 Youcompleteme 安裝位置
 
####編譯 YouCompleteMe

**不需要 C family 補全:**

`./install.sh `

**需要C family的補全:**

`./install.sh --clang-completer`


##iterm2
[iterm2](https://www.iterm2.com/) 為 macos 上 terminal 取代品
本身就內建滿多原本 terminal 上沒有的功能 e.g. 自動完成指令


###Theme
前面有提到設定 zsh 的 theme, iterm 這邊本身也要去做設定,  
這邊採用 Solarized 的 Theme
iTerm 設定 選擇 Profiles -> Colors -> Load Presets，選擇 Solarized Dark
###字體
接著處理字體, 習慣採用 [power line](https://github.com/supermarin/powerline-fonts) 的字體
下載後, 自行選取要安裝的字體, 點兩下就能安裝  
最後到 iTerm 的設定裡面 Profiles -> Text, 裡面 Change Font 兩個都改成你剛剛安裝的字體
