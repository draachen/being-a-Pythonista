## git简明教程  

首先，需明确几个概念：  

* 当前正在修改的叫工作区  
* --> git add 后进入暂存区  
* --> git commit 后进入分支  
* --> git push 后进入远程  

### 常用命令  

常见命令

    >git init  
    >git status  
    >git add readme.txt  #将工作区的修改放入暂存区  
    >git rm test.txt  
    >git comment -m"wrote a readme file"  #将暂存区更改放入本地分支

查看正在修改文件

    >git diff  #查看具体修改了什么  
    >git diff HEAD -- readme.txt  #diff查看的是，工作区（最近修改）与版本库（最近的commit）的差别  

版本间切换  

    >git log  #查看历史更改记录  
    >git log --pretty=oneline  #查看历史，一行显示  
    >git reset --hard HEAD^  #退到上一个版本HEAD^,  (HEAD^^, HEAD~100...) ；reset到之前的commit后，文件随之更新  
    >git reflog  #查看命令历史  

    想要恢复之前丢掉的最新的版本，使用reflog命令，查看最近commit ID  
    显示最近的commit ID后，再使用git reset --hard [commit ID] 返回  

    >git reflog  
    >git reset --hard 23ff632  

撤销修改(工作区或暂存区)  

    文件已保存，但没有git add，将readme.txt在在工作区的修改撤销
    回到最近一次git commit或git add时的状态  

    >git checkout -- readme.txt

    把暂存区的修改撤销掉，重新放回工作区（但还是已经修改了），此时如果想恢复到没修改的状态，需要git checkout -- readme.txt 命令（适用于已经git add, 但想重新修改的情况）  

    >git reset HEAD readme.txt

    撤销修改场景：  

    1. 当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。  
    2. 当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD readme.txt，就回到了场景1，第二步按场景1操作将工作区更改的内容丢掉。  

### 远程仓库操作  

**git clone**  

    >git init  
    >git clone git@github.com:draachen/gitskills.git  #远程库克隆到本地  

**git remote**  

    >git remote add origin git@github.com:draachen/learngit.git  #将本地文件关联一个远程库  

    >git remote jQuery git@github.com:draachen/Py103.git  #添加远程主机jQuery  
    >git remote  #查询所有主机

**git fetch**  

    >git fetch <远程主机名> <分支名>  #将远程主机的更新取回本地  
    >git merge origin/master  #在本地合并远程分支  

**git pull**  

    >git pull <远程主机名><远程分支名>:<本地分支名>  #取回远程主机某个分支的更新，再与本地的指定分支合并  
    
    等同于，先git fetch，再git merge
        >git fetch origin  
        >git merge origin/next

**git push**  

    >git push <远程主机名> <本地分支名>:<远程分支名>  
    >git push -u origin master  #若当前分支与多个主机存在追踪关系，则可以使用-u选项指定一个默认主机  
    
    PS: 强制推送，结果导致远程主机上最新的版本被覆盖
    >git push --force origin

### 分支管理  

创建并切换到新分支  

    >git checkout -b dev  #创建并切换到dev分支,-b参数表示创建并切换  
    等同于：
        >git branch dev  #创建分支，创建的分支是基于当前分支的，会包含所有之前提交信息  
        >git checkout dev  #切换分支  

创建空分支

    >git checkout --orphan draachen  
    >git rm -rf .  
    rm '.gitignore'  
    >git add .  
    >git commit -m"ramsey'init"  
    >git branch  
    master  
    *draachen  

查看分支  

    >git branch  #查看当前分支  
    >git branch --all  #查看所有分支  

合并分支  

    >git add readme.txt  #修改readme.txt  
    >git commit -m"branch test"  
    >git checkout master  #切换回master分支，此时查看readme.txt，刚才添加的内容不见  
    >git merge dev  #将dev分支的工作成果合并到master分支上，Fast forward模式（直接把master 指向dev的当前提交），看不出来曾经做过合并  
    >git branch -d dev  #合并完后，就可以放心删除dev分支  

解决分支合并冲突  

    >git checkout -b feature1  #修改readme.txt 然后 add, commit  
    >git checkout master  #修改readme.txt然后add, commit  
    >git merge feature1  #冲突
    >git status  
    此时可以打开readme.txt查看内容，手动修改
    >git add readme.txt  
    >git commit -m"conflict fixed"  #生成新的commit  
    >git log --graph --pretty=online --abbrev-commit  #git log查看分支的合并情况  
    >git branch -d feature1  #最后删除feature1分支  

### 分支管理策略  

Fast forward模式会丢掉分支信息，故建议使用--no-ff模式进行merge操作

    >git checkout -b dev
    ...

