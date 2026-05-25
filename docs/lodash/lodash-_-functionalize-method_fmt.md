# 洛达什 `_.functionalize()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-functionalize-method/](https://www.geeksforgeeks.org/lodash-_-functionalize-method/)

洛达什 `_.functionalize()` 方法获取一个函数（使用 `this` 的那个）并将 `this` 推入参数列表。返回的函数使用其第一个参数作为原始函数的接收者/上下文，其余参数用作原始函数的整个参数列表。

**语法:**

```javascript
_.functionalize( function )
```

**参数:** 该方法接受如上所述的单个参数，定义如下:

*   `function`: 这个方法取一个使用 `this` 的函数。

**返回值:** 这个方法返回一个函数。

**注意:** 要执行以下示例，您必须使用此命令提示符安装 `lodash-contrib` 库，并执行以下命令。

```bash
npm install lodash-contrib
```

以下示例说明了 Lodash `_.functionalize()` 方法在 JavaScript 中的使用:

## 例 1:

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

function get(g) {
        return this[g];
    }

var geekFunc = _.functionalize(geta);

var geeks = {
    GeeksforGeeks: "Computer Science Portal for Geeks"
};
console.log(geekFunc(geeks,"GeeksforGeeks"))
```

**输出:**

```
Computer Science Portal for Geeks
```

## 例 2:

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

function get(g) {
        return this[g];
    }

var geekFunc = _.functionalize(get);

var geeks = {
    GeeksforGeeks: 1000000
};
console.log(geekFunc(geeks,"GeeksforGeeks"))
```

**输出:**

```
1000000
```