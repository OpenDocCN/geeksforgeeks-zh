# node . js vs view . js

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-vs-view-js/

**Node.js:** 它是一个 JavaScript 运行时环境，构建在 Chrome 的 V8 JavaScript 引擎之上。它是由在谷歌大脑工作的软件工程师瑞安·达尔开发的，他还开发了 Deno JavaScript 和 TypeScript 运行时。Node.js 是跨平台和开源的，它在服务器端，即 web 浏览器之外执行 JavaScript 代码。由于其单线程特性，它主要用于事件驱动的非阻塞服务器，非阻塞输入/输出模型使其轻量级且高效，因此最适合数据密集型实时应用程序。传统网站和后端应用编程接口服务都使用它。它采用基于推送的实时架构设计，可在分布式设备上运行。HTTP(超文本传输协议)模块提供了一组用于构建 HTTP 服务器的类和函数。对于这个基本的 HTTP 服务器，我们使用像文件系统、路径和网址这样的本地节点。

**Vue.js:** 它是一个开源的渐进式 JavaScript 框架，主要用于构建 ui 和单页应用。它是由埃文创建的，由帕特里翁社区资助开发虚拟企业。它与大多数现代技术兼容，并且由于温和的学习曲线和可扩展性，它获得了大量的普及。VueJS 遵循模型-视图-视图模型(MVVM)架构模式，其中视图模型有一个“Vue”实例，视图和模型通过双向数据绑定进行绑定。它利用了一个虚拟的 DOM，就应用编程接口和设计而言，Vue 比 AngularJS 更容易学习。由于路由和状态的问题是在 ReactJS 中处理的，所以 Vue 也是通过关联库来处理的。

**node . js 与 Vue.js 的区别:**

<figure class="table">

| 节点。射流研究… | Vu.js |
| --- | --- |
| Node.js is a cross-platform, open source back-end framework that executes JavaScript code on the server side. | Vue.js is a structured open source JavaScript framework for building ui and single-page applications. |
| The learning curve of node.js is high [71,500 stars on GitHub (as of July 2020)]. | The learning curve of vue.js is relatively low. |
| Support the model-view-controller (MVC) framework. | Support model-view-view model (MVVM) mode. |
| is written in C/C++. | Written in Javascript and Typescript ... |
| It allows you to run JavaScript code on the server side and handle requests from browsers. | Used to build single-page and client applications. |
| Real-time data stream processing is easy. | Real-time data stream is not handled by VueJS. |
| It is fast and light, which makes it possible to write microservices. | It is faster than any other UI framework, and it is easy to set up existing projects. |
| It runs on chromes v8 engine and adopts event-driven and non-blocking I/O mode. | It uses JavaScript runtime' node.js' to compile and run. |
| DOM (Document Object Model) is not used. | Using virtual DOM (Document Object Model). |
| Single thread processing request is simple and fast. | Axios library is used to process AJAX requests. |
| Applications using Node.js: LinkedIn, Uber, Netflix, PayPal, Trello, Capital One, Yahoo, Mozilla, etc. | Applications using Vue.js: Google, Apple, Nintendo, Behance, Oval Money. |
| 

```js
if(gfg) {
console.log("Geeks for Geeks"); }

```

 | 

```js
<h1 v-if="gfg">Geeks for Geeks</h1>

```

 |

</figure>