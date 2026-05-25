# JavaScript Map.prototype[@@iterator]() 方法

> 原文：[https://www.geeksforgeeks.org/javascript-map-prototypeiterator-method/](https://www.geeksforgeeks.org/javascript-map-prototypeiterator-method/)

`Map[@@iterator]()` 方法用于使 `Map` 可迭代。`Map[@@iterator]()` 方法返回迭代器对象，该对象遍历 Map 的所有代码点。`Map[@@iterator]` 是 `Map` 的内置属性。

我们可以通过创建 `Map` 迭代器来使用这个方法。我们可以通过调用 `@@iterator` 属性来制作 `Map` 迭代器。代替 `@@iterator`，我们可以使用 `Symbol.iterator` 常量。

**语法：**

```
const iter = Map[Symbol.iterator]();
```

**参数：** 该属性不接受任何参数。
**返回值：** 它返回一个迭代器来迭代迭代器对象的代码点。

**示例：**

## JavaScript

```
<script>
    const m = new Map();
    m.set(0, "a")
    m.set(2, "b")
    m.set(3, "c")
    const iterator = m[Symbol.iterator]();
    let itr = iterator.next()
    for (let i = 0; i < m.size; i++) {
        console.log(itr.value, itr.done)
        itr = iterator.next()
    }
</script>
```

**输出：**

```
[0 : 'a'] false
[1 : 'b'] false
[2 : 'c'] false
```

**示例：** 我们可以使用 `Map.prototype[@@iterator]` 方法，将 `Map` 分配给迭代器。我们可以使用 `for` 循环迭代地图的代码点。`for-of` 循环使用迭代器来迭代映射的值。

## JavaScript

```
<script>
    const m = new Map();
    m.set(0, "a")
    m.set(2, "b")
    m.set(3, "c")

    const iterator = m[Symbol.iterator]();

    let itr = iterator.next()

    for (let i = 0; i < m.size; i++) {
        console.log(itr.value)
        itr = iterator.next()
    }

    console.log("iterating with for-of loop : ")

    for (let i of m) {
        console.log(i)
    }
</script>
```

**输出：**

```
[0 : 'a']
[1 : 'b']
[2 : 'c']
iterating with for-of loop :
[0 : 'a']
[1 : 'b']
[2 : 'c']
```