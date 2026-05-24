# vue . js 实例介绍

> 原文:[https://www . geesforgeks . org/introduction-to-vue-js-instance/](https://www.geeksforgeeks.org/introduction-to-vue-js-instance/)

**什么是 Vue 实例？**

**Vue.js** 是一个由开源开发者开发的前端 JavaScript 框架。它通常用于构建单页应用程序。要了解更多关于 VueJS 的信息，请参考 [Vue.js |简介&安装](https://www.geeksforgeeks.org/vue-js-introduction-installation/)。

VueJS 在运行时没有 HTML 代码，取而代之的是 VueJS 基于我们的 HTML 代码创建一个模板，并将其存储到 ***【虚拟 DOM】***&中，然后使用该模板来呈现原始的 HTML 代码，该代码随后被呈现为实际的 DOM。 **VueJS 实例**是 HTML 网页的 DOM 元素和 JavaScript 中的应用程序逻辑之间的中介。根据 [**MVVM 模式**](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel) 中的定义，VueJS 实例具体是一个**视图-模型**。演示 HTML 代码和在 VueJS 中定义为视图模型的 Vue 实例之间的联系的基本语法是:

## Javascript

```js
<div id="app"></div>

<script>
new Vue({ 
    el: "#app"
});
</script>
```