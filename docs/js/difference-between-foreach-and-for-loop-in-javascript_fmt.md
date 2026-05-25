# Javascript 中 forEach 和 for 循环的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-foreach-and-for-loop-in-javascript/](https://www.geeksforgeeks.org/difference-between-foreach-and-for-loop-in-javascript/)

本文详细描述了 `forEach` 和 `for` 循环的区别。两者的基本区别如下。

## For 循环

`for` 循环在 JavaScript 中用于迭代数组或元素指定次数。如果知道确定的迭代次数，就应该使用它。

**语法：**

```javascript
for (initialization; condition; increment)  
{  
   // code to be executed
}
```

**示例：**

```html
<script>
for (let i = 1; i <= 5; i++)
{
    document.write(i + "<br/>");
}
</script>
```

**输出：**

```
1
2
3
4
5
```

## forEach 循环

`forEach()` 方法也用于循环数组，但它使用的函数与经典的 `for` 循环不同。它为数组的每个元素传递一个回调函数以及以下参数：

*   **当前值（必需）**：当前数组元素的值。
*   **索引（可选）**：当前元素的索引号。
*   **数组（可选）**：当前元素所属的数组对象。

我们需要一个回调函数，通过使用 `forEach` 方法在数组中循环。

**语法：**

```javascript
numbers = [1, 2, 3, 4, 5];

numbers.forEach(function(number) {
   // code to be executed
});
```

对于数组的每个元素，函数都将被执行。回调应该至少有一个表示数组元素的参数。

**示例 1：** 此示例显示了带有回调函数的 `forEach` 方法。

```javascript
let arr = [1, 2, 3, 4, 5];

arr.forEach(function(element) {
    console.log(element);
});
```

**输出：**

```
1
2
3
4
5
```

**示例 2：** 此示例显示了 `forEach` 方法中索引参数的使用。

```javascript
numbers = [1, 2, 3, 4, 5];

numbers.forEach((number, index) => {
    console.log('Index: ' + index + 
                ', Value: ' + number);
});
```

**输出：**

```
Index: 0, Value: 1
Index: 1, Value: 2
Index: 2, Value: 3
Index: 3, Value: 4
Index: 4, Value: 5
```

| 特性 | For 循环 | forEach 循环 |
| :--- | :--- | :--- |
| 描述 | 这是迭代数组的原始方式之一。 | 用较少的代码迭代数组是一种较新的方法。 |
| 性能 | 它的性能更快。 | 它在性能上比传统的循环慢。 |
| 中断 | `break` 语句可用于从循环中出来。 | 由于回调函数，`break` 语句无法使用。 |
| 参数 | 参数是迭代器、计数器和增量器。 | 参数是迭代器、项的索引和要迭代的数组。 |
| 异步支持 | 它与 `await` 关键字一起工作。 | 由于回调函数，不能使用 `await` 关键字。这可能会导致不正确的输出。 |