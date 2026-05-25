# JavaScript 字符串 toUpperCase()方法

> 原文: [https://www.geeksforgeeks.org/javascript-string-touppercase/](https://www.geeksforgeeks.org/javascript-string-touppercase/)

下面是 String `toUpperCase()`方法的示例。

*   例:

## Java Script 语言

```javascript
<script>
function func() {
    var str = 'geeksforgeeks';
    var string = str.toUpperCase();
    document.write(string);
}
func();
</script>
```

*   输出:

```
GEEKSFORGEEKS
```

`str.toUpperCase()` 方法将整个字符串转换为大写。此方法不影响任何大写的特殊字符、数字和字母。

**语法:**

```
str.toUpperCase()
```

**返回值:**
这个方法返回一个新的字符串，其中所有小写字母都转换成大写。

上述方法的示例如下:

**示例 1:**

```
var str = 'It iS a Great Day.';
var string = str.toUpperCase();
print(string);
```

输出:

```
IT IS A GREAT DAY.
```

在本例中，方法`toUpperCase()`将所有小写字母转换为大写字母，而不影响特殊字符和数字。

**例 2:**

```
var str = 'It iS a 5r&e@@t Day.'
var string = str.toUpperCase();
print(string);
```

输出:

```
IT IS A 5R&E@@T DAY.
```

在本例中，方法`toUpperCase()`将所有小写字母转换为大写字母，而不影响特殊字符和数字。

上述方法的代码如下:

**程序 1:**

### Java Script 语言

```javascript
<script>
// JavaScript to illustrate .toUpperCase()

function func() {

// Original string
    var str = 'It iS a Great Day.';

// String converted to Upper Case
    var string = str.toUpperCase();
    document.write(string);
}

func();
</script>
```

输出:

```
IT IS A GREAT DAY.
```

**节目 2:**

### Java Script 语言

```javascript
<script>
// JavaScript to illustrate .toUpperCase()
function func() {

//Original string
    var str = 'It iS a 5r&:ampe@@t Day.'

//String converted to Upper Case
    var string = str.toUpperCase();
    document.write(string);
}

func();
</script>
```

输出:

```
IT IS A 5R&:AMPE@@T DAY.
```

**支持的浏览器:**

*   Chrome 1 及以上
*   边缘 12 及以上
*   Firefox 1 及以上版本
*   Internet Explorer 3 及以上版本
*   歌剧 3 及以上
*   Safari 1 及以上