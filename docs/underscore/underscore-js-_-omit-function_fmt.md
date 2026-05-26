# Underscore.js | _.omit() 函数

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-omit-function/](https://www.geeksforgeeks.org/underscore-js-_-omit-function/)

`_.omit()` 函数用于返回过滤后省略黑名单键的对象的副本。

## 语法

```
_.omit(object, *keys)
```

## 参数

该函数接受两个参数，如上所述，如下所述:

*   `object`: 此参数保存对象的值。
*   `keys`: 为可选参数。它包含需要省略值的键名。

## 返回值

它返回一个对象的副本，该对象被过滤以忽略黑名单中的键。

## 例 1

```
<!DOCTYPE html>
<html>

<head>
    <script type="text/javascript" src=
"https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js">
    </script>
</head>

<body>
    <script type="text/javascript">

var info = {
            Company: 'GeeksforGeeks',
            Address: 'Noida',
            Contact: '+91 9876543210'
        };

console.log(_.omit(info, 'Company', 'Address'));
    </script>
</body>

</html>
```

输出:
![](img/a8b6a4aabb910e5eab5badc27a69e865.png)

## 例 2

```
<!DOCTYPE html>
<html>

<head>
    <script type="text/javascript" src=
"https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js">
    </script>
</head>

<body>
    <script type="text/javascript">

var info = {
            key1: 10,
            key2: 20,
            key3: 30,
            key4: 40,
            key5: 50
        };

console.log(_.omit(info, function (value, key, info) {
            return value == 10 || value == 50;
        }));
    </script>
</body>

</html>
```

输出:
![](img/ecc79fa8bae918dedecce6711ad0cf6f.png)