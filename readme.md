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

======================================
这是第二次添加的内容哦
查询状态
$ git status
======================================
3
查看当前代码有没有被放到仓储中去

============================================
4
一句命令直接保存
git commit --all -m
