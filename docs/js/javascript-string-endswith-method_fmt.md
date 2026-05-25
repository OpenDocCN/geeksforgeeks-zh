# JavaScript 字符串 `endsWith()` 方法

> 原文：[https://www.geeksforgeeks.org/javascript-string-endswith-method/](https://www.geeksforgeeks.org/javascript-string-endswith-method/)

下面是 `String endsWith()` 方法的示例。

## 示例

```html
<script>
// JavaScript to illustrate endsWith() function
function func() {
    // Original string
    var str = 'Geeks for Geeks';

    // Finding the search string in the given string
    var value = str.endsWith('for', 9);
    document.write(value);
}
func();
</script>
```

输出：

```
true
```

`str.endsWith()` 函数用于检查给定字符串是否以指定字符串的字符结尾。

## 语法

```
str.endsWith(searchString, length)
```

## 参数

这个函数的第一个参数是一个字符串 `searchString`，它将在给定字符串的末尾进行搜索。该函数的第二个参数是 `length`，它决定了从开始搜索 `searchString` 时给定字符串的长度。

## 返回值

该函数返回布尔值。如果找到了搜索字符串，则返回 `true`，否则返回 `false`。

## 功能示例

### 示例 1

```javascript
var str = 'It is a great day.'
print(str.endsWith('day.'));
```

输出：

```
true
```

在本例中，函数 `endsWith()` 检查给定字符串末尾的 `searchString`。由于最后找到了 `searchString`，因此该函数返回 `true`。

### 示例 2

```javascript
var str = 'It is a great day.'
print(str.endsWith('great'));
```

输出：

```
false
```

在本例中，函数 `endsWith()` 检查给定字符串末尾的 `searchString`。由于最后没有找到 `searchString`，因此该函数返回 `false`。

### 示例 3

```javascript
var str = 'It is a great day.'
print(str.endsWith('great', 13));
```

输出：

```
true
```

在本例中，函数 `endsWith()` 检查给定字符串末尾的 `searchString`。由于第二个参数在索引 `13` 处定义了字符串的结尾，并且在该索引处发现 `searchString` 结束，因此该函数返回 `true`。

## 完整程序代码

### 程序 1

```html
<script>
// JavaScript to illustrate endsWith() function
function func() {
    // Original string
    var str = 'It is a great day.';

    // Finding the search string in the given string
    var value = str.endsWith('day.');
    document.write(value);
}
func();
</script>
```

输出：

```
true
```

### 程序 2

```html
<script>
// JavaScript to illustrate endsWith() function
function func() {
    // Original string
    var str = 'It is a great day.';

    // Finding the search string in the given string
    var value = str.endsWith('great');
    document.write(value);
}
func();
</script>
```

输出：

```
false
```

### 程序 3

```html
<script>
// JavaScript to illustrate endsWith() function
function func() {
    // Original string
    var str = 'It is a great day.';

    // Finding the search string in the given string
    var value = str.endsWith('great', 13);
    document.write(value);
}
func();
</script>
```

输出：

```
true
```

## 支持的浏览器

*   Chrome 41 及以上
*   Edge 12 及以上
*   Firefox 17 及以上版本
*   Opera 28 及以上
*   Safari 9 及以上