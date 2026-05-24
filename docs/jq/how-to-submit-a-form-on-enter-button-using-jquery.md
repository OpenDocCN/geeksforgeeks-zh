# 如何使用 jQuery 在回车按钮上提交表单？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery/](https://www.geeksforgeeks.org/how-to-submit-a-form-on-enter-button-using-jquery/) 提交输入按钮表单

给定一个 HTML 表单，任务是在使用 jQuery 单击“输入”按钮后提交表单。要使用“输入”按钮提交表单，我们将使用 [jQuery keypress()方法](https://www.geeksforgeeks.org/jquery-keypress/)，要检查“输入”按钮是否被按下，我们将使用“输入”按钮键码值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <script src="https://code.jquery.com/jquery-3.5.1.min.js"
integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" 
        crossorigin="anonymous">
    </script>
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
</head>

<body>
    <h3 style="color: green;font-size: 28px;">
        GeeksforGeeks
    </h3>

    <form class="info">
        <input name="fname" /><br>
        <input name="lname" /><br>
        <button type="submit">Submit</button>
    </form>
</body>

</html>
```

**JavaScript 代码:**

```html
<script>

    // Wait for document to load
    $(document).ready(() => {
        $('.info').on('submit', () => {

            // prevents default behaviour
            // Prevents event propagation
            return false;
        });
    });
    $('.info').keypress((e) => {

        // Enter key corresponds to number 13
        if (e.which === 13) {
            $('.info').submit();
            console.log('form submitted');
        }
    })
</script>
```

**说明:**
我们使用 jQuery `event.which`检查按键上的键码。回车键的键码是 13，所以如果键码匹配 13，那么我们使用。submit()方法提交表单。

**完整代码:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <script src="https://code.jquery.com/jquery-3.5.1.min.js"
        integrity=
        "sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" 
        crossorigin="anonymous">
    </script>
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
</head>

<body>
    <h3 style="color: green;font-size: 28px;">
        GeeksforGeeks
    </h3>
    <form class="info">
        <input name="fname" /><br><br>
        <input name="lname" /><br><br>
        <button type="submit">Submit</button>
    </form>

    <script>
        $(document).ready(() => {
            $('.info').on('submit', () => {
                return false;
            });
        });
        $('.info').keypress((e) => {
            if (e.which === 13) {
                $('.info').submit();
                alert('Form submitted successfully.')
            }
        })
    </script>
</body>

</html>
```

**输出:**
![](img/70bf9593c9d93fb34606c63376f49c3e.png)