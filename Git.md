## 版本控制，（版本迭代，版本更新)

在开发的过程中用于管理文件、目录或工程等内容的修改历史，方便查看和更改历史记录，备份以便回复以前版本的软件工程技术

主流的版本控制包括

Git

SVN

等

Git作为分布式版本控制系统，是目前最为先进的。

下面是Git的下载

https://git-scm.com/

或者淘宝的镜像

http://npm.taobao.org/mirrors/git-for-windows/

Git下分为三个程序，分别为：

**Git Bash：**Unix与Linux风格的命令行，使用最多，推荐最多

**Git CMD：**Windows风格的命令行

**Git GUI**：图形界面的Git

## 常用的Linux命令

```Linux
1）cd : 改变目录。
2）cd . . 回退到上一个目录，直接cd进入默认目录
3）pwd : 显示当前所在的目录路径。
4）ls(ll):  都是列出当前目录中的所有文件，只不过ll(两个ll)列出的内容更为详细。
5）touch : 新建一个文件 如 touch index.js 就会在当前目录下新建一个index.js文件。
6）rm:  删除一个文件, rm index.js 就会把index.js文件删除。
7）mkdir:  新建一个目录,就是新建一个文件夹。
8）rm -r :  删除一个文件夹, rm -r src 删除src目录
9）mv 移动文件, mv index.html src index.html 是我们要移动的文件, src 是目标文件夹,当然, 这样写,必须保证文件和目标文件夹在同一目录下。
10）reset 重新初始化终端/清屏。
11）clear 清屏。
12）history 查看命令历史。
13）help 帮助。
14）exit 退出。
15）#表示注释
```

查看git的配置文件 git config -l

查看相关的配置文件：

1）、Git\etc\gitconfig  ：Git 安装目录下的 gitconfig   --system 系统级

2）、C:\Users\Administrator\ .gitconfig   只适用于当前登录用户的配置  --global 全局

![image-20220306152312751](D:\Git\Git.assets\image-20220306152312751.png)

### 设置用户名和邮箱

每次使用Git提交的时候都会使用该信息并且嵌入到提交中，当然这一部分信息是可以通过配置来进行修改的，利用这一部分命令，将用户的配置修改。

![image-20220306152710543](D:\Git\Git.assets\image-20220306152710543.png)

![image-20220306152938563](D:\Git\Git.assets\image-20220306152938563.png)

当然也可以用system命令

![image-20220306153144400](D:\Git\Git.assets\image-20220306153144400.png)

![image-20220306153155142](D:\Git\Git.assets\image-20220306153155142.png)

在进行命令配置后会有直接的响应

## Git基本理论

git本地有三个工作区域：工作目录（Working Directory）、暂存区(Stage/Index)、资源库(Repository or Git Directory)，如果加上远程的git仓库(Remote Directory)就可以分为四个工作区域：

![图片](D:\Git\Git.assets\641.png)

- Workspace：工作区，就是你平时存放项目代码的地方
- Index / Stage：暂存区，用于临时存放你的改动，事实上它只是一个文件，保存即将提交到文件列表信息
- Repository：仓库区（或本地仓库），就是安全存放数据的位置，这里面有你提交到所有版本的数据。其中HEAD指向最新放入仓库的版本
- Remote：远程仓库，托管代码的服务器，可以简单的认为是你项目组中的一台电脑用于远程数据交换

本地的三个区域确切的说应该是git仓库中HEAD指向的版本：

![图片](D:\Git\Git.assets\640.png)

- Directory：使用Git管理的一个目录，也就是一个仓库，包含我们的工作空间和Git的管理空间。
- WorkSpace：需要通过Git进行版本控制的目录和文件，这些目录和文件组成了工作空间。
- .git：存放Git管理信息的目录，初始化仓库的时候自动创建。
- Index/Stage：暂存区，或者叫待提交更新区，在提交进入repo之前，我们可以把所有的更新放在暂存区。
- Local Repo：本地仓库，一个存放在本地的版本库；HEAD会只是当前的开发分支（branch）。
- Stash：隐藏，是一个工作状态保存栈，用于保存/恢复WorkSpace中的临时状态。

### git的工作流程

1、在工作目录中添加、修改文件；

2、将需要进行版本管理的文件放入暂存区域；

3、将暂存区域的文件提交到git仓库

所以git管理的文件有已修改（modified）,已暂存（staged）,已提交(committed)这样的三种状态

![图片](D:\Git\Git.assets\640.jpeg)

## Git项目搭建

### 创建工作目录与常用指令

工作目录一般是Git管理的文件夹，建议不要有中文

有pull add checkout commit push fetch/clone这六个命令

![图片](D:\Git\Git.assets\640.png)

本地仓库搭建，一种是建立全新的仓库，另一种是克隆远程仓库

#### 建立远程仓库

该命令用到了GIT管理的项目的根目录执行

我们可以用上文提到的pwd命令看看我们目前所处的位置：

![image-20220306161130804](D:\Git\Git.assets\image-20220306161130804.png)

这个目录不是我们想要的

