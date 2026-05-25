# JavaScript 警告 – `Date.prototype.toLocaleFormat` 已弃用

> 原文：[https://www.geeksforgeeks.org/javascript-warning-date-prototype-tolocaleformat-is-deprecated/](https://www.geeksforgeeks.org/javascript-warning-date-prototype-tolocaleformat-is-deprecated/)

这个 JavaScript 警告 `Date.prototype.toLocaleFormat is deprecated; consider using Intl.DateTimeFormat instead` 会在用户使用非标准的 `Date.prototype.toLocaleFormat` 方法时出现。

**消息：** `Date.prototype.toLocaleFormat is deprecated; consider using Intl.DateTimeFormat instead`

**错误类型：**
```
Warning. JavaScript execution won't be halted.
```

## 发生了什么？

在代码中，使用了非标准的 `Date.prototype.toLocaleFormat` 方法，但它已被弃用。

### 例 1
在本例中，使用了已弃用的方法，因此触发了警告。

```javascript
<script>
  var day = new Date(); 
  var date = day.toLocaleFormat('%B, %e. %A %Y'); // Warning here
</script>
```

**输出：**
```
Warning: Date.prototype.toLocaleFormat is deprecated; consider using Intl.DateTimeFormat instead
```

### 例 2
在本例中，同样使用了已弃用的方法，因此触发了警告。

```javascript
<script>
  var day = new Date();
  day.toLocaleFormat("%Y%m%d"); // Warning here
</script>
```

**输出：**
```
Warning: Date.prototype.toLocaleFormat is deprecated; consider using Intl.DateTimeFormat instead
```