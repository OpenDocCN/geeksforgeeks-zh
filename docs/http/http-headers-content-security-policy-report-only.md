# HTTP 头|内容-安全-策略-仅报告

> 原文:[https://www . geesforgeks . org/http-headers-content-security-policy-report-only/](https://www.geeksforgeeks.org/http-headers-content-security-policy-report-only/)

HTTP **内容-安全-策略-仅报告**响应头允许网络开发人员通过关注策略的效果来测试策略。这些违规报告由通过 HTTP POST 请求发送到指定 URI 的 JSON 文档组成。这是一个响应类型的头

**语法:**

```html
Content-Security-Policy-Report-Only: <policy-directive>
```

**指令:**该报头接受上面提到的和下面描述的单个报头:

*   **<政策指令> :** 在此标题中可以使用`content-security-policy`标题。`report-uri`指令应与此标题一起使用。

**注意:**`report-uri`指令打算被`report-to`指令取代，`report-to`仍然不被大多数浏览器支持。因此，为了解决兼容性问题，可以同时指定`report-uri`和`report-to`，因为这不仅可以增加与当前浏览器的兼容性，还可以在浏览器获得`report-to`支持时增加向前兼容性。

```html
Content–Security-Policy:  ….; report-uri
https://written.geeksforgeeks.com; report-to groupname
```

支持`report-to`的浏览器会忽略`report-uri`。

*   **报告给:**射击`SecurityPolicyViolationEvent`。如上所述，目前并非所有浏览器都支持。

**示例:**标题的目的是报告可能发生的任何违规行为。它可以反复用于制定内容安全策略。人们可以观察他们的站点的行为，观察**违规报告**和/或**恶意软件重定向**，然后选择由`Content-Security-Policy`标题强加的适当策略。

```html
Content-Security-Policy-Report-Only: default-src https:; 
report-uri /csp-violation-report-endpoint/ 
```

如果希望在实施策略的同时接收报告，他们可以使用带有`report-uri`指令的`Content-Security-Policy`标题。

```html
Content-Security-Policy: default-src https:; 
                          report-uri /csp-violation-report-endpoint/
```

要检查此内容-安全-策略-仅报告-正在运行，请转到**检查元素- >网络**检查内容-安全-策略-仅报告的请求标题如下所示，内容-安全-策略-仅报告突出显示，您可以看到。
T3】

**违规报告语法:**JSON 报告包含以下数据:

*   **blocked-uri:** 被内容安全策略阻止加载的资源的 uri。如果被阻止的 URI 来自与文档 uri 不同的来源，则被阻止的 URI 被缩短为仅包含方案、主机和端口。
*   **性格:**要么`“enforce”`要么`“reporting”`。取决于使用的是`**Content-Security-Policy**`还是`**Content-Security-Policy-Report-Only**`表头。
*   **文档-uri:** 遇到违规的文档的 uri。
*   **生效-指令:**其执行导致违规的指令。
*   **原始策略:**由`**Content-Security-Policy-Report-Only**` HTTP 头指定的原始策略。
*   **引用者:**遇到违规的文档的引用者。
*   **脚本-示例:**导致违规的内联脚本、事件处理程序或样式的前 40 个字符。
*   **状态代码:**包含全局对象的资源的 HTTP 状态代码。
*   **违规-指令:**违反的策略部分的名称。

**违规举报样本:**位于`http://geeksforgeeks.com/signup.html`的页面。下面是实现的策略，只允许来自`cdn.geeksforgeeks.com`的样式表。

```html
Content-Security-Policy-Report-Only: default-src ‘none’; 
style-src cdn.geeksforgeeks.com; report-uri /_/csp-reports
```

*   **HTML 代码:**的 HTML 看起来是这样的:

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>Sign Up</title>
        <link rel=”stylesheet” href=”css/style.css”>
    </head>

    <body>
        . . .
    </body>

    </html>
    ```

*   **违规:**这里 CSS 只允许从 CDN 下载，但是在 HTML 代码中，浏览器会尝试从自己的本地文件加载，因为浏览器会发送以下违规。

    ```html
    {
    “csp-report”:{
    “document-uri”: “http://geeksforgeeks.com/signup.html”,
    “referrer”: “”,
    “blocked-uri”: “http://geeksforgeeks.com/css/style.css”,
    “violated-directive”: “style-src cdn.geeksforgeeks.com”,
    “original-policy”: “default-src ‘none’; 
    style-src cdn.geeksforgeeks.com; report-uri /_/csp-reports”,
    “disposition”: “report”
    }
    }

    ```

**支持的浏览器:**浏览器兼容 **HTTP 内容-安全-策略-仅报告**标题如下:

*   谷歌 Chrome 25.0
*   Internet Explorer 10.0
*   Firefox 23.0
*   Safari 7.0
*   Opera 15.0