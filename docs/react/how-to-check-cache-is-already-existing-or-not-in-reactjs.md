# 如何检查 ReactJS 中缓存是否已经存在？

> 原文:[https://www . geeksforgeeks . org/如何检查缓存是否已经存在-reactjs/](https://www.geeksforgeeks.org/how-to-check-cache-is-already-existing-or-not-in-reactjs/)

我们可以在 ReactJS 中使用以下方法来缓存是否已经存在。我们可以从浏览器中检查缓存是否已经存在，并在需要时在我们的应用程序中使用它。缓存是一种技术，它帮助我们将给定资源的副本存储到浏览器中，并在请求时提供给用户。

**方法:**按照这些简单的步骤检查缓存是否已经存在于 ReactJS 中。我们已经创建了我们的 *isCacheAlreadyExisting()* 函数，该函数接受缓存名称，并根据给定的缓存名称是否已经存在来返回 true/false。当我们点击按钮时，该功能被触发，它检查缓存是否已经存在。在下面的示例中，我们试图检查缓存三和缓存八是否已经存在于浏览器中，我们的浏览器有五个缓存，命名为缓存一、缓存二、缓存三、缓存四和缓存五，如下所示:

![](img/8ac15bc68f3016d570fd085243e903ac.png)

**创建反应应用程序:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

```jsx
cd foldername
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**App.js:** 现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

App.js