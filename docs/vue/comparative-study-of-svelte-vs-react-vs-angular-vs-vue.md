# Svelte vs React vs Angular vs Vue 的对比研究

> 原文:[https://www . geesforgeks . org/对比研究-svelte-vs-react-vs-angular-vs-vue/](https://www.geeksforgeeks.org/comparative-study-of-svelte-vs-react-vs-angular-vs-vue/)

**[JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) :** 网景公司的“Brendan Eich”于 1990 年创建了 JavaScript，最初将其命名为**“LiveScript”**。后来，它被改名为 JavaScript。JavaScript 是 web 的脚本语言，它使用对象来执行动作，并通过向 web 添加运动来使其活跃。学习 JavaScript 的前提是 HTML 和 CSS，可以更准确的说是 HTML5 和 CSS3。

JavaScript 已经被重命名了很多次，就像在早期版本中它被称为**“摩卡”**，然后被重命名为**“LiveScript”**此外，随着时间的推移，它被重命名为**“JavaScript”**，现在一些组织将其称为**“ECMAScript”**。

为了编写 JavaScript 的代码，对工具没有这么高端的要求，我们只需要一个文本编辑器就可以了，一些流行的文本编辑器有记事本、Notepad++、Adobe Dreamweaver。

[**苗条:**](https://www.geeksforgeeks.org/svelte-introduction-and-installation/) 苗条的特点。

*   它是一个编译器，而不是框架。
*   它不像其他框架那样添加代码块。
*   非常小的代码和快速捆绑包。
*   仅提供核心指令集。
*   没有提供额外的改进。
*   受欢迎，但有一个小社区和相当新的市场。
*   单人表演，因为它不是由团队开发的。
*   值得探索的地方在于添加了但没有很好地建立，很难找到真实世界的项目。

**例:**是 Svelte 的样例代码。

## main.js

```js
<script>
    let name = 'Geeks';
</script>

<h1>Hello {name}!</h1>
```

**输出:**

```js
Hello Geeks
```

[**ReactJS:**](https://www.geeksforgeeks.org/react-js-introduction-working/)ReactJS 的特点。

*   这是一个 JavaScript 库。
*   提供小而快速的捆绑包。
*   仅提供核心指令集。
*   提供了一些额外的改进。
*   热门且相对成熟的图书馆。
*   为脸书开发。
*   它已经很好地建立起来了，并且正在被使用，也很容易学习和实现。

**例:**是 ReactJS 的样例代码。

## 应用..射流研究…

```js
ReactDOM.render(
  <h1>Hello, Geeks!</h1>,
  document.getElementById('root')
);
```

**输出:**

```js
Hello, Geeks!
```

[**安古拉杰:**](https://www.geeksforgeeks.org/introduction-to-angularjs/) 安古拉杰的特点。

*   这是一个 JavaScript 框架。
*   提供中型快速捆绑包。
*   提供了大量功能。
*   提供了许多额外的改进。
*   受欢迎，相对更成熟。
*   由谷歌开发。
*   使用 angular 框架很好地建立并容易找到项目实现

**例:**是 AngularJS 的样例代码。

## 索引. ts

```js
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf 8" />
  </head>
  <body ng-app="app">
    <h1 ng-controller="HelloWorldCtrl">
      {{message}}
    </h1>
    <script src=
"https://code.angularjs.org/1.6.9/angular.js">
    </script>
    <script>
      angular.module("app", [])
        .controller("HelloWorldCtrl", function ($scope) {
        $scope.message = "Hello Geeks";
      });
    </script>
  </body>
</html>
```

**输出:**

```js
Hello Geeks
```

[**VueJS:**](https://www.geeksforgeeks.org/vue-js-introduction-installation/)VueJS 的特点。

*   这是一个 JavaScript 框架。
*   提供小而快速的捆绑包。
*   提供中等大小的功能集。
*   提供了一些额外的改进。
*   极受欢迎且相对成熟。
*   开源团队的努力。
*   建立框架，需要更多时间占领市场。

**例:**是 VueJS 的样例代码。

## index.html

```js
<div id="app">
  {{ message }}
</div>
```

## app.js

```js
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Geeks!'
  }
})
```

**输出:**

```js
Hello Geeks!
```