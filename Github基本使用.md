## 前提

下载Git软件： [Git - 下载包 (git-scm.com)](https://git-scm.com/download/win) 

注册GitHub账号

## 命令行创建储存库

打开GitHub官网注册用户，完成之后，创建新的储存库

![1658221173960](D:\Typora\picture\1658221173960.png)

设置储存库的描述信息名称

![1658221393900](D:\Typora\picture\1658221393900.png)

现在我们在电脑上创建一个新的d盘下的目录，目录路径为：D:\Git\new project，项目都储存在这个目录下

打开cmd，切换到这个目录路径下面

```shell
C:\Users\嗑瓜子>d:
D:\>
D:\>cd D:\Git\new project 
```

```shell
#配置基本用户信息
D:\Git\new project>git config --global user.name 'milkQAQ'		##GitHub账号名
D:\Git\new project>git config --global user.email '2993013233@qq.com'		##邮箱
```

查看配置

```shell
D:\Git\new project>git config -l
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=D:/git/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager-core
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
user.name='milkQAQ'					#！！！
user.email='2993013233@qq.com'		 #！！！！
```



开始做GitHub项目

```shell
D:\Git\new project>git init			##创建一个新仓库
D:\Git\new project>git remote add origin https://github.com/milkQAQ/first-start.git		##把所在路径项目和GitHub账号远端下的项目进行关联
```

在D:\>cd D:\Git\new project目录下创建一个目录milk，在milk里面创建一个文本文档，里面写入 hello，world

使用cmd

```shell
D:\Git\new project>git status			##看本地目录发生了哪些变化，显示新增了一个milk目录	显示当前工作目录下的提交文件状态
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        milk/

nothing added to commit but untracked files present (use "git add" to track)
D:\Git\new project>git add *		##让目录生效，只是在本地生效，没有推送到远端	第一步	（将指定文件标记为将要提交的文件，这里*是代表所在路径下的所有文件）

D:\Git\new project>git commit -m 'first_commit'		##第二步	（创建一个提交并提供信息）
[master (root-commit) a0d43f3] 'first_commit'
 1 file changed, 1 insertion(+)
 create mode 100644 milk/1.txt
 D:\Git\new project>git push -u origin master		##向远程仓库推送目录数据，这一步需要用到浏览器，具体步骤靠自己记忆（这里已经成功推送）
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Writing objects: 100% (4/4), 262 bytes | 131.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/milkQAQ/first-start.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.
D:\Git\new project>git log							##显示提交历史
commit a0d43f3cea5f337e917deb6243f278192e831383 (HEAD -> master, origin/master)
Author: milkQAQ <2993013233@qq.com>
Date:   Tue Jul 19 17:26:16 2022 +0800

    'first_commit'
```

完成之后，刷新GitHub页面，出现了一个名为牛奶的本地目录文件夹（页面自动翻译成了中文，所以本名为milk的文件夹目录被翻译成了中文牛奶），上面我们所设置的提交信息将在推送的仓库后面显示："first_commit"

![1658224093223](D:\Typora\picture\1658224093223.png)



如果别人想把自己的项目搞到他的账号下面，进行以下操作

别人账号上操作：在GitHub上直接搜索自己的名称+项目名称：milkQAQ/milk，点击进去，在点击上面的Fork，这样就将自己的milk仓库转移到别人的账号下了

如果别人需要在自己的项目中进行修改，可以进行以下操作

别人账号上操作：在milk项目中，点击进行想修改的文件，进入之后，点击右边一个🖊的图标，之后就可以进行修改了，修改之后，点击最下面的commit changses，这样就可以将自己刚刚修改的变化保存到自己所有的文件中，但是自己的（也就是原文件所有者）的文件并没有进行修改

如果想让别人修改的变化让原文件所有者也进行相应的变化

那么点击GitHub首页中的pull requets，再点击 new pull requets，由于GitHub会自动将自己做的修改和原来的文件进行比对，所以在这个页面下显示所新增的修改部分，那么我们此时点击 create pull requets，把所修改的内容发送到原文件的所有者的账号下

在原文件所有者的账号下，在pull requets下，点击，有一个Update 文件，点击，如果发现没问题，可以修改，那么我们点击merge pull requets，点击comfirm merge就可以了



## 软件创建储存库

使用==gitkraken==使用GitHub		这是一款图形化的GitHub的软件，可以使用图形化进行远端仓库创建下载

下载gitkraken： [Download Free Git Client - Windows, Mac, Linux | GitKraken](https://www.gitkraken.com/download) 

选择GitHub账号登录

点击 on GitHub，创建一个储存库

![1658228844991](D:\Typora\picture\1658228844991.png)

创建完成之后显示以下界面	中间这个很大的空间，显示的是代码的所有提交历史，每提交一次，就会在这里显示一个分支，其中每一个分支都代表一个提交（commit），提交这个术语就像是游戏中的检查点，也可以叫做快照，每次对代码做出修改之后，我可以提交这一次的所有修改，此时Git会保存当前的代码快照，在之后的若干次修改之后，我们也可以轻松的回溯到这一次修改的状态，可以看到，这里唯一的一个提交是在新建代码仓库的时候自动创建的，我们点击这个Initial commit之后，可以看到这个提交中修改的所有文件 -->README.md，也就是右边的一个文件，

![1658228875946](D:\Typora\picture\1658228875946.png)

再点击右边自动创建的README.md界面转换为README.me文件中的内容

![1658228918388](D:\Typora\picture\1658228918388.png)

另外，在我们本地上也会自动创建一个相同的目录，其内容和上面一样，这个目录里所有新增的内容都是同步的

![1658229107247](D:\Typora\picture\1658229107247.png)



那么接下来，我们新建一个代码文件，并完成一次新的提交

我们可以先点击file中的“open in file manager”，之后会弹出下面界面，这个就是当前代码仓库在本地计算机上存放的位置

![1658229529885](D:\Typora\picture\1658229529885.png)

下面我们在这个目录下新创建一个文件，名为：hello.c，并向其中添加内容

![1658229694959](D:\Typora\picture\1658229694959.png)

将文件保存之后回到gitkraken中，我们可以看到在中间的“提交历史”中多出来了一项 WIP，代表这个提交“正在施工中”（working in progress），在右边我们可以看到多出来了一个我们刚刚创建的源代码文件，点击它也可以看到文件中被修改的具体内容，接下来我们提交这个文件

![1658229897482](D:\Typora\picture\1658229897482.png)

点击右边的 Stage file，Git要求在对修改的文件提交之前，必须将他们Stage，可以想象成提交之前的一个必经阶段，防止误操作，然后可以在下面的“commit Message”中，输入对这次代码提交的一个小总结，这个信息是必填的，我们想想看，如果我们面对的是一大堆无名的历史提交，想从中找出需要的如同大海捞针，最后点击下面的“commit changes to 1 file”完成这次提交，结果如下

![1658230405608](D:\Typora\picture\1658230405608.png)

到现在为止，我们所有的操作都是针对本地计算机上的代码仓库进行操作的，如果我们去浏览GitHub上的远程仓库，可以看到还是处于最原始的状态，如果我们希望将所有的提交都同步到远程的GitHub服务器上，我们需要使用gitkraken中的push(推送至远端服务器)功能，

我们只需要点击这个即可

![1658230581855](D:\Typora\picture\1658230581855.png)

推送之后，我们再次刷新GitHub页面，可以看到所有的代码已经成功上传上去了

![1658230761425](D:\Typora\picture\1658230761425.png)

如果我们点这里的commits，也可以看到和本地一样的所有的代码提交历史

![1658230833569](D:\Typora\picture\1658230833569.png)

