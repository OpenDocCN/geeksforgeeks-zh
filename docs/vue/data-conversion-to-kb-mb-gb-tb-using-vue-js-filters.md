# 使用 Vue.js 过滤器将数据转换为 KB、MB、GB、TB

> 原文:[https://www . geesforgeks . org/data-conversion-to-kb-MB-GB-TB-using-vue-js-filters/](https://www.geeksforgeeks.org/data-conversion-to-kb-mb-gb-tb-using-vue-js-filters/)

在本文中，我们将学习如何使用 VueJS 中的过滤器将数据转换为给定的数据单元。过滤器是 Vue 组件提供的一项功能，允许您对模板动态数据的任何部分应用格式和转换。组件的筛选器属性是一个对象。单个过滤器是接受一个值并返回另一个值的函数。返回值是实际打印在 Vue.js 模板中的值。

可以使用过滤器将数据值缩写为 KB、MB、GB 或 TB。滤波器的逻辑首先将该值除以 1024，再乘以常数的幂。例如，要以千字节为单位转换值，假定常数为 1，同样，对于以兆字节为单位的值，常数值为 2，依此类推。

下面的示例将演示这种方法:

**示例:**在本例中，我们将把各种字节值转换为给定给定过滤器的给定数据单位。

## index.html

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
    <p><strong>Bytes: </strong>{{d1}}B</p>

    <p><strong>MegaBytes : </strong>
      {{ d1 | bytes('MB') }}
    </p>

    <p><strong>Bytes: </strong>{{d2}}B</p>

    <p><strong>KiloBytes : </strong>
      {{ d2 | bytes('KB') }}
    </p>

    <p><strong>Bytes: </strong>{{d3}}B</p>

    <p><strong>TeraBytes : </strong>
      {{ d3 | bytes('TB') }}
    </p>

    <p><strong>Bytes: </strong>{{d4}}B</p>

    <p><strong>GigaBytes : </strong>
      {{ d4 | bytes('GB') }}
    </p>

  </div>
  <script src='app.js'></script>
</body>
</html>
```

## app.js

```js
const parent = new Vue({
  el: "#parent",

  // Define the data to be converted
  data: {
    d1: 200000,
    d2: 1024,
    d3: 3532283533343,
    d4: 24322664648,
  },

  filters: {
    bytes: function (data, to) {
      const const_term = 1024;

      // Convert the values and concatenate
      // the appropriate unit
      if (to === "KB") {
        return (data / const_term).toFixed(3) + "KB";
      } else if (to === "MB") {
        return (data / const_term ** 2).toFixed(3) + "MB";
      } else if (to === "GB") {
        return (data / const_term ** 3).toFixed(3) + "GB";
      } else if (to === "TB") {
        return (data / const_term ** 4).toFixed(3) + "TB";
      } else {
        return "Please pass valid option";
      }
    },
  },
});
```

**输出:**

![](img/1a374deb5ca23ee93424b5b8dab19b04.png)