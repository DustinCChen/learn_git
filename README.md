## git operation
```sh
ls -aL # show hidden files
git config --list # show config
# git config 作用域
git config --local user.name "dustin.chen" ## local
git config --system user.name "dustin.chen" ## system 
git config --global user.name "dustin.chen" ## global
git config --list --global
git config --list --system
git config --list --local ## 只能用于某个仓库git
# Initial config
git config --global user.name "dustin.chen"
git config --global user.email "648023262@qq.com"
git config --global color.ui auto
git status
touch index.html
git add .
git status
git commit -m "create learn_git.html"
git status # 红色的是未暂存的（位于工作区），绿色的是未提交的（位于stage暂存区，还没有提交到版本库）
git log
git restore --staged learn_git.html
git commit -m "add index.html"
git remote add origin git@github.com:DustinCChen/learn_git.git 
git remote -v # show remote repo

# set SSH Key
ssh-keygen -t rsa -C "648023262@qq.com"
cat ~/.ssh/id_rsa.pub # add SSH Key
cat /Users/dustchen/.ssh/id_rsa.pub # add SSH Key
ssh -T git@github.com   # test SSH Key

# push to remote repo
# git clone https://github.com/DustinCChen/dev_nestjs.git 不建议https clone，建议使用SSH clone
git push -u origin main
cd dev_nestjs/
git add .
git commit -m "my first commit"
git push -u origin main
# sync remote repo update to local repo
git remote add origin https://github.com/DustinCChen/dev_nestjs.git
git pull origin main
git status
git checkout -- .
git pull origin main

# 从零开始创建一个项目
git init git_demo
git config --local user.name 'dust.chen'
git config --local user.email 'dust.chen@outlook.com'
git add .
git commit -m "update README.md"
git add -u ##  add update
git mv Mermaid.md  mermaid.md
git reset --soft HEAD^ ##  reset,one commit,HEAD是头指针,指向标记现在工作区所在的记录,只移动HEAD指针，暂存区和工作目录中的更改都会保留在工作目录中，以便再次提交。
git reset --hard  [版本号] ## 回退命令,移动 HEAD 指针并重置索引和工作区，彻底删除了提交以及暂存区和工作区的修改，慎用，因为会导致工作区的内容丢失。
git reset --mixed [版本号]# mixed或不带选项（默认）：移动 HEAD 指针并重置索引，不会修改工作区，撤销了提交和暂存的更改，但保留了工作区的修改。
git reflog ## 查看git所有的日志操作记录,是后悔药,git reset 回退会影响工作区,
touch README2.md
git add README2.md
git commit -m "add README2.md"
git rm README2.md ##  remove
touch README3 
git add README3
git commit -m "add README3"
git log 
#  变更文件名称，直接使用git mv
git mv README3 README3.md
git status ## renamed:    README2 -> README2.md
git log -n4 # 查看最近4个提交记录
git log --graph # 绘制图
git branch -v # 查看分支
git log --oneline --graph # 绘制图
git log --oneline #  view a concise log of commits in Git
git checkout -b temp ed01860 # 创建临时分支
vim README2.md
git commit -am "update README2.md"
git branch -av
git log --all --graph
gitk # GitK,图形化界面
git stash # 暂存
ls -al
cd .git 
cat HEAD
cat refs/heads/main
cd ..
git checkout temp
cat .git/HEAD # 查看当前分支
cat .git/config
git config --local --list
ls -al .git/refs/ # tags对应里程碑,heads对应分支,remotes对应远程分支,stash对应暂存区
ls -al .git/refs/heads/ # 列出所有分支
cat .git/refs/heads/temp
git cat-file -t e7a42584e024a86 # 查看对象类型
git branch -av # 查看所有分支，列表所有分支
ls -al .git/refs/tags/ # 列出所有tag
cat .git/refs/tags/readme
git cat-file -t ff191b188fbf7
git cat-file -p ff191b188fbf7
ls -al .git/objects/ # git核心内容
cd .git/objects/ed/ 
git cat-file -t  ed01860036a14a25c9b ## 前面的ed 是文件名,必不可少
git cat-file -p  ed01860036a14a25c9b ## 前面的ed 是文件名,必不可少
# git 核心对象：tree,blob,commit,tag
# 一个commit对象包含：tree,parent,author,committer,message,
# 一个tag对象包含：object,type,tag,tagger,message
# 一个blob对象包含：content
# 一个commit对应一棵树
git cat-file -p 5bbe77c7bb70ee
git cat-file -p 2bde4168ab55ffe
git cat-file -p d01f779ffe857c35
```

## 之前被暂存区跟踪过，gitignore是后加的，忽略规则无效
```bash
git rm -r --cached ## 清除暂存区所有跟踪记录，重新暂存提交
```
## resources
* https://www.atlassian.com/git/tutorials/gitk # GitK，图形化界面

