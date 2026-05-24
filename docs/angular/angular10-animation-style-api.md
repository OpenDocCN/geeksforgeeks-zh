# Angular10 动画风格 API

> 原文:[https://www . geesforgeks . org/angular 10-动画风格-api/](https://www.geeksforgeeks.org/angular10-animation-style-api/)

在本文中，我们将看到什么是 Angular 10 中的 Style 以及如何使用它。

angular 10 中的 **样式** 用于创建包含可用于动画状态的 CSS 属性/样式的关键点/值对象。

**语法:**

```ts
Style(tokens)
```

**模块:**样式使用的模块为:

*   **动画**

**进场:**

*   创建要使用的角度应用程序。
*   在 app.module.ts 中导入浏览器动画引擎-什么
*   在 app.component.html 制作一个包含动画元素的 div。
*   在 app.component.ts 中导入要使用的触发器、状态、样式、过渡、动画。
*   制作包含动画标记的样式。
*   使用 ng serve 为 angular app 服务，以查看输出。

**参数:**

*   **标记:** 与动画状态相关联的一组 CSS 样式或 HTML 样式。

**返回值:**

*   **动画样式元数据:** 封装样式数据的对象。

**例 1:**

app.module.ts