所以我们用cd命令来转入到目标的文件夹中，并且利用ll命令查看目前文件夹中的文件

![image-20220306161334878](D:\Git\Git.assets\image-20220306161334878.png)

此时我之前通过mkdir命令创建了test文件夹

我们进去，然后创建一个仓库

![image-20220306161459168](D:\Git\Git.assets\image-20220306161459168.png)

当然也可以使用clone命令将远程服务器上的仓库镜像一份至本地

例如https://github.com/nonstriater/Learn-Algorithms.git

建议开启git加速（该网址克隆可能会有问题

![image-20220306162919510](D:\Git\Git.assets\image-20220306162919510.png)

https://github.com/labuladong/fucking-algorithm.git

![image-20220306163849880](D:\Git\Git.assets\image-20220306163849880.png)

![image-20220306165234009](D:\Git\Git.assets\image-20220306165234009.png)

## Git文件操作

### 文件的四种状态

版本控制就是对于文件的版本控制，要求对于文件进行修改、提交等操作，当然我们需要知道文件的四种状态

- Untracked: 未跟踪, 此文件在文件夹中, 但并没有加入到git库, 不参与版本控制. 通过git add 状态变为Staged.
- Unmodify: 文件已经入库, 未修改, 即版本库中的文件快照内容与文件夹中完全一致. 这种类型的文件有两种去处, 如果它被修改, 而变为Modified. 如果使用git rm移出版本库, 则成为Untracked文件
- Modified: 文件已修改, 仅仅是修改, 并没有进行其他的操作. 这个文件也有两个去处, 通过git add可进入暂存staged状态, 使用git  checkout 则丢弃修改过, 返回到unmodify状态, 这个git checkout即从库中取出文件, 覆盖当前修改 !
- Staged: 暂存状态. 执行git commit则将修改同步到库中, 这时库中的文件和本地文件又变为一致, 文件为Unmodify状态. 执行git reset HEAD filename取消暂存, 文件状态为Modified

### 查看文件状态

```git
#查看指定文件状态
git status [filename]
#查看所有文件状态
git status
```

### 忽略文件

当我们不想把文件纳入到版本控制中，我们可以在主目录下面建立".gitignore"文件，此文件有如下规则：

1.忽略文件中的空行或以井号（#）开始的行将会被忽略。

2.可以使用Linux通配符。例如：星号（*）代表任意多个字符，问号（？）代表一个字符，方括号（[abc]）代表可选字符范围，大括号（{string1,string2,...}）代表可选的字符串等。

3.如果名称的最前面有一个感叹号（!），表示例外规则，将不被忽略。

4.如果名称的最前面是一个路径分隔符（/），表示要忽略的文件在此目录下，而子目录中的文件不忽略。

5.如果名称的最后面是一个路径分隔符（/），表示要忽略的是此目录下该名称的子目录，而非文件（默认文件或目录都忽略）

```
#依然是以#为注释
*.txt        #忽略所有 .txt结尾的文件,这样的话上传就不会被选中！
!lib.txt     #但lib.txt除外
/temp        #仅忽略项目根目录下的TODO文件,不包括其它目录temp
build/       #忽略build/目录下的所有文件
doc/*.txt    #会忽略 doc/notes.txt 但不包括 doc/server/arch.txt
```

![image-20220306170152957](D:\Git\Git.assets\image-20220306170152957.png)

## 上传

设置本机绑定SSH公钥，实现免密码登录

![image-20220306170610838](D:\Git\Git.assets\image-20220306170610838.png)

输入

ssh-keygen 

将产生的id_rsa.pub文件打开并且写入到GitHub中去

https://github.com/reatcat/GIt.git

在我们的GitHub上面创建一个项目

由于GitHub的外网被墙，所以改用

[码云]: https://gitee.com/

我们首先在码云上创建一个项目，然后再本地建一个仓库

然后cd到本地目录下执行

```
git init
```

将项目的所有的文件添加到仓库中，然后使用命令

```
git add .
```

![image-20220306195654481](D:\Git\Git.assets\image-20220306195654481.png)

之后利用

```
git status
```

查看自己的更改

之后使用

```
git commit -m "注释"
```

随后将本地仓库关联到GitHub新建的仓库上

```
git remote add origin [filename]
```

使用pull命令

```
git pull origin master
```

可以将文件拉下来

使用命令

```
git push -u origin master
```

可以上传到远程仓库

这个时候如果GitHub上有新的文件，，可以先下载下来

```
git pull --rebase origion master
```

切换用户：

 git clone -b branch_name http：//xxx (-b指分支)

   cd branch_name

　再执行push操作

git新建分支并提交本地代码到远程分支

　　step1，在本地新建分支

　　　　　　git branch newbranch

　　step2：把本地分支push到远程

　　　　git push origin newbranch

　　step3：切换到该分支

　　　　git checkout newbranch

　　step4：查看本地修改

　　　　git status

　　step5：添加本地修改

　　　　git add .

　　step6：commit修改

　　　　git commit -m 'XXXX'

　　　step7：push代码

　　　　git push

git://github.com/reatcat/git.git

