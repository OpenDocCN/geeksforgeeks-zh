# JavaScript `Object.prototype.__lookupSetter__()` 方法

> 原文: [https://www.geeksforgeeks.org/javascript-object-prototype-__lookupsetter__-method/](https://www.geeksforgeeks.org/javascript-object-prototype-__lookupsetter__-method/)

JavaScript `Object.prototype.__lookupSetter__()` 方法用于在为对象的属性定义 setter 函数时获取对该函数的引用。无法通过该属性引用 setter 函数，因为它引用了函数的返回值。它返回作为 setter 绑定到指定属性的函数。

## 语法

`o.__lookupSetter__(P)`

## 术语

*   `o`: 指对象（此值）。对象接受参数值。它将参数转换为对象值。
*   `P`: 指从属性（`P`）生成的字符串键。它指的是应该由 setter 返回的属性的名称。

## 返回值

*   如果对象 `O` 为空或 `IsAccessorDescriptor` 为 `false`，则返回 `undefined`。
*   如果对象 `O` 不为空，且 `IsAccessorDescriptor` 为 `true`，则返回绑定到指定属性作为 setter 的函数。

## 示例 1

它返回一个名为 `gfg()` 的函数。

```javascript
<script>
const gfgObject = {
  set gfg(arg) {
    this.portalName = arg;
    console.log(portalName)
  }
};

const gfgFunction = gfgObject.__lookupSetter__('gfg')
gfgFunction("GeeksforGeeks");
</script>
```

**输出:**

```
GeeksforGeeks
```

Web 标准不再推荐此功能。虽然它仍然受到一些浏览器的支持，比如谷歌 Chrome，但它正在被淘汰。它不应该用于任何新的或旧的项目。依赖它的页面或网络应用程序随时都有可能失败。

建议使用 `Object.getOwnPropertyDescriptor()`。设置，取两个参数。

*   谁应该查找属性。
*   要从中检索描述的属性的名称。

**注意:** 返回作为属性设置器的函数，如果没有设置器则返回 `undefined`。

## 示例 2

```javascript
<script>
const gfgObject = {
  set gfg(arg) {
    this.portalName = arg;
    console.log(portalName)
  }
};
const gfgFunction =
  Object.getOwnPropertyDescriptor(gfgObject,"gfg").set
gfgFunction("GeeksforGeeks");
</script>
```

**输出:**

```
GeeksforGeeks
```

## 支持的浏览器

*   Google Chrome
*   Internet Explorer
*   Firefox

**注意:** 此功能已被弃用，不再推荐。