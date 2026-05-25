# JavaScript | Int16Array from()方法

> 原文: [https://www.geeksforgeeks.org/javascript-int16array-from-method/](https://www.geeksforgeeks.org/javascript-int16array-from-method/)

`Int16Array` 数组表示 16 位有符号整数的二进制补码数组。默认情况下，`Int16Array` 的内容被初始化为 0。
`Int16Array.from()` 函数用于从类似数组或可迭代的对象创建新的 `Int16Array`。因此，当您想要将类似数组或可迭代的对象转换为 `Int16Array` 时，您可以使用该函数，方法是将该对象作为参数传递给该函数，如果需要，还可以传递 `mapFn` 函数和 `mapFn` 函数所用的值。

## 语法:

```
Int16Array.from(source[, mapFn[, thisArg]])
```

## 参数:

该方法接受以下指定的三个参数:

1.  `source`: 此参数是一个类似数组或可迭代的对象，用于转换为 `Int16Array` 对象。
2.  `mapFn`: 这个参数是可选的，它是在 `Int16Array` 数组的每个元素上调用的 Map 函数。
3.  `thisArg`: 此参数是可选的，是执行 `mapFn` 时用作 `this` 参数的值。

## 返回值:

这个方法返回一个新的 `Int16Array` 实例。

## 示例1：从类字符串结构创建

JavaScript 程序说明 `from()` 函数的工作原理:

```javascript
<script>
    //create a Int16Array from a string like structure
    var array = Int16Array.from('654456543456');

    //print the result
    document.write(array);
</script>
```

**输出:**

```
6, 5, 4, 4, 5, 6, 5, 4, 3, 4, 5, 6
```

## 示例2：使用映射函数创建

```javascript
<script>
    //create a Int16Array from a array by converting numbers
    //twice the actual number
    var array = Int16Array.from([32, 43, 41, 34], z => z * 2);

    //print the result
    document.write(array);
</script>
```

**输出:**

```
64, 86, 82, 68
```

## 参考文献:

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/from](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/from)