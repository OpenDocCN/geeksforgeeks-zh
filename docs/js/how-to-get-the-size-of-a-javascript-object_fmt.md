# 如何获取一个 JavaScript 对象的大小？

> 原文: [https://www.geeksforgeeks.org/how-to-get-the-size-of-a-javascript-object/](https://www.geeksforgeeks.org/how-to-get-the-size-of-a-javascript-object/)

借助 [`Object.keys()`](https://www.geeksforgeeks.org/object-keys-javascript/) 方法，我们可以得到 JavaScript 对象的大小。

## 语法

```
Object.keys(object_name)
```

## Parameter

*   `object_name`

## 返回值

对象自身所有可枚举属性键的数组。

## Approach-1

1.  创建一个对象变量并为其赋值。
2.  创建一个显示大小的变量。
3.  调用 `Object.keys(object_name).length`，并将其分配给变量（在步骤 2 中）。

### 示例-1

通过 `Object.keys()` 方法获取 JavaScript 对象的大小。

```html
<script>
var object1 = {
    "rajnish": "singh",
    "sanjeev": "sharma",
    "suraj": "agrahari",
    "yash": "khandelwal"
};
var count = Object.keys(object1).length;
document.write(count);
</script>
```

```
Output: 4
```

获取 JavaScript 对象大小的另一种方法是：

## Approach-2

1.  创建一个对象变量并为其赋值。
2.  创建一个显示大小的变量。
3.  将对象名传递给 `Object.objsize`，`Object.objsize` 再输入到计算并返回大小的函数中，并将其赋给变量。

```html
<script>
Object.objsize = function(obj) {
    var size = 0, key;
    for (key in obj) {
        if (obj.hasOwnProperty(key))
            size++;
    }
    return size;
};

var object1 = {
    "rajnish": "singh",
    "sanjeev": "sharma",
    "suraj": "agrahari",
    "yash": "khandelwal"
};

var count = Object.objsize(object1);
document.write(count);
</script>
```

```
Output: 4
```