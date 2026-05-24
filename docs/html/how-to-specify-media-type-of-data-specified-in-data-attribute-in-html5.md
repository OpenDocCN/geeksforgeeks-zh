# 如何在 HTML5 中指定数据属性中指定的数据的媒体类型？

> 原文:[https://www . geesforgeks . org/how-to-specify-media-type-of-data-specified-in-data-attribute-in-html 5/](https://www.geeksforgeeks.org/how-to-specify-media-type-of-data-specified-in-data-attribute-in-html5/)

下面的方法介绍了如何在 HTML5 中指定对象要使用的资源的 URL。这可用于需要外部来源内容的页面。

**方法:**我们将使用<对象>元素的**数据**属性来指定要用于该对象的资源的 URL。指定的网址可以是相对的，也可以是绝对的。

**语法:**

```html
<object data="URL">
```

下面的例子说明了**数据**属性来指定对象要使用的资源的网址。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <p>Object with an image resource:</p>

    <object data=
"https://media.geeksforgeeks.org/wp-content/uploads/20200327230544/g4gicon.png">
    </object>

    <p>Object with a video resource:</p>

    <object data=
"https://media.geeksforgeeks.org/wp-content/uploads/20200107020629/sample_video.mp4">
    </object>
</body>

</html>
```

**输出:**

![](img/cb365b9573d22bba0019621901baf817.png)