# Node.js

## 1 Node.js介绍

### 1.1. 为什么要学习Node.js

- 企业需求
  + 具有服务端开发经验更好
  + front-end
  + back-end
  + 全栈开发工程师
    + 全干
  + 基本的网站开发能力
    + 服务端
    + 前端
    + 运维部署
  + 多人社区

### 1.2. Node.js是什么

- Node.js® is a JavaScript runtime built on [Chrome's V8 JavaScript engine](https://developers.google.com/v8/). 
  - Node.js不是一门语言
  - Node.js不是库、不是框架
  - Node.js是一个javascript运行时环境
  - 简单点来讲Node.js可以解析和执行javascript代码
  - 以前只有浏览器可以解析执行javascript代码
  - 也就是说现在的javascript可以完全脱离浏览器来运行，一切都归功于,Node.js
- 浏览器中的javascript
  - EcmaScript
    - 基本的语法
    - if
    - var 
    - function
    - Object
    - Array
  - BOM
  - DOM
- Node.js中的Javascript
  - 没有BOM、DOM
  - EcmaScript
  - 在Node这个javascript执行环境中为javascript提供了一些服务器级别的操作API
    - 例如文件读写
    - 网络服务的构建
    - 网络通信
    - http服务器
    - 等处理...
- 构建于Chrome的V8引擎之上
  - 代码只是具有特定格式的字符串而已
  - 引擎可以认识它 引擎可以帮你去解析和执行
  - Google Chrome的V8引擎是目前公认的解析执行javascript代码最快的
  - Node.js的作者把Google Chrome 中的V8引擎移植了出来，开发了一个独立的javascript运行时环境
- Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient.
  - event-driven 事件驱动
  - non-blocking I/O model 非阻塞IO模型(异步)
  - lightweight and efficient 轻量和高效
  - 随着课程慢慢的学习你会明白什么是事件驱动、非阻塞IO模型
- Node.js' package ecosystem, [npm](https://www.npmjs.com/), is the largest ecosystem of open source libraries in the world. 
  - npm 是世界上最大的开源库生态系统
  - 绝大多数javascript相关的包都存放在了npm上，这样做的目的是为了开发人员更方便的去下载使用我.
  - ```npm install jquery```

### 1.3. Node.js能做什么
- Web服务器后台
- 命令行工具
  - npm(node)
  - git(c语言)
  - hexo(node)
  - ...
- 对于前端开发工程师来讲，接触node最多的是它的命令行工具
  - 自己写的很少，主要是使用别人第三方的
  - webpack
  - gulp
  - npm 

### 1.4. 预备知识

- HTML
- CSS
- Javascript
- 简单的命令行操作
  - cd
  - dir
  - ls
  - mkdir
  - rm
- 具有服务端开发经验更佳

### 1.5. 一些资源
  - 《深入浅出Node.js》
    - 朴灵
    - 偏理论，几乎没有任何实战性内容
    - 理解原理底层有帮助
    - 结合课程的学习去看
  - 《Node.js权威指南》
    - API 讲解
    - 也没有业务，没有实战
  - javascript标准参考教程(alpha):http://javascript.ruanyifeng.com/
  - Node入门: http://www.nodebeginner.org/index-zh-cn.html
  - 官方API文档: https://nodejs.org/dist/latest-v6.x/docs/api/
  - 中文文档(版本比较旧，凑合看):http://www.nodeclass.com/api/node.html
  - CNODE社区:http://cnode.js.org
  - CNODE-新手入门:http://cnodejs.org/getstart

### 1.6. 这门课程你能学到啥?
  - B/S 编程模型
    - Browser -Server
    - back-end
    - 任何服务端技术这种BS编程模型都是一样，和语言无关
    - Node 只是作为我们学习BS编程模型的一个工具而已
  - 模块化编程
    - RequireJS
    - Seajs
    - `@import('文件路径')`
    - 以前认知的javascript只能通过`script`标签来加载
    - 在Node中可以像`@import()`一样来引用加载javascript脚本文件
  - Node常用API
  - 异步编程
    - 回调函数
    - Promise
    - async
    - generator
  - Express Web 开发框架
  - Ecmascript6
    - 在课程中穿插讲解
    - 它只是一个新的语法而已
  - ...
  - 学习Node不仅会帮助大家打开服务端黑盒子，同时会帮助你学习以后的前端高级内容
    - Vue.js

    - React

    - angular

      ------

## 2.起步
### 2.1. 安装Node环境
  - 查看当前Node环境的版本号
  - 下载:http://nodejs.org/en/download/
  - 安装
    - 傻瓜式的一路`next`就可以了
    - 对于已经装过的，重新安装就会升级
  - 确认Node环境是否安装成功
    - 打开命令行,输入`node --version`
    - 或者`node -v`
  - 环境变量

### 2.2. Hello World
	1.创建编写javaScript脚本文件
	2.打开终端，定位到脚本文件所属目录
	3.输入`node文件名`执行对应的文件
	注意:文件名不要使用`node.js`来命名,也就是说除了`node`这个名字你随便起,而且最好也不要使用中文
	- 解析执行Javascript
	- 读写文件
	- http
