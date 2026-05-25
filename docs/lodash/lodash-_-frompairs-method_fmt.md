# Lodash | `_.fromPairs()`方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-frompairs-method/](https://www.geeksforgeeks.org/lodash-_-frompairs-method/)

`_.fromPairs()`方法返回一个由键值对组成的对象。这个方法是`_.toPairs()`方法的逆操作。

**语法:**

```javascript
_.fromPairs( pairs )
```

**参数:** 该方法接受如上所述的单个参数，如下所述:

*   `pairs`: 此参数保存数组的键值对。

**返回值:** 这个方法返回一个新的对象。

**例 1:**

```javascript
const _ = require('lodash');

let pairs = [['x', 1], ['y', 2], ['z', 3]]

let obj = _.fromPairs(pairs);

console.log(obj)
```

**输出:**

```javascript
{ x: 1, y: 2, z: 3 }
```

**例 2:**

```javascript
const _ = require('lodash');

let pairs = [['one', 1], ['two', 2], ['three', 3]]

let obj = _.fromPairs(pairs);

console.log(obj)
```

**输出:**

```javascript
{ one: 1, two: 2, three: 3 }
```

**例 3:**

```javascript
const _ = require('lodash');

let pairs = [
    ['name', 'lodash'], 
    ['live', 'npm'], 
    ['used', 'nodejs']
]

let obj = _.fromPairs(pairs);

console.log(obj)
```

**输出:**

```javascript
{ name: 'lodash', live: 'npm', used: 'nodejs' }
```

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装库`lodash`。