# `npm install` 命令中的 `--save` 选项是什么意思？

> 原文：[https://www.geeksforgeeks.org/what-is-the-meaning-of-save-for-npm-install/](https://www.geeksforgeeks.org/what-is-the-meaning-of-save-for-npm-install/)

`NPM(节点包管理器)`是 Node.js 中 JavaScript 运行时环境采用的默认包管理器，它有一个非常常用的命令 `npm install [package-name] --save`。但事实是 `npm install [package-name]` 和 `npm install [package-name] --save` 在 npm 5.0.0 之后的更高版本中没有区别。

在 npm 5.0.0 之前，有必要在包名后添加 `--save`，因为它会将安装的包保存到 `package.json` 文件的依赖项部分。如果您正在使用最新版本的 npm，请避免不必要的输入，并使用 `npm install [package-name]` 而不是 `npm install [package-name] --save`。默认情况下，它会将已安装的包添加到 `package.json` 文件中的依赖列表中。

**NPM 有下面列出的几个命令：**

1.  **`--save` 或 `-s`：** 当此命令与 `npm install` 一起使用时，它会将所有安装的核心包保存到 `package.json` 文件的依赖部分。核心依赖是那些没有它们您的应用程序将无法给出预期结果的包。但如前所述，在 NPM 5.0.0 版本之后，这是一个不必要的功能。

    ```bash
    npm install --save
    ```

2.  **`--save-prod` 或 `-p`：** 以下命令是在 npm 的后期版本中引入的，除非有其他命令（如 `-D` 或 `-O`），否则它将执行与 `--save` 命令相同的任务。

    ```bash
    npm install --save-prod
    ```

3.  **`--save-dev` 或 `-D`：** 使用 `--save-dev` 或 `-D` 命令将您安装的包添加到 `package.json` 文件的 `devDependency` 部分。开发依赖是仅用于开发目的的包，它们不会影响应用程序的结果。

    ```bash
    npm install --save-dev
    ```

4.  **`--save-optional` 或 `-o`：** 使用此命令时，安装的包将被列在 `package.json` 文件的 `optional Dependency` 部分。可选依赖是仅在使用应用程序的特定功能时才需要的包，如果不使用该功能，则不需要这些包。

    ```bash
    npm install --save-optional
    ```

5.  **`--no-save`：** 当此命令与 `npm install` 一起使用时，它将不允许将安装的包保存到依赖项部分。

    ```bash
    npm install --no-save
    ```

**注意：** NPM 提供了两个额外的选项来将依赖项保存到 `package.json` 文件中。

1.  **`--save-exact` 或 `-e`：** 这是 npm 提供的一个额外或可选的命令，它将保存在开发时配置的已安装软件包的精确版本。它不会从 npm 的默认服务器范围操作符下载依赖项。

    ```bash
    npm install --save-exact
    ```

2.  **`--save-bundle` 或 `-b`：** 当使用 `--save-bundle` 或 `-B` 时，以下命令也是可选的。这还会将保存的依赖项添加到 `bundleDependency` 列表下。

    ```bash
    npm install --save-bundle
    ```