# 如何在 Node.js 中使用 Handlebars 显示图像？

> 原文：[https://www.geeksforgeeks.org/how-to-display-images-using-handlebars-in-node-js/](https://www.geeksforgeeks.org/how-to-display-images-using-handlebars-in-node-js/)

在本文中，我们将讨论如何使用 `Node.js` 中的 [Handlebars](https://www.geeksforgeeks.org/handlebars-templating-in-expressjs/) 来显示图像。您可以参考[这篇](https://www.geeksforgeeks.org/how-to-setup-handlebars-view-engine-in-node-js/)文章来设置 `Node.js` 中的 Handlebars 视图引擎。

我们将使用以下步骤来实现我们的目标：

1.  安装 `express` 和 `express-handlebars`
2.  设置我们的 `express` 服务器。
3.  创建基本 Handlebars 的文件夹结构。
4.  定义正确的路由。

## 安装 express 和 express-handlebars

```js
npm install --save express express-handlebars
```

## 设置 express 服务器

```js
//importing modules
import express from "express"
import path from "path"
import exphbs from "express-handlebars"

// Express server's instance
const app = express();

const PORT = process.env.PORT || 3000;

// listening
app.listen(PORT, () => console.log(`Server started running on PORT ${PORT}`));
```