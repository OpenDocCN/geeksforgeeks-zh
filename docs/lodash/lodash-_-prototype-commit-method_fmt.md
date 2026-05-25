# Lodash _.prototype.commit()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-prototype-commit-method/](https://www.geeksforgeeks.org/lodash-_-prototype-commit-method/)

**Lodash** 是一个工作在下划线.js之上的JavaScript库，有助于处理数组、字符串、对象、数字等。

`_.prototype.commit()`方法用于实现链序列类型并找到包装的输出。

## 语法

```javascript
_.prototype.commit()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回新的lodash包装器实例。

## 示例 1

```javascript
// Requiring lodash library
const _ = require('lodash');

// Creating an array of integers
var arr = [5, 6];

// Pushing an integer into the array
var wrapper = _(arr).push(7);

// Using the commit() method
wrapper = wrapper.commit();

// Displays output
console.log(arr);
```

**输出:**

```
[ 5, 6, 7 ]
```

## 示例 2

```javascript
// Requiring lodash library
const _ = require('lodash');

// Creating an array of strings
var arr = ['Geeks', 'for'];

// Pushing a string into the array
var wrapper = _(arr).push('Geeks');

// Using the commit() method
wrapper = wrapper.commit();

// Displays output
console.log(arr);
```

**输出:**

```
[ 'Geeks', 'for', 'Geeks' ]
```

## 示例 3

在本例中，返回包装器对象。

```javascript
// Requiring lodash library
const _ = require('lodash');

// Using the commit() method
obj = _(['G', 'f']).reverse().commit();

// Displays output
console.log(obj);
```

**输出:**

```
LodashWrapper {
  __wrapped__: [ 'f', 'G' ],
  __actions__: [],
  __chain__: false,
  __index__: 0,
  __values__: undefined
}
```