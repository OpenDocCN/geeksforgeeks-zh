# AngularJS 中的`$watch`和`$observe`有什么区别？

> 原文：[https://www.geeksforgeeks.org/what-is-the-difference-between-watch-and-observe-in-angularjs/](https://www.geeksforgeeks.org/what-is-the-difference-between-watch-and-observe-in-angularjs/)

AngularJS 提供了不同的方法来观察其元素和变量的变化。`$observe`和`$watch`是服务于此目的的两种不同方法。

## `$observe`

`$observe`是负责观察 DOM 属性变化的方法。当我们想要观察包含插值（`{{ }}`）的 DOM 元素时，我们使用`$observe`。

### 语法

```tshtml
<!-- Interpolation Element -->
attr1 = "Name: {{name}}"

<!-- Syntax of Observe in controller -->
attrs.$observe('attr1', function() {
    // body
});
```