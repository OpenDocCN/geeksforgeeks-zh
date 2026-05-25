# JavaScript | Intl.ListFormat.supportedLocalesOf() 方法

> 原文: [https://www.geeksforgeeks.org/javascript-intl-listformat-supportedlocalesof-method/](https://www.geeksforgeeks.org/javascript-intl-listformat-supportedlocalesof-method/)

`Intl.ListFormat.supportedLocalesOf()` 方法是 JavaScript 中的一个内置方法，它返回一个数组，该数组包含日期和时间格式支持的所提供的区域设置。

**语法:**

```
Intl.ListFormat.supportedLocalesOf(locales, options)
```

**参数:** 该方法接受两个参数，如上所述，如下所述:

*   `locales`: 此参数保存一个带有 BCP 47 语言标记的字符串，或此类字符串的数组。
*   `options`: 为可选参数。它是一个具有 `localeMatcher` 属性的对象。`localeMatcher` 是要使用的区域设置匹配算法。它的值是 `"lookup"` 和 `"best fit"`。

**返回值:** 该方法返回一个字符串数组，该数组表示日期和时间格式支持的给定区域设置标签的子集。

下面的例子说明了 `Intl.ListFormat.supportedLocalesOf()` 方法:

**示例 1:**

## JavaScript

```
<script>
const geeks = ['ban', 'id-u-co-pinyin', 'de-ID'];
const result = { localeMatcher: 'lookup' };
let val = Intl.ListFormat.supportedLocalesOf(geeks, result).join(', ');
console.log(val);
</script>
```

**输出:**

```
"id-u-co-pinyin, de-ID"
```

**例 2:**

## JavaScript

```
<script>
const geeks = ['ban', 'id-u-co-pinyin', 'de-ID'];
let val = Intl.ListFormat.supportedLocalesOf(geeks).join(', ');
console.log(val);
</script>
```

**输出:**

```
"id-u-co-pinyin, de-ID"
```

**支持的浏览器:** `Intl.ListFormat.supportedLocalesOf()` 支持的浏览器如下:

*   Google Chrome 72 及以上
*   Edge 79 及以上
*   Firefox 78 及以上版本
*   Opera 60 及以上
*   Safari 14.1 及以上版本