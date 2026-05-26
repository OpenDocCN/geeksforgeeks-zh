# 下划线.js _.iterators.K()方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-iterators-k-method/](https://www.geeksforgeeks.org/underscore-js-_-iterators-k-method/)

借助`_.iterators.K()`方法，我们可以得到这个方法调用时从给定值生成一个函数。

## 语法

```
_.iterators.K(value)
```

## 参数

该方法接受如上所述的单个参数，描述如下：

*   `value`：此参数保持一个给定的值。

## 返回

在调用函数时，一次返回一个值。

## 注意

要执行下面的示例，您必须安装`underscore-contrib`库。通过使用此命令提示符，我们必须执行以下命令。

```
npm install underscore-contrib
```

下面的例子说明了JavaScript中的下划线迭代器方法：

### 示例 1

在这个示例中，我们可以看到，通过使用`_.iterators.K()`方法，我们能够获得函数，该函数给出了在使用该方法创建迭代器时定义的值。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var iter = _.iterators.K("Geeks for Geeks");

iter();
```

**输出：**

```
'Geeks for Geeks'
```

### 示例 2

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var pi = _.iterators.K(3.141592653589793);

pi();
```

**输出：**

```
3.141592653589793
```