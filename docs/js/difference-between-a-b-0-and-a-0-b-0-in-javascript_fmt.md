# JavaScript 中 `a || b < 0` 和 `a < 0 || b < 0` 的区别？

> 原文：[https://www.geeksforgeeks.org/difference-between-a-b-0-and-a-0-b-0-in-javascript/](https://www.geeksforgeeks.org/difference-between-a-b-0-and-a-0-b-0-in-javascript/)

当我们关注 [`||` (Or)](https://www.geeksforgeeks.org/javascript-operators/) 运算符时，这两个表达式看起来几乎相同，但是这两个表达式彼此不同。要知道最后的结论，我们必须先获得`||` (Or)运算符的知识。

**`||`（或）运算符：** “或”运算符与“与”运算符相反。它确实从左到右计算操作数。对于每个操作数，它将首先将其转换为布尔值。如果结果为真，则停止并返回该操作数的原始值。否则，如果所有值都为假，则返回最后一个值。

关于 JavaScript 中其他逻辑运算符的深入内容，可以查看 [JavaScript 课程 JavaScript 中的逻辑运算符](https://www.geeksforgeeks.org/javascript-course-logical-operators-in-javascript/)。

## 表达式 1

```
a < 0 || b < 0
```

**示例：** 表达式`a < 0 || b < 0`被求值，如果不是布尔值，则被强制为`1`。`a`和`b`都与`0`进行比较。

### JavaScript 代码

```javascript
<script>
function myFunction(a, b) {

if (a < 0 || b < 0) {
  console.log("The value of a and b "+ a, b);
  }else{
  console.log("GFG")
}
}
myFunction(2,5);
</script>
```

**输出：**

```
GFG
```

## 表达式 2

```
a || b < 0
```

**示例：** 表达式被求值，如果它不是布尔值，则被强制为`1`。`a`的值与`b`进行比较。

### JavaScript 代码

```javascript
<script>
function myFunction(a, b) {

if (a || b < 0) {
  console.log("The value of a and b "+ a, b);
  }else{
  console.log("GFG")
}
}
myFunction(2,5);
</script>
```

**输出：**

```
The value of a and b
```

## `a || b < 0` 与 `a < 0 || b < 0` 的区别

| `a || b < 0` | `a < 0 || b < 0` |
| :--- | :--- |
| 在此表达式中，`a`的值将与`b < 0`的结果进行比较。 | 在此表达式中，`a`和`b`都与`0`进行比较。 |
| 这是用于比较一个变量与一个表达式结果的表达式。 | 这是比较两个变量的最常用表达式。 |