# `Intl.Collator.supportedLocalesOf()` 方法

> 原文：[https://www.geeksforgeeks.org/javascript-intl-collator-supportedlocalesof-method/](https://www.geeksforgeeks.org/javascript-intl-collator-supportedlocalesof-method/)

`Intl.Collator.supportedLocalesOf()` 方法是 JavaScript 中的一个内置方法，用于返回一个数组，该数组包含排序规则中支持的那些提供的区域设置，而不必返回到运行时的默认区域设置。

**语法：**

```
Intl.Collator.supportedLocalesOf(locales, options)
```

**参数：** 该方法接受两个参数，如上所述，如下所述：

*   `locales`：该参数是一个带有 BCP 47 语言标记的字符串，或者是这种字符串的数组。
*   `options`：为可选参数。它是一个具有 `localeMatcher` 属性的对象。`localeMatcher` 是要使用的区域设置匹配算法。它的值是 `"lookup"` 和 `"best fit"`。

**返回值：** 这个方法返回一个字符串数组，代表给定区域设置标签的子集。

下面的例子说明了 JavaScript 中的 `Intl.Collator.supportedLocalesOf()` 方法：

**示例 1：**

```javascript
const locales1 = ['ban', 'id-u-co-pinyin', 'de-ID'];
console.log(Intl.Collator.supportedLocalesOf(locales1));
```