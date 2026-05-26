# 下划线.js `_.eq()`方法

> 原文：`https://www.geeksforgeeks.org/underscore-js-_-eq-method/`

`_.eq()`方法使用松散的等式（`==`）来比较参数。

```
_.eq( val1, val2,..., valn );
```

**参数：** 该方法接受`n`个值进行比较。

**返回值：** 该方法返回一个布尔值（如果参数相等则返回`true`，否则返回`false`）。

**注意：** 这在标准的JavaScript中无法工作，因为它需要安装`underscore-contrib`库。

可以使用`npm install underscore-contrib --save`来安装`underscore-contrib`库。

### 示例 1

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

var equal = _.eq( 1, "1" );

console.log("The Given values are equal :",equal);
```

**输出：**

```
The Given values are equal : true
```

### 示例 2

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

var equal = _.eq( "Geeks", "Geeks" );

console.log("The Given values are equal :",equal);
```

**输出：**

```
The Given values are equal : true
```

### 示例 3
有效值返回真，因此与真布尔值比较时，比较返回真。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

var equal = _.eq( 1, true );

console.log("The Given values are equal :",equal);
```

**输出：**

```
The Given values are equal : true
```

### 示例 4
有效值返回真，因此与假布尔值进行比较时，比较返回假。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

var equal = _.eq( 1, false );

console.log("The Given values are equal :",equal);
```

**输出：**

```
The Given values are equal : false
```