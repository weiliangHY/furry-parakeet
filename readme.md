初始化git仓储
	在项目目录右键打开 git bash
	命令： git init

配置个人信息
	git config --global user.name "Your Name"
	git config --global user.email "email@example.com"

把文件添加到版本库
	git add readme.txt
	git conmit -m "这是添加readme.txt的说明信息。"


=====================================

commit可以一次提交很多文件，所以你可以多次add不同的文件，比如：
$ git add file1.md
$ git add file2.md file3.md
$ git commit -m "add 3 files."
保存文件夹里的全部
git add ./
======================================
这是第二次添加的内容哦
查询状态
$ git status
======================================
3
查看当前代码有没有被放到仓储中去

============================================
4
一句命令直接保存文件夹里的全部
# git commit --all -m
============================================
5 
# git diff  查看具体修改了什么内容

# git log   查看历史版本
	commit a38dcd4cd865c0d135b2428ad0edb90a246cfd36 // commit  版本号
	Author: hanyu <yuhan3935@gmail.com>
	Date:   Sun Apr 12 12:16:02 2020 +0800
	
	    1.js第3版
	
	commit 2f4fb8837645b7f89a9793455d920687e3bd7c9e
	Author: hanyu <yuhan3935@gmail.com>
	Date:   Sun Apr 12 12:15:09 2020 +0800
	
	    1.js第二版

# git log --pretty=oneline 查看历史版本精简版 
	b078465719a781c71fd1bab88900931259ab7435 (HEAD -> master) readme 添加一句保存
	a38dcd4cd865c0d135b2428ad0edb90a246cfd36 1.js第3版
	2f4fb8837645b7f89a9793455d920687e3bd7c9e 1.js第二版
	72f3d38107a9be6626eff1e3576db8ec07ce8a1f 这是添加readme.md的第4次说明信息(一句命令保存代码到仓储)。

# git reset 版本回退（回到过去版本，也可以回到过去版本后，再通过commit id 返回新的版本）
#  git reset --hard +commit id
	HEAD表示当前版本，上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100，一般可以用commit id来指定返回的版本
 git reset --hard 2f4fb8837645b7f89a9793455d920687e3bd7c9e

# git reflog  记录每一次命令
	if回退到了某个版本，关掉了电脑，第二天早上就后悔了，想恢复到新版本，找不到新版本的commit id时，用git reflog 找到每一次的命令，然后根据commit id 返回最新版本
	
	
# git checkout -b dev    创建dev分支，然后切换到dev分支	
	等同于 git branch dev
		  git checkout dev
# git branch命令会列出所有分支，当前分支前面会标一个*号。
	$ git branch
	* ccc
	  dev
	  master

# git checkout master   切换分支
# git merge  合并指定分支到当前分支，（一般先从自己的分支切换到主分支，然后再合并内容）