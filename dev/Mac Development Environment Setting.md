# 安装 Homebrew

## 什么是 Homebrew

Homebew 简称 brew，是 Mac OSX 上的软件包管理工具，能在 Mac 中方便的安装软件和卸载软件，可以说 Homebrew 是 mac 下的 apt-get、yum 神器。

## Homebrew 安装

Homebrew 安装非常简单，打开终端，复制、粘贴以下命令，回车即可。

```Shell
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

```

## Homebrew 常用命令

搜索软件：brew search 软件名，如 brew seach wget

安装软件：brew install 软件名，如 brew install wget

卸载软件：brew remove 软件名，如 brew remove wget

更多的，查看 Homebrew 官方网站：

[Homebrew]: https://brew.sh/index_zh-cn.html

# Shell 终端

Shell 可以用来执行命令，在 Mac 下打开 Terminal（终端）程序，会自动打开一个 Shell 命令行界面，而 Shell 每次在被打开（或执行）的时候都会自动加载默认未知文件 ~/.bash_profile。

## Shell 常用命令

- `cd` 跳转至目录
- `ls` 列出当前目录下的文件夹和文件
- `ls -la` 表示列出更多详细信息，包括隐藏文件
- `mv` 移动或重命名文件
- `touch` 新建文件
- `rm -r` 删除文件， `-r`参数表示递归删除目录
- `pwd` 显示当前目录
- `~` 波浪号表示当前用户根目录，一般用户的配置文件都放在这里
- `echo` 打印字符串或变量
- `>` 将结果输出至某文件中
- `cat` 输出文件的全部内容
- `du -sh *` 查看某目录下个文件和目录的大小
- `source` 执行某一个文件，通常 .bash_profile 修改后需要执行一下 source命令，或者新开一个 shell 来保证配置生效
- `natstat -an|grep 8080` 查看端口 8080 是否有进程占用

Mac 下默认的Terminal + bash 不够强大，推荐换成 iTerm2 + zsh，以下是具体的配置方法：

## 安装 iTerm2

iTerm2 是一个终端模拟器，官方网站：

[iTerm2]: http://www.iterm2.com/

## 更改配色方案

一般使用内置的配色方案就可以了：

依次打开 iTerm2 - Preferences - Profiles - Colors，在右下角的 Color Presets… 选择 Tango dark。

这是界面还是灰蒙蒙的，下面我们来回到彩色世界：

依次打开 iTerm2 - Preferences - Profiles - Text，在 Text Rendering 将第二项 Darw bold text in bright colors 前面的勾勾去掉，彩色界面就回来了。

## 呼出快捷键配置

依次打开 iTerm2 - Proferences - Keys，在 Hotkey 组里把三个勾都选上。

在第一个选项设置 Hotkey 为：⌥Space

子啊第二个选项选择：Hotkey Window

经过设置后，任何时候按一下⌥Space，都会在屏幕上半部弹出一个半透明的 Shell，在 Shell 外的任何地方单击一下 Shell 会消失。

## iTerm2 快捷键

- `⌘ + Click` 可以打开文件夹、文件和链接
- `⌘ + n` 新建窗口
- `⌘ + t` 新建标签页
- `⌘ + w` 关闭当前页
- `⌘ + 数字` & `⌘ + 方向键` 切换标签页
- `⌥⌘ + 数字` 切换窗口（不好用）
- `⌘ + enter` 切换全屏
- `⌘ + d` 左右分屏
- `⇧⌘ + w` 上下分屏
- `⌘ + ;` 自动补全历史记录
- `⇧⌘ + h` 自动补全剪贴板历史
- `⌥⌘ + e` 查找所有来定位某个标签页
- `⌘ + r`  & `⌃ + l` 清屏
- `⌘ + /` 显示光标位置
- `⌥⌘ + b` 历史回放
- `⌘ + f` 查找，然后用 `tab` 和 `⇧ + tab` 可以向右和向左补全，补全之后的内容会被自动复制，还可以用 `⌥ + enter` 将查找结果输入终端
- 选中即复制，鼠标中键粘贴

很多快捷键都是通用的，和 EMACS 等都是一样的

- `⌃ + u` 清空当前行
- `⌃ + a` 移动到行首
- `⌃ + e` 移动到行位
- `⌃ + f` 向前移动，和右方向键一致（我习惯用方向键）
- `⌃ + b` 向后移动，和左方向键一致（我习惯用方向键）
- `⌃ + p` 上一条命令，和上方向键一致（我习惯用方向键）
- `⌃ + n` 下一条命令，和下方向键一致（我习惯用方向键）
- `⌃ + r` 搜索历史命令
- `⌃ + h` 删除光标之前的字符
- `⌃ + d` 删除光标所指的字符
- `⌃ + w` 删除光标之前的单词
- `⌃ + k` 删除光标到行尾的内容
- `⌃ + t` 交换光标和之前的字符

## Zsh

Mac 系统自带了 Zsh，一般不是最新版本，通过 Hoembrew 可以安装最新版本

```shell
brew install zsh	
```

可以通过  `zsh --version` 命令查看 Zsh 的版本

使用 `echo $ZSH_VERSION` 命令查看当前使用的 Zsh 版本

修改默认 Shell

1. 在 /etc/shells 文件中加入如下一行

   ```
   /usr/local/bin/zsh
   ```

2. 然后运行命令

   ```
   chsh -s /usr/local/bin/zsh
   ```

## Oh My Zsh

Oh My Zsh 用来管理 Zsh 配置的，自带了好用的基本配置，基本都是 Zsh 的标配了，你不用再一步步重新配置 Zsh，可以节约很多宝贵的时间

项目主页：

[oh-my-zsh]: https://github.com/robbyrussell/oh-my-zsh

