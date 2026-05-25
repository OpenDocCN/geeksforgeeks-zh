# Lodash `_.prototype[Symbol.iterator]()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-prototypesymbol-iterator-method/](https://www.geeksforgeeks.org/lodash-_-prototypesymbol-iterator-method/)

`Lodash` 是一个工作在 `underscore.js` 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.prototype[Symbol.iterator]()` 方法用于允许包装器可迭代。

**语法:**

```javascript
_.prototype[Symbol.iterator]()
```

**参数:** 此方法不接受任何参数。

**返回值:** 该方法返回 `lodash` 包装对象。

**例 1:**

## JavaScript

```javascript
// Requiring lodash library
const _ = require('lodash');

// Creating wrapped variable
var wrapr = _([8, 9]);

// Calling [Symbol.iterator]() method
wrapr[Symbol.iterator]() === wrapr;

let obj = Array.from(wrapr);

// Displays output
console.log(obj);
```

**输出:**

```javascript
[ 8, 9 ]
```

**例 2:**

## JavaScript

```javascript
// Requiring lodash library
const _ = require('lodash');

// Creating wrapped variable
var wrapr = _(['Geeks', 'for', 'Geeks']);

// Calling [Symbol.iterator]() method
wrapr[Symbol.iterator]() === wrapr;

let obj = Array.from(wrapr);

// Displays output
console.log(obj);
```

**输出:**

```javascript
[ 'Geeks', 'for', 'Geeks' ]
```

**例 3:**

## JavaScript

```javascript
// Requiring lodash library
const _ = require('lodash');

// Calling [Symbol.iterator]() method and
// comparing it with wrapped value
_("Geeks")[Symbol.iterator]() === _("Geeks");

// Wrapper object
let obj = Array.from(_("Geeks"));

// Displays output
console.log(obj[0]);
console.log(obj[1]);
console.log(obj[2]);
console.log(obj[3]);
```

**输出:**

```javascript
G
e
e
k
```

**参考:** [https://lodash.com/docs/4.17.15#prototype-Symbol-iterator](https://lodash.com/docs/4.17.15#prototype-Symbol-iterator)