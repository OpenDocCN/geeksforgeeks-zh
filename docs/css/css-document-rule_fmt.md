# CSS @document 规则

> 原文: [https://www.geeksforgeeks.org/css-document-rule/](https://www.geeksforgeeks.org/css-document-rule/)

`@document` 规则用于维护一页或一组页面中样式的限制。这个规则为特定的网址制定了样式，假设用户在一个页面上包含了 10 个网址，并且想要给每个网址设置不同的样式，那么这个规则可能是王牌。`@document` 规则为您定义的每个网址页面定义了不同的样式规则。

## 语法

```html
@document url("") {
    // Style your defined URLs page
}
```

## 函数

### `url()`
此函数存储适用于样式的 URL。

### `url-prefix()`
此函数可以存储多个 URL，其中一个样式适用于多个页面。

### `domain()`
此函数保存域名，无论使用此属性的样式如何，它都将适用于此域名下的所有网页地址。

### `regexp()`
此函数使用正则表达式来保存文档。

下面的例子说明了 `@document` 规则:

## 示例 1
本示例中定义的样式将适用于所提到的网址、域和正则表达式。

```html
<style> 
@document url("https://auth.geeksforgeeks.org/user/skyridetim/articles"),
url-prefix("https://www.geeksforgeeks.org/"),
domain("html.comm"),
regexp("https:.*") {
    body {
        background-color: brown;
        font-size: 18px;
    }
    h1 {
        color: green;
        background: white;
    }
}
</style>
```

## 支持的浏览器
以下列出了 `CSS @document rule` 属性支持的浏览器: