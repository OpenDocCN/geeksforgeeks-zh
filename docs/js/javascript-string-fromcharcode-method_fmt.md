# JavaScript 字符串 `fromCharCode()` 方法

> 原文: [https://www.geeksforgeeks.org/javascript-string-fromcharcode-method/](https://www.geeksforgeeks.org/javascript-string-fromcharcode-method/)

下面是 `String.fromCharCode()` 方法的示例。

**例:**

```javascript
<script>
function func() {
    var str = String.fromCharCode(71, 70, 71);
    document.write(str);
}
func();
</script>
```

**输出:**

```
GFG
```

`String.fromCharCode()` 方法用于根据给定的 UTF-16 代码单元序列创建字符串。

**语法:**

```javascript
String.fromCharCode(n1, n2, ..., nX)
```

**参数:**
该方法以 UTF-16 Unicode 序列作为参数。此方法的参数数量取决于要连接为字符串的字符数量。数字的范围在 `0` 和 `65535` 之间。

**返回值:**
这个方法的返回值是一个包含字符的字符串，这些字符的 UTF-16 代码作为参数传递给了这个方法。

上述方法示例如下:

**例 1:**

```javascript
print(String.fromCharCode(65, 66, 67));
```

**输出:**

```
ABC
```

在本例中，方法 `fromCharCode()` 将 UTF-16 代码转换为它们的等效字符，并返回包含它们的字符串作为答案。在这种情况下，答案是 `ABC`。

**例 2:**

```javascript
String.fromCharCode(0x12014);
```

**输出:**

```
—
```

在本例中，方法 `fromCharCode()` 将 UTF-16 代码转换为其等效字符，并返回包含该字符的字符串作为答案。在这种情况下，答案是 `—`。

上述方法的代码如下:

**程序 1:**

```javascript
<script>
// JavaScript to illustrate fromCharCode() method
function func() {

// UTF-16 codes to be converted into characters
    var str = String.fromCharCode(65, 66, 67);
    document.write(str);
}

func();
</script>
```

**输出:**

```
ABC
```

**程序 2:**

```javascript
<script>
// JavaScript to illustrate fromCharCode() method
function func() {

// UTF-16 code to be converted into character
    var str = String.fromCharCode(0x12014);
    document.write(str);
}

func();
</script>
```

**输出:**

```
—
```

**支持的浏览器:**

*   Chrome 1 及以上
*   Edge 12 及以上
*   Firefox 1 及以上版本
*   Internet Explorer 4 及以上版本
*   Opera 4 及以上
*   Safari 1 及以上