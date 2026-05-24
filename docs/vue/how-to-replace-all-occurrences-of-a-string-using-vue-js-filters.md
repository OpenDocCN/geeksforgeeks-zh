# 如何使用 Vue.js 过滤器替换字符串的所有出现？

> 原文:[https://www . geesforgeks . org/如何使用-vue-js-filters 替换所有出现的字符串/](https://www.geeksforgeeks.org/how-to-replace-all-occurrences-of-a-string-using-vue-js-filters/)

在本文中，我们将学习如何使用 VueJS 中的过滤器将某个特定单词的所有出现替换为其他单词。Vue 是一个用于构建用户界面的进步框架。过滤器是 Vue 组件提供的一项功能，允许您对模板动态数据的任何部分应用格式和转换。组件的筛选器属性是一个对象。单个过滤器是接受一个值并返回另一个值的函数。返回值是实际打印在 Vue.js 模板中的值。

给定字符串中特定单词的出现替换为其他单词可以通过对所需字符串应用筛选器来完成。我们将使用 JavaScript **split()** 方法在需要替换的目标单词或字符上拆分字符串。这将返回一个数组，该数组包含字符串中除用于拆分字符串的单词或字符之外的所有单词。然后我们将使用 **join()** 方法将数组连接回来。此方法接受一个参数，该参数表示将数组连接回来时将使用的字符串。这将使添加所需的替换词成为可能。我们将最终返回结果字符串。

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
      <strong>After Replacing words: </strong>
      {{ st1 | replace('cse','computer science') }}
    </div>
    </p>

    <p>
      <strong>Original String: </strong>{{st2}}
    <div>
      <strong>After Replacing characters: </strong>
      {{ st2 | replace('!','.') }}
    </div>
    </p>

  </div>
  <script src='app.js'></script>
</body>
</html>
```