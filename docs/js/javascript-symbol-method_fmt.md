# JavaScript 符号()方法

> 原文:[https://www.geeksforgeeks.org/javascript-symbol-method/](https://www.geeksforgeeks.org/javascript-symbol-method/)

符号是作为 ES6 的一部分引入的新的基本内置对象类型。`Symbol()`返回唯一标识符，可用于向对象添加唯一属性键，而不会与可能添加到对象的任何其他代码的键冲突。它们被用作无法重新创建的对象属性。它基本上帮助我们启用封装或信息隐藏。

**语法:**

```
Symbol( optional_string )
```

**参数:** `optional_string`是一个可选参数，作为`Symbol()`的描述。

**返回值:** 这个方法返回一个新的符号对象。

下面是 `Symbol()`方法的示例。

## 例 1:

```javascript
<script>
    let symbol1 = Symbol("Geeks")
    let symbol2 = Symbol("Geeks")

    // Each time Symbol() method 
    // is used to create new global
    // Symbol
    console.log(symbol1 == symbol2);
</script>
```

**输出:**

```
false
```

## 例二:

```javascript
<script>
    // Symbol returns a symbol primitive 
    console.log(typeof Symbol("GFG"));
    console.log(typeof Object("GFG"));
</script>
```

**输出:**

```
symbol
object
```