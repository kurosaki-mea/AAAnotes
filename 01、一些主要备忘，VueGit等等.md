# Vue3 + TypeScript + Vue Router + Pinia + Axios + Element Plus + Vite



## 创建项目
npm create vue@latest

## 安装依赖 
进入项目目录并安装：cd xxx
自动下载到node_modulesq
npm install

## 运行项目
npm run dev


创建 Vue3 项目（用 Vite）
npm create vite@latest
输入项目名，选择 Vue，选择 JS

安装依赖：
cd todo-list （进入项目文件夹）
npm install （安装依赖）

运行项目：
npm run dev

==================================
==================================
==================================
## git 账号配置

git config user.name：查看当前登录用户
git config user.email：查看登录邮箱

1. 查看当前所有的有效配置（包含来源文件路径）
git config --list --show-origin
    file:C:/Users/neko/.gitconfig 代表全局配置文件。
	file:.git/config 代表当前项目单独的本地配置文件。

2. 查看全局配置文件里的所有设置
git config --global --list

3. 全局配置文件：文件路径：C:\Users\用户名字\.gitconfig

# 修改全局用户名（换成 3号 GitHub 的用户名）
git config --global user.name "你的GitHub用户名"

# 修改全局邮箱（务必换成 3号 GitHub 绑定的邮箱！）
git config --global user.email "你的GitHub绑定邮箱"

==================================

1. 以后每次更新项目时：（只用下面这3步）：

git add .
git commit -m "修改了 XXX"
git push


2. 想开新项目上传：在新文件夹里：
# 第一次用（初始化 + 绑定远程仓库）：

git init
git add .
git commit -m "项目初始化 首次提交"
（git branch -M main）
git remote add origin 远程仓库地址
git push -u origin main


【小记】
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





# Vue 常见错误
## 1、无法识别 vue 文件
无法找到模块“../views/NotFound.vue”的声明文件。“e:/Code/src/views/NotFound.vue”隐式拥有 "any" 类型。ts(7016)

在 src/env.d.ts 目录下，粘贴进此代码：
/// <reference types="vite/client" />
declare module '*.vue' {
  import type { DefineComponent } from 'vue'
  const component: DefineComponent<{}, {}, any>
  export default component
}

## 2、tsconfig.node.json 报错
--lib选项的参数必须为'es5'.....
是因为版本不兼容，ts node
方案二：更新项目依赖（推荐）
`npm 用户`
npm install -D @tsconfig/node tsconfig
`pnpm 用户`
pnpm add -D @tsconfig/node tsconfig

安装完成后，按 F1 或 Ctrl + Shift + P 打开命令面板，输入 TypeScript: Restart TS Server（重启 TS 语言服务），或者重新打开编辑器，红线报错即可消除。








