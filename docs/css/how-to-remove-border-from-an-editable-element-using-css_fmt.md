# 如何使用 CSS 移除可编辑元素的边框？

> 原文: [https://www.geeksforgeeks.org/how-to-remove-border-from-an-editable-element-using-css/](https://www.geeksforgeeks.org/how-to-remove-border-from-an-editable-element-using-css/) 从可编辑元素中移除边框

给定一个包含一些文档的 HTML 文档，任务是使用 CSS 从可编辑元素中移除边框。这是任何`contenteditable`属性设置为`true`的元素的默认行为，只要元素获得焦点，它就会在它们周围获得边框。使用`[contenteditable]`属性选择器选择所有内容可编辑的元素，去掉`outline`属性的边框，即可完成任务。

## 示例

### HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        [contenteditable] {
            outline: 0px solid transparent;
        }
    </style>
</head>

<body>
    <center>
        <h2>GeeksForGeeks</h2>

        <h2>
            How to remove the border from 
            an editable element with CSS?
        </h2>

        <p contenteditable="true">
            This paragraph is editable
        </p>

    </center>
</body>

</html>
```

## 输出

### 编辑元素前

![](img/cf3b94a1c6d548fe6e21164454b0d5a9.png)

### 在元素上编辑后

![](img/a1cd5ed225f03cc95ca8feb159eb47a5.png)