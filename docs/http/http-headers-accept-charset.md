# HTTP 头|接受-字符集

> 原文:[https://www.geeksforgeeks.org/http-headers-accept-charset/](https://www.geeksforgeeks.org/http-headers-accept-charset/)

**HTTP Accept-Charset** 是一个请求类型头。此标头用于指示服务器响应可接受的字符集。 **accept-charset 头**指定客户端接受的字符编码，这个头也允许用户代理指定它支持的字符集。
在**内容协商**的帮助下，它选择编码类型，然后用内容类型响应头通知客户端它的选择，这通常出现在`charset= parameter.`中。我们的网络浏览器通常不发送这个头，因为发送它将允许指纹识别，并且每个资源的默认值通常是正确的。如果此标题不存在，用户代理必须为其接受的每个文本/*媒体类型指定每个字符集参数，例如

```html
Accept: text/html;charset=US-ASCII, text/html;charset=UTF-8, text/plain;
charset=US-ASCII,text/plain;charset=UTF-8
```

**注意:**当服务器无法为该请求提供任何字符编码时，它将发回一个 **406 不可接受**错误代码，因此为了避免这种情况，并提供更好的用户体验，如果不存在 Accept-Charset 头，默认为任何字符集都是可接受的。

**语法:**

*   这是单字符集的。

    ```html
    Accept-Charset: <charset>
    ```

*   该语法用于选择多个具有质量值的字符集。

    ```html
    Accept-Charset: <charset>,  <charset> ;q= 
    ```

**指令:**该标题接受三个指令，如上所述，如下所述:

*   **<字符集> :** 该指令保存字符集类型，任何字符编码名称，如 UTF-32、UTF-16 或 iso-8859-15。
*   ***:** 该指令用作标题中未提及的任何字符的通配符。

**注:**本**；q=** 定义了因子权重，按照使用相对质量值表示的偏好顺序排列的值。

**示例:**

*   在本例中，单个值位于接受字符集标题

    ```html
    Accept-Charset: iso-8859-5
    ```

    上
*   在本例中，双精度值是 Accept-Charset 标题

    ```html
    Accept-Charset: utf-8, iso-8859-1;q=0.7
    ```

*   在本例中，双精度值是 Accept-Charset 头，第二个头使用**“***通配符选择所有编码

    ```html
    Accept-Charset: utf-8, iso-8859-1;q=0.7, *;q=0.9
    ```

**支持的浏览器:**浏览器与 **HTTP Accept-Charset 头不兼容。**