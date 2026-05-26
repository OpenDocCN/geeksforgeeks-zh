# 如何使用 SCSS 加载 Font Awesome

> 原文：[https://www.geeksforgeeks.org/how-to-load-font-awesome-using-scss/](https://www.geeksforgeeks.org/how-to-load-font-awesome-using-scss/)

为了在 SCSS 中加载 Font Awesome 图标，您需要遵循以下步骤：

*   **安装 Font-Awesome 入门套件：** 前往 Font-Awesome 网站，下载免费的 Web 入门套件。
*   **在您的目录中创建项目：** 在您的项目目录中创建两个文件夹：
    *   `public`
    *   `resources`

`public` 文件夹将包含您的 HTML 和 CSS 文件，而 `resources` 文件夹包含您的 SCSS 文件。

*   **在终端中运行 `npm init`：** 通过运行 `npm init` 命令来初始化 NPM，创建一个 `package.json` 文件。

```bash
npm init
```

*   **安装 `node-sass`：** 运行 `npm init` 命令后，安装一个名为 `node-sass` 的库。这个命令将把 SCSS 编译成 CSS。
    **注意：** `node-sass` 需要作为开发依赖项安装。

```bash
npm install node-sass --save-dev
```

*   **在 `resources` 内部创建一个文件夹：** 在 `resources` 文件夹中创建一个名为 `assets` 的文件夹。解压缩下载的 Font-Awesome 初学者工具包，复制 `scss` 文件夹，并粘贴到 `assets` 文件夹。
*   **将 `webfonts` 添加到 `public` 文件夹：** 在 `css` 文件夹内创建 `style.css` 文件。复制 `webfonts` 文件夹并将其粘贴到 `public` 文件夹中。
*   **编辑 `scss` 文件夹中的 `_variables.scss` 文件：** 打开变量文件，通过写入 `webfonts` 文件夹的路径来编辑 `$fa-font-path`。

```scss
// Variables
// --------------------------

$fa-font-path:         "../webfonts" !default;
```

*   **在 `scss` 文件夹内创建 `style.scss` 文件：** 在 `scss` 文件夹内创建 `style.scss` 文件，导入 Font Awesome。

```scss
@import "fontawesome.scss";
@import "solid.scss";
```

*   **创建 `index.html` 文件：** 在 `public` 目录中创建 `index.html` 文件，并添加以下代码：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <i class="fas fa-thumbs-up"></i>
</body>
</html>
```

*   **编辑 `package.json` 文件中的 `scripts` 字段：**

```json
"scripts": {
    "compile:sass": "node-sass resources/assets/scss/style.scss public/css/style.css -w"
}
```

该命令将把 SCSS 转换成 CSS 文件，同时跟踪更改。

*   **编译你的代码：** 打开终端，使用以下命令：

```bash
npm run compile:sass
```

**注意：** 编译后如果在 `style.css` 文件中遇到以下错误，请注释或删除 `-ms-filter` 行。