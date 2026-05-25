# Lodash _.snakeCase() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-snakecase-method/](https://www.geeksforgeeks.org/lodash-_-snakecase-method/)

`_.snakeCase()` 方法用于将字符串转换为蛇形命名（Snake case）。蛇形命名是指将单词组合成小写字符串，单词之间用下划线（`_`）连接。

**语法：**

```javascript
_.snakeCase( [string=''] )
```

**参数：** 该方法接受如上所述的单个参数，描述如下：

*   `string`：此参数持有待转换的字符串。

**返回值：** 此方法返回蛇形命名的字符串。

下面的例子说明了 Lodash 中的 `_.snakeCase()` 方法：

### 示例 1

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.snakeCase() method
console.log(_.snakeCase('Geeks For Geeks'));
console.log(_.snakeCase('GeeksForGeeks'));
console.log(_.snakeCase('@#$%GeeksForGeeks@#$%'));
```

**输出：**

```javascript
'geeks_for_geeks'
'geeks_for_geeks'
'geeks_for_geeks'
```

### 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.snakeCase() method
console.log(_.snakeCase(null));
console.log(_.snakeCase('123456789'));
console.log(_.snakeCase("gfg.Id"));
```

**输出：**

```javascript
''
'123456789'
'gfg_id'
```