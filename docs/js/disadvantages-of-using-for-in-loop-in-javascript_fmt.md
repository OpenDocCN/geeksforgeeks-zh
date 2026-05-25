# JavaScript 中 for...in 循环的缺点

> 原文: [https://www.geeksforgeeks.org/disadvantages-of-using-for-in-loop-in-javascript/](https://www.geeksforgeeks.org/disadvantages-of-using-for-in-loop-in-javascript/)

在本文中，我们将看到使用 `for..in` 循环的缺点是什么以及如何解决那些问题。

## for..in 循环的缺点

**原因 1:** 当你使用原型在数组或对象中添加一个与该属性无关的属性时，例如 `arr`，当你迭代数组 `x` 时，你也会得到该属性。

**示例:** 您在数组中添加了属性 `myCustomProp`。

**语法:**

```javascript
Array.prototype.myCustomProp = "Hello World";
```

现在创建一个数组 `x` 并给它赋值，然后遍历 `for..in` 循环。

### JavaScript

```javascript
<script>
  // Adding property using myCustomProp
  Array.prototype.myCustomProp = "Hello World";

  let arr = [1, 2, 3, 4, 5];

  // Iterating using for..in loop
  for (var index in arr) {
    console.log(arr[index]);
  }
</script>
```

**输出:**

```
1
2
3
4
5
Hello World
```

**解决方法:** 你可以使用 `hasOwnProperty()` 方法来解决这个问题。

### JavaScript

```javascript
<script>
  // Adding property using myCustomProp
  Array.prototype.myCustomProp = "Hello World";

  let arr = [1, 2, 3, 4, 5];

  // Iterating using for..in loop
  for (var index in arr) {
    // Checking if the item is present in arr or not
    if (arr.hasOwnProperty(index)) {
      console.log(arr[index]);
    }
  }
</script>
```

**输出:**

```
1
2
3
4
5
```

**原因 2:** `for..in` 循环会忽略数组的未定义值。假设你创建了一个空数组 `arr` 并给 `arr[0]`、`arr[3]`、`arr[5]` 分配了一些项目，这意味着 `arr[1]`、`arr[2]`、`arr[4]` 是 `undefined`，但是 `for..in` 循环会忽略它们。

**示例:**

### JavaScript

```javascript
<script>
  let arr = [];

  arr[0] = "A";
  arr[3] = "D";
  arr[5] = "F";

  console.log("Using for loop");

  for (var i = 0; i < arr.length; i++) {
    // "A", undefined, undefined, "D", undefined, "F"
    console.log(arr[i]);
  }

  console.log("Using for..in loop");

  for (var index in arr) {
    // "A", "D", "F"
    console.log(arr[index]);
  }
</script>
```

**输出:**

*   **for 循环:**

    ```
    A
    undefined
    undefined
    D
    undefined
    F
    ```

*   **for..in 循环:**

    ```
    A
    D
    F
    ```

一个简单的 `for` 循环会打印数组的所有元素，包括 `undefined`，但 `for..in` 循环会忽略所有 `undefined` 的值。但是，这仅适用于值未定义的数组，但是当 `undefined` 明确存在于数组中时，`for..in` 循环则不会忽略它们。

### JavaScript

```javascript
<script>
  let arr = [undefined, undefined, undefined, "Hello world"];

  for (var index in arr) {
    console.log(arr[index]);
  }
</script>
```

**输出:**

```
undefined
undefined
undefined
Hello World
```