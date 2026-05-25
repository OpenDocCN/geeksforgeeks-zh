# JavaScript `Object.prototype.__defineSetter__()` 方法

> 原文：[https://www.geeksforgeeks.org/javascript-object-prototype-__definesetter__-method/](https://www.geeksforgeeks.org/javascript-object-prototype-__definesetter__-method/)

`__defineSetter__()` 方法用于将对象的属性绑定到一个函数，当试图设置指定的属性时，该函数将被调用。建议使用对象初始化语法或 `Object.defineProperty()` API 来代替此方法，因为它已被弃用。

## 语法

```
obj.__defineSetter__(prop, fun)
```

## 参数

该函数接受两个参数，如下所述：

*   `prop`：它是一个字符串，包含要绑定到给定函数的属性的名称。
*   `fun`：是试图设置指定属性时要调用的函数。该函数的 `value` 参数可用于指定变量的别名，该变量保存试图分配给 `prop` 的值。

## 返回值

该方法返回 `undefined`。

以下示例说明了 `__defineSetter__()` 方法的用法：

### 示例 1：使用 `__defineSetter__()` 方法

```javascript
let tmpObj = {};
tmpObj.__defineSetter__('setValue', function(val) {
    this.currentValue = val;
});

obj.setValue = 10;
console.log(tmpObj.setValue);
console.log(tmpObj.currentValue);
```

**输出：**

```
undefined
```

### 示例 2：使用符合标准的方式，使用对象初始化器语法和 `Object.defineProperty()` API

```javascript
// Using the set operator
var obj1 = {
    set setValue(val) { this.currentValue = val; }
};

obj1.setValue = 10;
console.log(obj1.setValue);
console.log(obj1.currentValue);

// Using Object.defineProperty
var obj2 = {};
Object.defineProperty(obj2, 'value', {
  set: function(val) {
    this.currentValue = val;
  }
});
obj2.value = 2;
console.log(obj2.value);
console.log(obj2.currentValue);
```

**输出：**

```
undefined
undefined
```