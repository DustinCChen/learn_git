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
git commit -m "update README2.md"
git branch -av

```


```mermaid
graph TD;
  style A fill:	#98FB98,stroke:#333,stroke-width:4px
  A[工作目录] -- git add files ---> B[暂存区];
  style B fill:#00BFFF,stroke:#333,stroke-width:4px
  B -- git commit --->C[版本历史]
  style C fill:#F0E68C,stroke:#333,stroke-width:4px
```
```mermaid
gantt
dateFormat YYYY-MM-DD
title Yr2023WK20     WorkSchedule-GanttDiagram
excludes 2023-05-27,2023-05-28,2023-05-20,2023-05-21
section Dev

1.1 驾驶舱项目二期开发:activate,2023-05-19,6d
1.1.1 行业大盘逻辑梳理:done,2023-05-22,2d
1.1.2 京东行业关键词:active,2023-05-24,2d
1.1.3 天猫行业关键词:active,2023-05-24,2d

1.2 产品线中心爬虫支持:activate,2023-05-19,6d
1.2.1 竞品评论文本抓取:done,2023-05-19,2d
1.2.2 竞品评论图片抓取:active,2023-05-24,2d
1.2.3 竞品评论视频抓取:active,2023-05-24,2d


section Ops
2.1 京东自营数据维护:done,2023-05-19,6d
2.1.1 降压线数据补充:done,2023-05-22,2d
2.2 天猫官旗数据维护:done,2023-05-19,6d
2.2.1 6Pro补充:done,2023-05-23,4d
2.2.2 创意维护更新:done,2023-05-23,4d
2.3 天猫车旗数据维护:done,2023-05-19,6d
```