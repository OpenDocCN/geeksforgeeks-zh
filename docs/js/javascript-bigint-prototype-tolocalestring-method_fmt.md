# JavaScript BigInt.prototype.toLocaleString()方法

> 原文：[https://www.geeksforgeeks.org/javascript-bigint-prototype-tolocalestring-method/](https://www.geeksforgeeks.org/javascript-bigint-prototype-tolocalestring-method/)

`BigInt.prototype.toLocaleString()`方法是 JavaScript 中的一个内置方法，用于返回一个字符串，该字符串具有该 BigInt 的语言敏感表示。

## 语法

```
bigIntObj.toLocaleString(locales, options)
```

## 参数

该方法接受两个参数，如下所述：

*   `locales`：此参数保存地区的值。
*   `options`：为可选参数。

## 返回值

该方法返回一个字符串，该字符串具有给定 BigInt 的语言敏感表示。

下面的例子说明了 JavaScript 中的 `BigInt.prototype.toLocaleString()` 方法：

### 例子 1

```javascript
let geekvar = 45334n;
console.log(geekvar.toLocaleString());

geekvar = 78753456789123456789n;
console.log(geekvar.toLocaleString('de-DE'));
console.log(geekvar.toLocaleString('de-DE',
    { style: 'currency', currency: 'EUR' }));
console.log(geekvar.toLocaleString('hi'));
```