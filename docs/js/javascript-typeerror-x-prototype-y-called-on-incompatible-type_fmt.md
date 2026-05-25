# JavaScript TypeError: 'x.prototype.y' 调用了不兼容的类型

> 原文: [https://www.geeksforgeeks.org/javascript-typeerror-x-prototype-y-called-on-incompatible-type/](https://www.geeksforgeeks.org/javascript-typeerror-x-prototype-y-called-on-incompatible-type/)

这个 JavaScript 异常 **“TypeError: 'x.prototype.y' called on incompatible type”** 发生在一个函数（在一个给定的对象上）被调用时带有一个“this”，该“this”对应于不同于该函数所期望的类型。

**消息:**
`TypeError: 'this' is not a Set object` (或其他不兼容类型)

**错误类型:**
```
TypeError
```

**错误原因:** 在函数调用中的某个地方，函数（在给定的对象上）被调用时带有一个“this”，与函数期望的类型不对应。

## 示例 1

在此示例中，`GFG_Set.add` 是一个函数，但 `GFG_Set` 未被捕获为“this”。

### HTML
```html
<script>
    var GFG_Set = new Set;
    ['Geek', 'GFG'].forEach(GFG_Set.add);
</script>
```

**输出 (控制台):**
```
TypeError: 'this' is not a Set object
```

## 示例 2

在本例中，`GFG_Fun.bind` 是一个函数，但是 `GFG_Fun` 没有被捕获为“this”。

### HTML
```html
<script>
    var GFG_Fun = function () {
      console.log(this);
    };
    ['Geek', 'GFG'].forEach(GFG_Fun.bind);
</script>
```

**输出 (控制台):**
```
TypeError: 'this' is not a Set object
```