# CSS | @文档规则

> 原文:[https://www.geeksforgeeks.org/css-document-rule/](https://www.geeksforgeeks.org/css-document-rule/)

**CSS @document 规则**用于维护一页或一组页面中样式的限制。这个规则为特定的网址制定了样式，假设用户在一个页面上包含了 10 个网址，并且想要给每个网址设置不同的样式，那么这个规则可能是王牌。 **@document** 规则为您定义的每个网址页面定义了不同的样式规则。

**语法:**

```html
@document url("") {
    // Style your defined URLs page
}

```

**函数:**

*   **url ():** This function stores the URL applicable to the style.
*   **url-prefix ():** This function can store multiple URLs, in which a single style is suitable for multiple pages.
*   **Domain ():** This function saves the domain name, regardless of the style with this attribute, it will be applicable to all web addresses under this domain.
*   **regexp ():** This function uses regular expressions to save documents.

下面的例子说明了**@文档**规则:

**示例 1:** 本示例中定义的样式将适用于所提到的网址、域和正则表达式。

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

**支持的浏览器:**以下列出了 **CSS @document rule** 属性支持的浏览器: