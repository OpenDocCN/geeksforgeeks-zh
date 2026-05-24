# jQuery 面试问答

> 原文:[https://www . geesforgeks . org/jquery-面试-问答/](https://www.geeksforgeeks.org/jquery-interview-questions-and-answers/)

![jQuery interview questions](img/b76f91494d1eff99308a7f6cf832ce96.png)

1.  **[What is jQuery ?](https://www.geeksforgeeks.org/jquery-introduction/)**
    jQuery is an open source JavaScript library that simplifies the interactions between an HTML/CSS document, or more precisely the Document Object Model (DOM) and JavaScript.
    Elaborating the terms, jQuery simplifies HTML document traversing and manipulation, browser event handling, DOM animations, Ajax interactions, and cross-browser JavaScript development.
2.  **Does jQuery HTML work for both HTML and XML documents ?**
    No, JQuery HTML doesn’t work with XML document. It only works for HTML documents.
3.  **[什么是 jQuery 选择器？举一些例子。](https://www.geeksforgeeks.org/jquery-selectors-and-event-methods/)**
    jQuery 选择器用于选择 HTML 元素，并允许您以我们想要的方式操作 HTML 元素。它在一个变量参数上选择 HTML 元素，如它们的名称、类、id、类型、属性、属性值等。jQuery 中的所有选择器都是使用特殊符号选择的，即美元符号和括号:

    ```html
    $("selector-name")
    ```

    *   **元素选择器:**元素选择器根据名称选择元素。
        T3】例:

```html
$("h1")
```

*   **Id 选择器:**Id 选择器根据元素的 Id 选择元素。
    **例:**

    ```html
    $("#gfg")
    ```

    *   **Class Selector:** The class selector selects the element on the basis of its class.
    **Example:**

    ```html
    $(".GFG")
    ```

    *   **What are the advantages of jQuery ?**
    *   它包含各种各样的插件。jQuery 允许开发人员在 JavaScript 库之上创建插件。
    *   大型开发社区。
    *   它有一个良好而全面的文档。
    *   它包含大量的 JavaScript 库，与标准的 JavaScript 相比，它很容易使用。
    *   jQuery 让用户可以轻松地开发 Ajax 模板，Ajax 实现了更流畅的界面，可以在页面上执行操作，而不需要重新加载整个页面。
    *   轻量级和强大的链接能力使得 jQuery 更加强大。*   **[What are the methods used to provide effects?](https://www.geeksforgeeks.org/tag/jquery-effects/)**
    Some of methods are listed below which provides the effect:
    *   [jQuery toggle()方法](https://www.geeksforgeeks.org/jquery-toggle-method/)
    *   [jQuery slideDown()方法](https://www.geeksforgeeks.org/jquery-slidedown-method/)
    *   [jQuery 效果淡出()方法](https://www.geeksforgeeks.org/jquery-effect-fadeout-method/)
    *   [jQuery fadeToggle()方法](http://geeksforgeeks.org/jquery-fadetoggle-method/)*   **Difference between .empty(), .remove() and, .detach() in Jquery ?**
    *   **[jQuery empty()方法:](https://www.geeksforgeeks.org/jquery-empty-with-examples/)**jQuery 中的 empty()方法用于移除所选元素的所有子节点及其内容。
    *   **[jQuery remove()方法:](http://geeksforgeeks.org/jquery-remove/)**jQuery 中的 remove()方法用于移除包括所有文本在内的所有选定元素。此方法还会移除选定元素的数据和所有事件。
    *   **[jQuery detach()方法:](https://www.geeksforgeeks.org/jquery-detach-with-examples/)**jQuery 中的 detach()方法用于从 DOM 树中移除选定的元素，包括其所有文本和子节点，但它保留数据和事件。文档对象模型是一个万维网联盟标准。这定义了访问 DOM 树中的元素。
    *   **注:****移出()**法比**空出()**或**拆出()**法快。*   **Is jQuery a JavaScript or JSON library file ?**
    jQuery is a library of JavaScript file and it consists of DOM event effects and also the Ajax functions. jQuery is alleged to be one JavaScript file.

    *   **[What are the various ajax functions available in Jquery ?](https://www.geeksforgeeks.org/tag/jquery-ajax/)**
    Ajax allows the user to exchange data with a server and update parts of a page without reloading the entire page. Some of the functions of ajax are as follows:
    *   **[jQuery ajaxSetup()方法:](https://www.geeksforgeeks.org/jquery-ajaxsetup-method/)**AJAX setup()方法用于设置未来 AJAX 请求的默认值。
    *   **[jQuery ajax()方法:](http://geeksforgeeks.org/jquery-ajax-method/)**ajax()方法用于执行 AJAX 请求或异步 HTTP 请求。
    *   **[jQuery getScript()方法:](https://www.geeksforgeeks.org/jquery-getscript-method/)**getScript()方法用于运行一个使用 AJAX 的 JavaScript HTTP GET 请求。
    *   **[jQuery getJSON()方法:](https://www.geeksforgeeks.org/jquery-getjson-method/)**getJSON()方法使用 GET HTTP 请求从服务器获取 JSON 编码的数据。*   **Mention the compatible operating systems with jQuery.**
    *   苹果个人计算机
    *   Windows 操作系统
    *   Linux 操作系统*   **How to include the jQuery library in the ASP.Net project ?**
    *   从 jQuery.com 下载 jQuery 库
    *   包括在 ASP.NET 页面中引用。*   **Explain [bind()](https://www.geeksforgeeks.org/jquery-bind-with-examples/) vs [live()](http://geeksforgeeks.org/jquery-live-method/) vs [delegate()](https://www.geeksforgeeks.org/jquery-delegate-method/) methods in jQuery.**
    The bind() method does not attach the events to those elements that are added once DOM is loaded whereas live() and delegate() methods attach events to the future elements also.

    live()和 delegate()方法的区别在于 live()函数在链接中不起作用。它将只在选择器或元素上工作，而 delegate()方法将在链接中工作。

    *   **Write the command that gives the version of jQuery ?**
    The command **`$.ui.version`** returns jQuery UI version.*   **What is jQuery connect ?**
    A **jQuery connect** is a plugin that is used to connect or bind a function with another function. Connect is used to execute the function from the other function or plugin is executed.*   **How to use connect ?**
    *   从 jQuery.com 下载 jQuery 连接文件
    *   将该文件包含在 HTML 文件中。
    *   使用$。连接函数将一个函数连接到另一个函数。*   **[What is the use of param() method in JQuery ?](https://www.geeksforgeeks.org/jquery-param-method/)**
    The **param() method** in jQuery is used to create a serialized representation of an object.

    *   **Difference between $(this) and this in jQuery ?**
    The **this** and **$(this)** references are same but the difference is **“this”** is used in the traditional way but when “this” is used with $() then it becomes a jQuery object.*   **Difference between find and children methods ?**
    The **[find()](https://www.geeksforgeeks.org/jquery-find-with-examples/)** method is used to find all the descendant elements of the selected element and the **[children()](https://www.geeksforgeeks.org/jquery-children-with-examples/)** method is used to find all the children element related to that selected element.*   **In what scenarios jQuery can be used ?**
    jQuery can be used in following scenarios:
    *   主要用于动画效果
    *   操纵目的
    *   对事件调用函数
    *   应用静态或动态 CSS*   **How to read, write and delete cookies in jQuery ?**
    We can deal with cookies in jquery using *Dough cookie plugin*. Dough is easy to use and has powerful features.
    *   **创建饼干:**
        $。面团(“cookie_name”、“cookie _ value”)；
    *   **读饼干:**
        $。面团(“cookie _ name”)；
    *   **删除 cookie:**
        $。面团(“cookie_name”，“remove”)；*   **Features of jQuery which are used in web applications ?**
    jQuery uses features like Sliding, File uploading and accordian in web applications.

    jQuery 是一个开源的 JavaScript 库，它简化了 HTML/CSS 文档之间的交互，它以其“少写多做”的理念而闻名。
    跟随本 [jQuery 教程](https://www.geeksforgeeks.org/jquery-tutorials/)和 [jQuery 示例](https://www.geeksforgeeks.org/jquery-examples/)可以从头开始学习 jQuery。