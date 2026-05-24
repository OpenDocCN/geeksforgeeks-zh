# HTTP 头| Tk

> 原文:[https://www.geeksforgeeks.org/http-headers-tk/](https://www.geeksforgeeks.org/http-headers-tk/)

**HTTP Tk 标头**是一个响应类型的标头，用于指示应用于相应请求的跟踪状态。

**语法:**

```html
Tk: !  (under construction)
Tk: N  (not tracking)
Tk: T  (tracking)
Tk: C  (tracking with consent)
Tk: P  (potential consent)
Tk: D  (disregarding DNT)
Tk: U  (updated)
Tk: ?  (dynamic)
Tk: G  (gateway or multiple parties)
```

**指令:**本表头接受九条指令，如上所述，描述如下:

*   **！ :** under development. The root server is currently testing its communication in the following states.
*   **？ :** Dynamic. The server needs more data to determine the following states.
*   **G:** Gateway or multiple parties. The server acts as the exchange door including many parties.
*   **n:** Not tracked.
*   **t:** Tracking.
*   **C:** Tracking with consent. The root server accepts that it has obtained early permission to track this client, client agent or gadget.
*   **P:** Potential consent. The root server doesn't know in real time whether it has obtained an earlier license to track the client, client agent or gadget, but it promises not to use or share any DNT 1:1 information before the license is decided, and promises to delete or permanently cancel the identification of any DNT 1:1 information without the license within 48 hours in advance.
*   **D:** Ignore DNT. The root server is unable or unwilling to consider the following tendencies obtained from the requesting client agent.
*   **u:** Update. The request may change the following states related to this client, client agent or gadget.

**示例**

*   The Tk header of a resource that claims not to follow will look like:

    ```html
    Tk: N
    ```

*   The Tk header of the resource that claims to follow will look like

    ```html
    Tk: T
    ```

**支持的浏览器:**浏览器的兼容性至今未知。