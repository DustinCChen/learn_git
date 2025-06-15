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
git status
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
git reset --soft HEAD^ ##  reset,one commit
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
```
## resources
* https://www.atlassian.com/git/tutorials/gitk # GitK，图形化界面

