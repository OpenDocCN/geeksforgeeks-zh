# Lodash _.before()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-before-method/](https://www.geeksforgeeks.org/lodash-_-before-method/)

Lodash `_.before()` 方法是与 `_.after()` 方法相反的。此方法用于创建一个调用 `func` 的函数，该函数具有 `bind` 的 `this` 和所创建函数的参数，但调用次数少于 `n`。

## 语法

```javascript
_.before(n, func)
```

## 参数

该方法接受两个参数：

*   `n`: 此参数持有数字 `n`，用于定义不再调用 `func` 的调用次数。
*   `func`: 此参数存储要调用的函数。

## 返回值

该方法返回新的受限函数。

## 示例

下面的例子说明了 Lodash `_.before()` 方法：

### 示例 1

在本例中，我们将尝试调用函数 3 次，但它只会调用 2 次。

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Using _.before() method
var gfg = _.before(3, function () {
    console.log('Saved');
});

// It will print Saved
gfg();

// It will print Saved
gfg();

// It will print nothing
gfg();
```

**输出:**

```
Saved
Saved
```

### 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Applying _.before() method
var gfg = _.before(2, function () {
     console.log('Successful');
});

// It will print Successful
gfg();

// It will print nothing
gfg();
```

**输出:**

```
Successful
```

**参考:** [https://docs-lodash.com/v4/before/](https://docs-lodash.com/v4/before/)