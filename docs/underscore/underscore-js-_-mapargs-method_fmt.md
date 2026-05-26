# Underscore.js _.mapArgs()方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-mapargs-method/](https://www.geeksforgeeks.org/underscore-js-_-mapargs-method/)

`_.mapArgs()`方法接受一个目标函数并返回一个新的函数，该函数接受一个映射函数，该函数又返回一个函数，该函数将在调用原始目标函数之前映射其参数。

**语法:**

```
_.mapArgs( target_function, mapping_function );
```

**参数:**

*   `target_function`: 原被调用函数。
*   `映射_函数`: 函数要接受的映射函数。

**返回值:** 这个方法返回一个函数。

**注意:** 这在正常的 JavaScript 中无法工作，因为它需要安装 Underscore.js contrib 库。可以使用 `npm install underscore-contrib` 来安装 Underscore.js contrib 库。

**示例 1:** 我们制作了一个函数，将给定值立方，然后将该值加到自身上。

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

function add (x) { 
    return x + x; 
}

function cube (x) {
    return  x * x * x; 
}

var cubethenadd = _.mapArgs(add)(cube);

console.log(cubethenadd(5))
```

**输出:**

```

```

**例 2:**

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

function add (x) { 
    return x + x; 
}

function sub (x) {
    return  x - x; 
}

var subthenadd = _.mapArgs(add)(sub);

console.log(subthenadd(5))
```

**输出:**

```

```