- GUI 是图形化界面
- Bash 是命令

# Git 基础
## 用户名邮箱
``` c
git config --global user.name "your_username"
git congig --global user.email "email"
git config --global user.password "password"
git config --list 查看配置
```

## Git 工作流程
- 已修改、已暂存、已提交
- 工作区、暂存区、Git 仓库

![[Pasted image 20230722121629.png|500]]


# Git 版本管理
## 创建并提交
``` c
# 初始化本地仓库
git init

# 仓库状态
git status

# 添加到暂存区
git add --all
git add .
git add [file_name]
# --all 和 . 都是全部文件

# 暂存区移除
git restore --staged [file_name]
git reset HEAD [file_name]
# 注意restore只是移除暂存区
# reset是移除上一个操作，提交也可以移除

# 暂存区提交
git commit -m "备注信息"  # 感觉应该也是单双引号都可以
# 如果没加备注信息，退出的时候 wq

# 跳过暂存区直接提交
git commit -am '备注信息'

# 查询提交日志信息
git log
git log --pretty=oneline

# 查看git本地库和工作区的区别
git diff HEAD -- [file_name]
```

## 版本回退
``` c
# 查询提交日志信息
git log
git log --pretty=oneline

# 版本回退
git reset --hard HEAD^   # 回退一次
git reset --hard HEAD~3  # 回退三次
git reset --hard 指针的全部或者前几位  # 指定版本

# 回退之后回到回退前的版本
git reflog # 看所有版本
git reset --hard 指针
```

## 删除
``` c
# 查看所有文件(git仓库)
git ls-files

# 从git仓库拉回到工作区
git checkout 
git checkout [file_name]

# 工作区删除
直接删除

# git仓库删除(本质就是一次修改过程)
git add [file_name]
git commit -m '备注信息（删除xxx）'
# git仓库删除（不用先再工作区删除，自动删除工作区文件）
git rm [file_name]
```


# Git 远程仓库
- Github
- 码云 gitee
- 自己的服务器

## 下载远程代码
``` c
git clone xxx
```

[010_SSH下载项目_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1EY4y1G7ws?p=10&vd_source=5100aa45692ae0d50494ddfe01d72c71)

## 推送

``` c
github上建立一个仓库
新建完仓库之后就能看到代码了
```

![[Pasted image 20230722190413.png]]

[011_远程仓库推送_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1EY4y1G7ws?p=11&vd_source=5100aa45692ae0d50494ddfe01d72c71)



# 分支

## 本地分支操作
``` c
# 在master分支下创建本地分支
git branch 新分支名称
# 切换成新建的本地分支
git checkout 新分支名称
# 删除指定分支
git branch 分支名称
# 查看所有分支
git branch
# 合并分支（在主干上操作？）
git merge 分支名称
# 重命名分支 -M是强制重命名
git branch -m/-M 旧名 新名
```

## 远程分支操纵
[013_远程分支操作_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1EY4y1G7ws?p=13&vd_source=5100aa45692ae0d50494ddfe01d72c71)

## 本地分支冲突
在合并的时候可能会有分支冲突，更改后重新提交就好（add、commit）

## 多人分支冲突

[015_多人协同冲突解决_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1EY4y1G7ws?p=15&vd_source=5100aa45692ae0d50494ddfe01d72c71)


# 标签
![[Pasted image 20230722191049.png]]


# 集成 Git
[017_Idea集成Git_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1EY4y1G7ws?p=17&vd_source=5100aa45692ae0d50494ddfe01d72c71)

[018_Idea推送项目到远程仓库_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1EY4y1G7ws?p=18&spm_id_from=pageDriver&vd_source=5100aa45692ae0d50494ddfe01d72c71)

[019_Idea下分支操作_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1EY4y1G7ws?p=19&spm_id_from=pageDriver&vd_source=5100aa45692ae0d50494ddfe01d72c71)

[020_gitignore插件使用_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1EY4y1G7ws?p=20&vd_source=5100aa45692ae0d50494ddfe01d72c71)

[021_Idea冲突出现及解决_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1EY4y1G7ws?p=21&spm_id_from=pageDriver&vd_source=5100aa45692ae0d50494ddfe01d72c71)
