#### base

**1** 、git  config --global user.name "ccerdust"

**2** 、 git config --global user.email "987728187@qq.com" 

**3** 、midir

4、 git init        ~~添加为git本地仓库~~ 

**5** 、git add readme.txt   *文件添加到仓库*

> 可以多次添加到仓库 然后一次提交

**6** 、git commit -m "这是第一次改动"   `文件提交到仓库`

**7**、 git status 查看仓库状态

**8**、 git diff  查看改动内容

#### 时光穿梭机

1. git log   `查看历史版本修改的改动`   参数--pretty=oneline 缩略

2. git reset --hard  HEAD^ | HEAD~100 `回退到上一个版本| 回退上一百个版本` **！！** **慎用，回退后如果想要恢复，必须要没回退版本的id**   

   >  git reset --hard id 指定回退到某个版本

3.  git reflog `执行操作的历史命令`

   > git 跟踪管理修改而不是文件，所以优秀

4. git diff HEAD -- readme.txt `查看当前版本库与本地文件的区别`
5. 

