# HTML | DOM onabort 事件

> 原文:[https://www.geeksforgeeks.org/html-dom-onabort-event/](https://www.geeksforgeeks.org/html-dom-onabort-event/)

**DOM onabort 事件**发生在音频/视频加载中止时。
当媒体数据下载中止且没有任何错误时，会发生此事件。
媒体加载过程中出现中断时发生的事件有:

*   一个提示
*   不良事件
*   安装
*   onsuspend

**支持的标签**

*   **<音频>**
*   **<视频>**

**语法:**

*   **HTML:**

```html
<element onabort="myScript">
```

*   **JavaScript:**

```html
object.onabort = function(){myScript};
```

*   **在 JavaScript 中，使用 addEventListener()方法:**

```html
object.addEventListener("abort", myScript);
```

**例:**

## 超文本标记语言

```html
var video = document.getElementById("GFGVid");
video.onabort = function() {
    alert("Loading aborted");
};
```

**支持的浏览器:**T2 DOM on abort 事件支持的浏览器如下:

*   边缘