安装方法：

通过 curl

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

```

通过 wget

```Shell
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

```

配置文件所在的位置： `~/.zshrc`

- 连续按 tab, 能直接选择文件及文件夹，还可以使用 `⌃ + n/p/f/b` 来选择

- 直接输入文件名打开文件，可指定不同的后缀名用不同的程序打开。

  在配置文件中写入 `alias -s md=mvim`, 表明在命令行中输入 md 后缀的文件名，会用 mvim 打开 。

  又例如：`alias -s gz="tar -xzvf"`, 自动解压后缀为 gz 的压缩包 
  一些常用的压缩方式如下：

  ```shell
  alias -s tar="tar -xvf"
  alias -s gz="tar -xzvf"
  alias -s tgz="tar -xzvf"
  alias -s bz2="tar -xjvf"
  alias -s zip="unzip"
  ```

- `kill <tab>` 会自动列出进程，或者 `kill nginx`

- 支持递归，例如 `ls **/*` 列出当前目录下所有文件及目录，并递归目录

- 使 `man` 结果高亮显示，在配置文件中写入如下内容：

  ```shell
  # man page highlight
  export LESS_TERMCAP_mb=$'\E[01;31m'       # begin blinking
  export LESS_TERMCAP_md=$'\E[01;38;5;74m'  # begin bold
  export LESS_TERMCAP_me=$'\E[0m'           # end mode
  export LESS_TERMCAP_se=$'\E[0m'           # end standout-mode
  export LESS_TERMCAP_so=$'\E[38;5;246m'    # begin standout-mode - info box
  export LESS_TERMCAP_ue=$'\E[0m'           # end underline
  export LESS_TERMCAP_us=$'\E[04;38;5;146m' # begin underline
  ```

Oh My Zsh 本身自带了很多插件，不过基本都没有启用，插件目录 `~/.oh-my-zsh/plugins` 
例如启用插件 git, autojump osx, 需要在配置文件中加入如下内容

```Shell
plugins=(git autojump osx)
```

- osx 插件

  - `man-preview` 通过 preview 程序查看一个命令的手册
  - `quick-look` 快速预览文件
  - `pfd` 返回当前 Finder 打开的文件夹的路径
  - `cdf` 切换到当前 Finder 所在的目录

- autojump 插件

  需要先安装 autojump

  ```shell
  brew install autojump
  ```

  使用方法：

  ```shell
  j 目录名或目录名的一部分
  ```

  跳转到访问最多的目录

# 窗口控制软件 Spectacle

从官方主页下载并安装 Spectacle：

[Spectacle 主页]: https://www.spectacleapp.com/

常用快捷键：

- *Move to the left half* — ⌥⌘←
- *Move to the right half* — ⌥⌘→
- *Move to the top half* — ⌥⌘↑
- *Move to the bottom half* — ⌥⌘↓ 


- *Move to the upper left* — ⌃⌘←
- *Move to the lower left* — ⌃⇧⌘←
- *Move to the upper right* — ⌃⌘→
- *Move to the lower right* — ⌃⇧⌘→


- move a window to the next available display — ⌃⌥⌘→
- move a window to the previous display — ⌃⌥⌘←

# 软件卸载工具 App Cleaner & Uninstall

好用的软件卸载工具，通过App Store 下载

# Markdown 编辑工具 Typora

界面简洁，功能强大，用起来很顺手。

# 安装 Docker

到官方网站下载 Docker Mac版本

[Docker 官方网站]: https://www.docker.com/

然后点击安装，完成安装后，在 Preferences - daemon - Resgistry mirrors 设置加速器：

```Shell
http://6f410ddf.m.daocloud.io
```

# 数据库管理工具

- MySQL 数据库管理工具

  [Sequel Pro]: https://sequelpro.com/

# 安装 Composer

1. 手动下载 composer.phar

   ```Shell
   https://getcomposer.org/composer.phar
   ```

2. 把它变为全局指令

   ```bash
   mv composer.phar /usr/local/bin/composer
   ```

3. 修改权限

   ```shell
   sudo chmod a+x /usr/local/bin/composer
   ```

4. 安装国内镜像，再命令行窗口输入：

   ```Shell
   composer config -g repo.packagist composer https://packagist.phpcomposer.com
   ```

5. 提示：不要忘了经常执行 `composer selfupdate` 以保持 Composer 一直是最新版本哦！

# Laradock 设置

## 下载 laradock 和创建应用程序目录

1. 在 `~/Document` 里下载 laradock

   ```Shell
   git clone https://github.com/Laradock/laradock.git
   ```

2. 进入目录 laradock，执行

   ```shell
   cp env-example .env
   ```

3. 和 laradock 目录同级，创建项目目录 project1 和 project2，做法，在`~/Document`  里 git clone laravel

   ```shell
   git clone git@github.com:laravel/laravel.git
   ```

   把目录 `lavavel` 改为 `project1`

   用同样的方法，安装一个 Lumen 项目

   ```Shell
   git clone https://github.com/laravel/lumen
   ```

   把目录 `lumen` 改为 `project2`

4. 运行 laravel/lumen 如果出现空白，可能需要做下面两件事：

   ```shell
   chmod -R 777 storage bootstrap/cache
   ```

   ```Shell
   composer update
   ```

## 设置 laradock 环境变量

### 用 laradock_env 设置

在 `~/Document` 下载 laradock_env

```Shell
git clone git@github.com:bagart/laradock_env.git
```



### 自己设置

1. 设置 `laradock` 目录下的 .env，就是上面从  `env-example` 复制出来的文件。



# 安装 Node.js

到官方下载 node.js 的 mac 版本并安装

[官方网站]: https://nodejs.org/en/

