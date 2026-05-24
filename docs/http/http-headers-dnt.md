# HTTP 标头| DNT

> 原文:[https://www.geeksforgeeks.org/http-headers-dnt/](https://www.geeksforgeeks.org/http-headers-dnt/)

**HTTP DNT 头**是一个请求头，允许用户选择他们的活动是否可以被他们通过 HTTP 通信的每个服务器和网络应用程序跟踪。生成的标题字段是一种允许用户选择加入或退出跟踪的机制。跟踪允许用户在网络上体验个性化内容。选择退出追踪是随着用户对隐私需求的增长而产生的。

只有当用户启用了**时，才能设置跟踪首选项。如果用户设置了**未启用**跟踪首选项，则不允许用户代理显示跟踪首选项表达式。**

****语法:****

```html
DNT:0
DNT:1 
```

****指令:****

**如果跟踪首选项设置为**启用****

***   **1:** The following field values are generated for the HTTP DNT header field: this instruction indicates that the user is prohibited from tracking at the target site.*   **0:** This instruction indicates that the user allows tracking on the given target site, or that the user has approved the exception.**

****注意:**DNT 报头字段可以有零个或多个扩展名。扩展由用户代理决定。如果定义了扩展名但未设置跟踪首选项，则可以在没有字段值的情况下插入 DNT 标头字段。**

****示例:****

***   This is an example of W3C (World Wide Web Consortium), in which a DNT header is set to the field value–1:

    ```html
    GET /something/here HTTP/1.1
    Host: example.com
    DNT: 1

    ```

    *   The value of DNT header field can be checked by using the **navigator.donottrack** property of JavaScript.

    ```html
    console.log(navigator.doNotTrack); 
    // prints "1" if DNT is enabled; "0" 
    // if the user opted-in for tracking;
    // prints "null" if unspecified

    ```

    1.  Safari 7.1.3+、Edge、IE11 及后续版本使用**窗口。donotrack** 而非**航海家。donotrack**
    2.  Before Firefox 32, **navigator.donotrack** reported yes and no values instead of 1 and 0.**

****支持的浏览器:**以下列出 **HTTP DNT 头文件**支持的浏览器**

**T5】谷歌 ChromeT7】Internet ExplorerT9】微软 EdgeT11】火狐 T13】OperaT15】**