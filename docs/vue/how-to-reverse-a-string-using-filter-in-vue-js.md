# 如何在 Vue.js 中使用滤镜反转字符串？

> 原文:[https://www . geeksforgeeks . org/如何使用 vue-js 中的过滤器反转字符串/](https://www.geeksforgeeks.org/how-to-reverse-a-string-using-filter-in-vue-js/)

Vue 是一个用于构建用户界面的进步框架。核心库只专注于视图层，并且易于获取和与其他库集成。Vue 还完全能够结合现代工具和支持库为复杂的单页应用程序提供动力。

过滤器是 Vue 组件提供的一项功能，允许您对模板动态数据的任何部分应用格式和转换。组件的筛选器属性是一个对象。单个过滤器是接受一个值并返回另一个值的函数。返回值是实际打印在 Vue.js 模板中的值。要使用过滤器反转字符串，我们必须编写逻辑来反转字符串，并将过滤器应用于所需的字符串。

**方法 1:** 在这种方法中，我们将使用 JavaScript inbuild 方法 split()，reverse()和 join()。split()方法用于拆分每个字符，并转换为一组字符数组。reverse()方法将数组字符作为一个整体反转，finally join 方法将字符数组转换为普通字符串。

## 【index.html】

```js
<!DOCTYPE html>
<html lang="en">

<head>
    <script src=
"https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js">
    </script>
</head>

<body>
    <div id='parent'>
        <p><strong>Original String:
            </strong>{{st1}}
        </p>

        <p><strong>Reverse String :
            </strong>{{ st1 | reverse }}
        </p>
        </br>

        <p><strong>Original String:
            </strong>{{st2}}
        </p>

        <p><strong>Reverse String :
            </strong>{{ st2 | reverse }}
        </p>
    </div>

    <script src='app.js'></script>
</body>

</html>
```