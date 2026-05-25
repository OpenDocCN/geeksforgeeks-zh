# JavaScript TypeError: Invalid 'instanceof' Right-hand Side

> 原文链接：https://www.geeksforgeeks.org/javascript-type-error-invalid-instanceof-operators-x/

当 `instanceof` 运算符的右操作数不是一个构造函数对象时，JavaScript 会抛出此异常。`instanceof` 用于检测构造函数的 `prototype` 属性是否出现在某个对象的原型链中。

**消息:**
```
TypeError: Right-hand side of 'instanceof' is not an object
```

**错误类型:**
```
TypeError
```

**错误原因:** `instanceof` 运算符的右侧不是一个构造函数对象。

## 例 1

在本例中，`instanceof` 运算符的右侧不是一个构造函数对象。

```html
<script>
"Geeks" instanceof ""; // 此处报错
</script>
```

**输出:**
```
TypeError: Right-hand side of 'instanceof' is not an object
```

## 例 2

在本例中，`instanceof` 运算符的右侧不是一个构造函数对象。

```html
<script>
function GFG() {}
var gfg = GFG();   
var x = new GFG();
x instanceof gfg; // 此处报错
</script>
```

**输出:**
```
TypeError: Right-hand side of 'instanceof' is not an object
```