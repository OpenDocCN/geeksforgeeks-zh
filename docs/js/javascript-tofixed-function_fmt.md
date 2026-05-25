# JavaScript Number toFixed()方法

> 原文: [https://www.geeksforgeeks.org/javascript-tofixed-function/](https://www.geeksforgeeks.org/javascript-tofixed-function/)

下面是 `Number` `toFixed()`方法的示例。

## 示例

```html
<script type="text/javascript">
    var test=213.73145;
    document.write(test.toFixed(1));          
</script>
```

**输出:**

```
213.7
```

JavaScript 中的 `toFixed()`方法用于使用定点表示法格式化数字。它可以用来格式化小数点右边有特定位数的数字。

## 语法

```
number.toFixed( value )
```

`toFixed()`方法与一个`number`一起使用，如上面使用“.”的语法所示操作员。此方法将使用定点表示法格式化数字。

## 参数

该方法接受单个参数`value`。它表示小数点后出现的位数。

## 返回值

返回字符串形式的数字。该数字在小数点后有精确的位数，如 `toFixed()`方法中所述。

## 示例

### 不带参数使用 toFixed() 方法

如果在 `toFixed()`方法中没有指定参数，则不会显示小数点后的任何数字。

```html
<script type="text/javascript">
    var test=213.73145;
    document.write(test.toFixed());          
</script>
```

**输出:**

```
214
```

### 带参数使用 toFixed() 方法

如果在 `toFixed()`方法中指定了参数，将返回一个表示为字符串的数字，该数字在小数点后将有精确的指定位数。

```html
<script type="text/javascript">
    var test=213.73145;
    document.write(test.toFixed(3));          
</script>
```

**输出:**

```
214.731
```

### 对指数形式的数字使用 toFixed() 方法

`toFixed()`方法可用于将指数数字转换为具有小数点后特定位数的字符串表示形式。

```html
<script type="text/javascript">
    var test=2.13e+15;
    document.write(test.toFixed(2));          
</script>
```

**输出:**

```
2130000000000000.00
```

## 支持的浏览器

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