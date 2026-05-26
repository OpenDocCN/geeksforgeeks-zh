# Underscore.js 的 _.tap() 函数

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-tap-function/](https://www.geeksforgeeks.org/underscore-js-_-tap-function/)

**Underscore.js** 是一个 JavaScript 库，它提供了许多有用的函数，这些函数在很大程度上有助于编程，比如映射、过滤、调用等，甚至不使用任何内置对象。

**`_.tap()`函数**是 JavaScript 的 Underscore.js 库中的一个内置函数，用来调用带有声明对象的拦截器。而且，这个方法的主要目的是“*把*敲入”一个方法链，这样它就可以对中间结果进行链内操作。

## 语法

```javascript
_.tap(object, interceptor)
```

## 参数

接受以下指定的两个参数:

*   `object`: 是陈述的对象。
*   `interceptor`: 就是要调用的函数。

## 返回值

该方法返回 `object`。

## 例 1

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js">
    </script>
</head>

<body>
    <script>
        console.log(_.chain([4, 5, 6, 7])
        .tap(function (array) {
            array.push(8);
        }))
            .value(); 
    </script>
</body>

</html>
```

**输出:**

```
[4, 5, 6, 7, 8]
```

## 例 2

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js">
    </script>
</head>

<body>
    <script>
        console.log(_.chain(['a', 'b', 'c', 'd'])
        .tap(function (array) {
            array.pop();
        }))
            .value(); 
    </script>
</body>

</html>
```

**输出:**

```
["a", "b", "c"]
```

## 例 3

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js">
    </script>
</head>

<body>
    <script>
        console.log(_.chain([1, 2, 3, 4, 5, 6, 7, 8, 9])
            .filter(function (number) 
                { return number % 3 == 0; })
            .tap(alert)
            .map(function (number) 
                { return number * number }))
            .value();
    </script>
</body>

</html>
```

**输出:**

```
3, 6, 9   // Result of filter function
[9, 36, 81] // After tap method map function is performed
```

这里，`map`功能应用于通过`filter`方法获得的中间结果。

**参考:** [https://underscorejs.org/#tap](https://underscorejs.org/#tap)