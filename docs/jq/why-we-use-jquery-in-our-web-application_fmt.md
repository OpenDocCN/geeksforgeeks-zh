# 为什么我们在 web 应用中使用 jQuery？

> 原文：[https://www.geeksforgeeks.org/why-we-use-jquery-in-our-web-application/](https://www.geeksforgeeks.org/why-we-use-jquery-in-our-web-application/)

[`jQuery`](https://www.geeksforgeeks.org/jquery-tutorials/) 是一个快速、功能丰富、轻量级的 [`JavaScript`](https://www.geeksforgeeks.org/javascript-tutorial/) 库。使用 jQuery 的主要目的是让您在现代和智能的网站上使用 JavaScript 变得更加容易。强烈建议具备 [`HTML`](https://www.geeksforgeeks.org/html-tutorials/)、[`CSS`](https://www.geeksforgeeks.org/css-tutorials/)、[`JavaScript`](https://www.geeksforgeeks.org/javascript-tutorial/) 的基础知识。

jQuery 的开发是为了通过减少代码来节省开发人员的时间。它承担了大量的常见任务，需要许多行 JavaScript 代码来执行，并将它们包装成策略，您可以用一行代码来命名这些策略。

## 在应用程序中使用 jQuery 的理由

*   **简单易懂：** 它的代码比 JavaScript 简单。所以你只需要写几行代码就可以做同样的事情。此外，构建者不应该是编程或网页布局方面的专业人士来为他们的网站创建令人难以置信的模式。任何花了几个小时编写和测试 CSS 文档的开发人员都会认识到 jQuery 带来的简单实现。此外，还有一组强大的 [`jQuery` 用户界面添加剂](https://www.geeksforgeeks.org/jquery-plugins-introduction/)，建设者可以将其插入他们的网站。

参考下面的例子，你可能会明白。

**JavaScript 代码片段：**

```html
function changeColor(color) {
    document.body.style.background = color;
}

Onload = changeColor('green');
```

**jQuery 语法：**

```html
$('body').css('background', 'green');
```

从上面的例子可以注意到，JavaScript 代码比 jQuery 代码更长更复杂。这两个代码都在执行相同的改变背景颜色的工作，但是 jQuery 需要更少的代码。您可以参考其他示例，这表明 jQuery 最大限度地减少了代码，并且使用起来不那么复杂。

*   **与其他 IDE 轻松集成：** 大多数网络开发人员通过使用 Visual Studio 熟悉 [`nuget`](https://www.nuget.org/)。这也是为什么 [`jQuery`](https://jquery.com/) 在 .NET 开发人员中的认可度持续发展的部分原因。随着 [`jQuery` 单元 for Windows](https://docs.microsoft.com/en-us/previous-versions/windows/apps/hh454774(v=vs.105)) 的难度增加，您现在拥有了适用于 Windows Phone 平台的 [`jQuery`](https://jquery.com/) 库的所有开发优势。
*   **动画变得简单：** [`jQuery`](https://jquery.com/) 使用 [`CSS`](https://www.geeksforgeeks.org/css-tutorials/)、[`HTML`](https://www.geeksforgeeks.org/html-tutorials/)、[`JavaScript`](https://www.geeksforgeeks.org/javascript-tutorial/) 和 [`AJAX`](https://www.geeksforgeeks.org/ajax-tutorial/)。通过这种方法，您可以在您的网站上实践一种在线优化方法，而无需为 [`Flash`](https://www.geeksforgeeks.org/introduction-to-flash/) 等技术进行独特的更改。您可以获得良好的搜索结果，以保持您的受众参与。
*   **更快：** 许多搜索引擎将页面加载时间视为主要因素之一，因为它会影响 [`SEO`](https://www.geeksforgeeks.org/what-is-seo-search-engine-optimization/)。因此，当今世界上的每个开发人员都希望代码尽可能简洁。使您的网站更快的最佳方法是编写更少的代码，这可以通过使用最简单的 [`JavaScript`](https://www.geeksforgeeks.org/javascript-tutorial/) 库 [`jQuery`](https://jquery.com/) 来实现。
*   **对 SEO 友好：** [`SEO`](https://www.geeksforgeeks.org/what-is-seo-search-engine-optimization/) 代表搜索引擎优化，是提高来自搜索引擎的网站或网页流量质量和数量的过程。所以许多流行的搜索引擎如 [`Google`](https://www.google.com/)、[`Bing`](https://www.bing.com/) 和 [`Yahoo`](https://www.yahoo.com/) 都使用 [`SEO`](https://www.geeksforgeeks.org/what-is-seo-search-engine-optimization/)。[`jQuery`](https://jquery.com/) 可以针对搜索引擎进行优化，并且有许多插件可供开发人员使用。
*   **在所有主流浏览器中运行：** [`jQuery`](https://jquery.com/) 库背后的团队知道所有主流浏览器中通常会出现什么主要问题。因此他们开发了这个库来简化开发人员的工作。