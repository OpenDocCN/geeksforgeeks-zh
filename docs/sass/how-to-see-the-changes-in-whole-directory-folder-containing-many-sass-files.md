# 如何查看包含很多 sass 文件的整个目录/文件夹的变化？

> 原文:[https://www . geesforgeks . org/如何查看包含许多 sass 文件的整个目录文件夹中的更改/](https://www.geeksforgeeks.org/how-to-see-the-changes-in-whole-directory-folder-containing-many-sass-files/)

SASS 是一种强大的预处理语言，可以帮助我们以简单明了的方式更高效地编写代码。sass 的一些最佳特性是使用变量、支持嵌套和使用函数。虽然它有很多优点，但跟踪 sass 文件中的所有更改似乎是一项复杂的任务。
在 sass 文件中编译更改的最简单方法可以在**节点包管理器(NPM)的帮助下完成。**
为此，你需要安装最新版本的 Node.js 或者拥有稳定的 LTS 版本的 Node。要检查系统中是否正确安装了 Node.js，请在终端/命令提示符下运行以下命令:

```html
node -v 

npm -v 

```

安装最新版本的 Node.js 后，按照以下步骤编译您的 sass 文件。这些是:

*   **Initialize NPM in your root directory using the terminal.**

    ```html
    npm init
    ```

    `npm init`命令会询问一些问题，以便在您的项目中生成一个 package.json 文件。该文件包含有关已安装依赖项的信息。
    **为了绕过这些问题，您可以键入以下命令:**

    ```html
    npm init -y
    ```

    这将自动将选项设置为默认值。

*   **Install node-sass.**

    ```html
    npm install node-sass --save-dev

    ```

    Node-sass 是一个将 SCS 本机编译成 css 文件的库。此命令将安装 node-sass 作为开发依赖项。

*   **In the package.json file, you need to make changes to the scripts field.**

    ```html
    "scripts" :{
      "compile:sass": "node-sass sass/main.scss css/style.css -w"
    }
    ```

    这个命令告诉我们寻找我们的主 sass 文件，并将其编译成 CSS。`-w`代表 watch 标志，用于跟踪源文件中的所有更改，并在每次保存 sass 文件时重新编译。

*   **在你的终端运行命令:**打开终端运行命令:

    ```html
    npm run compile:sass

    ```