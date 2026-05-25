# ES6 数组

> 原文：[`https://www.geeksforgeeks.org/es6-array/`](https://www.geeksforgeeks.org/es6-array/)

数组是值的同构集合。它是用于存储不同元素的单个变量。当我们想要存储一个元素列表并通过一个变量来访问它们时，通常会用到它。与大多数语言中数组是对多个变量的引用不同，ES6 数组是存储多个元素的单个变量。我们可以使用正常变量（`v1`，`v2`，`v3`，..）当我们有少量对象时，但是如果我们想要存储大量实例，那么用普通变量来管理它们就变得很困难。数组的思想是在一个变量中表示多个实例。

**阵的特点:**

*   数组中有索引，因此可以使用数组索引随机访问元素。
*   可以使用单个变量名存储多个元素。
*   使用循环遍历数组变得很容易。
*   排序变得很容易，因为它可以通过在数组中写入更少的代码行来完成。
*   数组值可以修改或更新，但不能删除。

**初始化数组:** 初始化或声明数组是小菜一碟。下面的程序实现了数组的初始化。

*   **节目:**

## java 描述语言

```javascript
// Initializing while declaring
var JS = ["ES1", "ES2", "ES3", "ES4", "ES5", "ES6"];

// Initializing after declaring
JS[0] = "ES6";
JS[1] = "ES6";
JS[2] = "ES6";
JS[3] = "ES6";
```

**访问数组元素:** 要访问任何特定的数组元素，我们需要知道该元素的索引号。数组索引号用于访问数组元素。数组的索引总是从 0 开始。

*   **节目:**

## java 描述语言

```javascript
<script>
// Initializing while declaring
var JS= ["ES1", "ES2", "ES3", "ES4", "ES5", "ES6"];

// Accessing array element
console.log(JS[4])
console.log(JS[5])
</script>
```

*   **输出:**

```
ES5
ES6
```

**数组对象:** 数组构造函数可以作为代表数组大小的数值传递，数组元素是逗号分隔的值。

*   **节目 1:**

## java 描述语言

```javascript
<script>
var js = ["ES6", 2015, "ES8", 2017, "ES10", 2019];

// len contains the length of the array
var len = js.length;
for (var i = 0; i < len; i++)
    console.log(js[i]);

</script>
```

*   **输出:**

```
ES6
ES8
ES10
```

*   **节目 2:**

## java 描述语言

```javascript
<script>
var Geeks = new Array(6)
for(var i = 0; i < Geeks.length; i++)
{
   Geeks[i] = (i * 2)/3
   console.log(Geeks[i])
}
</script>
```

*   **输出:**

```
0
0.6666666666666666
1.3333333333333333
2
2.6666666666666665
3.3333333333333335
```

**数组方法:** ES6 中引入了很多数组方法。

| 方法 | 描述 |
| --- | --- |
| [`concat()`](https://www.geeksforgeeks.org/javascript-array-prototype-concat-function/) | 此方法用于将两个或多个数组合并在一起。 |
| [`every()`](https://www.geeksforgeeks.org/javascript-array-prototype-every-function/) | 此函数检查数组中的所有元素是否满足作为参数传递给它的函数所给定的条件。 |
| [`filter()`](https://www.geeksforgeeks.org/es6-array-filter-method/) | 此方法创建一个新数组，其中的元素遵循或通过给定的标准和条件。 |
| [`find()`](https://www.geeksforgeeks.org/javascript-array-find-method/) | 通过函数过滤元素，并返回第一个/所有使它们返回 true 值的元素。 |
| [`forEach()`](https://www.geeksforgeeks.org/es6-array-foreach-method/) | 此方法用于遍历其元素并操作它们。 |
| [`Array.from()`](https://www.geeksforgeeks.org/javascript-array-method/) | 这将所有类似数组或可迭代的内容转换为真正的数组，尤其是在使用 DOM 时，以便可以使用其他数组方法，如 `reduce`、`map`、`filter` 等。 |
| [`indexOf()`](https://www.geeksforgeeks.org/javascript-array-indexof/) | 此方法用于查找作为方法参数提供的搜索元素第一次出现的索引。 |
| [`join()`](https://www.geeksforgeeks.org/javascript-array-join-method/) | 此方法用于将数组的元素连接成一个字符串。 |
| [`lastIndexOf()`](https://www.geeksforgeeks.org/javascript-array-prototype-lastindexof-function/) | 从 `pos` 开始搜索项目，如果未找到则返回索引或 -1。 |
| [`map()`](https://www.geeksforgeeks.org/javascript-array-map-method/) | 此方法通过调用在每个元素中提供的函数来创建一个新数组。 |
| [`Array.of()`](https://www.geeksforgeeks.org/javascript-array-method/) | 这从传递给它的每个参数创建一个数组。 |
| [`pop()`](https://www.geeksforgeeks.org/javascript-array-prototype-pop/) | 从数组中删除最后一个元素并返回它。 |
| [`push()`](https://www.geeksforgeeks.org/javascript-array-prototype-push-function/) | 将一个或多个元素添加到数组的末尾并返回数组的新长度。 |
| [`reduce()`](https://www.geeksforgeeks.org/javascript-array-reduce-method/) | `reduce()` 方法将一个函数应用于累加器和数组中的每个元素（从左到右）以将其归约为一个值 - MDN。 |
| [`reverse()`](https://www.geeksforgeeks.org/javascript-array-prototype-reverse/) | 反转数组元素的顺序——第一个变成最后一个，最后一个变成第一个。 |
| [`shift()`](https://www.geeksforgeeks.org/javascript-array-prototype-shift/) | 此方法删除数组的第一个元素，从而将原始数组的大小减小 1。 |
| [`slice()`](https://www.geeksforgeeks.org/javascript-array-slice/) | 创建一个新数组以从起始位置复制元素到结束位置（不包括起始位置）。 |
| [`some()`](https://www.geeksforgeeks.org/javascript-array-prototype-function/) | 此方法检查数组中是否至少有一个项目通过了条件。如果通过，它将返回 `true`，否则它将返回 `false`。 |
| [`sort()`](https://www.geeksforgeeks.org/javascript-array-sort/) | 此方法用于根据 `compare()` 函数按给定顺序对数组进行排序。 |
| [`splice()`](https://www.geeksforgeeks.org/javascript-array-splice-method/) | 这些方法用于通过删除现有元素来修改数组的内容。 |
| [`unshift()`](https://www.geeksforgeeks.org/javascript-array-prototype-unshift-function/) | 此函数通过增加数组中的元素数量来增加现有数组的长度。 |

**注意:** 在 JavaScript 中，数组使用编号索引，对象使用命名索引。