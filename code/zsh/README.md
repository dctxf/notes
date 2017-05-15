# ZSH

## 安装

### 安装zsh

- Mac

Mac自带zsh，不用安装

- centos

```bash
yum install zsh
```

- ubuntu

```bash
apt-get install zsh
```

### [安装Git](../git/install.md)

### 安装Oh-My-Zsh

- 自动安装(**推荐**)

```bash
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
```

- 手动安装

```bash
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

## 配置

```bash
vim .zshrc
```
这里是一些别名设置，根据自己等需求做。把以下内容放进`.zshrc`

```vim
alias cls='clear'
alias ll='ls -l'
alias la='ls -a'
alias vi='vim'
alias javac="javac -J-Dfile.encoding=utf8"
alias grep="grep --color=auto"
alias -s html=mate   # 在命令行直接输入后缀为 html 的文件名，会在 TextMate 中打开
alias -s rb=mate     # 在命令行直接输入 ruby 文件，会在 TextMate 中打开
alias -s py=vi       # 在命令行直接输入 python 文件，会用 vim 中打开，以下类似
alias -s js=vi
alias -s c=vi
alias -s java=vi
alias -s txt=vi
alias -s gz='tar -xzvf'
alias -s tgz='tar -xzvf'
alias -s zip='unzip'
alias -s bz2='tar -xjvf'
```

### 主题配置

```bash
vim ~/.oh-my-zsh/themes/robbyrussell.zsh-theme
```

主题修改

```vim
PROMPT='%{$fg_bold[red]%}➜ %{$fg_bold[green]%}%p%{$fg[cyan]%}%d %{$fg_bold[blue]%}$(git_prompt_info)%{$fg_bold[blue]%}% %{$reset_color%}>'
#PROMPT='%{$fg_bold[red]%}➜ %{$fg_bold[green]%}%p %{$fg[cyan]%}%c %{$fg_bold[blue]%}$(git_prompt_info)%{$fg_bold[blue]%} % %{$reset_color%}'
```
对照原来的版本，把 c 改为 d，c 表示当前目录，d 表示绝对路径，另外在末尾增加了一个「 > 」

## 插件

- [autojump](https://github.com/wting/autojump)
- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)


## 拓展阅读

[终极 Shell——ZSH](https://zhuanlan.zhihu.com/p/19556676)