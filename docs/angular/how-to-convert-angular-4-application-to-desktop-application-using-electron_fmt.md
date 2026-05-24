# 如何用 Electron 将 Angular 4 应用转换成桌面应用？

> 原文：[https://www.geeksforgeeks.org/how-to-convert-angular-4-application-to-desktop-application-using-electron/](https://www.geeksforgeeks.org/how-to-convert-angular-4-application-to-desktop-application-using-electron/)

使用 Electron JS，我们可以非常容易地将我们现有的 Angular 项目转换成桌面应用程序。在这篇文章中，我们将创建一个示例 Angular 项目，并逐步将其转换为桌面应用程序。

## 先决条件

*   [必须安装 NPM](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/)

## 环境设置

*   安装 Angular 命令行界面：
```bash
npm install -g @angular/cli
```
*   创建新的 Angular 项目。这里我们的项目名称是 `electron-sample`：
```bash
ng new electron-sample
cd electron-sample
```
*   现在运行项目，打开 `http://localhost:4200` 检查安装是否成功。
```bash
ng serve -o
```
*   安装 Electron JS 作为开发依赖项：
```bash
npm install electron --save-dev
```
*   我们还需要一个名为 `electron-packager` 的包装。这个包将捆绑我们的应用程序，并产生桌面应用程序文件。全局安装：
```bash
npm install -g electron-packager
```

## 示例

在根目录中，创建一个文件 `main.js`，它将成为 Electron 的入口点。在 `main.js` 中添加以下代码：

### JavaScript 描述语言

```javascript
const { app, BrowserWindow } = require("electron");
const path = require("path");
const url = require("url");

let win;
function createWindow() {
  win = new BrowserWindow({ width: 700, height: 700 });
  // load the dist folder from Angular
  win.loadURL(
    url.format({
      // compiled version of our app
      pathname: path.join(__dirname, '/dist/index.html'),
      protocol: "file:",
      slashes: true
    })
  );
  win.on("closed", () => {
    win = null;
  });
}
app.on("ready", createWindow);
// If you are using MACOS, we have to quit the app manually
app.on("window-all-closed", () => {
  if (process.platform !== "darwin") {
    app.quit();
  }
});
```

在上面的代码中，我们简单地打开了 Angular 应用程序的编译版本，该版本位于 `dist/` 目录中。请注意，我们直接提供了 `dist` 文件夹，因此这段代码可以在任何应用程序上运行。但是文件 `index.html` 位于子目录中。因此，在 `angular.json` 中，按如下方式更改 `outputPath` 键中的值。

```json
...
"architect": {
       "build": {
         "builder": "@angular-devkit/build-angular:browser",
         "options": {
           // Make changes in this line
           "outputPath": "dist",
           "index": "src/index.html",
           ....
```

这将把编译后的文件保存到 `dist` 文件夹，而不是子目录。在 `src/index.html` 中，将行 `<base href="/">` 更改为 `<base href="./">` 如下。

```html
<head>
 <meta charset="utf-8">
 <title>ElectronSample</title>
 <base href="./">   <!-- Change this line -->
 <meta name="viewport" content="width=device-width, initial-scale=1">
 <link rel="icon" type="image/x-icon" href="favicon.ico">
</head>
```

### package.json 配置

现在在 `package.json` 中，我们除了要指向 Electron app 的起点之外，还要为我们的 app 的开发和测试添加一些命令。在 `scripts` 中添加以下行：

```json
{
 "name": "electron-sample",
 "version": "0.0.0",
 // This line will provide an entry
 // point for the electron app
 "main": "main.js",
 "scripts": {
   // Runs the app after compilation
   "electron": "electron .",
   // Compiles and runs the app
   "electron-build": "ng build --prod && electron .",
   "ng": "ng",
   "start": "ng serve",
   "build": "ng build",
   "test": "ng test",
   "lint": "ng lint",
   "e2e": "ng e2e"
 },
 ...
 ...
```

现在我们可以通过运行该应用程序来测试它：
```bash
npm run electron-build
```
请注意，如果我们在全球范围内安装了 `electron`，我们可以直接运行这些命令。您应该会看到以下输出：

**输出：**

![](img/8fc88067a529b841d8125d5c166f727b.png)

对于已编译的应用程序，我们可以使用 `npm run electron` 直接运行该应用程序。

当我们创建了最终的应用程序时，我们可以生成编译后的文件，这些文件可以直接在我们的系统上使用，而无需安装依赖项。`electron-packager` 模块帮助我们构建二进制文件。
```bash
electron-packager . --platform=linux
```
这里我们可以在 `darwin`、`linux`、`mas` 和 `win32` 中选择我们的平台。执行上述命令将创建一个带有应用程序和操作系统名称的新文件夹。在这个目录中打开终端：
```bash
sudo chmod +x electron-sample
./electron-sample
```
这将打开应用程序，您应该会看到以下输出：

**输出：**

![](img/0d9cc1556191b8f565620f1e149e14d3.png)