# 如何用 JavaScript 映射、缩小、过滤一个 Set 元素？

> 原文：[https://www.geeksforgeeks.org/how-to-map-reduce-and-filter-a-set-element-using-javascript/](https://www.geeksforgeeks.org/how-to-map-reduce-and-filter-a-set-element-using-javascript/)

`map()`，`reduce()`和`filter()`是数组函数，它们根据应用的函数转换数组并返回更新的数组。它们用于编写简单、简短和干净的代码来修改数组，而不是使用循环。

## map() 方法

[`map()` 方法](https://www.geeksforgeeks.org/javascript-array-map-method/)：它对数组的所有元素应用一个给定的函数，并返回更新后的数组。它是比循环更简单、更简短的代码。`map` 类似于以下代码：

```
arr = new Array(1, 2, 3, 6, 5, 4);
for(int i = 0; i < 6; i++) {
    arr[i] *= 3;
}
```

**语法：**

```
array.map(function_to_be_applied)
```

```
array.map(function (args) {
    // code;
})
```

**示例：**

```
function triple(n){
    return n*3;
}    
arr = new Array(1, 2, 3, 6, 5, 4);
var new_arr = arr.map(triple)
console.log(new_arr);
```

**输出：**

```
[ 3, 6, 9, 18, 15, 12 ]
```

## reduce() 方法

[`reduce()` 方法](https://www.geeksforgeeks.org/javascript-array-reduce-method/)：它通过重复应用一个函数，将数组的所有元素缩减为单个值。它是使用循环并为每个扫描到的元素更新结果的替代方案。`reduce` 可以用于替代以下代码：

```
arr = new Array(1, 2, 3, 6, 5, 4);
result = 1
for(int i = 0; i < 6; i++) {
    result = result * arr[i];
}
```

**语法：**

```
array.reduce(function_to_be_applied)
```

```
array.reduce(function (args) {
    // code;
})
```

**示例：**

```
function product(a, b){
    return a * b;
}
arr = new Array(1, 2, 3, 6, 5, 4);
var product_of_arr = arr.reduce(product)
console.log(product_of_arr)
```

**输出：**

```

```

## filter() 方法

[`filter()` 方法](https://www.geeksforgeeks.org/javascript-array-filter/)：它过滤掉数组中对应用条件返回 `false` 的元素，并返回包含满足应用条件的元素的数组。它是比下面使用循环的代码更简单、更简短的代码：

```
arr = new Array(1, 2, 3, 6, 5, 4);
new_arr = {}
for(int i = 0; i < 6; i++) {
    if(arr[i] % 2 == 0) {
         new_arr.push(arr[i]);           
    }
}
```

**语法：**

```
array.filter(function_to_be_applied)
```

```
array.filter(function (args) {
    // condition;
})
```

**示例：**

```
arr = new Array(1, 2, 3, 6, 5, 4);
var new_arr = arr.filter(function (x){
    return x % 2==0;
});
console.log(new_arr)
```

**输出：**

```
[ 2, 6, 4 ]
```