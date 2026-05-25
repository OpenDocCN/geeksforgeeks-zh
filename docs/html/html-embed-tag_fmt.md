
# HTML embed 标签

> 原文: [https://www.geeksforgeeks.org/html-embed-tag/](https://www.geeksforgeeks.org/html-embed-tag/)

HTML 中的 `<embed>` 标签用于将外部应用程序嵌入到 HTML 文档中，这些外部应用程序通常是音频或视频等多媒体内容。它被用作嵌入插件（如 flash 动画）的容器。这个标签是 HTML 5 中的一个新标签，它只需要一个起始标签。

## 语法

```html
<embed attributes>
```

## 属性

`<embed>` 标签包含以下讨论的四个属性：

*   **高度**：该属性包含以像素为单位的属性值。它用于指定嵌入内容的高度。
*   **src**：用于保存网址。它用于指定嵌入内容的网址。
*   **宽度**：宽度值以像素为单位设置。它用于指定嵌入内容的宽度。
*   **类型**：它包含了 media_type 内容。它用于指定嵌入内容的媒体类型。

## 示例

### 示例 1

```html
<!DOCTYPE html>
<html>
    <head>
        <title>embed Tag</title>
        <style>
            q {
                color: #00cc00;
                font-style: italic;
            }
        </style>
    </head>
    <body>
        <q>GeeksforGeeks</q> is loading.
        <br>
        <embed src="loading2.swf"
        type="application/x-shockwave-flash">
    </body>
</html>
```

### 示例 2

```html
<!DOCTYPE html>
<html>
    <head>
        <title>embed Tag</title>
        <style>
            q {
                color: #00cc00;
                font-style: italic;
            }
        </style>
    </head>
    <body>
        Click here to redirect to <q>GeeksforGeeks</q>
        <br>
        <embed src="animProps02.swf" width="30px" height="30px">
        <a href="http://geeksforgeeks.org">GeeksforGeeks</a>
    </body>
</html>
```

## 支持的浏览器

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队
