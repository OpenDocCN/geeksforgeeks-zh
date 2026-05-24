# HTTP 头

> 原文:[https://www.geeksforgeeks.org/http-headers/](https://www.geeksforgeeks.org/http-headers/)

**HTTP 头**用于通过**请求**和**响应**头在客户端和服务器之间传递附加信息。所有标题都不区分大小写，标题字段用冒号分隔，键值对采用明文字符串格式。由空字段标题表示的标题部分的结尾。有几个标题字段可以包含注释。一些头可以包含用等号分隔的质量(q)键值对。

**上下文中有四种标题:**

*   **常规头:**这种类型的头应用于请求和响应头，但不会影响数据库主体。
*   **请求头:**这种类型的头包含关于客户端提取的请求的信息。
*   **响应头:**这种类型的头包含客户端请求的源的位置。
*   **实体头:**这种类型的头包含关于资源主体的信息，如 MIME 类型、内容长度。

**头也可以根据代理如何处理它们来分类:**

*   [**连接**](https://www.geeksforgeeks.org/http-headers-connection/)
*   [](#)
*   **[**代理-认证**](https://www.geeksforgeeks.org/http-headers-proxy-authenticate/)**
*   **[**代理-授权**](https://www.geeksforgeeks.org/http-headers-proxy-authorization/)**
*   **[**【te】**](#)**
*   **[**拖车**](https://www.geeksforgeeks.org/http-headers-trailer/)**
*   **[**传输编码**](https://www.geeksforgeeks.org/http-headers-transfer-encoding/)**
*   ****认证**T2】**

<figure class="table">

| 页眉 | 描述 |
| [授权](#) | 它用于请求受限文档。 |
| [代理-认证](https://www.geeksforgeeks.org/http-headers-proxy-authenticate/) | 它是一个响应头，通过定义授权方法来访问资源文件。它允许代理服务器通过验证它来进一步传输请求。 |
| [代理授权](https://www.geeksforgeeks.org/http-headers-proxy-authorization/) | 它是请求类型的头。此标头包含在用户代理和用户指定的服务器之间进行身份验证的凭据。 |
| [WWW-认证](#) | 它是定义身份验证方法的响应头。它应该用于获取对资源的访问。 |

</figure>

*   ****缓存**** 

<figure class="table">

| 页眉 | 描述 |
| [年龄](https://www.geeksforgeeks.org/http-headers-age/) | 这是一个响应头。它以秒为单位定义对象在代理缓存中的时间。 |
| [缓存控制](#) | 这是一个通用类型头，用于指定缓存机制的指令。 |
| [清理现场数据](https://www.geeksforgeeks.org/http-headers-clear-site-data/) | 这是一个响应类型的头。该标题用于删除请求网站中的浏览数据。 |
| [到期](#) | 它是一个响应类型的标题，用于定义在该时间之后将消失的日期/时间。 |
| [语用学〔t1〕](#) | 它是一般类型的头，但是没有指定响应行为，因此是特定于实现的。 |
| [警告](#) | 这是一个通用类型头，用于向客户端通知可能的问题。 |

</figure>

*   ****客户端提示**T2】**

<figure class="table">

| 页眉 | 描述 |
| 接受-CH | 这是一个响应类型的头。它指定客户端应该在后续请求中包含哪些客户端提示头。 |
| 接受生命周期 | 它是一个响应类型的头，用于指定 Accept-CH 头值的持久性。 |
| 内容-DPR | 这是一个响应类型的头。它用于定义所选图像响应的物理像素与 CSS 像素之间的比率。 |
| DPR | 它是响应类型的标题，用于定义设备当前窗口的物理像素与 CSS 像素的比率。 |
| 设备-内存 | 它用于指定客户端设备上剩余的大致 ram。 |
| [早期数据](#) | 它是一个请求类型的头。该报头用于指示请求已经在早期数据中传送。 |
| [保存-数据](#) | 它用于减少客户端的数据使用。 |
| 视口宽度 | 它用于以 CSS 像素表示布局视口宽度。 |
| 宽度 | 它是一个请求类型的头。该标题用于以物理像素表示所需的资源宽度。 |

</figure>

*   ****条件句**** 

<figure class="table">

| 页眉 | 描述 |
| [最后修改的](https://www.geeksforgeeks.org/http-headers-last-modified/) | 最后修改的响应报头是由服务器发送的报头，指定了所请求的源的最后修改日期。这是 HTTP 头最后修改的正式定义 |
| [ETag](#) | 它是一个响应类型的头，用作特定版本资源的标识符。 |
| [如果匹配](#) | 它是一个请求类型的头。它用于使请求有条件。 |
| [如果-无-匹配](https://www.geeksforgeeks.org/http-headers-if-none-match/) | 它是一个请求类型的头。通常，它用于更新服务器上的实体标签。首先，客户机向服务器提供一组实体标签(电子标签)。 |
| [如果-修改-自](#) | 它是一个请求类型的头。如果实体在指定日期后被修改，则此标题用于使请求有条件，并期望实体被传输。 |
| [如果-未修改-自](#) | 它是一个请求类型的头。如果该实体在指定日期后未被修改，则该标头用于使请求有条件，并期望发送该实体。 |
| [变化](#) | 它是响应类型的头。服务器使用它来指示在内容协商算法中选择资源表示时使用了哪些头。 |

</figure>

*   ****连接管理**** 

<figure class="table">

| 页眉 | 描述 |
| [连接](https://www.geeksforgeeks.org/http-headers-connection/) | 它是一个通用类型头，允许发送方或客户端指定特定连接所需的选项。 |
| [保活](#) | 这是一个通用类型的头，用于通知持久连接应该保持打开的时间。 |

</figure>

*   ****内容谈判**** 

<figure class="table">

| 页眉 | 描述 |
| [接受](https://www.geeksforgeeks.org/http-headers-accept/) | 这是一个请求类型头。接受头用于由客户机通知服务器，客户机可以理解哪种内容类型，表示为 MIME 类型。 |
| [接受-字符集](https://www.geeksforgeeks.org/http-headers-accept-charset/) | 这是一个请求类型头。此标头用于指示服务器响应可接受的字符集。 |
| [接受-编码](https://www.geeksforgeeks.org/http-headers-accept-encoding/) | 这是一个响应类型的头。通常是请求头的比较算法。所有的 HTTP 客户端都用来告诉服务器它支持哪种编码。 |
| [接受-语言](https://www.geeksforgeeks.org/http-headers-accept-language/) | 它是一个请求类型的头，告诉服务器客户端可以理解的所有语言。 |

</figure>

*   ****控制**** 

<figure class="table">

| 页眉 | 描述 |
| [期待](https://www.geeksforgeeks.org/http-headers-expect/) | 这是一个请求类型头。它用于指示服务器为了响应客户端而需要满足的特定行为或期望。通常，期望:100-继续是为标题字段定义的唯一期望。 |

</figure>

*   ****饼干**T2】**

<figure class="table">

| 页眉 | 描述 |
| [饼干](https://www.geeksforgeeks.org/http-headers-cookie/) | 这是一个请求类型头。用户发送到服务器的请求中使用的 cookie。 |
| [设置-饼干](https://www.geeksforgeeks.org/http-headers-set-cookie/) | 它是一个响应头，用于将 cookies 从服务器发送到用户代理。因此，用户代理可以稍后将它们发送回服务器，以便服务器可以检测到用户。 |
| [烹饪 2](#) | 这是一个请求类型头。用户发送给服务器的请求中使用的 cookie2。 |
| [设置-烹饪 2](https://www.geeksforgeeks.org/http-headers-set-cookie2/) | 它是响应类型头，已经过时。它提供了从客户端向服务器提供和检索状态信息的机制。 |

</figure>

*   ****颜色**** 

<figure class="table">

| 页眉 | 描述 |
| [访问控制-允许-起源](https://www.geeksforgeeks.org/http-headers-access-control-allow-origin/) | 它是一个响应头，用于指示该响应是否可以与来自给定来源的请求代码共享。 |
| [访问控制-允许-凭证](https://www.geeksforgeeks.org/http-headers-access-control-allow-credentials/) | 这是一个响应头。访问控制允许凭证头用于告诉浏览器，当请求的凭证模式为请求时，向前端 JavaScript 代码公开响应。 |
| [访问控制-允许-标题](#) | 它是一个响应头，用于公开其中提到的头。默认情况下，已经公开了 6 个响应头，称为 CORS 安全列表响应头。 |
| [访问控制允许方法](#) | 它是一个响应类型头，指定访问资源时允许的一个或多个方法。 |
| [访问控制-公开-标题](#) | 它是一个响应类型的头，指示可以公开哪些头。 |
| [访问控制-最大年龄](https://www.geeksforgeeks.org/http-headers-access-control-max-age/) | 它是一个响应头，给出了 CORS 飞行前请求的结果可以被缓存的时间，该请求检查 CORS 协议是否被理解，以及服务器是否知道使用特定的方法和头。 |
| [访问控制请求标题](#) | 它是一个请求类型头，它让服务器知道在发出实际请求时将使用哪些 HTTP 头。 |
| [访问控制请求方法](#) | 它是一个请求类型头，它让服务器知道在发出实际请求时将使用哪种 HTTP 方法。 |
| [原点](https://www.geeksforgeeks.org/http-headers-origin/) | 它是一个响应 HTTP 头，指示启动 HTTP 请求的安全上下文，而不指示路径信息。 |
| [计时-允许-原点](#) | 这是一个响应类型头。它指定允许查看通过资源计时应用编程接口的特性检索的属性值的原点。 |

</figure>

*   ****不追踪**** 

<figure class="table">

| 页眉 | 描述 |
| [DNT](#) | 这是一个请求类型头。它让用户表明他们是否更喜欢隐私而不是个性化内容。 |
| [TK](#) | 它是一个响应类型头，它指示跟踪状态。 |

</figure>

*   ****下载**T2】**

<figure class="table">

| 页眉 | 描述 |
| [内容-处置](#) | 它是正文的响应类型头。它让用户指示传输的资源应该以内嵌方式显示，或者应该下载并显示“另存为”对话框。 |

</figure>

*   ****消息正文信息**** 

<figure class="table">

| 页眉 | 描述 |
| [内容-长度](https://www.geeksforgeeks.org/http-headers-content-length/) | 这是一个响应类型头。它用于以八进制数(即字节数)表示实体体的大小，并将其发送给接收方。这是一个禁止的标题名称。 |
| [内容类型](https://www.geeksforgeeks.org/http-headers-content-type/) | 它是一个实体类型头。它用于指示资源的媒体类型。媒体类型是与文件一起发送的字符串，表示文件的格式。 |
| [内容编码](https://www.geeksforgeeks.org/http-headers-content-encoding/) | 这是一个响应类型头。它用于压缩媒体类型。它通知服务器用户将支持哪种编码。 |
| [内容-语言](https://www.geeksforgeeks.org/http-headers-content-language/) | 它是一个实体类型头。它用于定义说话者文档要使用哪种语言。它没有定义文档的语言。 |
| [内容-位置](https://www.geeksforgeeks.org/http-headers-content-location/) | 它是一个实体类型头，为返回的数据提供了另一个位置，并通过指示直接的 URL 告诉如何访问资源。 |

</figure>

*   ****代理人**** 

<figure class="table">

| 页眉 | 描述 |
| [转发](#) | 它是一个请求类型的头。它用于存储代理服务器面向客户端的一面，当请求路径中涉及代理时，该面会丢失。 |
| [X-转发-用于](https://www.geeksforgeeks.org/http-headers-x-forwarded-for/) | 它是一个请求类型的报头，是 Forwarded 报头的替代和事实上的标准版本，当客户端通过 HTTP 代理或负载平衡器连接到网络服务器时使用，用于识别原始 IP 地址。 |
| [X-转发主机](#) | 它是一个请求类型的头。它用于在主机 HTTP 请求头中标识客户端请求的原始主机。 |
| [X-转发原型](https://www.geeksforgeeks.org/http-headers-x-forwarded-proto/) | 这是一个请求类型的头。它用于标识客户端用来连接代理或负载平衡器的协议。它可以是 HTTP 或 HTTPS。 |
| [通过](https://www.geeksforgeeks.org/http-headers-via/) | 它是一个通用类型的头，用于通知服务器通过其发送请求的代理。 |

</figure>

*   ****重定向**T2】**

<figure class="table">

| 页眉 | 描述 |
| [位置](https://www.geeksforgeeks.org/http-headers-location/) | 它是一个响应头，用于在两种情况下要求浏览器重定向一个网址(状态代码 3xx)或提供关于新创建的资源的位置信息(状态代码 201)。 |

</figure>

*   ****请求上下文**** 

<figure class="table">

| 页眉 | 描述 |
| [从](#)开始 | 它是一个请求类型的标题，用于包含控制请求用户代理的人类用户的互联网电子邮件地址。 |
| [主机](https://www.geeksforgeeks.org/http-headers-host/) | 它是一个请求类型的头。它用于表示服务器的域名。它也可以代表服务器使用的传输控制协议端口号。 |
| [推荐人](#) | 这是一个请求类型头。这是用来保存这个新页面所在的上一页链接，以便浏览器的后退按钮可以工作。 |
| [推荐人-政策](#) | 这是一个响应类型头。它用于定义请求中应包含多少推荐人信息。 |
| [用户代理](https://www.geeksforgeeks.org/http-headers-user-agent/) | 它是一个请求头，允许一个特征字符串，该字符串允许网络协议对等方识别网络服务器的操作系统和浏览器。 |

</figure>

*   ****范围请求**** 

<figure class="table">

| 页眉 | 描述 |
| [接受范围](https://www.geeksforgeeks.org/http-headers-accept-ranges/) | 它是响应类型头，也是范围系统的一部分。这个头充当服务器用来支持客户端部分请求的标记。 |
| [范围](https://www.geeksforgeeks.org/http-headers-range/) | 它是请求类型的头，用于从服务器获取文档的一部分。如果服务器返回文档的该部分，它将使用 206(部分内容)状态代码。 |
| [中频范围](#) | 这是一个请求类型头。这用于使范围请求有条件。 |
| [含量-范围](https://www.geeksforgeeks.org/http-headers-content-range/) | 它是一个响应头，指示部分消息在全身按摩中的归属。 |

</figure>

*   ****安全**T2】**

<figure class="table">

| 页眉 | 描述 |
| [跨产地-资源-政策](#) | 它是响应类型的头，并通知客户端浏览器阻止对给定资源的跨来源/跨站点请求。 |
| [内容-安全-策略](#) | 它是响应类型的头，用于允许网站管理员控制资源。 |
| [内容-安全-策略-仅报告](https://www.geeksforgeeks.org/http-headers-content-security-policy-report-only/) | 它是一个响应头，允许 web 开发人员通过关注策略的效果来测试策略。 |
| [预计-CT](#) | 它是一个响应头，可以防止错误地为站点颁发证书，并确保它们不会被忽视。 |
| [功能-策略](#) | 这是一个响应类型头，用于允许或拒绝在其自己的帧上使用功能。 |
| [公钥密码](#) | 这是一个响应头。它将特定的加密公钥与某个 web 服务器相关联。 |
| [公钥-pin-仅限报告](#) | 这是一个响应类型头。它用于向 report-uri 报告。 |
| [严格-运输-安全](https://www.geeksforgeeks.org/http-headers-strict-transport-security/) | 这是一个响应类型头。这是一种网络安全策略机制，有助于保护网站免受恶意活动的攻击，并通过响应头通知用户代理和网络浏览器如何处理其连接。 |
| [升级-不安全-请求](https://www.geeksforgeeks.org/http-headers-upgrade-insecure-requests/) | 这是一个请求类型头。它向服务器发送一个信号，表达客户端对加密和验证响应的偏好 |
| [X-内容-类型-选项](https://www.geeksforgeeks.org/http-headers-x-content-type-options/) | 这是一个响应类型头。它充当一个标记，指示内容类型头中的 MIME 类型头不应更改为服务器。 |
| [X-框架-选项](https://www.geeksforgeeks.org/http-headers-x-frame-options/) | 这是一个响应头。它用于防止网站遭受点击劫持攻击。它定义了是否允许浏览器在、<iframe>、<embed>或<object>中呈现页面。</object></embed></iframe> |
| [X-XSS 保护](https://www.geeksforgeeks.org/http-headers-x-xss-protection/) | 这是一个响应类型的头。它用于启用跨站点脚本过滤。 |

</figure>

*   ****转移编码**** 

<figure class="table">

| 页眉 | 描述 |
| [传输编码](https://www.geeksforgeeks.org/http-headers-transfer-encoding/) | 它是一个响应类型的报头，作为逐跳报头执行，逐跳报头连接是单个传输级连接，不得重新传输。 |
| [TE](#) | 请求类型头用于指定用户代理愿意接受的传输编码。 |
| [拖车](https://www.geeksforgeeks.org/http-headers-trailer/) | 它是一个响应头，指示给定的头字段集出现在用分块传输编码编码的消息的尾部。 |

</figure>

*   ****网络插座**** 

<figure class="table">

| 页眉 | 描述 |
| [秒-网络套接字-接受](#) | 这是响应类型的标题类别。这被服务器用来告知客户端它知道这是一个网络套接字连接，并且它准备打开连接。 |

</figure>

*   ****其他标题**** 

<figure class="table">

| 页眉 | 描述 |
| [Alt-Svc](#) | 它用于以另一种方式访问网站。 |
| [日期](https://www.geeksforgeeks.org/http-headers-date/) | 它是一个通用类型的头，用于通过 HTTP 响应或 HTTP 请求传递附加信息。 |
| [大额分配](#) | 它是一个响应类型的头，通知支持的浏览器(目前只有火狐)内存的需求，让他们确保大分配成功，并使用一些未碎片化的内存启动一个新的进程。 |
| [链接](#) | 它是实体类型的头，用于序列化 HTTP 头中的一个或多个链接。 |
| [重试-在](https://www.geeksforgeeks.org/http-headers-retry-after/)之后 | 它是响应类型的头，用于通过 HTTP 请求或响应传递附加信息。HTTP 重试后标头是一个 HTTP 响应标头，它指示在发出另一个请求之前要等待多长时间。 |
| [服务器计时](https://www.geeksforgeeks.org/http-headers-server-timing/) | 它是一个响应类型的头。该报头用于在来自用户代理的给定请求-响应周期的两个或多个度量和描述之间进行通信。 |
| 来源图 | 它是一个响应类型的头，用于从转换后的源映射原始源。例如，在执行时，浏览器会将 JavaScript 资源从其原始来源转换为其他来源。 |
| [X-DNS-预取-控制](#) | 它是用于控制域名系统预取的响应类型头。 |

</figure>

*   ****Ent-to-End headers:** This type of headers should be transmitted to the final recipient of the message so the server can make a request to the clients and the client can respond to that requests. The intermediate proxies must retransmit these headers as unmodified. 

    **逐跳报头:**这种类型的报头仅适用于单个传输级连接。这种硬盘不应该被代理重传或缓存。**