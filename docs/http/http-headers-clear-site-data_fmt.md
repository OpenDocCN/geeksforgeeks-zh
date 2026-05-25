# HTTP 头 | Clear-Site-Data

> 原文: [https://www.geeksforgeeks.org/http-headers-clear-site-data/](https://www.geeksforgeeks.org/http-headers-clear-site-data/)

`Clear-Site-Data` 是一个响应头。该头用于**删除请求网站中的浏览数据**。这些浏览数据包括**缓存**、**cookie**、**存储**和**执行上下文**。它有助于 web 开发人员提高对浏览器本地存储的数据的控制水平。

## 语法:

```html
Clear-Site-Data: "cache"|"cookies"|"storage"|"executionContexts"|"*"
```

## 注意:

要删除的数据，值应在**双引号（`" "`）内给出**。一次可以给出多个指令。

## 指令:

这个头接受上面提到的下面描述的四个指令：

*   **`"cache"`:** 表示服务器希望**删除本地缓存的数据**。
*   **`"cookies"`:** 表示服务器希望**删除所有 cookie**（针对响应 URL 的源）。
*   **`"storage"`:** 表示服务器希望**删除本地存储的数据**。
*   **`"executionContexts"`:** 表示服务器希望**删除所有浏览上下文**（针对响应 URL 的源）。
*   **`"*"`:** 表示服务器希望**删除所有类型的数据**（针对响应 URL 的源）。

## 示例:

*   在此示例中，该头希望删除**缓存**、**cookie**、**存储**和**执行上下文**数据。

    ```html
    Clear-Site-Data: "cache", "cookies", "storage", "executionContexts"
    ```

*   在此示例中，该头希望删除所有数据。

    ```html
    Clear-Site-Data: "*"
    ```

根据上述指令，相应类型的数据将被删除。要查看 `Clear-Site-Data`，请转到**检查元素 -> 网络**，单击任何可见的名称，然后单击**标头**选项卡。如果使用了此头，您将可以看到它。

## 支持的浏览器:

兼容 `Clear-Site-Data` HTTP 响应头的浏览器如下。