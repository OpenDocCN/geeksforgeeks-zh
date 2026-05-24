# HTTP 头|推荐人-策略

> 原文:[https://www.geeksforgeeks.org/http-headers-referrer-policy/](https://www.geeksforgeeks.org/http-headers-referrer-policy/)

**推荐人策略** HTTP 头设置了请求时与推荐人头一起发送的信息量参数。Referrer 策略用于在获取资源或执行导航时维护源帐户的安全性和隐私性。这是通过修改用于填充推荐人*标题*的算法来完成的。

**推荐者策略**可以通过各种方法为请求提供。这可以通过简单地使用 HTTP 头或 HTML 中的*元*元素来完成，该元素以 *referrer* 关键字为值，进而允许通过标记来设置 referrer 策略，或者使用 [**HTML 中的 *referrerpolicy* 内容属性**](https://www.geeksforgeeks.org/html-tutorials/) 。 [**CSS**](https://www.geeksforgeeks.org/css-tutorials/) 在使用*样式*属性时，参考所有者文档的引用策略，对于外部**样式表**可以重写策略，这些样式表的默认值为*“降级时无引用”*。

**语法:**

```html
Referrer-Policy : no-referrer
Referrer-Policy : no-referrer-when-downgrade
Referrer-Policy : origin
Referrer-Policy : strict-origin
Referrer-Policy : origin-when-cross-origin
Referrer-Policy : strict-origin-when-cross-origin
Referrer-Policy : same-origin
Referrer-Policy : unsafe-url
```

**指令:**此标题接受八个指令，如上所述，如下所述:

*   **No referrer:** This will not send referrer information with the request.
*   **No recommender-when-downgrade:** This will send the complete website information to a potential trusted website, which comes from *modern* HTTPS state or non-modern **HTTPS** state. Message sent to **https-> https** and **http-> https** transitions. This is the default referrer-policy.
*   **Origin:** It only sends the origin value of the requesting client when making requests from the same origin (same website) or across origins (different websites).
*   **Strict-Origin:** This will only send origin information to potentially trusted websites from modern **HTTPS** states or from non-modern **HTTPS** states to any origin.
*   **Origin-when-across origin:** When making a request at the same origin, send complete URL information, and when making a request across origin, send only the origin information.
*   **Strict-origin-when-cross origin:** It sends complete website information when processing requests from the same origin. It only sends source information to potentially trusted websites from modern **HTTPS** states or non-modern **HTTPS** states. No recommender information was sent to potentially untrusted websites.
*   **Homologous:** When the origin is in the same website, but there is no cross-origin information sent, the referral information will be sent.
*   **unsafe-url:** It sends complete URL information regardless of any standard.

**示例:**这是万维网联盟给出的标准示例。此处的示例列出了请求作为导航网站发送到的网站以及与其一起发送的推荐人信息。为方便起见，**https://example.com/page.html**将被视为每个示例的原点。

*   **None-Referral**

```html
Navigation website : https://notexample.com/page.html (or any other website)
Referrer : no referrer sent
```

*   **None-referrer-pawn-demotion**

```html
Navigation website : https://not.example.com/ 
Referrer : https://example.com/page.html
-------------------------------------------
Navigation Website : http://not.example.com/
Referrer : no referrer sent
```

*   **Origin**

*   **Strict-origin**

```html
Navigation Website : https://not.example.com
Referrer : https://example.com/.
---------------------------------------------
Navigation Website : http://not.example.com
Referrer : no-referrer 
---------------------------------------------
Origin Website : http://example.com/page.html
Navigation Website : any trustworthy or non-trustworthy URL
Referrer : http://example.com/
```

*   Origin-when-cross origin

**支持的浏览器:**下面列出了 **HTTP 头 Referrer-Policy** 支持的浏览器