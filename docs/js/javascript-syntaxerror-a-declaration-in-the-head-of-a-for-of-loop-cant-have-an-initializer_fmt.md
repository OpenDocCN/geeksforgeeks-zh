# JavaScript 语法错误–for-of 循环头部的声明不能有初始值设定项

> 原文：`https://www.geeksforgeeks.org/javascript-syntaxerror-a-declaration-in-the-head-of-a-for-of-loop-cant-have-an-initializer/`

如果 `for-of` 循环包含像 `for (var i = 0 of iterable)` 这样的初始化表达式，那么 for-of 循环头中的声明不能有初始值设定项就会出现这个 JavaScript 异常。这在 `for-of` 循环中是无效的初始化。

## 消息

```
SyntaxError: for-of loop head declarations cannot have 
             an initializer (Edge)
SyntaxError: a declaration in the head of a for-of loop
             can't have an initializer (Firefox)
SyntaxError: for-of loop variable declaration may not have 
             an initializer. (Chrome)
```

## 错误类型

```
SyntaxError
```

## 错误原因

循环包含一个在 `for-of` 循环内部无效的初始化。

## 示例 1

### 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>Syntax Error</title>
</head>
<body>
    <script>
        let iter = [10, 20, 30]; 
        for (let val of iter) { 
          document.write(val + "<br>"); 
        } 
    </script>
</body>
</html>
```

**输出：**

```

```

## 示例 2

该示例在循环的 `for-of` 头部包含无效初始化。

### 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>Syntax Error</title>
</head>
<body>
    <script>
        let iter = [10, 20, 30]; 
        for (let val = 10 of iter) { 
              document.write(val + "<br>"); 
        } 
    </script>
</body>
</html>
```

**输出（控制台中）：**

```
SyntaxError: for-of loop variable declaration may not have 
an initializer.
```