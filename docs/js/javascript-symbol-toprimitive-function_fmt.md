# JavaScript Symbol.toPrimitive() 函数

> 原文：`https://www.geeksforgeeks.org/javascript-symbol-toprimitive-function/`

`Symbol[Symbol.toPrimitive]()` 是 JavaScript 中的一个内置函数，用于*将给定的 Symbol 对象转换为一个原始值*。

## 语法：

```
Symbol()[Symbol.toPrimitive](hint);
```

这里 `Symbol()` 是要找到原始值的 Symbol 对象。

## 参数：

该函数接受可选参数 `hint`。

## 返回值：

该函数返回给定 Symbol 对象的原始值。

显示该函数工作情况的 JavaScript 代码。

## 例-1：

```
<script>
    // 创建一些 Symbol 对象
    const symbol1 = Symbol('Geeks');
    const symbol2 = Symbol("Geeks");
    const symbol3 = Symbol(123);
    const symbol4 = Symbol();

    // 调用 Symbol[Symbol.toPrimitive]() 函数
    var result1 = symbol1[Symbol.toPrimitive]("Value");
    var result2 = symbol2[Symbol.toPrimitive]("String");
    var result3 = symbol3[Symbol.toPrimitive](789);
    var result4 = symbol4[Symbol.toPrimitive]();

    // 获取原始值
    console.log(result1);
    console.log(result2);
    console.log(result3);
    console.log(result4);
</script>
```

## 输出：

```
> Symbol(Geeks)
> Symbol(Geeks)
> Symbol(123)
> Symbol()
```

在上面的代码中，可以看到可选参数 `hint` 可以是 `"value"`、`"string"`、任意整数值等。

## 示例-2：

```
<script>
    // 创建一个 Symbol 对象
    const symbol = Symbol('gfg');

    // 调用 Symbol[Symbol.toPrimitive]() 函数
    var result = symbol[Symbol.toPrimitive];

    // 获取原始值
    console.log(result);
</script>
```

## 输出：

```
> function [Symbol.toPrimitive]() { [native code] }
```

在上面的代码中，可以看到括号应该用于 `hint` 参数，否则它会给出类似上面输出的结果。

## 支持的浏览器：

*   Google Chrome 47 及以上
*   Firefox 44
*   Edge 15 及以上
*   Opera 34 及以上
*   Apple Safari 10 及以上版本

## 参考：

`https://devdocs.io/javascript/global_objects/symbol/@@toprimitive`