# 在 ES6 中定义异常处理

> 原文: [https://www.geeksforgeeks.org/define-exception-handling-in-es6/](https://www.geeksforgeeks.org/define-exception-handling-in-es6/)

## 异常

异常是基本上中断程序正常流程的不想要的事件。一般有两种例外情况：

*   同步（如运行时错误）
*   异步（如系统错误）

## 异常处理

程序中经常发生异常，导致程序突然终止或以不友好的方式终止。处理或防止意外行为被称为异常处理。异常处理处理同步异常，如错误的用户输入、不存在的文件等。（它包括运行时错误）。

## 为什么异常处理

异常处理基本上保证了程序不会突然终止或者程序的流程不会以不友好的方式中断。有意义的错误报告是可能的，并且可以为用户生成可理解的错误报告。

**ES6**（ECMA 脚本编程语言第 6 版）提供了异常处理的重要特性。使用 `try` 块，然后或者 `catch` 块，或者 `finally` 块。由于 `try` 块并不单独存在，所以它们要么后面跟着一个 `catch` 块，要么后面跟着 `finally` 块。它以三种形式之一存在：

*   `try...catch`
*   `try...finally`
*   `try...catch...finally`

### 1. try…catch block

`try` 块中的代码或语句将首先执行。每当异常发生时，它将被置于 `exception_var` 中，并且 `catch` 块将进一步执行。

**语法:**

```
try {
    // try statements
    // code to run
} catch (exception_var) {
    // catch statements
    // code to run
}
```

### 2. try…finally block

首先将执行 `try` 语句。之后 `finally` 语句将执行。`finally` 块将总是被执行，不管是否发生异常。

**语法:**

```
try {
    // try statements
    // code to run
} finally {
    // finally statements
    // code that is always executed
}
```

### 3. try…catch…finally block

`try` 块首先执行。如果发生异常，它的值将被放在 `exception_var` 和 `catch` 块中，然后 `finally` 块将被执行。然而，`finally` 块将执行，不管异常是否发生。

**语法:**

```
try {
    // try statements
    // code to run
} catch (exception_var) {
    // catch statements
    // code to run if exception occurs
} finally {
    // finally statements
    // code that is always executed
}
```

让我们用下面的例子来理解：

### 例 1

我们举一个用户输入不好的例子，用户把问题除以零“0”。

```javascript
<script>
    var num = 5;
    var de_num = 0;
    try {
        if(de_num == 0) {
            throw "Divide by zero error";
        } else {
            var sol = num / de_num;
        }
    } catch(e) {
        console.log("Error : " + e);
    }
</script>
```

**输出:**

```
Error : Divide by zero error
```

### 例 2

我们再举一个例子，每当我们使用一个我们没有声明的引用时，就会抛出一个引用错误。在本例中，我们没有有意声明函数，而是直接调用了它，这会导致 `ReferenceError`。

```javascript
<script>
    try{
      ab();
      // We have not declared the
      // function ab anywhere
    } catch(e){
      console.log("Error : "+ e.name);
    }
</script>
```

`e.name` 将返回错误的名称。

**输出:**

```
Error : ReferenceError
```

### 示例 3

在我们的最后一个示例中，我们特意编写了一条语句，试图阻止语法错误。我们没有正确地将字符串括在单引号之间。它会给我们带来 `SyntaxError`。

```javascript
<script>
    try {
        eval("alert('ES6 Exception Handling)");
    } catch(e){
        console.log("Error : " + e.name)
    }
</script>
```

**输出:**

```
Error : SyntaxError
```