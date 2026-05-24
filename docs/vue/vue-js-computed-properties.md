# 计算属性

> 原文:[https://www.geeksforgeeks.org/vue-js-computed-properties/](https://www.geeksforgeeks.org/vue-js-computed-properties/)

Vue 是一个用于构建用户界面的进步框架。核心库只专注于视图层，并且易于获取和与其他库集成。Vue 还完全能够结合现代工具和支持库为复杂的单页应用程序提供动力。

在 Vue.js 中，任何数据值都可以用括号输出。然而，这可能会进行小的计算，因为它仅限于单个 JavaScript 表达式，而且模板应该只关心向用户显示数据，而不执行任何逻辑计算。为了避免单个表达式的这种限制，并有更多的声明性模板，我们使用 Vue.js 的**计算属性**，计算值遵循相同的旧插值，但计算逻辑是在 JavaScript 中定义的。

**例 1:**

```js
<html>
<head>
    <script src=
"https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js">
      </script>
</head>
<body>
    <div id='parent'>

<p>{{ fullName }}</p>

    </div>
    <script src='app.js'></script>
</body>
</html>
```