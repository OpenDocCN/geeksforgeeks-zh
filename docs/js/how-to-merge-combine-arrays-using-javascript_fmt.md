# 如何使用 JavaScript 合并/组合数组？

> 原文: [https://www.geeksforgeeks.org/how-to-merge-combine-arrays-using-javascript/](https://www.geeksforgeeks.org/how-to-merge-combine-arrays-using-javascript/)

JavaScript 中有很多合并数组的方法。我们将讨论在合并数组时经常遇到的两个问题陈述：

1.  合并而不删除重复的元素。
2.  删除重复元素后合并。

## 合并而不删除重复元素

我们首先从三个数组开始合并。稍后，我们将把它推广到不定数量的数组。

这三个数组声明如下：
`let nums1 = [1, 2, 3, 4]`
`let nums2 = [3, 4, 5, 6]`
`let nums3 = [5, 6, 7, 8]`

我们必须合并它们，这样我们的新数组就变成：

```
combinedNums = [1, 2, 3, 4, 3, 4, 5, 6, 5, 6, 7, 8]
```

### 1. 使用 `concat()` 方法

`concat()` 方法接受数组作为参数并返回合并后的数组。

```javascript
<script>
    // nums2 和 nums3 的元素被连接到 nums1 的元素上，并返回合并后的数组 - combinedNums 数组
    let combinedNums = nums1.concat(nums2, nums3);

    // 更易读的形式
    let combinedNums = [].concat(nums1, nums2, nums3);

    console.log(combinedNums);
</script>
```

**输出：**

```
[1, 2, 3, 4, 3, 4, 5, 6, 5, 6, 7, 8]
```

### 2. 使用扩展运算符

[扩展运算符](https://www.geeksforgeeks.org/javascript-spread-operator/) 将数组的值展开为其组成元素。

```javascript
<script>
    let combinedNums = [...nums1, ...nums2, ...nums3];

    console.log(combinedNums);
</script>
```

**输出：**

```
[1, 2, 3, 4, 3, 4, 5, 6, 5, 6, 7, 8]
```

### 3. 使用 `push()` 方法

`push()` 方法与扩展运算符一起使用，将数组的元素推入现有数组。当我们需要向现有数组追加值而不需要返回新数组时，这尤其有用。

**注意：** 如果不使用扩展运算符，则数组作为一个整体被追加。

```javascript
<script>
    nums1.push(...nums2, ...nums3);
    console.log(nums1);

    // 如果不使用扩展运算符
    nums1.push(nums2, nums3);
    console.log(nums1);
</script>
```

**输出：**

```
first log: [1, 2, 3, 4, 3, 4, 5, 6, 5, 6, 7, 8]
second log: [1, 2, 3, 4, [3, 4, 5, 6], [5, 6, 7, 8]]
```

我们现在将**推广**这一点，用于合并不定数量的数组：
我们的函数 `mergeArrays` 接受任意数量的数组作为参数（[rest](https://www.geeksforgeeks.org/javascript-rest-operator/) 运算符）。我们将使用 [forEach](https://www.geeksforgeeks.org/javascript-array-foreach/) 循环遍历每个数组，并将其添加到我们的最终数组 `mergedArray` 中。

下面是使用 `concat`、扩展运算符和 `push` 方法的实现：

#### 使用 `array.concat()` 方法

```javascript
<script>
    let nums1 = [1, 2, 3, 4];
    let nums2 = [3, 4, 5, 6];

    function mergeArrays(...arrays) {
        let mergedArray = [];

        arrays.forEach(array => {
            mergedArray = mergedArray.concat(array)
        });

        return mergedArray;
    }

    console.log(mergeArrays(nums1, nums2));
</script>
```

**输出：**

```
[1, 2, 3, 4, 3, 4, 5, 6]
```

#### 使用扩展运算符

```javascript
<script>
    let nums1 = [1, 2, 3, 4];
    let nums2 = [3, 4, 5, 6];

    function mergeArrays(...arrays) {
        let mergedArray = [];

        arrays.forEach(array => {
            mergedArray = [...mergedArray, ...array]
        });

        return mergedArray;
    }

    console.log(mergeArrays(nums1, nums2));
</script>
```

**输出：**

```
[1, 2, 3, 4, 3, 4, 5, 6]
```

#### 使用 `Array.push()` 方法

```javascript
<script>
    let nums1 = [1, 2, 3, 4];
    let nums2 = [3, 4, 5, 6];

    function mergeArrays(...arrays) {
        let mergedArray = [];

        arrays.forEach(array => {
            mergedArray.push(...array)
        });

        return mergedArray;
    }

    console.log(mergeArrays(nums1, nums2));
</script>
```

**输出：**

```
[1, 2, 3, 4, 3, 4, 5, 6]
```

## 合并和移除重复元素

考虑以下三种方法：

### 1. 使用 `Set` 方法

在这里，我们将 `mergedArray` 的元素展开到我们的 `Set` 中。`Set` 存储唯一项并删除重复项。然后，我们将 `Set` 中的元素展开到一个新数组中，并返回该包含合并后非重复元素的数组。

```javascript
<script>
    let nums1 = [1, 2, 3, 4];
    let nums2 = [3, 4, 5, 6];
    let nums3 = [5, 6, 7, 8];

    function mergeNoDuplicates(...arrays) {
        let mergedArray = [];

        arrays.forEach(array => {
            mergedArray = [...mergedArray, ...array]
        });

        return [...new Set([...mergedArray])];
    }

    console.log(mergeNoDuplicates(nums1, nums2, nums3));
</script>
```

**输出：**

```
[1, 2, 3, 4, 5, 6, 7, 8]
```

### 2. 使用 `filter()` 方法

在这种方法中，我们根据元素在数组中首次出现的位置来过滤 `mergedArray` 的元素。我们借助 [indexOf](https://www.geeksforgeeks.org/javascript-array-indexof/) 方法检查该项是否首次出现。

```javascript
<script>
    let nums1 = [1, 2, 3, 4];
    let nums2 = [3, 4, 5, 6];
    let nums3 = [5, 6, 7, 8];

    function mergeNoDuplicates(...arrays) {
        let mergedArray = [];

        arrays.forEach(array => {
            mergedArray = [...mergedArray, ...array]
        });

        const mergedUnique = mergedArray
            .filter((item, index) => 
                mergedArray.indexOf(item) === index);
        return mergedUnique;
    }

    console.log(mergeNoDuplicates(nums1, nums2, nums3));
</script>
```

**输出：**

```
[1, 2, 3, 4, 5, 6, 7, 8]
```

### 3. 使用 `Array reduce()` 方法

在这种方法中，我们将 `noDuplicates` 数组作为累加器。如果一个项目尚未存在于 `noDuplicates` 数组中，则将其追加到该数组。如果项目已存在，我们只需为下一次迭代返回当前数组。

```javascript
<script>
    let nums1 = [1, 2, 3, 4];
    let nums2 = [3, 4, 5, 6];
    let nums3 = [5, 6, 7, 8];

    function mergeNoDuplicates(...arrays) {
        let mergedArray = [];

        arrays.forEach(array => {
            mergedArray = [...mergedArray, ...array]
        });

        const mergedUnique = mergedArray
           .reduce((noDuplicates, item) => {
            if (noDuplicates.includes(item)) {
                return noDuplicates;
            }
            else {
                return [...noDuplicates, item];
            }
        }, [])

        return mergedUnique;
    }

    console.log(mergeNoDuplicates(nums1, nums2, nums3));
</script>
```

**输出：**

```
[1, 2, 3, 4, 5, 6, 7, 8]
```