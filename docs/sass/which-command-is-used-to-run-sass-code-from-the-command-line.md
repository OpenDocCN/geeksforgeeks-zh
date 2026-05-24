# 哪个命令用于从命令行运行 SASS 代码？

> 原文:[https://www . geesforgeks . org/哪个命令用于从命令行运行 sass 代码/](https://www.geeksforgeeks.org/which-command-is-used-to-run-sass-code-from-the-command-line/)

在本文中，我们将讨论如何从命令行运行 SASS 代码。 **SASS(语法上很棒的样式表)**是一个简单的 CSS 预处理器，它可以为网站创建可管理的、独立于平台的、可重用的样式表。它完全兼容 CSS 的每个版本。Sass 减少了 CSS 的重复，因此节省了时间。SASS 不直接用 HTML 运行。因此，在网页上使用 SASS 之前，我们必须将其转换为 CSS，我们可以通过使用 npm 包管理器的 SASS 包来实现这一点。

**配置 SASS 编译成 CSS:** 我们可以使用以下命令从 npm 安装最新版本的 SASS 包。在我们运行以下命令之前，必须在系统上安装 Node.js。详细安装流程请参考 [Node.js NPM(节点包管理器)](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/)。现在，运行下面的命令来全局安装 SASS 编译器。

**语法:**

```html
npm install sass -g
```

**注意:**如果安装过程中因为权限问题出现问题，请以管理员身份运行命令提示符。

如果 SASS 仍然没有安装使用，请使用下面的命令。

```html
sudo npm install sass -g
```

此命令以超级用户权限将 SASS 全局安装到系统中。

**将 SASS 预编译成 CSS:**

为了将 SASS 编译成 CSS，我们在命令提示符下使用下面的命令。sass 命令允许我们将 SASS 文件预编译成一个基本的 CSS 文件。这有助于我们使用 SASS 编程编写模块化代码，并通过将其编译成传统的快速 CSS 来获得 CSS 的所有好处。

**语法:**

```html
sass <source> [destination]
```

**参数:**有以下参数。

*   **来源:**SASS 文件的完整名称，地址来自当前工作目录。
*   **目的地:**所需 CSS 文件的完整名称，地址来自当前工作目录。

**例 1:** 如果我们在当前的工作目录中有一个文件 style . SCS，我们想把它编译成一个 css 文件，作为同一个目录中的 style.css。我们使用以下命令:

```html
sass style.scss style.css
```

## style . scss

```html
$color: green;
$font: "Times New Roman";
.container1 {
    font-family: $font;
}
.container2 {
    background-color: $color;
}
```

**输出:**

## style.css

```html
.container1 {
    font-family: "Times New Roman";
}
.container2 {
    background-color: green;
}
```

**示例 2:** 如果我们在另一个目录中有一个文件 style . SCS(在这种情况下，它在“D:\Geeksforgeeks”中)，而不是在当前目录中，并且我们希望在同一个目录中将它编译成一个作为 style.css 的 css 文件，我们可以使用以下命令:

```html
sass D:\Geeksforgeeks\style.scss D:\Geeksforgeeks\style.css
```

## style . scss

```html
$color1: blue;
$color2: red;
$font: 20px;

body {
    background-color: $color1;
    color: $color2;
    font-size: $font;
}
```

**输出:**

## style.css

```html
body {
    background-color: blue;
    color: red;
    font-size: 20px;
}
```