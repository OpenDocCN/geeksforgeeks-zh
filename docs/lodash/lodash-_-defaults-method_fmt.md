# 洛达什 _.defaults()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-defaults-method/](https://www.geeksforgeeks.org/lodash-_-defaults-method/)

洛达什 `_.defaults()` 方法为解析为未定义的所有目标属性将源对象的属性分配给目标对象。源对象从左向右应用。一旦设置了属性，相同属性的附加值将被忽略。此方法使对象变异。

## 语法

```javascript
_.defaults( dest_object, [src_obj])
```

## 参数

该方法接受两个参数，如上所述，如下所述:

*   `dest_object`: This is the destination object.
*   `src_obj`: These are the source objects.

## 返回值

这个方法返回一个对象。

## 例 1

```javascript
// Defining Lodash variable 
const _ = require('lodash');

a = _.defaults({ 'gfg': 3 }, 
    { 'geek': 1 }, { 'gfg': 6 });

console.log(a);
```

**输出:**

```javascript
{ gfg: 3, geek: 1 }
```

## 例 2

```javascript
// Defining Lodash variable 
const _ = require('lodash');

a = _.defaults({ 'a': 3 }, { 'b': 1 }, 
    { 'c': 5 }, { 'd': 5 }, { 'e': 5 });

console.log(a);
```

**输出:**

```javascript
{ a: 3, b: 1, c: 5, d: 5, e: 5 }
```

## 例 3

```javascript
// Defining Lodash variable 
const _ = require('lodash');

a = _.defaults({ 'a': 'first setting'}, 
               { 'a': 'second setting but doesn\'t changes'});
console.log(a);
```

**输出:**

```javascript
{ a: 'first setting' }
```

**注意:** 这在正常的 JavaScript 中无法工作，因为它需要安装 lodash 库，可以使用以下命令进行安装:

```bash
npm install lodash
```