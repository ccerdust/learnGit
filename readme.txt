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
5. git checkout -- readme.txt `让文件回到最近一次修改`

#### 远程仓库

>
>
>上面是在本地仓库进行操作，下面将其推送到远程
>
>

**1、** 本地仓库内必须有`README.md`文件

**2、** git  branch -M main   `创建主分支`

**3、** git remote add origin https://github.com/dustccer/learnGit.git   `创建远程库链接地址`

**4、** git push -u origin main  `推送到远程库主分支，第一次需要加参数-u`

**5、** git push origin main `推送到远程库主分支，因为已经链接了所以直接到了github上`

>远程库名写错了或者想要删除 1. git remote -v 查看远程库 2.git remote rm origin 删除远程库

**6、**  git clone https://github.com/dustccer/learnGit.git `克隆仓库，即下载`

#### 分支管理

>HEAD指向当前分支
>
>当我们创建新的分支，例如`dev`时，Git新建了一个指针叫`dev`，指向`master`相同的提交，再把`HEAD`指向`dev`，就表示当前分支在`dev`上：
>
>创建新分支 --> 改动都到了新分支上，主分支不变 --> 合并新分支到主分支上-->删除新分支

**1、** git branch dev     `创建一个dev新分支`

**2、** git checkout dev  `切换到dev分支上`              

>以上也可以一条命令  `git checkout  -b dev`    -b表示创建并切换

 

**3、** git branch     `查看当前拥有的分支`

**4、**  git checkout main     git merge dev   `切回主分支  --> 合并dev分支上的文件到主分支 `

**5、**  git merge dev  `合并dev分支到到当前分支`    

>提示Fast-forward  为此次合并为快进模式 ，直接把main的指针指向的dev

**6、** git branch -d dev `删除dev分支`

**7、** git stash  `存储工作区`

**8、** git stash list `查看存储的工作区列表`

**9、** git stash apply `恢复存储的工作区,但此方式不会删除存储的工作区`

**10、** git stash drop  `删除存储的工作区`

>以上两条命令可以用`git stash pop` 代替

**11、** git cherry-pick xxxxx `复制某次提交的内容到当前分支`

**12、** git remote -v  `查看远程库信息`

**13、** git pull `将远程当前版本抓取下来`

**14、** git rebase `将本地未push的分叉整理的更干净`

#### 标签管理

**1、** git tag v1.0    `创建一个叫做v1.0的标签`

**2、** git tag v0.9 [commit指令md5] `给这个提交打标签`

**3、** git show v1.0  `查看这个tag的详细信息`

**4、** git tag -a v0.1 -m "version 0.1 released"  `给标签附上说明`

**5、** git tag -d v0.1  `删除标签`

**6、** git push origin v0.1  `推送标签到远程`

**7、** git push origin --tags  `推送全部标签到远程`

**8、** git push origin :refs/tags/v0.9  `删除远程标签`





**自定义Git**

**忽略文件**

>在Git工作区的根目录下创建一个特殊的`.gitignore`文件，然后把要忽略的文件名填进去

>`例如：`
>
>```
># Windows:
>Thumbs.db
>ehthumbs.db
>Desktop.ini
>
># Python:
>*.py[cod]
>*.so
>*.egg
>*.egg-info
>dist
>build
>
># My configurations:
>db.ini
>deploy_key_rsa
>```

**配置别名**

1、 git config --global alias.st status         `st代表status`