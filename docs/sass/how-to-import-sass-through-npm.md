# 如何通过 npm 导入 SASS？

> 原文:[https://www . geesforgeks . org/如何通过 npm 导入 sass/](https://www.geeksforgeeks.org/how-to-import-sass-through-npm/)

**[SASS 简介:](https://www.geeksforgeeks.org/css-preprocessor-sass/)** SASS 代表“语法上令人敬畏的样式表”。它是 CSS 的扩展，使得使用 CSS 变量、嵌套规则、内联导入和许多其他重要功能变得容易

**SASS 有两个语法选项:**

*   **SCSS (Sassy CSS):** 它使用了。scss 文件扩展名，并且完全符合 css 语法。
*   **SASS:** 它使用。sass 文件扩展名和缩进，而不是括号。

**注意:**可以使用 **sass-convert** 命令将文件从一种语法转换为另一种语法。

**安装 SASS 的步骤:**
**步骤 1:** 要安装 SASS，首先确保系统中已经安装了**节点和 npm** 。如果没有，则使用下面给出的说明安装它们。

*   首先，下载系统中某个节点的最新版本并安装。
*   现在转到命令提示符，并指定要安装 SASS 的文件夹。
*   之后，你要创建 **package.json** 文件。它管理我们项目的依赖关系。
*   使用下面写的命令，询问用户选择的包名和描述。还有一些手续，只需按回车键，您的 **package.json** 文件将被创建。

    ```html
    npm init
    ```

**步骤 2:** 现在要安装 SASS，只需使用一个简单的命令:

```html
npm install node-sass --save
```

**注意:****––上述命令中的**保存用于将 SASS 保存在 json 文件的依赖项中。
现在，您的系统已经成功安装了 SASS。

**第三步:**要使用 SASS，请转到项目中的 package.json 文件，即如果您正在使用 VSC，请在那里打开您的项目，然后打开 package.json 文件。
你会得到这样的包. json 文件:

```html
{
    "name": "sass-ex",
    "version": "1.0.0",
    "description": "",
    "main": "index.js",
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
    },
    "author": "",
    "license": "ISC"
}

```

去掉“测试”脚本，添加自己的脚本名称**编译:sass** (可以选择任何其他名称)，给出你的 sass 文件的链接作为目标。

package.json 应该如下所示:

```html
{
    "name": "sass-ex",
    "version": "1.0.0",
    "description": "",
    "main": "index.js",
    "scripts": {
        "compile:sass": "node-sass scss/style.scss css/style.css"
    },
    "author": "",
    "license": "ISC"
}
```

现在返回命令提示符并运行命令

```html
npm rum compile:sass
```

或者像这样添加 node-sass 脚本:
在您选择的文本编辑器中打开 package.json 文件，并在“scripts”对象内添加以下行:

```html
"scss": "node-sass --watch assets/scss -o assets/css"
```

package.json 文件如下所示:

```html
{
    "name": "sass-ex",
    "version": "1.0.0",
    "description": "",
    "main": "index.js",
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "scss": "node-sass --watch assets/scss -o assets/css"
    },
    "author": "",
    "license": "ISC"
}

```

保存文件并关闭它。现在在项目目录的根目录下，运行下面给出的命令，开始监视对的任何更改。scss 文件。

```html
npm run scss
```

**安装 sass 的替代方法:**多知道一点就好了。因此，对于安装 Sass，也有一些替代方法。您可以通过付费和免费应用程序安装萨斯，如[代码包](https://codekitapp.com/)。您可以通过从[官方 Github 网站](https://github.com/sass)下载软件包来安装 Sass，并将其直接添加到您的路径中。

**安装 node-sass:** 一旦安装了 npm，就该安装 node-sass 了。您可以通过在终端中运行此命令来全局安装软件包。

```html
npm install -g node-sass
```

或者，您可以在没有 **-g** 标志的情况下运行上述命令，以便仅安装到您的当前目录，如下所示。

```html
npm install node-sass
```