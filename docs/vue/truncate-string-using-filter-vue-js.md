# 使用 Vue.js 中的过滤器截断字符串

> 原文:[https://www . geesforgeks . org/truncate-string-use-filter-vue-js/](https://www.geeksforgeeks.org/truncate-string-using-filter-vue-js/)

在本文中，我们将学习如何在 VueJS 中使用过滤器截断字符串。过滤器是 Vue 组件提供的一项功能，允许您对模板动态数据的任何部分应用格式和转换。组件的筛选器属性是一个对象。单个过滤器是接受一个值并返回另一个值的函数。返回值是实际打印在 Vue.js 模板中的值。

字符串提取可以通过对所需的字符串应用过滤器来执行。可以有两种方法来编写过滤器函数的逻辑:

**方法 1:** 在这个方法中，我们使用了 JavaScript 内置方法**拆分、切片**以及**连接**。**拆分**方法用于拆分每个字符，并将其转换为一组字符数组。**切片**方法提取字符串的所需部分并返回。 **join** 方法用于将字符数组转换为普通字符串。我们将一起使用这三种方法来截断字符串。 **substr** 方法也可以用来返回截断的字符串。

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
        <p>
          <strong>Original String: </strong>
            {{st1}}
        </p>

        <p>
          <strong>Truncated String : </strong>
            {{ st1 | truncate(13) }}
        </p>

    </div>
    <script src='app.js'></script>
</body>
</html>
```