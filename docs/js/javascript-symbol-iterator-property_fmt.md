# JavaScript 符号.迭代器属性

> 原文: [https://www.geeksforgeeks.org/javascript-symbol-iterator-property/](https://www.geeksforgeeks.org/javascript-symbol-iterator-property/)

它是 [Iterables](https://www.geeksforgeeks.org/javascript-iterator/) 的一个对象，也是一种广义数组。使任何对象更容易在 `for...in` 或 `for...of` 循环中使用的。我们知道数组本质上是迭代的，但除此之外，还有几个对象用于迭代目的。假设任何不是数组但拥有一组列表、集合等的对象，其内容可用于迭代它。

我们使用一个 `range` 对象来表示任意区间的范围。它决定了循环将如何工作并迭代。

我们将使用一个方法 `Symbol.iterator`（JavaScript 中的内置方法）来迭代上面提到的 `range` 对象。该方法的工作步骤为：

1.  在第一次循环开始时，它首先检查错误，如果没有发现错误，则使用该方法来访问方法和对象。
2.  为了获取下一个即将到来的值，它为输出对象调用 `next()` 方法。
3.  返回值的形式为 `{done: Boolean, value: any}`。当 `done=true` 返回时，循环将被视为完成。

**语法：**

```
[Symbol.iterator]
```

## 特点

*   该 `range` 对象本身不会有 `next()` 方法。
*   当我们调用 `range[Symbol.iterator]()` 时，就形成了一个迭代器，`next()` 方法将为进一步的迭代生成该值。

**例：**

## Javascript

```javascript
let range = {
  from: 2,
  to: 7
};

range[Symbol.iterator] = function() {

  return {
    now: this.from,
    end: this.to,
    next() {
      if (this.now <= this.end) {
        return { done: false, value: this.now++ };
      } else {
        return { done: true };
      }
    }
  };
};

for (let i of range) {
  console.log(i); 
}
```

**输出：**

```
2
3
4
5
6
7
```