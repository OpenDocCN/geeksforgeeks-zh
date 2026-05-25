
# HTML 框架集标签

> 原文: [https://www.geeksforgeeks.org/html-frameset-tag/](https://www.geeksforgeeks.org/html-frameset-tag/)

HTML 中的 `<frameset>` 标签用于定义框架集。该元素包含一个或多个框架元素，用于指定框架集中的行数和列数以及它们的空间像素。每个 `<frameset>` 元素可以保存一个单独的文档。

**注意:** HTML 5 不支持 `<frameset>` 标签。

## 语法

```html
<frameset cols = "pixels|%|*">
```

## 属性

框架集属性列表如下:

*   **cols**: `cols` 属性用于在网页浏览器中创建垂直框架。该属性用于定义框架集标签中的列数及其大小。
*   **rows**: `rows` 属性用于在网页浏览器中创建水平框架。此属性用于定义框架集标记中的行数及其大小。
*   **边框**: `frameset` 标签的这个属性以像素为单位定义了每一帧边框的宽度。零值用于无边框。
*   **框架边框**: 框架集标签的该属性用于指定是否应该在框架之间显示三维边框。使用两个值 0 和 1，其中 0 表示没有边框，值 1 表示有边框。
*   **框架间距**: 框架集标签的该属性用于指定框架集中框架之间的间距量。这可以采用任何整数值作为参数，该参数基本上表示像素值。

## 示例

### 示例 1: 使用 `rows` 属性创建水平框架

```html
<!DOCTYPE html>
<html>
    <head>
        <title>frameset attribute</title>
    </head>

<!-- frameset attribute starts here -->   
    <frameset rows = "20%, 60%, 20%">
        <frame name = "top" src = "attr1.png" />
        <frame name = "main" src = "gradient3.png" />
        <frame name = "bottom" src = "col_last.png" />
        <noframes>
            <body>The browser you are working does not
                                  support frames.</body>
        </noframes>
    </frameset>
    <!-- frameset attribute ends here -->
</html>
```

### 示例 2: 使用 `cols` 属性创建垂直框架

```html
<!DOCTYPE html>
<html>    
    <head>
        <title>frameset attribute</title>
    </head>

<frameset cols = "30%, 40%, 30%">
        <frame name = "top" src = "attr1.png" />
        <frame name = "main" src = "gradient3.png" />
        <frame name = "bottom" src = "col_last.png" />        
        <noframes>
            <body>The browser you are working does
            not support frames.</body>
        </noframes>
    </frameset>
</html>
```

## 支持的浏览器

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队
