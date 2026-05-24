# jQuery 中如何使用自动完成搜索？

> 原文:[https://www . geesforgeks . org/如何使用-搜索-jquery 中的自动完成/](https://www.geeksforgeeks.org/how-to-use-search-autocomplete-in-jquery/)

在本文中，我们将看到如何在 JQuery 中使用搜索自动完成。为此，我们将使用名为自动完成的 jQuery 内置函数。我们将分两个不同的阶段进行。

*   创建一个基本的 HTML 文件，并向其中添加一个输入栏。
*   实现自动完成功能。

**HTML 代码:**这里我们将创建结构来接受用户的输入，并在头部附加 jQuery CDN 链接。

**将 jQuery 脚本添加到您的 HTML 文件中:**

> <脚本 src = " https://code . jquery . com/ui/1 . 12 . 1/jquery-ui . js "></脚本>

## index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" 
          content="IE=edge">
    <meta name="viewport" 
          content="width=device-width, 
                   initial-scale=1.0">
    <title>Jquery Autocomplete</title>
    <script src="https://code.jquery.com/jquery-1.12.4.js">
    </script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js">
    </script>
</head>

<body>
    <input type="text" 
           id="auto" 
           placeholder="enter something" />
</body>

</html>
```