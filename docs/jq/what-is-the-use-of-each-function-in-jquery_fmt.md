# jQuery 中的 `$.each()` 函数有什么用？

> 原文: [https://www.geeksforgeeks.org/what-is-the-use-of-each-function-in-jquery/](https://www.geeksforgeeks.org/what-is-the-use-of-each-function-in-jquery/)

jQuery 中的 `$.each()` 函数分别遍历对象和数组。具有 `length` 属性的数组从索引 `0` 遍历到 `length-1`，而像对象这样的非数组集合则通过它们的属性名遍历。

**语法:**

```html
$.each('array or object', function(index, value){
  // Your code
})
```

在这里，`$.each()` 函数中，数组或对象作为第一个参数，一个回调函数作为第二个参数给出。这个回调函数可选地接受两个参数：`index` 和 `value`。因此，我们必须向 `$.each()` 方法传递一个回调函数。

**例 1:**

## HTML 示例

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- using jquery library -->
    <script src=
"https://code.jquery.com/jquery-git.js">
    </script>
</head>

<body>
  <script>
    let arr = [10, 20, 30, 40, 50];
    $.each(arr, function (index, value) {
        document.write(index + ": " + value + "<br>");
    });
  </script>
</body>

</html>
```

**输出:**

![](img/ca4ec2c93f95a6435434bc779974312f.png)

**`$(selector).each()`:** 我们也可以通过回调函数返回 `false` 来提前打破循环。它与上面的 `$.each()` 函数功能相似，但是它专门用于遍历 jQuery 对象的 DOM 元素，并且可以为每个元素执行一个函数。

**语法:**

```html
$('selector').each(function(index, value){
    // Your code
})
```

它只接受一个回调函数，该函数会为每个选定的元素执行。

**示例:**

## HTML 示例

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- using jquery library -->
    <script src=
"https://code.jquery.com/jquery-git.js">
    </script>
</head>

<body>
    <p>para-1</p>
    <p>para-2</p>
    <p>para-3</p>
    <p>para-4</p>
    <p>para-5</p>
    <script>
        $("p").each(function (index) {
            console.log(index 
                + ": " + $(this).text());
        });
    </script>
</body>

</html>
```

**输出:**

![](img/3e8cd1224d04140fb61fb4e35e7fcc34.png)