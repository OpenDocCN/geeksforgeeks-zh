# CSS |居中元素

> 原文:[https://www.geeksforgeeks.org/css-centering-elements/](https://www.geeksforgeeks.org/css-centering-elements/)

有时，我们会遇到在网页中居中元素的问题。真的这么难吗？元素居中并不太难。有这么多不同的方法。
有一点我们需要知道的是，哪种技术是为了哪种目的。一旦你理解了这个问题，学会最好的技巧就会容易得多。
那么让我们看看一些情况，讨论一下实现目标的最佳方法。

*   **水平**
    *   **内联元素**
        我们可以很容易地将一个内联元素集中在一个块级元素中，如下所示:

## 钢性铸铁

```html
// Aligning text in center
.center
{
     text-align: center;
}
```

*   **块级元素**
    我们可以通过给块级元素指定 auto 的左边距和右边距(具有已知的指定宽度):

## 钢性铸铁

```html
// Aligning an element of defined length in center
// Remember to define the width of the element otherwise it
//will be full width and 'auto' will not work
.center
{
    margin: 0 auto;
    width: 200px;
}
```

*   **多个块级元素**
    如果我们有两个或两个以上的块级元素需要水平居中排成一行，那么让它们成为不同的**显示**类型**显示:内联块会更好；**

## 钢性铸铁

```html
.parent
{
  // Aligning the child of this parent in center
  text-align: center;
}
.child
{
  // set the display of child elements
  display: inline-block;
  text-align: left;
}
```