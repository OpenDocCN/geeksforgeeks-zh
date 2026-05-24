# 使用 VueJS 中的过滤器将字符串大写

> 原文:[https://www . geesforgeks . org/capitalizing-a-string-use-filters-in-vuejs/](https://www.geeksforgeeks.org/capitalizing-a-string-using-filters-in-vuejs/)

Vue.js 是一个用于构建用户界面的渐进式框架。核心库只专注于视图层，并且易于获取和与其他库集成。Vue 还完全能够结合现代工具和支持库为复杂的单页应用程序提供动力。

过滤器是 Vue 组件提供的功能，可用于对模板动态数据的任何部分应用格式和转换。组件的筛选器属性是一个对象。单个过滤器是接受一个值并返回另一个值的函数。返回值是实际打印在 Vue.js 模板中的值。要使用大写字符串，我们必须在过滤器中编写字符串大写逻辑，并将过滤器应用于所需的字符串。

**例:**

```js
<html>
<head>
  <script src=
"https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js">
  </script>
</head>
<body>
  <div id='parent'>
    <h1 style="color: green;">
      GeeksforGeeks
    </h1>

<p><strong>Name : </strong>
      {{ name | capitalising }}
    </p>

<p><strong>Details : </strong>
      {{ details | capitalising }}
    </p>

  </div>
    <script src='app.js'></script>
</body>
</html>
```