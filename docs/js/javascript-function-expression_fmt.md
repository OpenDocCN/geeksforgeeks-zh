# JavaScript 函数表达式

> 原文: [https://www.geeksforgeeks.org/javascript-function-expression/](https://www.geeksforgeeks.org/javascript-function-expression/)

**函数表达式**允许我们创建一个没有任何函数名的匿名函数，这是函数表达式和函数声明的主要区别。函数表达式可以用作 IIFE（立即调用的函数表达式），它一被定义就运行。函数表达式必须存储在变量中，并且可以使用变量名称进行访问。随着 ES6 特性引入箭头函数，声明函数表达式变得更加容易。

## 函数声明语法

```
function functionName(x, y) { statements... return z };
```

## 函数表达式语法（匿名）

```
let variableName = function(x, y) { statements... return z };
```

## 函数表达式语法（命名）

```
let variableName = function functionName(x, y) 
{ statements... return z };
```

## 箭头函数语法

```
let variableName = (x, y) => { statements... return z };
```

## 注意

*   在调用函数表达式或将其用作参数之前，必须先定义函数表达式。
*   箭头函数必须有 `return` 语句。

以下示例说明了 JavaScript 中的函数表达式：

### 例 1：函数声明代码

```html
<script>
    function callAdd(x, y){
        let z = x + y;
        return z;   
    }
    console.log("Addition : " + callAdd(7, 4));
</script>
```

**输出：**

```
Addition : 11
```

### 例 2：函数表达式代码（匿名）

```html
<script>
    var calSub = function(x, y){
        let z = x - y;
        return z;
    }

    console.log("Subtraction : " + calSub(7, 4));
 </script>
```

**输出：**

```
Subtraction : 3
```

### 例 3：函数表达式代码（命名）

```html
<script>
    var calMul = function Mul(x, y){
        let z = x * y;
        return z;
    }

    console.log("Multiplication : " + calMul(7, 4));
</script>
```

**输出：**

```
Multiplication : 28
```

### 例 4：箭头函数代码

```html
<script>
    var calDiv = (x, y) => {
        let z = x / y;
        return z;
    }

    console.log("Division : " + calDiv(24, 4));
</script>
```

**输出：**

```
Division : 6
```

## 支持的浏览器

*   Chrome 1 及以上
*   Edge 12 及以上
*   Firefox 1 及以上版本
*   Internet Explorer 3 及以上版本
*   Opera 3 及以上
*   Safari 1 及以上