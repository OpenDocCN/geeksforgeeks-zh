# JavaScript 数组 some() 方法

> 原文: [https://www.geeksforgeeks.org/javascript-array-some-method/](https://www.geeksforgeeks.org/javascript-array-some-method/)

下面是`数组 some()`方法的例子。

### 示例

```html
<script>
    function checkAvailability(arr, val) {
        return arr.some(function (arrVal) {
            return val === arrVal;
        });
    }
    function func() {
        // Original function
        var arr = [2, 5, 8, 1, 4];

        // Checking for condition
        document.write(checkAvailability(arr, 2));
        document.write("<br>");
        document.write(checkAvailability(arr, 87));
    }
    func();
</script>
```

### 输出

```
true
false
```

`arr.some()`方法检查数组的至少一个元素是否满足参数方法检查的条件。

### 语法

```
arr.every(callback(element[, index[, array]])[, thisArg])
```

### 参数

该方法接受五个参数，如上所述，如下所述:

*   `回调`: 该参数保存数组每个元素要调用的函数。
*   `元素`: 参数保存当前正在处理的元素的值。
*   `索引`: 这个参数是可选的，它保存数组中从 0 开始的 currentValue 元素的索引。
*   `数组`: 这个参数是可选的，它保存了调用 array . after 的完整数组。
*   `thisArg`: 这个参数是可选的，它保存要传递的上下文，以便在执行回调函数时使用。如果传递了上下文，它将像这样用于回调函数的每次调用，否则使用 undefined 作为默认值。

### 返回值

此方法返回`true`即使数组的一个元素满足参数方法实现的条件(并且不检查剩余值)。如果数组中没有元素满足条件，则返回`false`。

下面的例子说明了 JavaScript 中的方法:

#### 示例 1

在这个例子中，`some()`方法检查是否有任何数字大于`5`。由于存在满足此条件的元素，因此该方法返回`true`。

```javascript
function isGreaterThan5(element, index, array) 
{
  return element > 5;
}

print([2, 5, 8, 1, 4].some(isGreaterThan5));
```

**输出:**

```
true
```

#### 示例 2

在这个例子中，`some()`方法检查是否有任何数字大于`5`。由于没有元素满足此条件，因此该方法返回`false`。

```javascript
function isGreaterThan5(element, index, array) 
{
  return element > 5;
}

print([-2, 5, 3, 1, 4].some(isGreaterThan5));
```

**输出:**

```
false
```

#### 示例 3

在这个例子中，`some()`方法检查数组中是否存在`2`和`87`。由于只有`2`存在，因此该方法对第一个查询返回`true`，对第二个查询返回`false`。

```javascript
var arr = [2, 5, 8, 1, 4]

function checkAvailability(arr, val) 
{
  return arr.some(
           function(arrVal) 
           {
             return val === arrVal;
           } );
}

print(checkAvailability(arr, 2));
print(checkAvailability(arr, 87));
```

**输出:**

```
true
false
```

上述方法的代码如下:

### 程序 1

```html
<script>
    function isGreaterThan5(element, index, array) {
        return element > 5;
    }
    function func() {
        // Original array
        var array = [2, 5, 8, 1, 4];

        // Checking for condition in array
        var value = array.some(isGreaterThan5);

        document.write(value);
    }
    func();
</script>
```

**输出:**

```
true
```

### 程序 2

```html
<script>
    function isGreaterThan5(element, index, array) {
        return element > 5;
    }

    function func() {
        // Original array
        var array = [-2, 5, 3, 1, 4];

        // Checking for condition in the array
        var value = array.some(isGreaterThan5);

        document.write(value);
    }

    func();
</script>
```

**输出:**

```
false
```

### 支持的浏览器

JavaScript`Array some()`方法支持的浏览器如下:

*   谷歌 Chrome 1 以上
*   边缘 12 及以上
*   Firefox 1.5 及以上版本
*   Internet Explorer 9 及以上版本
*   Opera 9.5 及以上
*   Safari 3 及以上版本