准备合并dev, --no-ff参数，表示禁用Fast forward

    >git merge --no-ff -m"merge with no-ff" dev  #创建新的commit  
    >git log --graph --pretty=oneline --abbrev-commit

在实际开发中，应该按照几个基本原则进行分支管理：

    1. master分支应该是稳定的，仅用来发布新版本，平时不能在上面干活；  
    2. 干活在dev分支上，1.0版本发布时，再把dev分支合并到master上，在master分支发布1.0版本；  
    3. 每个小伙伴在dev分支上干活，每人都有自己的分支，时不时地往dev分支上合并  

### 修复Bug分支  

修复bug可以通过新的临时分支来，修复后，分支合并，然后将临时分支删除

    >git stash  #把现场储藏起来  
    >git status  
    >git checkout master  
    >git checkout -b issue-101  #创建临时分支  
    >git add readme.txt  
    >git commit -m"fix bug 101"  
    >git checkout master  
    >git merge --no-ff -m"merge bug fix 101" issue-101  
    >git branch -d issue-101  #删除修复bug临时分支  
    >git stash list  #查看刚才存的工作现场  
    >git stash apply  #恢复  
    >git stash drop  #删除  
        or 使用git stash pop  #恢复及删除  
    >git stash apply stash@{0}  #多次stash，恢复的时候用git stash list查看  

### Feature分支  

添加新技能时，最好新建一个feature分支  

    >git checkout -b feature-vulcan
    ...
    >git add vulcan.py
    >git status
    >git commit -m"add vulcan.py"
    >git checkout dev
    接下来就是分支合并，删除  
    但，接上级命令，新功能取消  
    >git branch -d feature-vulcan  #只能用于删除已合并过的分支
    >git branch -D feature-vulcan  #强行删除没有被合并的分支

### 多人协作  

查看远程库的信息  

    >git remote  
    >git remote -v  

推送分支

    >git push origin master  #master是主分支，要时刻与远程同步  
    >git push origin dev  #dev是开发分支，团队成员都需要在上面工作，所以也需要与远程同步  

多人协作  

    小伙伴：在另一台电脑或者同一台电脑的另一个目录下克隆  
    >git clone git@github.com:draachen/learngit.git
    >cd learngit
    >git branch
    *master
    >git checkout -b dev origin/dev  #创建远程origin的dev分支到本地
    ...
    >git commit -m"add/user/bin/env"
    >git push origin dev  #把dev分支push到远程
    
    此时本人也对文件作了修改，并试图推送  
    >...
    >git commit -m"add coding: utf-8"  
    >git push origin dev  #此时push会报错  

    而是先git pull把最新的提交从origin/dev抓下来，然后本地合并，解决冲突后再推送  
    >git pull  #git pull也失败，因为没有指定本地dev分支与远程origin/dev分支的链接
    >git branch --set-upstream dev origin/dev
    >git pull  
    >git commit -m"merge & fix hello.py"      #此时会报错
    >git status
    >vi hello.py  #解决冲突  
    >git commit -m"merge & fix hello.py"
    >git push origin dev

    多人协作的工作模式：

    1. 用git push origin branch-name推送自己的修改  
    2. 如果推送失败，远程分支比你本地更新，先用git pull试图合并  
    3. 如果合并有冲突，则解决冲突，并在本地提交  
    4. 没有冲突或冲突解决后，再用git push origin branch-name推送就能成功  

### 标签管理  

标签就是让人容易记住的有意义的名字，它跟某个commit绑在一起  

创建标签  

    >git branch
    >git checkout master  #切换到master分支  
    >git tag v1.0  #默认tag打在最新提交的commit上
    
    >git log --pretty=oneline --abbrev-commit
    >git tag v0.9 6224937  #将标签打在某个commit上
    
    >git tag
    v1.0
    v0.9  
    >git show v0.9
    >git show v1.0

创建带有说明的标签  

    >git tag -a v0.1 -m"version 0.1 released" 3628164  #用-a指定标签名，用-m指定说明文字

删除标签（本地标签）  

    >git tag -d v0.1
    >git push origin v1.0
    >git push origin tags  #推送全部本地标签

删除标签（远程标签）

    >git tag -d v0.9  #先从本地删除  
    >git push origin :refs/tags/v0.9  #再从远程删除  

### 忽略特殊文件  

文件放在git目录中，但又不能提交（e.g 保存了数据库密码的配置文件等）  

- 在git工作区的根目录下创建.gitignore文件，将忽略的文件名填进去  

### Changelog

- 2017/8/27 13:49:21 新增远程操作
- 2017/8/27 11:52:36 init

参考资料:

- [廖雪峰git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
- [Git远程操作详解](http://www.ruanyifeng.com/blog/2014/06/git_remote.html)



PS: 图解远程操作

![](http://image.beekka.com/blog/2014/bg2014061202.jpg)
