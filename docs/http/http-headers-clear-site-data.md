# HTTP 头|清除-站点-数据

> 原文:[https://www.geeksforgeeks.org/http-headers-clear-site-data/](https://www.geeksforgeeks.org/http-headers-clear-site-data/)

**HTTP 头清除站点头**是一个响应类型的头。该标题用于**删除请求网站中的浏览数据**。这些浏览数据包括**缓存**、**cookie**、**存储**和**执行内容**。它有助于 web 开发人员提高对浏览器本地存储的数据的控制水平。

**语法:**

```html
Clear-Site-Data: "cache"|"cookies"|"storage"|"executionContexts"|"*"
```

**注意:**要删除的数据，方向应在**双引号(" ")内给出。**一次可以给出多个指令。

**指令:**这个头接受上面提到的下面描述的四个指令:

*   **[Cache]:** It means that the server wants **to delete the locally cached data** .
*   **[cookie]:** means that the server wants **to delete all cookies** as the source of the reply URL.
*   **"Store:** means that the server wants **to delete the locally stored data** .
*   **[executive content]:** means that the server wants **to delete all browsing content** as the source of the reply URL.
*   **"*":** It means that the server wants **to delete all types of data** as the source of the reply URL.

**示例:**

*   In this example, the header wants to delete **cache** , [T3】 cookie 【T4], **storage** and **execution content** data.

    ```html
    Clear-Site-Data: "cache", "cookies", "storage", "executionContents"
    ```

*   In this example, the header wants to delete all the data.

    ```html
    Clear-Site-Data: " * "
    ```

根据上述指令，相应类型的数据将被删除。要查看**清除-站点-数据**转到**检查元素- >网络**单击任何可见的名称，然后单击标题选项卡如果使用了此标题，您将可以看到它。

**支持的浏览器:**兼容 **HTTP 明文数据**的浏览器标题如下。