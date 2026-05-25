# JavaScript Math.LN2 属性

> 原文: [https://www.geeksforgeeks.org/javascript-math-ln2-property/](https://www.geeksforgeeks.org/javascript-math-ln2-property/)

## 描述

`Math.LN2` 是 JavaScript 中的一个属性，它表示 2 的自然对数的值。自然对数以常数 `e` 为底，通常用 `ln` 表示。因此，2 的自然对数表示为 `ln(2)`，其值约为 0.693。

## 语法

```
Math.LN2;
```

## 参数

此属性不接受任何参数。

## 返回值

它返回 2 的自然对数的值。

## 示例

### 示例 1

下面是 `Math.LN2` 属性的基本示例。

```javascript
// 打印 Math.LN2 的值。
document.write(Math.LN2);
```

**输出:**

```
0.6931471805599453
```

### 示例 2

自然对数 2 的值可以通过函数形式打印。

```javascript
// 定义函数。
function get_Value_of_natural_log_of_2() {
    return Math.LN2;
}

// 调用函数。
document.write(get_Value_of_natural_log_of_2());
```

**输出:**

```
0.6931471805599453
```

### 示例 3

这里我们尝试将 `Math.LN2` 作为函数调用，但实际上它是一个属性，因此会输出错误。

```javascript
// 我们将 Math.LN2 视为函数，但它是一个属性，因此会显示错误。
document.write(Math.LN2(12));
```

**输出:**

```
Error: Math.LN2 is not a function
```

**注意:** 请检查控制台以查看错误信息。

## 支持的浏览器

*   Google Chrome
*   Microsoft Edge
*   Firefox
*   Opera
*   Safari