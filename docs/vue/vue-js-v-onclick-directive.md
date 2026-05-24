# vista . js | v-on:点击指令

> 哎哎哎:# t0]https://www . geeksforgeeks . org/view-js-v-onclick-directive/

**v-on:click** 指令是一个 [**Vue.js**](https://www.geeksforgeeks.org/vue-js-introduction-installation/) 指令，用于向元素添加 click 事件监听器。首先，我们将创建一个 id 为 *app* 的 div 元素，让我们将 **v-on:单击**指令应用于一个元素。此外，我们甚至可以在点击发生时执行一个功能。

**语法:**

```js
v-on:click="function"

```

**参数:**该指令接受点击事件发生时将执行的功能。
**示例:**本示例使用 VueJS 通过 v-on:click 切换元素的可见性。

## 超文本标记语言

```js
<!DOCTYPE html>
<html>

<head>
    <title>
        VueJS | v-on:click directive
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
            VueJS | v-on:click directive
        </b>
    </div>

    <div id="canvas" style="border:1px solid #000000;
                            width: 600px;height: 200px;">
        <div id="app" style="text-align: center;
                             padding-top: 40px;">
            <button v-on:click="data = !data">
              Show
            </button>
            <h1 v-if="data">GeeksforGeeks</h1>
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

![](img/5d23b7a9e1440af00f20ed6a73a4cc88.png)