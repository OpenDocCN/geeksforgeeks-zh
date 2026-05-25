# Intl.Collator.prototype.resolvedOptions() 方法

> 原文：[https://www.geeksforgeeks.org/javascript-intl-collator-prototype-resolvedoptions-method/](https://www.geeksforgeeks.org/javascript-intl-collator-prototype-resolvedoptions-method/)

`Intl.Collator.prototype.resolvedOptions()` 方法是 JavaScript 中的内置方法，用于返回一个新对象，该对象的属性反映了在初始化此 `Collator` 对象期间计算的区域设置和排序规则选项。

## 语法

```
collator.resolvedOptions()
```

## 参数

此方法不接受任何参数。

## 返回值

此方法返回一个新对象，其属性反映了在给定排序规则对象初始化期间计算的区域设置和排序规则选项。

以下示例说明了 `Intl.Collator.prototype.resolvedOptions()` 方法在 JavaScript 中的用法：

## 示例 1

```javascript
var vall = new Intl.Collator('de', { sensitivity: 'base' })
var geek = vall.resolvedOptions();

console.log(geek.locale);          
console.log(geek.usage);       
console.log(geek.sensitivity);  
console.log(geek.ignorePunctuation);
console.log(geek.collation);        
console.log(geek.numeric);
```

**输出：**

```
"de"
"sort"
"base"
false
"default"
false
```

## 示例 2

```javascript
let geek = new Intl.Collator('de-DE');
let geek1 = new Intl.Collator('ar');
let geek2 = new Intl.Collator('hi');
let val1 = geek.resolvedOptions();
let val2 = geek1.resolvedOptions();
let val3= geek2.resolvedOptions();
console.log(val1.sensitivity);
console.log(val2.collation);
console.log(val3.numeric);
```

**输出：**

```
"variant"
"default"
false
```

## 支持的浏览器

`Intl.Collator.prototype.resolvedOptions()` 方法支持的浏览器如下：

*   Google Chrome 24 及以上版本
*   Firefox 29 及以上版本
*   Opera 15 及以上
*   Edge 12 及以上
*   IE 11 及以上
*   Safari 10 及以上