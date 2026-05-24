# 如何在 jQuery.each() util 中跳到下一个迭代？

> 原文:[https://www . geeksforgeeks . org/如何跳过 jquery 中的下一个迭代-每个-util/](https://www.geeksforgeeks.org/how-to-skip-to-next-iteration-in-jquery-each-util/)

**jQuery 的每一个()**函数都允许我们循环遍历不同的数据集，比如数组或者对象。 **jQuery.each()** 是 jQuery 中使用最多的函数之一。

**语法:**

```html
$(selector).each(function(index, element))
$.each(function(index))
```

$.每个()本质上都是传统 for 或 for 的替代..循环中。

**示例 1:** 该示例跳过步骤 4 到下一次迭代，即步骤 5。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>jQuery.each() method</title>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head>

<body>
    <script>
        var arr = ["Step1", "Step2", 
            "Step3", "Step4", "Step5"];

        $.each(arr, function (i) {
            if (arr[i] === "Step4") {
                return;
            }
            document.write(arr[i] + ' ');
        });
    </script>
</body>

</html>
```

**输出:**

```html
Step1 Step2 Step3 Step5
```

**解释:**在上面的代码中，可以看到当迭代在“i=4”时，那么“if”条件变为“true”，返回一个非 false 值。所以它跳过了下一个迭代，即步骤 4。

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>jQuery.each() method</title>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head>

<body>
    <script>
        var arr = [1, 2, 3, 4, 5];
        $.each(arr, function (i) {
            if (arr[i] === 3) {
                return true;
            }
            document.write(arr[i] + ' ');
        });
    </script>
</body>

</html>
```

**输出:**

```html
1 2 4 5
```