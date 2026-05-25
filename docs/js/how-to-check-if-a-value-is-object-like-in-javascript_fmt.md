# 如何在 JavaScript 中检查一个值是否像对象？

> 原文: [https://www.geeksforgeeks.org/how-to-check-if-a-value-is-object-like-in-javascript/](https://www.geeksforgeeks.org/how-to-check-if-a-value-is-object-like-in-javascript/)

在 JavaScript 中，对象是相关数据的集合。它也是名称-值对的容器。在 JavaScript 中，我们可以通过多种方式检查值类型。基本上，我们使用 `typeof`、`instanceof`、`constructor` 和 `Object.prototype.toString.call()` 来检查一个值是否像对象。所有的运算符都用于某些特定的条件。

## `typeof` 运算符

这是用来识别变量的类型。它返回一个变量类型。这是检查变量类型的最简单方法。它适用于某些变量，但它没有确定变量的确切类型。

**条件：** 它将数组、集合和 `null` 视为与对象相同。`typeof` 返回所有这些的 `object`。在变量的情况下，除了三个之外，使用 `typeof`。

*   **语法：**

```
typeof VariableName;
```

*   **示例：**

```javascript
<script>
let k = {Name:'gfg',Country:'India'};
let k0 = new Set()
let k1 = [1,2,3];
let k2 = "hello";
let k3 = null ;
let k4 = undefined;

console.log( typeof k )
console.log( typeof k0 )
console.log( typeof k1 )
console.log( typeof k2 )
console.log( typeof k3 )
console.log( typeof k4 )
</script>
```

**输出：**

```
object
object
object
string
object
undefined
```

## `instanceof` 运算符

用于检查某个实例是否由某个构造函数生成。如果是用构造函数做的，则返回 `true`，否则返回 `false`。它只适用于那些包装在常规对象类型中的对象。

**条件：** 它将数组作为对象来处理和 `Set`。所以我们可以对除这两个值之外的所有值使用 `instanceof` 运算符。

*   **语法：**

```
Variable instanceof Object;
```

*   **示例：**

```javascript
<script>
let k = {Name:'gfg',Country:'India'};
let k0 = new Set()
let k1 = [1,2,3];
let k2 = "hello";
let k3 = null ;
let k4 = undefined;

console.log( k instanceof Object)
console.log( k0 instanceof Object)
console.log( k1 instanceof Object)
console.log( k2 instanceof Object)
console.log( k3 instanceof Object)
console.log( k4 instanceof Object)
</script>
```

**输出：**

```
true
true
true
false
false
false
```

## `constructor` 属性

这是指向该对象的基本对象构造函数类型的变量的属性。我们可以检查那些具有 `constructor` 属性的变量。

**条件：** `constructor` 方法对于没有 `constructor` 属性的变量抛出错误。`null` 和 `undefined` 没有 `constructor` 属性，所以抛出错误。

*   **语法：**

```
Variable.constructor === Object
```

*   **示例：**

```javascript
<script>
let k = {Name:'gfg',Country:'India'};
let k0 = new Set()
let k1 = [1,2,3];
let k2 = "hello";

console.log( k.constructor === Object)
console.log( k0.constructor === Object)
console.log( k1.constructor === Object)
console.log( k2.constructor === Object)
</script>
```

**输出：**

```
true
false
false
false
```