## 在文件夹中 点开git命令 输入 git init 创建git 会在这个文件夹中生成一个 .git 的文件   .git所在的文件夹就是我们所称为的工作区  .git 就是git仓库  里面包含了暂存区 和 版本库


master/main  主分支（默认）旧版本就是master  新版本就是main因为种族歧视的原因改为main

git 本地操作
1. 添加 （添加到暂存区）
> 只有文件有修改才能实现添加  如果add的文件和暂存区的文件一样 那就加不了
    添加单个文件： git add 加上文件名
    添加目录里面的所有文件  git add 加上目录名字
    添加很多目录  git add .  加上所有的目录
    以上操作都只是将文件添加到暂存区 并没有进入版本库  没有记录 如果要加入版本库并产生记录 就要用新的命令

2. 提交 （把暂存区的内容提交到版本库）
    git commit 

    按 i 进入输入页面 就可以输入很多行备注  写完后退出输入状态  按esc键退出输入状态   然后按shift 加 冒号键 再加wq   保存并 退出


## git 常用辅助命令
    git status  查看仓库当前状态
    git log     显示提交日志  记录  添加 -m  "这里面添加备注"上传的文件做的什么功能就怎么备注

### 总结一下
    git add  添加文件到暂存区  加 . 就是添加所有
        > 前提是文件有修改
    git commit 提交到版本库 
        > 前提是暂存区的文件有修改了


### 一般工作中 上传的都是公司自己的电脑服务器 
以上都为本地操作  下面我想要上传 共享到远程服务器

远程仓库 （为了进行代码的共享 同步）公共服务器


### 关联是本地仓库关联远程仓库  所以我们的git命令页面要在需要关联的本地仓库打开才行

### http  关联远程仓库
git remote add origin（名字随便取） https://github.com/aaron-xie/laoxietest.git（地址在github中的地址）

git remote add  加名字（随便取）再加远程仓库的地址  地址再github里面的仓库地址

 git remote -v 查看 关联的远程仓库
### ssh 关联远程仓库

利用命令  ssh-keygen 会生成一个 .ssh的文件 在c盘麦本本 打开文件里面的 id_rsa.pub文件 里面的东西就公钥 复制 然后到github里面 点击头像出来下拉菜单倒数第二个 settings 再点击左边一栏中的 SSH and GPG keys 添加到服务器

# 命令行通过 git remote add origin 加地址这个地址是github里面的


详细可以观看 git视频 4

git push origin master 推送到远程仓库










1. git  init   先初始化git创建一个新的文件的时候使用这个操作在项目根目录生成一个 .git文件
2. git add 加上文件名或者目录名 加上 . 就是所有文件  ————  有修改的情况下将文件添加到暂存区

### gir add 的时候要注意过滤清单 把一些不必要的庞大的文件过滤掉不上传到远程仓库  在项目根目录创建一个文件名为 .gitignore 的文件 不是文件夹 详细过滤操作 请看本文件夹下的  .gitignore文件
 * 添加单个文件：`git add 文件`
            * 添加一个目录：`git add 目录名`
            * 添加当前目录：`git add .`
            ```bash
                git add ./js/home.js;
                git add ./js/
                git add .
            ```
3. git commit  将暂存区的文件提交到版本库 加上 -m 写备注 不写-m进入vim软件编写备注 按i进入输入状态 输入好之后 按esc键退出输入状态 再按shift加冒号键 再在地下输入wq wq的意思是保存并退出（记得切换英文输入）
4. git log 显示提交日志
5. 关联远程仓库
* git remote -v 查看关联的远程仓库
    1. http关联（设置简单但每次提交拉取都需要输入一次账户密码）
        git remote add origin(名字随便取) https://github.com/aaron-xie/laoxietest.git（地址在github中的地址）
        git push origin(名字上面取的名字) master(推送到远程仓库)
    2. ssh关联（设置相对复杂但以后上传拉去都不需要输入账户密码）
    利用命令  ssh-keygen 会生成一个 .ssh的文件 在c盘麦本本 打开文件里面的 id_rsa.pub文件 里面的东西就公钥 复制 然后到github里面 点击头像出来下拉菜单倒数第二个 settings 再点击左边一栏中的 SSH and GPG keys 添加到服务器

6. 同步远程与本地
    * 推送: git push origin master
        > 一定是本地比远程版本更加新
    * 拉取与合并: git pull origin master
        * 拉取: git fetch origin master
        * 合并: git merge origin/master
        > 有可能产生冲突，如果出现冲突，必须先要手动解决冲突，然后才能提交代码
# 以上可以观看git视频4详细操作

