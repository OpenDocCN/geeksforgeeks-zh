# HTTP 头|警告

> 原文:[https://www.geeksforgeeks.org/http-headers-warning/](https://www.geeksforgeeks.org/http-headers-warning/)

[**HTTP 头**](https://www.geeksforgeeks.org/http-headers/) 允许客户和服务器通过 HTTP 请求或响应传递附加信息。**警告**通用 HTTP 头包含消息状态潜在问题的信息，这些问题可能不会反映在消息中。该字段本身由警告代码、警告代理、警告文本和可选的警告日期组成。作为响应，可能会出现多个警告标头。警告头字段可以应用于任何消息，但是，用于警告缓存操作可能缺乏语义透明度，并且只能应用于转换消息。

**语法:**

```html
Warning: <3-DIGIT-warn-code> <SP warn-agent> <SP warn-text> [< SP warn-date>]
```

**指令:**该标题接受上述四个指令，描述如下:

**<警告码> :** 是一个三位数的警告号，应该用自然语言书写，其中第一位数字表示批准后是否需要从存储的响应中删除警告。警告代码为 SIP 反应消息中的状态代码提供数据补充。1xx 和 2xx 范围内的警告代码特定于 HTTP。

*   **1xx** 警告码:描述响应的新鲜度或重新验证状态，重新验证成功后必须删除。它仅在批准缓存条目时由缓存生成。它不能由顾客产生。
*   **2xx** 警告代码:它描述了表示的某些方面，这些方面没有通过验证进行纠正，并且在批准后不会被缓存删除，除非发送完整的响应。

**< warn-agent > :** 表示哪个服务器添加/插入了头字段。添加警告标头的服务器或软件的名称或假名(当代理未知时，可能是“-”。

**<警告文本> :** 用引号括起来(警告文本=引号字符串)，显示错误的建议文本最有可能被接收响应的用户理解。

**<警告-日期> :** 可选。如果发送了一个以上的警告标题，请加入一个与[日期](https://www.geeksforgeeks.org/http-headers-date/)标题相匹配的日期(警告日期= HTTP-date)。

**Warn-codes 和推荐的 warn-text 在下表中列出:**

<figure class="table">

| 警告-代码 | 警告-文本 | 描述 |
| --- | --- | --- |
| One hundred and ten | 响应过时 | Whenever the sent response is outdated, it must be included. |
| One hundred and eleven | 重新验证失败 | If the cache tries to approve the failed response because it cannot reach the server and returns an outdated response, the cache must be merged. |
| One hundred and twelve | 断开操作 | If the cache is deliberately separated from the rest of the server network for a period of time, it should be merged. |
| One hundred and thirteen | 启发式过期 | If the cache tentatively selects a cache freshness lifetime greater than 24 hours, and the response age is greater than 24 hours, it must be encapsulated. |
| One hundred and ninety-nine | 杂项警告 | The warning text may include whimsical information to be introduced to customers. The framework that accepts this warning must not take any automated steps except to introduce the warning to customers. |
| Two hundred and fourteen | 应用的转换 | It should be merged by proxy or cache unless it applies any changes to the response, such as changing the content encoding, media type or entity body of the response, unless the warning code already appears in the response.
 |
| Two hundred and ninety-nine | 杂项持续警告 | This is the same as warn-code 199, however, a stubborn warning message is explained to the user. |

</figure>

**示例**:

```html
Warning: 246 - "Embedded Warning" "sat, 05 Oct 2019 10:47:47 GMT"

```

```html
Warning: 199 -"Miscellaneous warning" "sun, 18 Oct 2015 07:28:00 GMT"

```

**支持的浏览器:****HTTP 头警告**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧
*   边缘