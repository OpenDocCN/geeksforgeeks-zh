# 如何使用 Vue.js 删除特定字符串的所有出现？

> 原文:[https://www . geesforgeks . org/如何使用-vue-js/](https://www.geeksforgeeks.org/how-to-delete-all-occurrences-of-a-particular-string-using-vue-js/) 删除特定字符串的所有出现

在本文中，我们将学习如何使用 VueJS 中的过滤器删除特定单词的所有出现。Vue 是一个用于构建用户界面的进步框架。过滤器是 Vue 组件提供的一项功能，允许您对模板动态数据的任何部分应用格式和转换。组件的筛选器属性是一个对象。单个过滤器是接受一个值并返回另一个值的函数。返回值是实际打印在 Vue.js 模板中的值。

通过对所需字符串使用过滤器，可以删除特定单词的出现。我们将使用 JavaScript **split()** 方法在必须删除的特定目标单词上分割字符串。这将返回一个数组，该数组在除用于拆分字符串的单词之外的特定单词出现的位置进行拆分。最后，我们将使用 **join()** 方法连接数组并返回结果字符串。

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
    <div>
      <strong>After Delete: </strong> 
      {{ st1 | delete('computer') }}
    </div>
    </p>

    <p>
      <strong>Original String: </strong>
      {{st2}}
    <div>
      <strong>After Delete: </strong> 
      {{ st2 | delete('language') }}
    </div>
    </p>

  </div>
  <script src='app.js'></script>
</body>
</html>
```