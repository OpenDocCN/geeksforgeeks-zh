# 如何使用 Node.js 将 JPG 转换成 PNG？

> 原文：[https://www.geeksforgeeks.org/how-to-convert-jpg-to-png-using-node-js/](https://www.geeksforgeeks.org/how-to-convert-jpg-to-png-using-node-js/)

JPG 和 PNG 都是广泛使用的图像格式。使用这些格式允许用户包含和使用数字图像。在本文中，我们将讨论如何使用 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 将给定的 JPG 图像转换为 PNG 图像，这将有助于在我们的 web 应用程序中使用该图像。

**Jimp (JavaScript 图像处理程序):**

[Jimp](https://www.npmjs.com/package/jimp) 是一个完全用 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 编写的图像处理库，由 Node 使用。对于 JPG 到 PNG 的转换，我们将使用 Jimp。

**安装:**

要在我们的项目中安装 Jimp，我们只需将其 npm 模块安装到我们的项目中。这可以通过在我们的终端中执行下面一行来完成。

```js
npm install --save jimp
```

**用法:**

为了在我们的项目中使用它，我们需要使用下面一行代码将包导入到我们的 `index.js` 文件中。

```js
const Jimp = require("jimp");
```

现在我们已经安装了 Jimp 并准备使用，我们可以继续将 JPG 转换为 PNG。

**JPG 至 PNG 转换:**

我们将使用 `.read()` 和 `.write()` 方法做转换。让我们考虑一个例子，我们将有一个输入 JPG 图像，然后将其转换为 PNG 图像。

**示例:**

假设我们有一个 JPG 图像作为输入。

![](img/985142b124bd6799e9d48c6e95339f1a.png)

gfg.jpg 格式

我们将代码保存在 `images` 文件夹中。现在将其转换为 PNG 格式，我们的脚本代码如下所示。

## index.js

```js
// Importing the jimp module
const Jimp= require("jimp");

//We will first read the JPG image using read() method. 
Jimp.read("images/gfg.jpg", function (err, image) {
  //If there is an error in reading the image, 
  //we will print the error in our terminal
  if (err) {
    console.log(err)
  } 
  //Otherwise we convert the image into PNG format 
  //and save it inside images folder using write() method.
  else {
    image.write("images/gfg.png")
  }
})
```

在使用 `node` 执行代码时，我们应该能够在 `images` 文件夹中获得 PNG 转换后的图像，如下所示。

**输出:**

![](img/39da02ca6e546d6dab13bb16512da2a1.png)