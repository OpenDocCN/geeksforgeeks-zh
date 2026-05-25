# 如何在 JavaScript 中使用动态变量名？

> 原文：[https://www.geeksforgeeks.org/how-to-use-dynamic-variable-names-in-javascript/](https://www.geeksforgeeks.org/how-to-use-dynamic-variable-names-in-javascript/)

在编程中，**动态变量名**在脚本中没有硬编码的具体名称。它们是用其他来源的字符串值动态命名的。动态变量很少在 JavaScript 中使用。但在某些情况下，它们是有用的。与 PHP 不同，JavaScript 中没有动态变量名的特殊实现。但是使用一些其他的方法也可以获得类似的结果。在 JavaScript 中，动态变量名可以通过使用下面给出的 2 种方法/途径来实现。

## eval()

`eval()` 函数将参数中表示为字符串的 JavaScript 代码进行求解。一个字符串作为参数传递给 `eval()`。如果该字符串表示一个表达式，`eval()` 会求解该表达式。在 `eval()` 内部，我们传递一个字符串，其中变量 `valuei` 被声明并在每次迭代中被赋值为 `i`。`eval()` 函数执行此操作并创建具有赋值的变量。下面的代码实现了使用 `eval()` 创建动态变量名。

**示例：**

```javascript
<script>
    var k = 'value';
    var i = 0;
    for(i = 1; i < 5; i++) {
        eval('var ' + k + i + '= ' + i + ';');
    }
    console.log("value1=" + value1);
    console.log("value2=" + value2);
    console.log("value3=" + value3);
    console.log("value4=" + value4);
</script>
```

**输出：**

```
value1=1
value2=2
value3=3
value4=4
```

## Window 对象

JavaScript 总是定义了一个全局对象。当程序创建全局变量时，它们作为全局对象的成员被创建。`window` 对象是浏览器中的全局对象。任何全局变量或函数都可以通过 `window` 对象访问。定义全局变量后，我们可以从 `window` 对象访问其值。下面的代码使用 `window` 对象实现了动态变量名。因此，该代码基本上为 `i` 的每次迭代创建了一个具有动态名称 `“valuei”` 的全局变量，并将 `i` 的值赋给它。之后，这些变量可以在脚本的任何地方访问，因为它们变成了全局变量。

**示例：**

```javascript
<script>
    var i;
    for(i = 1; i < 5; i++) {
        window['value'+i] = + i;
    }
    console.log("value1=" + value1);
    console.log("value2=" + value2);
    console.log("value3=" + value3);
    console.log("value4=" + value4);
</script>
```

**输出：**

```
value1=1
value2=2
value3=3
value4=4
```

JavaScript 最出名的是网页开发，但它也用于各种非浏览器环境。您可以通过以下 [JavaScript 教程](https://www.geeksforgeeks.org/javascript-tutorial/)和 [JavaScript 示例](https://www.geeksforgeeks.org/javascript-examples/)从头开始学习 JavaScript。