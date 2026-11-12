
# VScode：Vue 常见错误
## 1、无法识别 vue 文件
`无法找到模块“../views/NotFound.vue”的声明文件。“e:/Code/src/views/NotFound.vue”隐式拥有 "any" 类型。ts(7016)`

在 `src/env.d.ts` 目录下，粘贴进此代码：
```ts
/// <reference types="vite/client" />
declare module '*.vue' {
  import type { DefineComponent } from 'vue'
  const component: DefineComponent<{}, {}, any>
  export default component
}
```

## 2、tsconfig.node.json 报错
`--lib选项的参数必须为'es5'.....`
是因为版本不兼容，`ts node`
方案二：更新项目依赖（推荐）
**npm 用户**
`npm install -D @tsconfig/node tsconfig`
**pnpm 用户**
`pnpm add -D @tsconfig/node tsconfig`

安装完成后，按 F1 或 Ctrl + Shift + P 打开命令面板，输入 TypeScript: Restart TS Server（重启 TS 语言服务），或者重新打开编辑器，红线报错即可消除。


