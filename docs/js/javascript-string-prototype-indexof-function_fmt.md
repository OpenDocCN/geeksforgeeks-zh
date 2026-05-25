# JavaScript 字符串 indexOf() 方法

> 原文：[https://www.geeksforgeeks.org/javascript-string-prototype-indexof-function/](https://www.geeksforgeeks.org/javascript-string-prototype-indexof-function/)

下面是字符串 `indexOf()` 方法的示例。

## 示例

### JavaScript 语言

```javascript
// JavaScript to illustrate indexOf() function
<script>
function func() {

    // Original string
    var str = 'Departed Train';

    // Finding index of occurrence of 'Train'
    var index = str.indexOf('Train');
    document.write(index);
}
func();
</script>
```

输出：

```
9
```

`str.indexOf()` 函数查找给定字符串中参数字符串第一次出现的索引。返回值从 0 开始。该函数的语法如下：

```
str.indexOf(searchValue, index)
```

**参数：**
函数的第一个参数 `searchValue` 是要在基本字符串中搜索的字符串。函数的第二个参数 `index` 定义了起始索引，从该索引开始在基本字符串中搜索 `searchValue`。

**返回值：**
该函数返回第一次找到 `searchValue` 的字符串的索引（从 0 开始）。如果在字符串中找不到 `searchValue`，则该函数返回 `-1`。

上述功能示例如下：

**示例 1：**

```javascript
print('Departed Train'.indexOf('Train'));
```

在本例中，函数 `indexOf()` 找到字符串 `'Train'` 的索引。由于第一个也是唯一一个存在该字符串的索引是 9，因此该函数返回 `9` 作为答案。

输出：

```
9
```

**示例 2：**

```javascript
print('Departed Train'.indexOf('ed Tr'));
```

输出：

```
6
```

在本例中，函数 `indexOf()` 找到字符串 `'ed Tr'` 的索引。由于该字符串出现的第一个也是唯一一个索引是 6，因此该函数返回 `6` 作为答案。

**示例 3：**

```javascript
print('Departed Train'.indexOf('train'));
```

输出：

```
-1
```

在本例中，函数 `indexOf()` 找到字符串 `'train'` 的索引。由于字符串中不存在 `searchValue`，因此该函数返回 `-1` 作为答案。

**示例 4：**

```javascript
print('Departed Train before another Train'.indexOf('Train'));
```

输出：

```
9
```

在本例中，函数 `indexOf()` 找到字符串 `'Train'` 的索引。由于 `searchValue` 的第一个索引是 `9`，因此该函数返回 `9` 作为答案。

上述功能的代码如下：

**程序 1：**

### JavaScript 语言

```javascript
// JavaScript to illustrate indexOf() function
<script>
function func() {

    // Original string
    var str = 'Departed Train';

    // Finding index of occurrence of 'Train'
    var index = str.indexOf('Train');
    document.write(index);
}
func();
</script>
```

输出：

```
9
```

**程序 2：**

### JavaScript 语言

```javascript
<script>
// JavaScript to illustrate indexOf() function
function func() {

    // Original string
    var str = 'Departed Train';

    // Finding index of occurrence of 'Train'
    var index = str.indexOf('ed Tr');
    document.write(index);
}
func();
</script>
```

输出：

```
6
```

**程序 3：**

### JavaScript 语言

```javascript
// JavaScript to illustrate indexOf() function
<script>
function func() {

    // Original string
    var str = 'Departed Train';

    // Finding index of occurrence of 'Train'
    var index = str.indexOf('train');
    document.write(index);
}
func();
</script>
```

输出：

```
-1
```

**程序 4：**

### JavaScript 语言

```javascript
// JavaScript to illustrate indexOf() function
<script>
function func() {

    // Original string
    var str = 'Departed Train before another Train';

    // Finding index of occurrence of 'Train'
    var index = str.indexOf('Train');
    document.write(index);
}
func();
</script>
```

输出：

```
9
```

**支持的浏览器：**

*   Chrome 1 及以上
*   Edge 12 及以上
*   Firefox 1 及以上版本
*   Internet Explorer 3 及以上版本
*   Opera 3 及以上
*   Safari 1 及以上