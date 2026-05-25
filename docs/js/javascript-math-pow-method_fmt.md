# JavaScript Math.pow() 方法

> 原文: [https://www.geeksforgeeks.org/javascript-math-pow-method/](https://www.geeksforgeeks.org/javascript-math-pow-method/)

下面是 `Math.pow()` 方法的例子。

## 示例

```html
<script type="text/javascript">
    document.write(Math.pow(3, 4));
</script>
```

**输出:**

```
81
```

## 方法描述

`Math.pow()` 方法用于对一个数进行幂运算，即把数的值提升到某个指数。因为 `Math.pow()` 是一个静态的 `Math` 方法，所以它总是被用作 `Math.pow()`，而不是作为在 `Math` 类中创建的对象的方法。

## 语法

```javascript
Math.pow(base, exponent)
```

## 参数

该方法接受两个参数：

*   `base`: 是要升幂的基数。
*   `exponent`: 是用来提升 `base` 的数值。

## 返回值

`Math.pow()` 方法返回一个数字，该数字代表给定的 `base` 乘以给定的 `exponent` 的幂。

## 更多示例

### 程序 1

当 `base` 和 `exponent` 在参数中作为正数传递时：

```html
<script type="text/javascript">
    document.write(Math.pow(9, 3));
</script>
```

**输出:**

```
729
```

### 程序 2

当 `base` 值为负且 `exponent` 为正时：

```html
<script type="text/javascript">
    document.write(Math.pow(-9, 3));
</script>
```

**输出:**

```
-729
```

### 程序 3

当 `base` 值为正值而 `exponent` 为负值时：

```html
<script type="text/javascript">
    document.write(Math.pow(9, -3));
</script>
```

**输出:**

```
0.0013717421124828531
```

### 程序 4

当 `base` 值为负且 `exponent` 有小数点时：

```html
<script type="text/javascript">
    document.write(Math.pow(-9, 0.5));
</script>
```

**输出:**

```
NaN
```

## 支持的浏览器

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队