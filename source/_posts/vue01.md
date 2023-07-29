---
title: Vue01
date: 2023-07-03 18:09:00
author: 小白学Vue
img: https://cdn.jsdelivr.net/gh/panpan987/CDN@master/cover_img/123916-1635741556813b.jpg
categories: Vue
tags:
  - Vue3
---
## 创建Vue3项目
在桌面打开Powershell窗口，输入`npm  init vue@latest`  
```bash
PS C:\Users\panda\Desktop> npm init vue@latest

Vue.js - The Progressive JavaScript Framework

√ Project name: ... vue3-project
√ Add TypeScript? ... No / Yes
√ Add JSX Support? ... No / Yes
√ Add Vue Router for Single Page Application development? ... No / Yes
√ Add Pinia for state management? ... No / Yes
√ Add Vitest for Unit Testing? ... No / Yes
√ Add an End-to-End Testing Solution? » No
√ Add ESLint for code quality? ... No / Yes

Scaffolding project in C:\Users\panda\Desktop\vue3-project...

Done. Now run:

  cd vue3-project
  npm install
  npm run dev

PS C:\Users\panda\Desktop>
```
再使用vscode打开，使用`npm install`安装依赖、`npm run dev`启动  
浏览器打开：  
![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-07-03_18-24-54.png)

关键文件： 
- vite.config.js - 项目的配置文件，基于vite的配置
- package.json - 项目包文件 核心依赖项变成Vue3.x和vite
- main.js - 入口文件 createApp函数创建应用实例
- app.vue - 根组件 SFC单文件组件 script - template - style  
变化一：脚本script和模块template顺序调整   
变化二：模板template不再要求唯一根元素  
变化三：脚本script添加setup标识支持组合式API  
- index.html - 单页入口 提供id为app的挂载点

### 组合式API 
