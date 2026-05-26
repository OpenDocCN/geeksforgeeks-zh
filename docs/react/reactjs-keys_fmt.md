# 反作用|键

> 原文:[https://www.geeksforgeeks.org/reactjs-keys/](https://www.geeksforgeeks.org/reactjs-keys/)

在上一篇关于[ReactJS | list](https://www.geeksforgeeks.org/reactjs-lists/)的文章中，我们已经讨论了`键`，并告诉了为什么在创建列表时需要它们。我们将在本文中继续讨论。

“`键`”是在`React`中创建元素列表时需要包含的特殊字符串属性。按键用于作出反应，以识别列表中哪些项目被更改、更新或删除。换句话说，我们可以说`键`被用来给列表中的元素赋予一个身份。接下来想到的是，哪些应该被选为列表中项目的关键。建议使用字符串作为唯一标识列表中项目的`关键字`。下面的示例显示了一个带有字符串`键`的列表:

## Javascript

```jsx
const numbers = [ 1, 2, 3, 4, 5 ];

const updatedNums = numbers.map((number)=>{
return <li>{ number } </li>;
});
```

您还可以将数组索引作为`键`分配给列表项。下面的示例将数组索引指定为元素的`键`。

## Javascript

```jsx
const numbers = [ 1, 2, 3, 4, 5 ];

const updatedNums = numbers.map((number, index)=>{
return <li>{ number } </li>;
});
```