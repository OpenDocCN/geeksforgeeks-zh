# JavaScript SyntaxError: Missing ) after condition

> 原文: [https://www.geeksforgeeks.org/javascript-syntaxerror-missing-after-condition/](https://www.geeksforgeeks.org/javascript-syntaxerror-missing-after-condition/)

如果 `if` 条件有问题，就会出现这个 JavaScript 异常：`SyntaxError: missing ) after condition`。括号应该在 `if` 关键字之后。

## 消息

```
SyntaxError: Expected ')' (Edge)
SyntaxError: missing ) after condition (Firefox)
```

## 错误类型

```
SyntaxError
```

## 错误原因

在代码的某个地方，`if` 条件的编写方式有问题。条件应该写在括号内。

## 例 1

在本例中，`if` 关键字后有一个 `missing )`，所以出现了错误。

### HTML

```html
<!DOCTYPE html>
<html>
<head>
    <title>Syntax Error</title>
</head>
<body>
    <script>
        if (3 < Math.PI {
            document.write("This will not print");   
        }
    </script>
</body>
</html>
```

**输出（在 Edge 浏览器的控制台中）：**

```
Expected ')'
```

## 例 2

在本例中，误用了 `is` 关键字，因此出现了错误。应该是 `===`。

### HTML

```html
<!DOCTYPE html>
<html>
<head>
    <title>Syntax Error</title>
</head>
<body>
    <script>
        if (someVar is true) {
            document.write("This will not print");   
        }
    </script>
</body>
</html>
```

**输出（在 Edge 浏览器的控制台中）：**

```
Expected ')'
```