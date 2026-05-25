# JavaScript 语法错误–无效的正则表达式标志“x”

> 原文: [https://www.geeksforgeeks.org/javascript-syntaxerror-invalid-regular-expression-flag-x/](https://www.geeksforgeeks.org/javascript-syntaxerror-invalid-regular-expression-flag-x/)

如果写在正则表达式文字中第二个斜杠之后的标志不是来自(`g`、`i`、`m`、`s`、`u` 或 `y`)中的任何一个，就会出现这个 JavaScript 异常 **无效正则表达式标志**。

## 消息

```
SyntaxError: Syntax error in regular expression (Edge)
SyntaxError: invalid regular expression flag "x" (Firefox)
SyntaxError: Invalid regular expression flags (Chrome)
```

## 错误类型

```
SyntaxError
```

## 错误原因

在代码的某个地方，有无效的正则表达式标志。

## 示例 1

此示例具有有效的正则表达式标志。

### HTML

```html
<!DOCTYPE html>
<html>
<head>
    <title>Syntax Error</title>
</head>
<body>
    <script>
        var patt = /GeeksforGeeks/i;
        var str = 'This is GeeksforGeeks';
        document.write(str.match(patt));
    </script>
</body>
</html>
```

**输出:**

```
GeeksForGeeks
```

## 示例 2

在本例中，第二个斜杠后的‘GFG’用作无效标志。

### HTML

```html
<!DOCTYPE html>
<html>
<head>
    <title>Syntax Error</title>
</head>
<body>
    <script>
        var patt = /Geek/GFG;
        var str = 'This is GeeksforGeeks';
        document.write(str.match(patt));
    </script>
</body>
</html>
```

**输出(控制台中):**

```
SyntaxError: Invalid regular expression flags
```