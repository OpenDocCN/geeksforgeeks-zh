# 如何使用 jQuery Mobile 制作图标按钮？

> 原文:[https://www . geesforgeks . org/how-to-make-a-icon-button-use-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-a-icon-button-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作一个图标按钮。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">

我们将使用不同类型的 ui 类和类型来组成标记按钮。

**示例 1:** 在本文中，我们将使用带有 class = " ui-BTN ui-icon-delete ui-BTN-icon-left "的 Anchor 来制作按钮。

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<head>
    <link rel="stylesheet" href=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />
    <script src=
"http://code.jquery.com/jquery-1.11.1.min.js">
    </script>
    <script src=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>
</head>

<body> 
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>Icon Anchor using jQuery Mobile</h4>
    </center>

    <a href="https://www.geeksforgeeks.org/" 
        class="ui-btn ui-icon-delete 
               ui-btn-icon-left">
          Icon Anchor
      </a>
</body> 

</html>
```

**输出:**

![](img/846503ee3fbe1b98d09deadeb91e966a.png)

**示例 2:** 在本文中，我们将使用带有 class = " ui-BTN ui-icon-delete ui-BTN-icon-left "的 button 标记来实现我们的目的。

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<head>
    <link rel="stylesheet" href=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />
    <script src="http://code.jquery.com/jquery-1.11.1.min.js">
    </script>

    <script src=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
</head>

<body> 
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>Icon buttons using jQuery Mobile</h4>
    </center>

    <button class="ui-btn ui-icon-delete
                   ui-btn-icon-left" id="gfg">
          Icon Button
      </button>
</body> 

</html>
```

**输出:**

![](img/8b0195c304cc7a715f838c32a783c0f9.png)