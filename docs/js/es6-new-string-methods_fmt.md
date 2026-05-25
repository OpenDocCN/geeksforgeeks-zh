# ES6 新字符串方法

> 原文：[https://www.geeksforgeeks.org/es6-new-string-methods/](https://www.geeksforgeeks.org/es6-new-string-methods/)

在 [ES6](https://www.geeksforgeeks.org/introduction-to-es6/) 中，`String` 增加了四个新方法。当涉及到在 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 中的字符串操作时，这些方法对程序员来说就像是一个福音。在日常编程中，我们经常处理字符串。前三种方法还减少了某些任务对正则表达式的依赖。下面描述了四种 ES6 新字符串方法：

## `startsWith( queryString, position )` 方法

此方法返回 `true` 或 `false`。如果字符串从指定位置开始包含提供的字符串，则返回 `true`，否则返回 `false`。此方法是**区分大小写**的。此方法接受两个参数：

*   **查询字符串**：必须在字符串开头搜索的字符串。
*   **位置（可选）**：开始搜索的位置。请注意，其默认值为 `0`。

下面的例子说明了第一种方法 `startsWith(queryString, position)`。

**示例：**

```html
<script>
    let str = "GeeksforGeeks";

    console.log(str.startsWith("Geeks"));

    // Here specified position is 5, that means
    // searching will start from 'f' whose index
    // in string str is 5
    console.log(str.startsWith("for", 5));

    console.log(str.startsWith("geeks"));
</script>
```

**输出：**

```
true
true
false
```

## `endsWith( queryString, length )` 方法

此方法返回 `true` 或 `false`。如果字符串在指定长度内以提供的字符串结尾，则返回 `true`，否则返回 `false`。此方法是**区分大小写**的。此方法接受两个参数：

*   **查询字符串**：必须在字符串末尾搜索的字符串。
*   **长度（可选）**：字符串的长度。请注意，它的默认值是字符串长度。

下面的例子说明了第二种方法 `endsWith(queryString, length)`。

**示例：**

```html
<script>
    let str = "GeeksforGeeks";

    console.log(str.endsWith("Geeks"));

    // Here specified length is 8, that means
    // length of str will be considered as 8
    // and rest will be omitted
    console.log(str.endsWith("for", 8));

    console.log(str.endsWith("geeks"));
</script>
```

**输出：**

```
true
true
false
```

## `includes( queryString, position )` 方法

此方法返回 `true` 或 `false`。如果字符串中包含提供的字符串，则返回 `true`，否则返回 `false`。此方法是**区分大小写**的。此方法接受两个参数：

*   **查询字符串**：字符串中要搜索的字符串。
*   **位置（可选）**：开始搜索的位置。请注意，其默认值为 `0`。

下面的例子说明了第三种方法 `includes(queryString, position)`。

**示例：**

```html
<script>
    let str = "GeeksforGeeks";

    console.log(str.includes("eks"));

    // Here search will start from index 8
    // of str
    console.log(str.includes("for", 8));

    console.log(str.includes("geeks"));
</script>
```

**输出：**

```
true
false
false
```

## `repeat( count )` 方法

此方法接受单个参数，该参数是一个整数值，表示字符串要重复的次数。此方法返回一个新创建的字符串，其中包含重复了 `count` 次的旧字符串。

**注意**：提供的参数 `count` 必须是正整数。

下面的例子说明了第四种方法 `repeat(count)`。

**示例：**

```html
<script>
    let str = "GeeksforGeeks";
    console.log(str.repeat(2));
    let newStr = str.repeat(3);
    console.log(newStr);
</script>
```

**输出：**

```
GeeksforGeeksGeeksforGeeks
GeeksforGeeksGeeksforGeeksGeeksforGeeks
```

## 模板文字

这些文字允许嵌入表达式。它不使用单引号或双引号，而是使用反引号（`` ` ``）。模板文字有两种类型。

### 单行字符串和模板文字

单行字符串和模板文字包含单行字符串，下面的例子将说明这一点。

**示例：**

```html
<script>
    var a = "Geeks";
    var b = "for";
    console.log(`We are the ${a+b+a} `)
</script>
```

**输出：**

```
We are the GeeksforGeeks
```

### 多行字符串和模板文字

多行字符串和模板文字包含多行字符串，下面的例子将说明这一点。

**示例：**

```html
<script>
    var a = `GeeksforGeeks`;
    var b = ` A Online 
    Computer Science 
    Portal for Geeks`;

    console.log(a + b)
</script>
```

**输出：**

```
GeeksforGeeks A Online 
Computer Science 
Portal for Geeks
```

## `String.raw()` 方法

`String.raw()` 方法用于按原样打印反斜杠，它不会将换行符带入控制台。

**示例：**

```html
<script>
    var geeks = String.raw `A Online Computer \nScience Portal for Geeks`

    //Printing backslash as string
    console.log(geeks)
</script>
```

**输出：**

```
A Online Computer \nScience Portal for Geek
```

## `String.fromCodePoint()` 方法

`String.fromCodePoint()` 是 JavaScript 中的内置函数，用于返回给定代码点值序列（ASCII 值）的字符串或元素。

**示例：**

```html
<script>
    // Taking some code point values
    a = String.fromCodePoint(42);
    b = String.fromCodePoint(66, 65, 102);

    // Printing the corresponding elements of
    // the code point value.
    console.log(a + "<br>")
    console.log(b)
</script>
```

**输出：**

```
*
BAf
```