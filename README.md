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
#### 2.2.1.解析执行Javascript

#### 2.2.2.读写文件
读取文件

```
// 浏览器中的Javascript是没有文件操作的能力的
// 但是Node中的Javascript具有文件操作的能力

// fs 是filesystem的简写，就是文件系统的意思
// 在Node中 如果想要进行文件操作，就必须引入fs这个核心模块
// 在fs这个核心模块中，就提供了所有的文件操作相关的API
// 例如：fs.readFile 就是用来读取文件的

//1.使用require方法加载fs核心模块 
var fs = require('fs');

// 2.读取文件
// 第一个参数就是要读取的文件路径
// 第二个参数是一个回调函数
// 	
// 	成功
// 		data数据
// 		error null
// 	失败
// 		data undefined 没有数据
// 		error 错误对象
fs.readFile('./data/a.txt',function(error,data){
	// <Buffer 68 65 6c 6c 6f 20 6e 6f 64 65 6a 73>
	// 文件中存储的其实都是二进制数据 0 1
	// 这里为什么看到的不是0 和 1 呢?原因是二进制转为16进制了
	// 但是无论是二进制还是16进制，人类都不认识
	// 所以我们可以通过toString方法把其转为我们能认识的字符
	// console.log(data);
	// console.log(error);
	// console.log(data.toString());
	// 在这里就可以通过判断error来确认是否有错误发生
	if(error){
		console.log('读取文件失败了');
		return
	}
	console.log(data.toString());
});
```
写入文件

```
var fs = require('fs');
// 第一个参数:文件路径
// 第二个参数:文件内容
// 第三个参数:回调函数
// 		error
// 		
// 		成功:
// 			文件写入成功
// 			error是null
// 		失败:
// 			文件写入失败
// 			error就是错误对象
fs.writeFile('./data/你好.md','大家好,给大家介绍一下,我是Node.js',function(error){
	// console.log('文件写入成功');
	// console.log(error);
	if(error){
		console.log('写入失败');
	}else{
		console.log('写入成功了');
	}
})

```


#### 2.2.3. http
最简单的http服务:

​	Javascript
	// 接下来，我们要干一件使用node很有成就感的一件事儿
	// 你可以使用Node非常轻松的构建一个Web服务器
	// 在Node中专门提供了一个核心模块:http
	// http这个模块的职责就是帮你创建编写服务器的
	
	// 1.加载http核心模块
	var http = require('http');
	// 2.使用http.createServer()方法创建一个Web服务器
	// 		返回一个Server实例
	var server = http.createServer();
	
	// 3.服务器要干嘛?
	// 		提供服务:对 数据的服务
	// 		发请求
	// 		接收请求
	// 		处理请求
	// 		给个反馈(发送响应)
	// 		注册request请求事件
	// 		当客户端请求过来，就会自动触发服务器的request请求事件，然后执行第二个参数:回调处理函数
	server.on('request',function(){
		console.log('收到客户端的请求了');
	})
	
	// 4.绑定端口号,启动服务器
	server.listen(3000,function(){
		console.log('服务器启动成功了，可以通过http://127.0.0.1:3000/来进行访问');
	})


​	
	```
  ![1527240024047](https://raw.githubusercontent.com/html546/node.js-learning/master/1527240024047.png)

  

## 3. Node中的Javascript

	- EcmaScript
	- 核心模块
	- 第三方模块
	- 用户自定义模块

------


## 4.NodeJS的模块化系统