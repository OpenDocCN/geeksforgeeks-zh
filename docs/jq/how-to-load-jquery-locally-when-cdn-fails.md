# CDN 失败时如何在本地加载 jQuery？

> 原文:[https://www . geeksforgeeks . org/如何加载-jquery-本地-当-cdn-失败/](https://www.geeksforgeeks.org/how-to-load-jquery-locally-when-cdn-fails/)

在本文中，我们将学习如何在 CDN 失败时加载我们的本地 jQuery 文件。首先，如果有失败的可能，为什么要用 CDN。使用 CDN 而不是本地 jQuery 文件有很多优点。

使用 CDN 的一些优势如下。

*   它减少了服务器的负载。
*   jQuery 框架从这些 CDN 加载速度更快，因此节省了我们的带宽。

CDN 失败的可能性很小。但这并不意味着它永远不会失败。所以我们必须考虑到这一点。

**如何检查我们的 CDN 脚本加载是否正确？**

我们可以通过检查脚本加载后应该出现的任何变量或函数的类型来检查我们的 CDN 脚本是否被加载。如果我们得到类型“未定义”，这意味着我们的 CDN 失败。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <!-- jQuery library -->
    <script src=
 "https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
   </script>
</head>

<body>
    <script>
        if(typeof jQuery == 'undefined'){
            document.write("CDN fails")
        }
        else{
            document.write("CDN loaded")
        }
    </script>
</body>

</html>
```

**输出:**

```html
CDN loaded
```

如果我们只是从 CDN 中删除任何字母，那么我们的 CDN 将不会加载，它会给出以下输出:

```html
CDN fails
```

**CDN 失败时如何在本地加载 jQuery？**

首先，让我们看看如何从本地机器链接 jQuery。首先，我们将从 jQuery 网站下载 jQuery 库文件，然后将它包含在我们的 HTML 代码中，如下所示。

```html
<script src="jquery-3.6.0.js"></script>
```

**从本地机器加载 jQuery 的代码:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <!-- jQuery library -->
    <script src="jquery-3.6.0.js"></script>
</head>

<body>
    <script>
        if(typeof jQuery == 'undefined'){
            document.write("CDN fails")
        }
        else{
            document.write("CDN loaded")
        }
    </script>
</body>

</html>
```

**输出:**

```html
CDN loaded
```

**注意:**使用下载的 jQuery 文件的完整路径。在我的例子中，HTML 和 jQuery 文件都在同一个文件夹中。现在，我们将看到如何加载本地 jQuery，以防我们的 CDN 失败。

编写以下几行代码，当 CDN 失败时，它会从机器中添加 jQuery。

> <脚本>window . jquery | | document . write(<脚本 src = " jquery-3 . 6 . 0 . js "><\/脚本>)</脚本>

我们正试图从 CDN 加载 jQuery。如果 CDN 失败，那么“jQuery”变量将是未定义的。

在第二行，我们将检查“jQuery”变量是否未定义，如果未定义，意味着 CDN 没有加载，那么我们将从本地机器加载 jQuery 文件。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <!-- jQuery library -->
    <script src=
 "https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js">
    </script>
    <script>
window.jQuery || document.write('<script src="jquery-3.6.0.js"><\/script>')
    </script>;
</head>

<body>
    <script>
        $().ready(function(){
            document.write("Hey Geeks");
        })
    </script>
</body>

</html>
```

**输出:**

```html
Hey Geeks
```

即使我们的 CDN 失败了，我们也会一直得到这个输出。当我们处理如果我们的 CDN 失败的情况时，从我们的机器添加 jQuery 文件。