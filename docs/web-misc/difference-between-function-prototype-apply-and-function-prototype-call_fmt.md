# Function.prototype.apply() 和 Function.prototype.call() 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-function-prototype-apply-and-function-prototype-call/](https://www.geeksforgeeks.org/difference-between-function-prototype-apply-and-function-prototype-call/)

[JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 把一切都当成一个对象，甚至是函数，每个对象都有自己的属性和方法。函数对象上既有 [`apply()`](https://www.geeksforgeeks.org/javascript-function-apply/) 又有 [`call()`](https://www.geeksforgeeks.org/javascript-function-call/) 方法。但是，对于 JavaScript 中的这两个函数存在混淆。它们之间的主要区别是如何处理函数参数。这两个函数在如何将参数传递给被调用函数方面没有区别，但是函数内部的定义不同。

除了第一个参数， [`apply()`](https://www.geeksforgeeks.org/javascript-function-apply/) 需要一个数组作为它的第二个参数。目标方法的参数表示为数组。

## JavaScript `call()` 函数

它使用给定的参数和值来调用函数。

**语法:**

```javascript
function.call(object, arg1, arg2)
```

**示例:**

```html
<script>
   let obj = {
      fname: "geeks",
      mname: "for",
      lname: "geeks",
   };
   let display = function (str1, str2) {
      console.log(`${str1} ${str2} ${this.fname + 
                  this.mname + this.lname}`);
   };
   display.call(obj, "Welcome", "to");
</script>
```

**输出:**

```
Welcome to geeksforgeeks
```

## JavaScript `apply()` 函数

此方法用于调用一个以数组或数组对象形式存在参数和值的函数。

在这两种情况下，第一个参数将是在被调用函数中表示“this”的对象引用。因此，`call()` 不同于 `apply()`。每个都可以应用于一个函数，该函数在第一个参数的上下文中运行。在 `call()` 中，剩余的参数按原样传递到函数中，而在 `apply()` 中，第二个参数将是一个数组，被调用的函数会将其解包为参数。

**语法:**

```javascript
function.apply(object, [arg1, arg2])
```

**示例:**

```html
<script>
    let obj = {
       fname: "geeks",
       mname: "for",
       lname: "geeks",
    };
    let display = function (str1, str2) {
       console.log(`${str1} ${str2} ${this.fname + 
                   this.mname + this.lname}`);
    };
    display.apply(obj, ["Welcome", "to"]);
</script>
```

**输出:**

```
Welcome to geeksforgeeks
```

## `Function.prototype.apply()` 和 `Function.prototype.call()` 的区别

| `Function.prototype.apply()` | `Function.prototype.call()` |
| --- | --- |
| Using the `apply()` method, you can call the function with the specified value and the parameters provided as an array (or object). | Use `call()` to call the function with the given values and parameters. |
| `function.call(object, arg1, arg2)` | `function.apply(object, [arg1, arg2])` |