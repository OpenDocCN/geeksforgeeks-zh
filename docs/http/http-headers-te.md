# HTTP 标头|TE

> 原文:[https://www.geeksforgeeks.org/http-headers-te/](https://www.geeksforgeeks.org/http-headers-te/)

**HTTP TE** (也称为接受-传输-编码)是一个请求类型的头，它指定了用户愿意接受的传输编码。它与[传输编码](https://www.geeksforgeeks.org/http-headers-transfer-encoding/)响应头非常相似。不同的是，这个头使用了另一个被称为拖车的指令，它与分块指令非常相关。

**语法:**

```html
TE: compress | deflate | gzip | trailers | q
```

**注意:**可以使用多个指令。

**指令:**HTTP TE 头接受五个指令，如上所述，描述如下:

*   **压缩:**这是一种使用伦佩尔-齐夫-韦尔奇(LZW)算法作为传输编码名称的格式。
*   **deflate:** 这是一种被接受为使用 zlib 结构的传输编码名称的格式。
*   **gzip:** 这是一种 32 位循环冗余校验格式，使用伦佩尔-齐夫-韦尔奇(LZW)算法作为传输编码名称被接受。
*   **预告片:**它讲述了在分块传输编码中接受预告片字段的意愿。
*   **q:** 当使用多个指令时，它们由质量值加权，该质量值用于描述值的优先级。

**示例:**

*   当使用单一指令时。

    ```html
    TE: trailers
    ```

*   当使用多个指令时。

    ```html
    TE: trailers, compress; q=0.67
    ```

要检查运行中的 TE，请转到**检查元素- >网络**检查 TE 的响应头，如下所示。
T3】

**支持的浏览器:**与 **HTTP 头 TE** 兼容的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   微软边缘
*   火狐浏览器
*   歌剧
*   旅行队