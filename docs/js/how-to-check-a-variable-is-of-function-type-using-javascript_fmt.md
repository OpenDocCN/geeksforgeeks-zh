# 如何用 JavaScript 检查一个变量是函数类型？

> 原文：[https://www.geeksforgeeks.org/how-to-check-a-variable-is-of-function-type-using-javascript/](https://www.geeksforgeeks.org/how-to-check-a-variable-is-of-function-type-using-javascript/)

JavaScript 中的函数是用于执行特定任务的一组语句。函数可以是命名函数，也可以是匿名函数。函数内部的一组语句在函数被调用时执行。函数可以赋给变量，也可以传递给方法。

```
var gfg = function(){/* A set of statements */};
```

这里，一个匿名函数被分配给名为`gfg`的变量。有各种方法可以检查变量是否属于函数类型。其中一些将在下面讨论：

## 1. 使用 instanceof 运算符

`instanceof`运算符在运行时检查对象的类型。它返回一个相应的布尔值，即`true`或`false`，以指示对象是否属于特定类型。

**示例：** 本示例使用`instanceof`运算符检查变量是否属于函数类型。

```
<script>
    // Declare a variable and initialize it
    // with anonymous function
    var gfg = function(){/* A set of statements */};

    // Function to check a variable is of
    // function type or not
    function testing(x) {
        if(x instanceof Function) {
            document.write("Variable is of function type");
        }
        else {
            document.write("Variable is not of function type");
        }
    }

    // Function call
    testing(gfg);
</script>
```

**输出：**

```
Variable is of function type
```

## 2. 使用严格相等 (===) 运算符

在 JavaScript 中，`===`运算符用于检查两个实体是否具有相同的值和相同的类型，并提供布尔结果。在这个例子中，我们使用`===`运算符。这个运算符被称为严格相等运算符，它检查操作数是否属于同一类型。

**示例：** 本示例使用`===`运算符检查变量是否属于函数类型。

```
<script>
    // Declare a variable and initialize it
    // with anonymous function
    var gfg = function(){/* A set of statements */};

    // Function to check a variable is of
    // function type or not
    function testing(x)
    {
        if (typeof x === "function") {
            document.write("Variable is of function type");
        }
        else {
            document.write("Variable is not of function type");
        }
    }

    // Function call
    testing(gfg);
</script>
```

**输出：**

```
Variable is of function type
```

## 3. 使用 Object.prototype.toString

此方法使用`Object.prototype.toString`。每个对象都有一个`toString()`方法，当期望字符串类型的值时会隐式调用该方法。如果未覆盖`toString()`方法，默认情况下它会返回`'[object *type*]'`，其中`'type*'`是对象类型。

**示例：** 本示例使用`Object.prototype.toString`方法检查变量是否属于函数类型。

```
<script>
    // Declare a variable and initialize it
    // with anonymous function
    var gfg = function(){/* A set of statements */};

    // Function to check a variable is of
    // function type or not
    function testing(x)
    {
        if (Object.prototype.toString.call(x) == '[object Function]')
        {
            document.write("Variable is of function type");
        }
        else {
            document.write("Variable is not of function type");
        }
    }

    // Function call
    testing(gfg);
</script>
```

**输出：**

```
Variable is of function type
```