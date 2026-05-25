# JavaScript `Intl.Collator.prototype.compare()` 方法

> 原文：[https://www.geeksforgeeks.org/javascript-intl-collator-prototype-compare-method/](https://www.geeksforgeeks.org/javascript-intl-collator-prototype-compare-method/)

`Intl.Collator.prototype.compare()` 方法基本上是用来按照 collator 对象的排序顺序对两个字符串进行比较的。

这里 `compare` 函数根据排序器对象的排序顺序给出一个数字作为两个字符串之间的比较结果：如果第一个字符串在第二个字符串之前，则显示一个小于 0 的值；如果第一个字符串在第二个字符串之后，则显示一个大于 0 的值；如果两个参数字符串相等，则显示 0。

## 语法

```
collator.compare(firstString, secondString)
```

## 参数

该方法将两个字符串 `(firstString, secondString)` 作为输入参数进行比较。

## 示例 1

使用 `compare` 函数对数组进行排序，该函数被绑定在排序器（collator）对象上，排序器进一步直接传递给 `Array.prototype.sort()`。

使用 JavaScript 代码演示：

```javascript
var x = ['Geeks', 'Geeksfor', 'GFG', 'courses', 'java'];
var collator = new Intl.Collator('de-u-co-phonebk');

// 使用 collator 的 compare 函数
x.sort(collator.compare);
console.log(x.join(', '));
```

输出：

```
courses, Geeks, Geeksfor, GFG, java
```

## 示例 2

同样使用 `compare` 函数来搜索给定参数字符串之间的匹配字符串。让我们看看如何实现：

使用 JavaScript 代码演示：

```javascript
var x = ['GFG-for-GFG', 'stress', 'Care', 'surprise', 'gfg'];
var collator = new Intl.Collator('fr',
    { usage: 'search', sensitivity: 'base' });

var srch = 'gfg';
var mtchs = x.filter(n => collator.compare(n, srch) === 0);
console.log(mtchs.join(', '));
```

输出：

```
gfg
```