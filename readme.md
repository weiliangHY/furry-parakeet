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
	
#======================================================
# 创建分支：git branch <name>

# 切换分支：git checkout <name>或者git switch <name>

# 创建并切换到新的dev分支 （合并上述两步）

	## git checkout -b dev
		等于 ###1.  git branch dev
			 ###2.  git checkout dev
	## git switch -c dev
#  切换分支
	## git checkout master
	## git switch master

# 查看分支：git branch
	列出所有分支，当前分支前面会标一个*号。
	* ccc
	  dev
	  master

# 合并某分支到当前分支：git merge <name>
	（一般先从自己的分支切换到主分支，然后再合并内容）
	* 合并如果有冲突时，需要手动处理，处理后再次提交

# 删除分支：git branch -D <name>
	git branch -D ccc   合并完成之后，删除掉自己开的‘ccc’分支
# ===========================================================
# ===========================================================
# GitHub   提交代码到gitHub上（上传到服务器） 【地址】：http 
+ 	git push github个人地址 master
-   git push【地址】 分支
-   
# 把远程分支的数据下载到本地（*本地需要先初始化一个仓储）
	## git pull 【地址】 分支  // 常用
	## git clone 【地址】 //(第一次下载的时候会应用，但多次执行会覆盖本地内容)
# 
# 
# ssh
# 创建公钥 和 私钥   $ ssh -keygen -t rsa -c "yuhan3935@gmail.com"
