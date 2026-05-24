# HTML | DOM 全屏错误事件

> 原文:[https://www . geesforgeks . org/html-DOM-full screenerror-event/](https://www.geeksforgeeks.org/html-dom-fullscreenerror-event/)

当一个元素不能在全屏模式下查看时，即使它已经被请求，也会发生 **HTML DOM 全屏错误事件**。
使用**element . request full screen()**方法在全屏模式下查看元素，使用**element . exitfulscreen()**方法取消全屏模式。
**支持的标签**

*   **支持所有 HTML 元素。**

**语法:**

*   **在 HTML 中:**

```html
<element onfullscreenerror="myScript">
```

*   **在 JavaScript 中:**

```html
object.onfullscreenerror = function(){myScript};
```

*   **在 JavaScript 中，使用 addEventListener()方法:**

```html
object.addEventListener("fullscreenerror", myScript);
```

**跨浏览器代码使用前缀:**

*   **标准语法:**

## java 描述语言

```html
document.addEventListener("fullscreenerror", function() {
  ...
});
```