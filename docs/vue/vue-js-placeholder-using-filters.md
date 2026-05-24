# 使用过滤器的 Vue.js 占位符

> 原文:[https://www . geesforgeks . org/vue-js-placeholder-using-filters/](https://www.geeksforgeeks.org/vue-js-placeholder-using-filters/)

[Vue。JS](https://www.geeksforgeeks.org/vue-js-introduction-installation/) 过滤器是 Vue 组件提供的一项功能，允许您对模板动态数据的任何部分应用格式和转换。组件的筛选器属性是一个对象。单个过滤器是接受一个值并返回另一个值的函数。返回值是实际打印在 Vue.js 模板中的值。这里是一个占位符，我们关心的是，如果数据没有按照要求进入任何函数，那么函数就没有相应地执行，在我们的应用程序(网页)中，函数应该返回的地方现在变成了空白。在这些情况下，我们可以使用一个占位符(它也可以用来提供一些错误消息，比如数据没有作为例外接收)

**示例-1(当数据如预期出现时):**当数据如预期出现时，屏幕中的输出如预期出现。如果在某个情况下，我们的应用程序内部无法获取数据，或者它包含空值或空值，那么该位置上的屏幕似乎不是空的，否则用户界面会受到影响。在这里的例子中，我试图显示当默认值(占位符值)和当实际数据。

## index.html

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
        <h3>Message From GeekforGeeks</h3>

        <p><strong></strong>{{ name | gfgMsg }}</p>
    </div>
    <script src='app.js'></script>
</body>

</html>
```

## app . js

```js
const parent = new Vue({
    el: '#parent',
    data: {
        name: 'Techies!'
    },

    filters: {
        gfgMsg: function(data) {
            if (data.length === 0) {
                return "Welcome to GeekforGeeks
                Computer Science Portal,\n\
                Explore yourself as much as you can!"
            } else {
                return `Hi ${data}, We hope you have
                a very good memory,\n learning\
                 with GeekforGeeks`
            }
        }
    }
})
```