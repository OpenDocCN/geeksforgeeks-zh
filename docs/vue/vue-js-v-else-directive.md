# vista . js | v-else 指令

> 哎哎哎:# t0]https://www . geeksforgeeks . org/view-js-v-else-directive/

**v-else** 指令是一个 [**Vue.js**](https://www.geeksforgeeks.org/vue-js-introduction-installation/) 指令，仅当不满足 if 条件时用于切换元素的显示 CSS 属性。首先，我们将创建一个 id 为 *app* 的 div 元素，让我们将 *v-else* 指令应用到一个有数据的元素。现在我们将通过用包含该值的数据属性初始化一个 Vue 实例来创建这个数据。

**语法:**

```js
v-else

```

**参数:**该指令不接受任何参数。
**示例 1:** 本示例使用 VueJS 使用算术条件显示带有 v-else 的元素。

## 超文本标记语言

```js
<!DOCTYPE html>
<html>

<head>
    <title>
        VueJS | v-else directive
    </title>

    <!-- Load Vuejs -->
    <script src=
"https://cdn.jsdelivr.net/npm/vue/dist/vue.js">
    </script>
</head>

<body>
    <div style="text-align: center;width: 600px;">
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <b>
            VueJS | v-else directive
        </b>
    </div>

    <div id="canvas" style="border:1px solid #000000;
                            width: 600px;height: 200px;">
        <div id="app">
            <h2 v-if="a > 10">a is greater than 10</h2>
            <h2 v-else>a is smaller than or equal to 10</h2>
        </div>
    </div>

    <script>
        var app = new Vue({
            el: '#app',
            data: {
                a: 9
            }
        })
    </script>
</body>
</html>
```

**输出:**

![](img/8527c2a5d9ac3517254ba689fbba6d80.png)

**示例 2:** 本示例使用 VueJS，使用 booleans 显示一个带有 v-else 的元素。

## 超文本标记语言

```js
<!DOCTYPE html>
<html>

<head>
    <title>
        VueJS | v-else directive
    </title>

    <!-- Load Vuejs -->
    <script src=
"https://cdn.jsdelivr.net/npm/vue/dist/vue.js">
    </script>
</head>

<body>
    <div style="text-align: center;width: 600px;">
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <b>
            VueJS | v-else directive
        </b>
    </div>

    <div id="canvas" style="border:1px solid #000000;
                            width: 600px;height: 200px;">
        <div id="app">
            <h2 v-if="data">if is executed</h2>
            <h2 v-else>else is executed</h2>
        </div>
    </div>

    <script>
        var app = new Vue({
            el: '#app',
            data: {
                data: false
            }
        })
    </script>
</body>
</html>
```

**输出:**

![](img/71ff8ff1a8bae771495834d60a29b373.png)