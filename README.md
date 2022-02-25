# Configuration 仅配置MAC本地端，不配置SERVER端

Mac+Iterm2+oh-my-zsh+p10k+tmux(or screen)

依赖
- iterm2
- Dracula
- zsh
- oh-my-zsh
- powerlevel10k
- autojump
- zsh-autosuggestions
- zsh-syntax-highlighting
- colorls
- tmux(or screen)

主要需要配置的文件包括: 
- ~/.bashrc  ~/.zshrc  ~/.p10k.zsh, 存放在 ./configuration_files 中
- 字体包在 ./fonts 中
- iterm2的Dracula主题在 ./iterm-Dracula


## 1. 安装 iTerm2 终端工具：

- 打开 iTerm2 官网, 直接点击 Download 下载并安装即可
- 推荐用 brew install cask iterm2 (我是GUI安装的)
- 官网下载主题 Dracula

## 2. 安装zsh

使用 brew 安装 zsh（Mac从2019年后好像自带的，好像是brew装的）
- brew install zsh 

## 3. 安装 oh-my-zsh

(查看GitHub官网)通过 curl 安装（我选择的方式）

- sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

- 安装过程中有一个步骤需要输入密码（是切换默认shell解释器的命令需要授权chsh -s /bin/zsh，因为我的mac默认shell解释器是bash，所以要切换到zsh），你可以通过cat /etc/shells来查看你的机器安装了哪些shell解释器

## 4. 安装 oh-my-zsh 的主题 - p10k

- 我们用的是 Oh My Zsh，所以这样安装 p10k 即可：
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k
# 然后需要打开 ~/.zshrc 设置 ZSH_THEME:
ZSH_THEME="powerlevel10k/powerlevel10k
```

- 安装字体 Nerd Fonts, [p10k官网](https://github.com/romkatv/powerlevel10k#set-colors-through-Powerlevel10k-configuration-parameters)手动下载安装 


## 5. 下载 oh-my-zsh 的插件 - ...

### autojump
- #.下载插件autojump到/.oh-my-zsh/custom目录中:
    git clone git://github.com/wting/autojump.git $ZSH_CUSTOM/plugins/autojump
- #.到目录autojump中:
    cd $ZSH_CUSTOM/plugins/autojump
- #执行install.py:
    ./install.py
- 也可以自己从网页上下载后再安装

### zsh-autosuggestions
- 终端命令自动推荐，会记录下来之前使用过的命令，当你输入开头时，会暗色提示之前的历史命令供你选择，可直接按右方向键选中该命令
```
# 克隆
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
# ~/.zshrc 中配置
plugins=(zsh-autosuggestions)
```

### zsh-syntax-highlighting
- 终端命令语法高亮
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# ~/.zshrc 中配置
plugins=(zsh-syntax-highlighting)
```

### colorls
- gem install colorls (国内网络问题安装不上)


## 6. 修改 VSCode 的终端

- VSCode 带的终端界面也可保持一致，只需简单设置字体即可, terminal font = MesloLGS NF


## Reference

- [zhihu-超全教程](https://www.zhihu.com/column/p/145437836)
- [个性化p10k配置](https://suixinblog.cn/2019/09/beautify-terminal.html)
- [个性化p10k配置](https://www.packetmania.net/2021/11/13/iTerm2-OMZ-Powerlevel10k/)
- [少数派Ternimal主题推荐](https://sspai.com/post/53008)
- [B站详细视频讲解](https://www.bilibili.com/video/BV19Z4y1P7ZL/?spm_id_from=autoNext)
- [B站讲解tmux](https://www.bilibili.com/video/BV1rb411t7kd?from=search&seid=15827394807027530041&spm_id_from=333.337.0.0)
- [大佬参考配置GitHub](https://github.com/wangshub/dotfile)
- [大佬参考配置GitHub](https://github.com/thehalfspace/dotfiles2)
- [洪鹤庭CSDN](https://blog.csdn.net/icestars/article/details/121098804?spm=1001.2014.3001.5501)