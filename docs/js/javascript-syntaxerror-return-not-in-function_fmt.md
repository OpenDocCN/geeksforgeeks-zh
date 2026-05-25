# JavaScript 语法错误：return not in function

> 原文：[https://www.geeksforgeeks.org/javascript-syntaxerror-return-not-in-function/](https://www.geeksforgeeks.org/javascript-syntaxerror-return-not-in-function/)

如果在函数体之外写了一个 `return`/`yield` 语句，就会出现这个 JavaScript 异常 **return not in function**（或 **yield not in function**）。

## 消息

```
SyntaxError: 'return' statement outside of function (Edge)
SyntaxError: return not in function (Firefox)
SyntaxError: yield not in function (Firefox)
```

## 错误类型

```
SyntaxError
```

## 发生了什么？

要么在函数体外部调用了 `return` 或 `yield` 语句，要么代码中可能缺少花括号。

## 例 1

本例中 `if` 语句后缺少花括号，所以出现了错误。

```javascript
<!DOCTYPE html>
<html>
<head>
<title>Syntax Error</title>
</head>
<body>
    <script>
    var GFG = function(val) {
      if (val === 'GFG')
        return 'Text1';
      }; 
       /* looks like function ends here, because of
       missing opening curly bracket after 'if' keyword*/
      if (val === 'Geek') {
        return 'Text2';
      }
    }
    document.write(GFG());
    </script>
</body>
</html>
```

**输出（控制台中）：**

```
SyntaxError: 'return' statement outside of function
```

## 例 2

在本例中，返回语句是在函数结束后编写的，所以出现了错误。

```javascript
<!DOCTYPE html>
<html>
<head>
<title>Syntax Error</title>
</head>
<body>
    <script>
    var GFG = function(val) {
      if (val === 'GFG')
        return 'Text1';
      if (val === 'Geek') {
        return 'Text2';
      }
    };
    return "Text3"; 
  // this is outside the function body.
    document.write(GFG('GFG'));
    </script>
</body>
</html>
```

**输出（控制台中）：**

```
SyntaxError: 'return' statement outside of function
```