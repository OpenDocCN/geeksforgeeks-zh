# JavaScript Object.getOwnPropertyNames()方法

> 原文: [https://www.geeksforgeeks.org/javascript-object-getownpropertynames-method/](https://www.geeksforgeeks.org/javascript-object-getownpropertynames-method/)

JavaScript 中的 `Object.getOwnPropertyNames()` 方法是标准的内置对象方法，它返回给定对象中存在的所有属性。

## 语法

```
Object.getOwnPropertyNames(obj)
```

## 参数

该方法接受如上所述的单个参数，描述如下:

*   `obj`: 此参数保存要返回其可枚举和不可枚举属性的对象。

## 返回值

该方法返回一个字符串数组，该数组对应于直接在给定对象中找到的属性。

以下示例说明了 JavaScript 中的 `Object.getOwnPropertyNames()` 方法:

### 示例 1

```javascript
const gfg = {
  val1: "Geek1",
  val2: "Geek2",
  val3: "Geek3",
  val4: "Geek4"
};
console.log(Object.getOwnPropertyNames(gfg));

var gfg2 = { val1: 'Geek1', val2: 'Geek2', val3: 'Geek3' }; 
console.log(Object.getOwnPropertyNames(gfg2).sort());

Object.getOwnPropertyNames(gfg2).
        forEach(function(val, idx, array) { 
  console.log(val + ' -> ' + gfg2[val]);

});
```

**输出:**

```
Array ["val1", "val2", "val3", "val4"]
Array ["val1", "val2", "val3"]
"val1 -> Geek1"
"val2 -> Geek2"
"val3 -> Geek3"
```

### 示例 2

```javascript
function ParentClass() {}
ParentClass.prototype.inheritedMethod = function() {};

function ChildClass() {
  this.prop = 5;
  this.method = function() {};
}
ChildClass.prototype = new ParentClass;
ChildClass.prototype.prototypeMethod = function() {};

console.log(
  Object.getOwnPropertyNames(
    new ChildClass()
  )
);

var my_obj = Object.create({}, {
  getFoo: {
    value: function() { return this.foo; },
    enumerable: false
  }
});
my_obj.foo = 1;

console.log(Object.getOwnPropertyNames(my_obj).sort());
```

**输出:**

```
Array ["prop", "method"]
Array ["foo", "getFoo"]
```

## 支持的浏览器

`Object.getOwnPropertyNames()` 方法支持的浏览器如下:

*   Google Chrome 5.0 及以上版本
*   Edge 12 及以上
*   Firefox 4 及以上版本
*   Internet Explorer 9.0 及以上版本
*   Mozilla 4.0 及以上版本
*   Opera 12 及以上
*   Safari 5.0 及以上版本