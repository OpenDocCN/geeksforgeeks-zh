# JavaScript 字符串 `@@iterator` 方法

> 原文：`https://www.geeksforgeeks.org/javascript-string-iterator-method/`

字符串的 `@@iterator()` 方法用于使字符串可迭代。`@@iterator()` 返回一个迭代器对象，该对象迭代字符串的所有代码点。`String.prototype[@@iterator]` 是字符串的内置属性。

我们可以通过创建一个字符串迭代器来使用这个方法。我们可以通过调用 `String` 的 `@@iterator` 属性来创建一个迭代器。我们用 `Symbol.iterator` 常量代替 `@@iterator`。

## 语法

```
// Test String
var str = "String";

// iterator to String
var iter = str[Symbol.iterator]();
```

我们可以用 `next()` 获取迭代器对象。它返回带有 `value` 和 `done` 键的对象。`value` 键保存真实的迭代值字符串，`done` 键保存 `true` 或 `false`，如果迭代完成，则保持 `true`，否则保持 `false`。我们可以通过 `iter.value` 和 `iter.done` 来获取对象的值。

## 示例 1

下面是说明使用上述方法的代码。

### JavaScript

```
<script>
  const str = 'GFG';
  const iterator = str[Symbol.iterator]();
  let theChar = iterator.next();

  for(let i = 0; i < str.length ;i++) {
    console.log(theChar.value , theChar.done);
    theChar = iterator.next();
  }
</script>
```

**输出：**

```
"G" false
"F" false
"G" false
```

我们可以使用 `@@iterator` 方法，而不用通过使用 `for...of` 循环来分配迭代器，通过使用 `@@iterator` 方法来迭代数据的过度收集。在循环调用 `next()` 的每次迭代中。值在集合中迭代。

## 示例 2

下面是说明使用上述方法的代码。

### JavaScript

```
<script>
  const str = 'GFG';
  const iterator = str[Symbol.iterator]();
  let theChar = iterator;

  for(let i = 0; i < str.length ;i++)
  {
      console.log(theChar.next().value );
  }

  // Using for-of loop
  console.log("Iterating by for-of loop :")
  for(let i of str)
  {
      console.log(i)
  }
</script>
```

**输出：**

```
"G"
"F"
"G"
Iterating by for-of loop  :
"G"
"F"
"G"
```