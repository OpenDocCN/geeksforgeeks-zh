# 如何检查是否加载了 jQuery 插件？

> 原文：[https://www.geeksforgeeks.org/how-to-check-if-a-jquery-plugin-is-loaded/](https://www.geeksforgeeks.org/how-to-check-if-a-jquery-plugin-is-loaded/)

有多种方法可以让我们简单地检查 jQuery 插件是否使用 jQuery 成功加载。我们还可以检查插件中的特定功能是否可访问。本教程将演示如何检查是否加载了 jQuery 插件。

## 步骤

**步骤 1:** 使用 [npm](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/) 安装 [`browser-sync`](https://www.browsersync.io/)。我们将使用 `browser-sync` 启动一个服务器，并提供一个网址来查看 HTML 网站，并使用内容交付网络加载 `jQuery`。我们将在全球范围内安装 `browser-sync`。

```bash
npm install -g browser-sync
```

**步骤 2:** 我们将在本教程中使用 [`jQuery-UI`](https://jqueryui.com/) 插件。我们将使用 `jQuery` 测试这个插件是否成功加载。下载这个插件的最新版本，并将其解压到您的项目根文件夹中。

**步骤 3:** 创建一个 `index.html` 文件。

### 示例 1

`jQuery` 插件是 `jQuery` 作用域上的命名空间。`jquery-ui` 插件不扩展 `fn` 命名空间，因此我们可以使用上述代码检查插件是否成功加载。`ui` 代表插件的名称，可以替换为要检查的插件名称。我们在 `head` 标签中加载了 `jQuery`，因为它需要在应用程序中使用之前就可用。建议将所有 JavaScript 文件加载到 `body` 标签的末尾，以提高性能并更快地渲染页面。因此，我们在检查插件是否成功加载之前使用了 `$(document).ready()` 函数。

[`typeof`](https://www.geeksforgeeks.org/javascript-typeof-operator/) 运算符以字符串形式返回其操作数的数据类型。在本例中，操作数是 `jQuery` 的 `$` 运算符本身。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>JQuery Plugin</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
</head>
<body>
    <div>Hello GeeksForGeeks</div>
    <script type="text/javascript">
        $(document).ready(function () {
            if (typeof $.ui !== 'undefined') {
                console.log('jquery-ui is loaded successfully')
            }         
        });
    </script>
    <script src="jquery-ui-1.12.1/jquery-ui.js" type="text/javascript"></script>
</body>
</html>
```

### 示例 2

由于每个插件都保证有一些功能定义或值等同于 `true`，我们可以使用代码中所示的较短版本。

```javascript
if ($.ui) {
    console.log('jquery-ui is loaded successfully')
}
```