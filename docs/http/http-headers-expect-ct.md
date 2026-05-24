# HTTP 头| Expect-CT

> 原文:[https://www.geeksforgeeks.org/http-headers-expect-ct/](https://www.geeksforgeeks.org/http-headers-expect-ct/)

**HTTP Expect-CT** 报头是一个响应类型的报头，用于防止错误地为站点颁发证书，并确保它们不会被忽视，它还允许站点决定报告或实施证书透明度要求。

**语法:**

```html
Expect-CT max-age=<age>, enforce, report-uri="<uri>"
```

**注意:**强制和报告 uri 是可选指令。

**指令:**HTTP Expect-CT 头接受上面提到的和下面描述的三个指令:

*   **最大年龄:<年龄> :** 该指令告知用户在接收到预期联系类型报头后应考虑预期联系类型主机(从其接收消息)的秒数。
*   **强制:**这是一个可选指令，提示用户拒绝不符合证书透明性(CT)策略的进一步连接，并强制执行该策略。
*   **报告-uri: < uri > :** 它是一个可选指令，描述了用户可以报告 Expect-CT 头失败的 URL。

**示例:**

*   在本例中，证书透明度实施 12 小时，并向 geeksforgeeks.org 报告。

    ```html
    Expect-CT: max-age=43200, enforce, report-uri="https://geeksforgeeks.org/report"
    ```

*   In this example, the Certificate Transparency is enforced for an hour.

    ```html
    Expect-CT: max-age=3600, enforce
    ```

    要检查正在运行的预期联系类型，请转到**检查元素- >网络**检查预期联系类型的响应标题如下所示，预期联系类型突出显示。
    T3】

    **支持的浏览器:**浏览器兼容 **HTTP Expect-CT 头文件**如下:

    *   谷歌 Chrome
    *   歌剧