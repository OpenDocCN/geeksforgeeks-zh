# JavaScript中unshift()和push()方法有什么区别？

> 原文：[https://www.geeksforgeeks.org/what-is-the-difference-between-unshift-and-push-method-in-javascript/](https://www.geeksforgeeks.org/what-is-the-difference-between-unshift-and-push-method-in-javascript/)

JavaScript [`unshift()`](https://www.geeksforgeeks.org/javascript-array-unshift-method/) 方法与 [`push()`](https://www.geeksforgeeks.org/javascript-array-push-method/) 方法非常相似，但区别在于 `unshift()` 方法在数组的最开始添加元素，而 `push()` 方法在数组的末尾添加元素。

## 两种方法的共同点

这两种方法都用于将元素添加到数组中。

*   这两种方法都通过添加到数组中的元素数量来改变数组的长度。
*   这两种方法都用于增加数组的长度。
*   `unshift()` 和 `push()` 都是数组对象的内置方法。
*   这两种方法都会改变原始数组。
*   这两个方法都返回新添加的元素（或元素数量）。

## Unshift()和Push()的主要区别

略有不同的是，`unshift()` 方法将元素添加到索引0处，通过最终返回数组的长度，所有的值都向后移动了1。`push()` 方法返回从最后一个索引添加新元素后的数组长度。

**例：** 下面是数组 `unshift()` 方法的例子。

## JavaScript 描述语言

```javascript
<script> 
function func() {

    // Original array 
    var array = ["GFG", "Geeks", "for", "Geeks"];

    // Checking for condition in array 
    var value = array.unshift("GeeksforGeeks");

    document.write(value); 
    document.write("<br />"); 
    document.write(array); 
}

func(); 
</script> 
```

**输出：**

```
GeeksforGeeks,GFG,Geeks,for,Geeks
```

**例2：** 下面是数组 `push()` 方法的例子。

## JavaScript 描述语言

```javascript
<script> 
    function func() { 
        var arr = ['GFG', 'gfg', 'g4g'];

        // Pushing the element into the array 
        arr.push('GeeksforGeeks'); 
        document.write(arr);
    } 
    func(); 
</script>
```

**输出：**

```
GFG,gfg,g4g,GeeksforGeeks
```