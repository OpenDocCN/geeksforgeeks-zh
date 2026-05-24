# 如何使用 jQuery 实时统计字数？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery 实时计算字数/](https://www.geeksforgeeks.org/how-to-count-words-in-real-time-using-jquery/)

在本文中，我们将学习如何使用 jQuery 实时统计单词。我们有一个输入字段，当我们打字时，我们会实时得到输入中的字数。

**方法:**首先，我们选择输入字段，并将其值存储到变量中。当释放键盘键时，我们调用一个名为**字数统计()**的函数来统计输入字段中的字数。为了统计输入字段中的字数，我们使用 jQuery [split()](https://www.geeksforgeeks.org/javascript-string-prototype-split-function/) 方法按空间分割值，然后统计字数。

**代码片段:**下面是方法**的实现字数()。**

```html
function wordCount( field ) {
    var number = 0;

    // Split the value of input by
    // space to count the words
    var matches = $(field).val().split(" ");

    // Count number of words
    number = matches.filter(function (word) {
        return word.length > 0;
    }).length;

    // final number of words
    $("#final").val(number);
}
```

**HTML 代码:**下面是上述方法的完整实现。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <script src=
"https://code.jquery.com/jquery-3.5.0.js">
    </script>

    <style>
        body {
            color: green;
            font-size: 30px;
        }

        input {
            font-size: 30px;
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <input type="text" id="inp" />
    <input type="text" id="final" disabled />

    <script>
        function wordCount(field) {
            var number = 0;

            // Split the value of input by
            // space to count the words
            var matches = $(field).val().split(" ");

            // Count number of words
            number = matches.filter(function (word) {
                return word.length > 0;
            }).length;

            // Final number of words
            $("#final").val(number);
        }

        $(function () {
            $("input[type='text']:not(:disabled)")
            .each(function () {
                var input = "#" + this.id;

                // Count words when keyboard
                // key is released
                $(this).keyup(function () {
                    wordCount(input);
                });
            });
        });
    </script>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-609711-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210523191656/gfg1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210523191656/gfg1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210523191656/gfg1.mp4)</video>