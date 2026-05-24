# jQuery | Introduction

> 原文:[https://www.geeksforgeeks.org/jquery-introduction/](https://www.geeksforgeeks.org/jquery-introduction/)

**jQuery** 是一个开源的 JavaScript 库，它简化了 HTML/CSS 文档，或者更准确地说是文档对象模型(DOM)和 JavaScript 之间的交互。
通过阐述这些术语，jQuery 简化了 HTML 文档遍历和操作、浏览器事件处理、DOM 动画、Ajax 交互和跨浏览器 JavaScript 开发。
![](img/529c9c5d29a0ccde2c4a40a3e97de0a1.png)
**注:**目前唯一能同时满足设计者类型和程序员类型需求的库是 jQuery。

jQuery 以其“少写多做”的哲学而闻名这个哲学可以进一步阐述为三个概念:

*   找到一些元素(通过 CSS 选择器)并使用它们做一些事情(通过 jQuery 方法)，即在 DOM 中定位一组元素，然后使用该组元素做一些事情。
*   在一组元素上链接多个 jQuery 方法
*   使用 jQuery 包装和隐式迭代

<u>**在 HTML 页面上使用 jQuery (JS)库**</u>
在你的网站上有几种方法可以开始使用 jQuery。

1.  使用谷歌托管/微软托管的内容交付网络(CDN)来包含一个版本的 jQuery。
2.  从 jQuery.com 下载自己的 jQuery 版本，并将其托管在自己的服务器或本地文件系统上。

**注意:**所有 jQuery 方法都在文档就绪事件中，以防止任何 jQuery 代码在文档加载完成(就绪)之前运行。

**任何 jQuery 函数的基本语法为:**

```html
$(selector).action()
```

*   一个$符号是定义/访问 jQuery
*   一个(选择器)是“查询(或查找)”html 页面中的 HTML 元素
*   jQuery 操作()是要对选定元素执行的操作

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <script src=                
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
      </script>
        <script>
            $(document).ready(function () {
                $("h2").click(function () {
                    $(this).hover();
                });
            });
        </script>
    </head>
    <body>
        <center>
            <h2 style="color: green;">
              GeeksforGeeks
          </h2>
        </center>
    </body>
</html>
```

**输出:**
![](img/181197308ae5d448f0ca7227f37acd35.png)

**为什么是 jQuery？**
支持为什么要使用 jQuery 的一些关键点:

*   它非常受欢迎，也就是说它有一个庞大的用户社区和相当数量的贡献者，他们作为开发者和传播者参与进来。
*   它使网络浏览器之间的差异正常化，这样你就不必。
*   这是一个轻量级的足迹，具有简单而巧妙的插件架构。
*   它的插件库非常庞大，自 jQuery 发布以来一直稳步增长。
*   它的应用编程接口有完整的文档，包括内联代码示例，这在 JavaScript 库的世界里是一种奢侈。见鬼，多年来任何文件都是奢侈品。
*   它是友好的，也就是说它提供了避免与其他 JavaScript 库冲突的有用方法。

**优势:**

*   插件种类繁多。jQuery 允许开发人员在 JavaScript 库之上创建插件。
*   大型开发社区
*   它有一个良好和全面的文件
*   与标准 javascript 和其他 javascript 库相比，它更容易使用。
*   JQuery 让用户可以轻松地开发 Ajax 模板，Ajax 实现了更流畅的界面，可以在页面上执行操作，而不需要重新加载整个页面。
*   轻量级和强大的链接能力使得 jQuery 更加强大。

**缺点:**

*   虽然 JQuery 在数量上有一个令人印象深刻的库，但取决于您在网站上需要多少定制，功能可能会受到限制，因此在某些情况下使用原始 javascript 可能是不可避免的。
*   运行 JQuery 命令需要 JQuery javascript 文件，虽然该文件的大小相对较小(25-100KB，取决于服务器)，但如果您打算在自己的 web 服务器上托管 JQuery 脚本，它对客户端计算机和您的 web 服务器来说仍然是一个负担。