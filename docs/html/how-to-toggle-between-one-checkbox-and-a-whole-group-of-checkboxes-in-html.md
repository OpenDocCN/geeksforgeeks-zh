# 如何在 HTML 中一个复选框和一整组复选框之间切换？

> 原文:[https://www . geeksforgeeks . org/如何在 html 中的一个复选框和一整组复选框之间切换/](https://www.geeksforgeeks.org/how-to-toggle-between-one-checkbox-and-a-whole-group-of-checkboxes-in-html/)

给定一个有一个复选框和一组复选框的 HTML 文档，任务是在 JavaScript 的帮助下在它们之间切换。

我们可以通过使用事件 [onChange()](https://www.geeksforgeeks.org/html-dom-onchange-event/) 来实现这一点，每当我们*选中*或*取消选中*复选框时，就会触发该事件。

我们可以给这个事件传递一个函数，如果单独的复选框是**选中的**，则该函数应该**使用 [forEach](https://www.geeksforgeeks.org/javascript-array-foreach-method/) 循环取消选中**组中的所有复选框，并且还应该**取消选中**组中任何**复选框**的单独复选框。

**语法:**

```html
let groupCheck = Array.from(document.getElementsByName('group'))
let sepCheck = document.getElementById('sep')

groupCheck.forEach(element => {
    element.onchange = () => {
        if (element.checked) {
            sepCheck.checked = false;
        }
    }
})

sepCheck.onchange = () => {
    if (sepCheck.checked) {
        groupCheck.forEach(element => {
            element.checked = false;
        })
    }
}}
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <title>
        How to toggle between one checkbox 
        and a whole group of checkboxes?
    </title>

    <style>
        body {
            text-align: center;
            margin-top: 30%;
        }

        h1 {
            color: green;
        }

        p {
            margin-top: 4%;
        }

        label {
            margin-left: 3%;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h4>
        How to toggle between one checkbox 
        and a whole group of checkboxes?
    </h4>

    <p>
        <label for="one"><input type="checkbox"
            name="group" id="one" />First
        </label>

        <label for="two"><input type="checkbox"
            name="group" id="two" />Second
        </label>

        <label for="three"><input type="checkbox"
            name="group" id="three" />Third
        </label>
    </p>

    <p>
        <label for="sep"><input type="checkbox"
            name="sep" id="sep" />Separate
        </label>
    </p>

    <script>

        // Returns an array of all the 
        // checkboxes in the group
        let groupCheck = Array.from(
            document.getElementsByName('group'))

        // Returns the separate checkbox
        let sepCheck = document.getElementById('sep')

        groupCheck.forEach(element => {

            // Setting onChange event for every
            // checkbox in the group
            element.onchange = () => {
                if (element.checked) {

                    // Unchecking the checkbox
                    sepCheck.checked = false;
                }
            }
        })

        // Setting onChange event for the
        // separate checkbox 
        sepCheck.onchange = () => {
            if (sepCheck.checked) {
                groupCheck.forEach(element => {

                    // Unchecking the checkbox
                    element.checked = false; 
                })
            }
        }
    </script>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-536270-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210101151435/gfgcheck.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210101151435/gfgcheck.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210101151435/gfgcheck.mp4)</video>