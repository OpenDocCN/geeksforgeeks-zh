# HTML | 标签

> 原文:[https://www.geeksforgeeks.org/html-frame-tag/](https://www.geeksforgeeks.org/html-frame-tag/)

HTML 框架用于将网络浏览器窗口分成多个部分，每个部分都可以单独加载。框架集标记是浏览器窗口中框架的集合。

**创建框架:**用 HTML 中的 frameset 标签来使用网页浏览器中的框架，而不是用 body 标签。但是这个标签在 HTML 5 中被否决了。frameset 标记用于定义如何划分浏览器。每个框架由框架标签指示，它基本上定义了哪个 HTML 文档应该打开到框架中。使用 HTML 文档中框架标记的行属性定义水平框架，使用 HTML 文档中框架标记的列属性定义垂直框架。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Example of HTML Frames using row attribute</title>
    </head>

    <frameset rows = "20%, 60%, 20%">
        <frame name = "top" src = 
        "C:/Users/dharam/Desktop/attr1.png" />
        <frame name = "main" src = 
        "C:/Users/dharam/Desktop/gradient3.png" />
        <frame name = "bottom" src = 
        "C:/Users/dharam/Desktop/col_last.png" />
        <noframes>
            <body>The browser you are working does 
                        not support frames.</body>
        </noframes>
    </frameset>
</html>                    
```

**输出:**上面的例子基本上是用 frameset 标签的 row 属性创建了三个水平框架:上、中、下，noframe 标签是给那些不支持 noframe 的浏览器使用的。
T3】

**示例:**本示例说明了 frameset 标签的 col 属性。

```html
<!DOCTYPE html>
<html>    
    <head>
        <title>Example of HTML Frames Using col Attribute</title>
    </head>

    <frameset cols = "30%, 40%, 30%">
        <frame name = "top" src = 
        "C:/Users/dharam/Desktop/attr1.png" />
        <frame name = "main" src = 
        "C:/Users/dharam/Desktop/gradient3.png" />
        <frame name = "bottom" src = 
        "C:/Users/dharam/Desktop/col_last.png" />        
        <noframes>
            <body>The browser you are working does 
                         not support frames.</body>
        </noframes>
    </frameset>
</html>                    
```

**输出:**上面的例子基本上是用 frameset 标签的 col 属性创建三个垂直框架:左、中、右。
T3】

**框架集标签的属性:**

*   **cols:**cols 属性用于在网页浏览器中创建垂直框架。这个属性基本上用于定义框架集标签中的列数及其大小。
    柱的大小或宽度在框架集中以下列方式设置:
    *   使用像素绝对值
        **示例:**

        ```html
        <frameset cols = "300, 400, 300">
        ```

    *   使用百分比值
        **示例:**

        ```html
        <frameset cols = "30%, 40%, 30%">
        ```

    *   Use wild card values:
        **Example:**

        ```html
        <frameset cols = "30%, *, 30%">
        ```

        在上面的例子中，将使用剩余的百分比来创建垂直框架。

*   **行:**rows 属性用于在 web 浏览器中创建水平框架。此属性用于定义框架集标记中的行数及其大小。
    行的大小或每行的高度采用以下方式:

*   使用像素绝对值
    **示例:**

    ```html
    <frameset rows = "300, 400, 300">
    ```

*   使用百分比值
    **示例:**

    ```html
    <frameset rows = "30%, 40%, 30%">
    ```

*   Use wild card values
    **Example:**

    ```html
    <frameset rows = "30%, *, 30%">
    ```

    在上面的例子中，将使用剩余的百分比来创建水平框架。

*   **边框:**框架集标签的这个属性定义了每个框架的边框宽度，以像素为单位。零值用于无边框。
    **例:**

    ```html
    <frameset border="4" frameset>
    ```

    *   **框架边框:**框架集标签的这个属性用于指定是否应该在框架之间显示三维边框。对于这个用途，有两个值 0 和 1，其中 0 表示没有边框，值 1 表示有边框。*   **框架间距:**框架集标签的这个属性用于指定框架集中框架之间的间距。这可以将任何整数值作为参数，该参数基本上表示像素值。
    **例:**

    ```html
    <framespacing="20">
    It means there will be 20 pixel spacing between the frames

    ```

    **帧标签的属性:**

    *   **name:** This attribute is used to give names to the frame. It differentiate one frame from another. It is also used to indicate which frame a document should loaded into.
        **Example:**

        ```html
         <frame name = "top" src = "C:/Users/dharam/Desktop/attr1.png" />
         <frame name = "main" src = "C:/Users/dharam/Desktop/gradient3.png" />
         <frame name = "bottom" src = "C:/Users/dharam/Desktop/col_last.png" />

        ```

        这里我们使用三个框架，名字分别是左中右。

    *   **src:** This attribute in frame tag is basically used to define the source file that should be loaded into the frame.The value of src can be any url.
        **Example:**

        ```html
        <frame name = "left" src = "/html/left.htm" />
        ```

        在上面的例子中，框架的名称是左的，源文件将从框架中的“/html/left.htm”加载。

    *   **边框宽度:**框架标签中的该属性用于指定左右框架的边框和内容之间的空间宽度(以像素为单位)。
        **例:**

        ```html
        <frame marginwidth="20">

        ```

    *   **边框高度:**框架标签中的该属性用于指定顶部和底部框架的边框和内容之间的空间高度(以像素为单位)。
        **例:**

        ```html
        <frame marginheight="20">

        ```

    *   **滚动条:**使用框架标签中的滚动条属性来控制框架中滚动条的外观。这基本上是用来控制滚动条的外观。该属性的值可以是是、否、自动。其中数值“否”表示不会出现滚动条。
        **例:**

        ```html
        <frame scrollbar="no">

        ```

**优势:**

*   它允许用户在一个网页中查看多个文档。
*   它在一个框架集中从不同的服务器加载页面。
*   不支持框架的旧浏览器可以使用标签进行寻址。

**缺点:**由于它的一些缺点，很少在网页浏览器中使用。

*   框架会使网站的制作变得复杂。
*   用户无法为框架内查看的任何网页添加书签。
*   浏览器的后退按钮可能不会像用户希望的那样工作。
*   使用太多的帧会给服务器带来很高的工作负载。
*   许多旧的网络浏览器不支持框架。

**注意:**html 5 不支持这个标签。
**支持的浏览器:**框架<标签支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。