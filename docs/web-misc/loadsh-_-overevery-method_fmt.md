# Lodash _.overEvery()方法

> 原文: [https://www.geeksforgeeks.org/loadsh-_-overevery-method/](https://www.geeksforgeeks.org/loadsh-_-overevery-method/)

Lodash 是一个工作在下划线之上的 JavaScript 库。Lodash 有助于处理数组、字符串、对象、数字等。

**`_`方法用于创建一个函数，该函数负责检查当调用传递给它的参数时所有谓词是否返回真。**

**语法:**

```javascript
_.overEvery(predicates)
```

**参数:** 该方法接受一个参数，如上所述，如下所述:

*   **`predicates`**: 把谓词给调用了。

**返回值:** 返回一个新函数。

**例 1:**

## Javascript

```javascript
// Requiring the lodash library   
const _ = require("lodash");

// Function call
var myReturnedFunction = _.overEvery([Boolean, isFinite]);

// Printing the value returned from function call
console.log(myReturnedFunction('1'));
```

**输出:**

```javascript
true
```

**例二:**

## Javascript

```javascript
// Requiring the lodash library   
const _ = require("lodash");

// Function call
var myReturnedFunction = _.overEvery([Boolean, isFinite]);

// Printing the value returned from function call
console.log(myReturnedFunction(null));
```

**输出:**

```javascript
false
```

**例三:**

## Javascript

```javascript
// Requiring the lodash library   
const _ = require("lodash");

// Function call
var myReturnedFunction = _.overEvery([Boolean, isFinite]);

// Printing the value returned from function call
console.log(myReturnedFunction(Infinity));
```

**输出:**

```javascript
false
```

**参考:** [https://lodash.com/docs/4.17.15#overEvery](https://lodash.com/docs/4.17.15#overEvery)