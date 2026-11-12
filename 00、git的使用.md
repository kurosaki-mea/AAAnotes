
`2026年11月12日`

# GIT
## 1、初次使用

```
git init
git add .
git commit -m '本次提交更新：xxx'
git push
```

- `git init`
初始化本地仓库
- `git add .`
添加文件到暂存区
- `git commit -m "项目初始化 首次提交"`
提交到本地，并说明备注
- `git branch -M main` 
↑ 分支改名为 main；把当前分支强制重命名为main
-M 是 --move --force 的简写，即重命名并覆盖同名分支
作用：老版本 Git 默认分支叫 master，现在 GitHub 等平台默认用 main
- `git remote add origin 远程仓库地址`
↑ 关联远程仓库；给本地仓库添加一个远程仓库，并起别名 origin（约定俗成的默认名）。
远程仓库地址：需要替换成真实地址，例如 https://github.com/用户名/仓库名.git 或 SSH 地址 git@github.com:用户名/仓库名.git。
之后就可以用 origin 代替那一长串地址。
- `git push -u origin main`
推送到远程并建立追踪；把本地 main 分支推送到远程仓库 origin
- `git push`
推送提交(commit)
推送，把本地仓库的提交"推"到远程仓库
---
## 2、git 账号配置

git config user.name：查看当前登录用户
git config user.email：查看登录邮箱

1. 查看当前所有的有效配置（包含来源文件路径）
git config --list --show-origin
    file:C:/Users/neko/.gitconfig 代表全局配置文件。
	file:.git/config 代表当前项目单独的本地配置文件。

2. 查看全局配置文件里的所有设置
git config --global --list

3. 全局配置文件：文件路径：C:\Users\用户名字\.gitconfig

### 修改全局用户名（换成 3号 GitHub 的用户名）
git config --global user.name "你的GitHub用户名"

### 修改全局邮箱（务必换成 3号 GitHub 绑定的邮箱！）
git config --global user.email "你的GitHub绑定邮箱"


## 3、小记
git add .
把所有修改的文件，准备提交。

git commit -m "改了xxx"
提交一次修改，并写一个备注说明（提交日志）
-m 后面跟的是你对这次修改的说明，比如 "修复了 header 显示问题"

git push
把刚才“提交”的内容上传到 GitHub
如果之前已经连好远程仓库，它就直接上传

git branch -M main
把当前分支的名字强制改为 main。

git push -u origin main（第一次上传用）
意思：第一次上传的时候告诉 Git：我以后就往这个远程仓库推了
-u 是 --set-upstream 的缩写，意思是绑定远程主干分支
origin：远程仓库的名字（默认都是 origin）
main：主分支的名字（以前叫 master，现在叫 main）
这个命令 只需要第一次 push 的时候写，以后只用 git push 就行了！

git remote add origin [远程仓库地址]
意思：把本地项目连接到 GitHub 的远程仓库
你只需要做一次，比如新建了一个 GitHub 仓库：
git remote add origin https://github.com/mea75/my-vue-app.git

---
















---
## 999、一些问题 FAQ
### 每次开机git push都需要登录
首先打开 `C:\Users\用户名\.gitconfig` 文件，确认：
```
[user]
	name = 提交时的名字
	email = 邮箱号码@gmail.com
```
之前是因为`[credential "https://gitee.com"] helper = manager`导致push github异常，
没有这条信息就可以正常 git push 而无需每次登录

**凭据管理器**\
第一次登录后，登录信息token将存储到Windows系统里面的凭据管理器中，
访问路径为：`控制面板\用户帐户\凭据管理器\Windows凭据` ，然后可以修改或者删除词条凭据，然后就可以再次触发登录切换账号等等操作








