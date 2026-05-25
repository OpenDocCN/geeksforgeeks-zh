# JavaScript 布尔值 `valueOf()` 方法

> 原文：[https://www.geeksforgeeks.org/javascript-boolean-valueof-method/](https://www.geeksforgeeks.org/javascript-boolean-valueof-method/)

下面是 `Boolean.valueOf()` 方法的例子。

## 代码示例

### 示例 1

```html
<script>
  // Here Boolean object obj
  // is created for the value 27
  var obj = new Boolean(27);

  // Here boolean.valueOf() function is
  // used for the created object obj.
  document.write(obj.valueOf());
</script>
```

**输出：**

```
true
```

`Boolean.valueOf()` 方法用于根据指定布尔对象的值返回布尔值 `true` 或 `false`。

**语法：**

```javascript
boolean.valueOf()
```

**参数：** 此方法不接受任何参数。
**返回值：** 根据指定布尔对象的值，返回布尔值 `true` 或 `false`。

### 示例 2

```html
<script>
  // Here Boolean object obj is created
  // for the value true.
  var obj = new Boolean(true);

  // Here boolean.valueOf() function is
  // used for the created object obj.
  document.write(obj.valueOf());
</script>
```

**输出：**

```
true
```

### 示例 3

```html
<script>
  // Here Boolean object obj is
  // created for the value 1.
  var obj = new Boolean(1);

  // Here boolean.valueOf() function
  // is used for the created object obj.
  document.write(obj.valueOf());
</script>
```

**输出：**

```
true
```

### 示例 4

```html
<script>
  // Here Boolean object obj is
  // created for the value -1.
  var obj = new Boolean(-1);

  // Here boolean.valueOf() function
  // is used for the created object obj.
  document.write(obj.valueOf());
</script>
```

**输出：**

```
true
```

### 示例 5

```html
<script>
  // Here Boolean object obj is
  // created for the value 1.2
  var obj = new Boolean(1.2);

  // Here boolean.valueOf() function
  // is used for the created object obj.
  document.write(obj.valueOf());
</script>
```

**输出：**

```
true
```

### 示例 6

```html
<script>
  // Here Boolean object obj is
  // created for the value as string "gfg"
  var obj = new Boolean("gfg");

  // Here boolean.valueOf() function is
  // used for the created object obj.
  document.write(obj.valueOf());
</script>
```

**输出：**

```
true
```

### 示例 7

```html
<script>
  // Here Boolean object obj is created for the value false.
  var obj = new Boolean(false);

  // Here boolean.valueOf() function is
  // used for the created object obj.
  document.write(obj.valueOf());
</script>
```

**输出：**

```
false
```

### 示例 8

```html
<script>
  // Here Boolean object obj is created
  // for the value zero (0)
  var obj = new Boolean(0);

  // Here boolean.valueOf() function is
  // is used for the created object obj.
  document.write(obj.valueOf());
</script>
```

**输出：**

```
false
```

### 示例 9

这里 `geeksforgeeks` 的值给出了一个错误，因为这个值没有定义，只有 `true` 和 `false` 是预定义的。

```html
<script>
  // Here Boolean object obj is created
  // for the value geeksforgeeks.
  var obj = new Boolean(geeksforgeeks);

  // Here boolean.valueOf() function is
  // used for the created object obj.
  console.log(obj.valueOf());
</script>
```

**输出：**

```
Error: geeksforgeeks is not defined
```

### 示例 10

这里复数不能作为参数，只有整数值和字符串可以作为参数，这就是它返回错误的原因。

```html
<script>
  // Here Boolean object obj is created
  // for the value such as complex number 1+2i
  var obj = new Boolean(1 + 2i);

  // Here boolean.valueOf() function is
  // used for the created object obj.
  console.log(obj.valueOf());
</script>
```

**输出：**

```
Error: Invalid or unexpected token
```

## 支持的浏览器

JavaScript 布尔值 `valueOf()` 方法支持的浏览器如下：

*   谷歌 Chrome 1 及以上版本
*   Internet Explorer 4 及以上版本
*   Mozilla Firefox 1 及以上版本
*   Safari 1 及以上
*   Opera 4 及以上