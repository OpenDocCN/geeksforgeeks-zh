# 使用 HTML 和 CSS 创建印度国旗

> 原文：[https://www.geeksforgeeks.org/create-indian-flag-using-html-and-css/](https://www.geeksforgeeks.org/create-indian-flag-using-html-and-css/)

在本文中，我们将使用 HTML 和 CSS 设计一个印度的动画旗帜。正如我们所知，我们的印度国旗有藏红花、白色和绿色三种颜色，白色部分的中心还有一个轮子。所以让我们建立印度国旗。在这里，我们还将创建一个旗杆。所以首先创建一个包装器 `div`（类名为 `wrapper`），它包含两个名为 `stick` 和 `flag` 的 `div` 类。

## HTML

```html
<div class = "wrapper">
    <div class="stick"></div>
    <div class="flag"></div>
</div>
```

棒和标志应该是内联的，所以我们将包装 `div` 的 `display` 属性设置为 `flex`。并添加一些 `height`，`width`，`background`，`border` 样式到 `stick`，并在 `flag`，添加 `height`，`width`，`box-shadow`，`background-color`，和 `position` 属性。

## CSS

```css
.wrapper {
    display: flex;
}

.stick {
    height: 450px;
    width: 10px;
    background: black;
    border-top-left-radius: 10px;
    border-bottom-left-radius: 5px;
    border-bottom-right-radius: 5px;
}

.flag {
    width: 270px;
    height: 180px;
    box-shadow: 0px 0px 90px 1px #989;
    background-color: transparent;
    position: relative;
}
```