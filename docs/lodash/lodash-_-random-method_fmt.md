# Lodash _.random() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-random-method/](https://www.geeksforgeeks.org/lodash-_-random-method/)

`_.random()` 方法用于返回一个在提供给函数的范围内的随机数。如果 `floating` 为 `true`，或者 `lower` 或 `upper` 为 `floating`，则返回浮点数而不是整数。

**语法:**

```
_.random([lower = 0], [upper = 1], [floating])
```

**参数:** 该方法接受三个参数，如下所述：

*   `lower`: 此参数保持下限。
*   `upper`: 此参数保持上限。
*   `floating`: 此参数指定返回浮点数。

**返回值:** 此方法返回随机数。

### 示例 1

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.random method
console.log(_.random(10));
console.log(_.random(10, 12));
console.log(_.random(10, 12));
console.log(_.random(10.3, 12.5));
```

**输出:**

```
12.000118273018167
```

### 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// lower and upper value
let lower = 2;
let upper = 11;

// Printing 5 random values
// in range 2 and 11
for (let i = 0; i < 5; i++) {
    console.log(_.random(lower, upper));
}
```

**输出:**

```