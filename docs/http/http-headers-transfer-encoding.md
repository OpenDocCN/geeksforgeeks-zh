# HTTP 头|传输编码

> 原文:[https://www . geesforgeks . org/http-headers-transfer-encoding/](https://www.geeksforgeeks.org/http-headers-transfer-encoding/)

**HTTP 传输编码**是一个响应类型的报头，作为逐跳报头执行，逐跳报头连接是单个传输级连接，不得重新传输。该报头在两个节点之间执行(单个传输级连接)。如果有多节点连接，则必须使用其他`Transfer-Encoding`值。有一个端到端 [`Content-Encoding`](https://www.geeksforgeeks.org/http-headers-content-encoding/) 头，可用于压缩整个连接上的数据。

**语法:**

```html
Transfer-Encoding: chunked | compress | deflate | gzip | identity
```

**指令:**该标题接受上面提到的和下面描述的五个指令:

*   **分块:**该指令用于以块格式发送数据序列，但在以十六进制格式发送数据块之前，必须提到每个块的长度，如`'\r\n'`，然后是块本身，接着是另一个`'\r\n'`。
*   **压缩:**这是一种使用伦佩尔-齐夫-韦尔奇(LZW)算法的压缩格式。
*   **deflate:** 这是一种使用 zlib 结构的压缩格式，带有 deflate 压缩算法。
*   **gzip:** 这是一种使用莱姆佩尔-齐夫编码(LZ77)的压缩格式，带有 32 位循环冗余校验。
*   **标识:**该指令指示始终可接受的标识功能。

**注意:**终止组块是常规组块，这些组块的长度默认为零。

**示例:**当服务器向客户端发送大量的系列数据时，这个头的块编码非常有用。在请求完成之前，响应的总大小可能未知。假设数据库查询中有大量数据，分块响应如下所示

```html
HTTP/1.0 200 OK 
Content-Type: text/plain 
Transfer-Encoding: chunked

0\r\n
Mozilla\r\n 
7\r\n
Developer\r\n
9\r\n
Network\r\n
0\r\n 
\r\n
```

要检查此传输编码是否有效，请转到**检查元素- >网络**检查传输编码的请求头，如下所示，传输编码高亮显示，您可以看到。
T3】

**支持的浏览器:**浏览器兼容 **HTTP 传输编码**标题如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