# HTTP 头|范围

> 原文:[https://www.geeksforgeeks.org/http-headers-range/](https://www.geeksforgeeks.org/http-headers-range/)

HTTP 头用于通过 HTTP 请求或响应传递附加信息。 **HTTP 范围**是一个 HTTP 请求头，用于从服务器获取文档的一部分。如果服务器返回文档的该部分，它将使用 206(部分内容)状态代码。如果范围无效，使用的状态代码是 416(范围不可满足)，服务器使用状态代码 200(正常)，以防它忽略范围请求。

**语法:**

*   Get the whole document from a specific range

    ```html
    Range: <unit>=<range-start>-
    ```

*   Request multiple parts

    ```html
    Range: <unit>=<range-start>-<range-end>, <range-start>-<range-end>
    ```

*   Specific end part of the request document

    ```html
    Range: <unit>=-<suffix-length>
    ```

**指令:**HTTP Range 头接受的指令有四个，上面提到了，下面描述:

*   **Unit:** Specify the unit of a given range. Generally, *bytes* are used.
*   **Range-Start:** is an integer that specifies the start of the document part.
*   **Range-End:** is an integer that specifies the end of the document part. This is an optional instruction.
*   **suffix-length:** is an integer, indicating the end of the document to be returned.

**示例:**

*   Get the first 100 bytes of the file

    ```html
    Range: bytes=0-99
    ```

*   Get the last 100 bytes of the file

    ```html
    Range: bytes=-100
    ```

*   Multiple request ranges

    ```html
    Range: bytes=0-99, 700-799
    ```

要检查该范围是否有效，请转到检查**元素- >网络**检查范围的请求标题。

**支持的浏览器:**以下列出了 **HTTP 头范围**支持的浏览器: