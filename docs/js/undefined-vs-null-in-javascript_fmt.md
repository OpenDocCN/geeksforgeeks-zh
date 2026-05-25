# JavaScript 中 undefined 与 null 的区别

> 原文：[https://www.geeksforgeeks.org/undefined-vs-null-in-javascript/](https://www.geeksforgeeks.org/undefined-vs-null-in-javascript/)

`null` 和 `undefined` 之间有几个区别，它们有时被理解为相同的。

## 1. 定义

- **`null`**：表示值的有意缺失。它是 JavaScript 的基本值之一。
- **`undefined`**：表示编译器中不存在该值。它是全局对象的属性。

## 2. 类型

- **`null`**：对象
- **`undefined`**：未定义

## 3. 相等性比较

可以参考[等于（`==`）与全等（`===`）运算符](https://www.geeksforgeeks.org/javascript-vs-comparision-operator/)一文。

```javascript
null == undefined // true
null === undefined // false
```

意思是 `null` 等于 `undefined` 但不全等（类型不同）。

## 4. 语义区别

当我们将一个变量定义为 `undefined` 时，我们试图传达该变量尚未被赋值。
当我们将一个变量定义为 `null` 时，我们试图传达这个变量是有意被设置为空值。

## 5. 使用 `isNaN()` 进行区分

大家可以参考 [NaN](https://www.geeksforgeeks.org/number-isnan-javascript/) 一文进行更好的理解。

```javascript
isNaN(2 + null)      // false
isNaN(2 + undefined) // true
```

## 6. 示例

- **`null`**：

```javascript
null ? console.log("true") : console.log("false") // false
```

`null` 在布尔上下文中被视为假值。

- **`undefined`**：

当变量没有赋值时：

```javascript
var temp;
if(temp === undefined)
    console.log("true");
else
    console.log("false");
```

**输出：**

```
true
```

访问不存在的数组元素：

```javascript
var temp = ['a', 'b', 'c'];
if(temp[3] === undefined)
    console.log("true");
else
    console.log("false");
```

**输出：**

```
true
```