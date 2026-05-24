# HTTP 头|内容-语言

> 原文:[https://www . geesforgeks . org/http-headers-content-language/](https://www.geeksforgeeks.org/http-headers-content-language/)

**HTTP 头**用于在 HTTP 请求和 HTTP 响应中提供附加信息。 **HTTP 头内容-语言**用于定义说话人文档打算使用哪种语言。它没有定义文档的语言。如果未指定此标题，则假定该文档面向所有讲语言的人。

**语法:**

*   仅指定一种语言时

    ```html
    Content-Language: <language-tag>

    ```

*   指定多种语言时

    ```html
    Content-Language: <language-tag>, <language-tag>, <language-tag>

    ```

**指令:**

*   **语言标签:**定义语言的是不区分大小写的指令。一般由两部分组成。第一部分定义了主要语言，它定义了一大类相关语言(例如，“en”=英语)，可选的第二部分由“-”分隔，用于缩小语言范围。

**示例:**

*   它说说英语的人是页面的目标受众。

    ```html
    Content-Language: en
    ```

*   它说说德语和英语的人是页面的目标受众。

    ```html
    Content-Language: de, en
    ```

要检查正在运行的内容语言，请转到检查**元素- >网络**检查内容语言的请求头，如下所示。
T3】

**支持的浏览器:**与 **HTTP 头内容语言**兼容的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