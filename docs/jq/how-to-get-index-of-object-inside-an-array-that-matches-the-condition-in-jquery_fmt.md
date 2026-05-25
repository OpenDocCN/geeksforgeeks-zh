# 如何获取 jQuery 中匹配条件的数组内部对象的索引？

> 原文: [https://www.geeksforgeeks.org/how-to-get-index-of-object-inside-an-array-that-matches-the-condition-in-jquery/](https://www.geeksforgeeks.org/how-to-get-index-of-object-inside-an-array-that-matches-the-condition-in-jquery/)

jQuery 是一个免费的开源 JavaScript 库，旨在为 HTML 网页增加交互性。jQuery 在功能上类似于 JavaScript，但它受欢迎的地方在于它的简单性和易用性。jQuery 附带了内置方法的捆绑包，有助于实现所需的输出。在本文中，我们将讨论 jQuery 中的两种方法，这两种方法可用于获取与给定条件匹配的数组中对象的索引。这两种方法讨论如下。

## 1. `findIndex()`
该方法执行作为参数传递给数组中每个元素的函数。

### 语法
```html
array.findIndex(function(curr, index, arr), thisVal)
```

### 参数
*   `curr`: 将在其上执行函数的数组的当前元素。这是强制参数。
*   `index`: 当前元素的索引。这是可选参数。
*   `arr`: 当前元素所属的数组。这是可选参数。
*   `thisVal`: 该值作为其 `this` 值传递给函数。如果未指定此参数，则值 `undefined` 将作为 `this` 值传递。此参数是可选的。

### 返回值
该方法返回函数的返回值为真的第一个元素的索引。如果没有找到匹配，它将返回 `-1`。如果有多个元素满足标准，则返回第一个匹配元素的索引。

## 2. `some()`
`arr.some()` 方法检查数组的至少一个元素是否满足参数方法检查的条件。

### 语法
```html
array.some(function(curr, index, arr), thisVal)
```

### 参数
*   `curr`: 将在其上执行函数的数组的当前元素。这是强制参数。
*   `index`: 当前元素的索引。这是可选参数。
*   `arr`: 当前元素所属的数组。这是可选参数。
*   `thisVal`: 该值作为其 `this` 值传递给函数。如果未指定此参数，则值 `undefined` 将作为 `this` 值传递。此参数是可选的。

### 返回值
该方法返回函数的返回值为 `true` 的第一个元素的索引。如果没有找到匹配，它将返回 `-1`。如果有多个元素满足标准，则返回第一个匹配元素的索引。

## 方法 1
在第一种方法中，我们展示了使用 jQuery 的 `findIndex()` 方法来查找数组中与给定条件匹配的对象的索引的过程。`findIndex()` 方法将一个函数作为第一个参数。这个函数在数组的每个元素上执行，函数返回 `true` 的元素是符合指定条件的元素。因此，这个匹配元素的索引存储在 `index` 变量中。`index` 变量值返回到控制台。类似地，对于 `index1` 变量，有多个对象具有 `age = "20"`。在这种情况下，返回第一个匹配对象的索引。如果不匹配，则输出为 `-1`。

```html
// Write JavaScript code here
var arr = [
    { name: "ram", age: "20" }, 
    { name: "sam", age: "20" },
    { name: "tom", age: "19" }, 
    { name: "harry", age: "19" }
];

var index;

arr.findIndex(function (entry, i) {
    if (entry.name == "tom") {
        index = i;
        return true;
    }
});

// Arrow function expression ( =>) is 
// an alternative to a traditional 
// function expression
// It has limited use and returns the
// index of the first element for 
/// which the function returns "true"
index1 = arr.findIndex(x => x.age === "20");

console.log(index);
console.log(index1); 
```

**输出:**
```html

```

## 方法 2
在第二种方法中，我们展示了使用 jQuery 的 `some()` 方法来查找数组中与给定条件匹配的对象的索引的过程。`some()` 方法将函数作为第一个参数。这个函数在数组的每个元素上执行，函数返回 `true` 的元素是符合指定条件的元素。因此，这个匹配元素的索引存储在 `index` 变量中。`index` 变量值返回到控制台。

```html
// Write Javascript code here
var arr = [
    { name: "ram", age: "20" }, 
    { name: "sam", age: "21" },
    { name: "tom", age: "19" }, 
    { name: "harry", age: "19" }
];

var index;

arr.some(function (entry, i) {
    if (entry.name == "tom") {
        index = i;
        return true;
    }
});

console.log(index);
```

**输出:**
```html

```