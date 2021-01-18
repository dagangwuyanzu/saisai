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
git remote add origin https://github.com/aaron-xie/laoxietest.git

git remote add  加名字（随便取）再加远程仓库的地址

 git remote -v 查看
### ssh 关联远程仓库

利用命令  ssh-keygen 会生成一个 .ssh的文件 在c盘麦本本 打开文件里面的 id_rsa.pub文件 里面的东西就公钥 复制 然后到github里面 点击头像出来下拉菜单倒数第二个 settings 再点击左边一栏中的 SSH and GPG keys 添加到服务器

# 命令行通过 git remote add origin 加地址这个地址是github里面的


详细可以观看 git视频 4