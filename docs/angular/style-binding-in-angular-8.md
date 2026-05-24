# 有角 8 中的样式绑定

> 原文:[https://www.geeksforgeeks.org/style-binding-in-angular-8/](https://www.geeksforgeeks.org/style-binding-in-angular-8/)

在 Angular 8 中，使用样式绑定很容易给 HTML 元素赋予 CSS 样式。样式绑定用于设置视图元素的样式。我们可以使用有角度的样式绑定来设置和 HTML 元素的内嵌样式。您还可以有条件地向元素添加样式，从而创建动态样式的元素。

**语法:**

```ts
<element [style.style-property] = "'style-value'">

```

**例 1:**

**app . component . HTML:**

## HTML

```ts
<h1 [style.color] = "'green'" 
    [style.text-align] = "'center'" >
  GeeksforGeeks
</h1>
```