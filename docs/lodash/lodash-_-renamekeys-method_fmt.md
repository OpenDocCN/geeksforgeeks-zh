# Lodash `_.renameKeys()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-renamekeys-method/](https://www.geeksforgeeks.org/lodash-_-renamekeys-method/)

`_.renameKeys()` 方法获取一个对象和一个映射对象，并返回一个新的对象，其中给定对象的键已经被重命名为 `mapObj` 中的相应值。

## 语法

```javascript
_.renameKeys(obj, mapObj);
```

## 参数

该方法接受两个参数，如下所述：

*   `obj`: 给定对象，用于创建新对象。
*   `mapObj`: 给定的映射对象，用于创建新对象。

## 返回值

这个方法返回一个生成的对象。

## 注意

这在正常的 JavaScript 中不会起作用，因为它需要安装 `lodash-contrib` 库。可以使用以下命令安装：

```bash
npm install lodash-contrib
```

## 例 1

```javascript
// Defining underscore lodash variable 
var _ = require('lodash-contrib');

// Declare and object and rename its key
var obj = _.renameKeys( { 1 : "Geeks",  
            2 : "Computer_Science_Portal" }, 
            { 1 : "g", 2 : "c" });

console.log("Generated Object: ", obj);
```

**输出:**

```
Generated Object: Object {c: "Computer_Science_Portal", g: "Geeks"}
```

## 例 2

```javascript
// Defining underscore lodash variable 
var _ = require('lodash-contrib');

// Declare and object and rename its key
var obj = _.renameKeys(  
    { 1 : "Geeks", 2 : "Computer_Science_Portal",  
    3 : "Geeks" }, { 1 : "g", 2 : "c", 3 : "g" });

console.log("Generated Object: ", obj);
```

**输出:**

```
Generated Object: Object {c: "Computer_Science_Portal", g: "Geeks"}
```

## 例 3

```javascript
// Defining underscore lodash variable 
var _ = require('lodash-contrib');

// Declare and object and rename its key
var obj = _.renameKeys( [ "Computer_Science_Portal", "Geeks" ], 
                        { 0 : "a", 1 : "b", 3 : "g" });

console.log("Generated Object: ", obj);
```

**输出:**

```
Generated Object: Object {c: "Computer_Science_Portal", g: "Geeks"}
```