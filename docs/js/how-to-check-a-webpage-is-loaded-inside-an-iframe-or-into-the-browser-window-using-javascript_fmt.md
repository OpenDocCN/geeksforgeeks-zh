# 如何使用 JavaScript 检查网页是加载到 iframe 内部还是浏览器窗口中？

> 原文: [https://www.geeksforgeeks.org/how-to-check-a-webpage-is-loaded-inside-an-iframe-or-into-the-browser-window-using-javascript/](https://www.geeksforgeeks.org/how-to-check-a-webpage-is-loaded-inside-an-iframe-or-into-the-browser-window-using-javascript/)

一个 `iFrame` 是网页中的一个矩形框或区域，用于加载或显示其中的另一个单独的网页或文档。因此，基本上，`iFrame` 用于在网页中显示网页。

你可以在这里看到更多关于 `iFrames` 的信息: [HTML iFrames](https://www.geeksforgeeks.org/html-iframes/)

检查网页是否加载到 `iFrame` 中可能有多种原因，例如，当我们需要动态调整元素的高度或宽度时。

## 方法一：比较对象位置与 window 对象的父级位置

这里，我们简单地将对象的位置与 `window` 对象的父级位置进行比较。如果结果为 `true`，则网页在 `iFrame` 中。如果为 `false`，则不在 `iFrame` 中。

```html
<script>
function iniFrame() {
    if ( window.location !== window.parent.location )
    {
        // The page is in an iFrames
        document.write("The page is in an iFrame");
    } 
    else {
        // The page is not in an iFrame
        document.write("The page is not in an iFrame");
    }
}

// Calling iniFrame function
iniFrame();
</script>
```

**输出:**

```
The page is in an iFrame
```

## 方法二：使用 window.top 和 window.self 属性

`top` 和 `self` 都是 `window` 对象，与 `parent` 一样，因此可以检查当前窗口是否是顶层/主窗口。

```html
<script>
// Function to check whether webpage is in iFrame
function iniFrame() {
    if(window.self !== window.top) {
        // !== operator checks whether the operands
        // are of not equal value or not equal type
        document.write("The page is in an iFrame");
    }
    else {
        document.write("The page is in an iFrame");
    }
}

// Calling iniFrame function
iniFrame();
</script>
```

**输出:**

```
The page is in an iFrame
```

## 方法三：使用 window.frameElement 属性

请注意，此方法仅支持与主页面同源的网页。函数 `window.frameElement` 返回嵌入网页的元素（如 `iframe` 和 `object`）。

```html
<script>
function iniFrame() {
    var gfg = window.frameElement;
    // Checking if webpage is embedded
    if (gfg) {
        // The page is in an iFrame
        document.write("The page is in an iFrame");
    } 
    else {
        // The page is not in an iFrame
        document.write("The page is not in an iFrame");
    }
}

// Calling iniFrame function
iniFrame();
</script>
```

**输出:**

```
The page is in an iFrame
```

在上面的代码中，将网页嵌入的元素存储到变量 `gfg` 中。如果窗口没有嵌入到另一个文档中，或者如果它嵌入到的文档具有不同的来源（例如来自不同的域），`gfg` 为空。