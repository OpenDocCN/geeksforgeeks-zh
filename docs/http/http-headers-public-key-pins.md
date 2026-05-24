# HTTP 头|公钥密码

> 原文:[https://www.geeksforgeeks.org/http-headers-public-key-pins/](https://www.geeksforgeeks.org/http-headers-public-key-pins/)

**已弃用:**此功能不再推荐。由于它的复杂性和副作用，它在 2017 年被谷歌 Chrome 团队否决了。谷歌建议使用 **Expect-CT** 作为更好的选择。它已经从 90%的网络浏览器中移除，但是一些浏览器仍然支持它，只是为了兼容。

**HTTP 公钥锁定(HPKP)** 是在 HTTP 头的帮助下提供的一种互联网安全机制，允许 HTTPS 网站使用误用或欺诈的数字证书来抵御攻击者。这是通过向客户端(例如网络浏览器)传递一组公钥来实现的。这些密钥被传递给那些应该被信任的客户端，以便将来使用相同的域名进行连接。

例如，攻击者可能会侵入一个证书颁发机构，然后滥用网络来源的证书。为了降低这种风险，HTTPS web 服务器提供了一个“固定”公钥哈希列表，这些哈希在后续连接的给定时间内有效，在该有效时间内，客户端希望服务器在其证书链中使用一个或多个公钥。如果没有，屏幕上会显示一条错误消息。

```html
Header type: Response header
```

**语法:**

```html
Public-Key-Pins: pin-sha256 = "pin-value"; 
                 max-age = expire-time; 
                 includeSubDomains; 
                 report-uri = "uri"

```

**指令**

*   **pin–sha 256 =“pin–值”**
    此 pin 用于为不同的公钥指定多个 pin。未来我们还可以使用 SHA-256 以外的其他哈希算法。
*   **max-age = expire-time**
    此 pin 表示浏览器应记住使用其中一个定义的键访问网站的时间(秒)。
*   **包含域名**
    此 pin 指定网站的规则也适用于网站的子域。此参数是可选的。
*   **报告–uri =“uri”**
    此引脚发送引脚验证失败的报告。此参数也是可选的。

**例**

```html
Public-Key-Pins: 
  pin-sha256 = "cUPcTAZWKaASuYWhhneY3oBAkE3h2+soZS7sWs="; 
  pin-sha256 = "M8HztCzM3elS5P4hhyBNf6lHkmjAHKhpGPWE="; 
  max-age = 51000; 
  includeSubDomains; 
  report-uri = "https://www.geeksforgeeks.org/hpkp-report"

```

在本例中，第一个 pin**pin-sha 256 =“CupctazwkaaSuywHhny3 bake 3 H2+Sozs7 SWS =**是生产中使用的服务器公钥。
第二个针脚**针脚-sha 256 =“m8hztczm3els 5p 4 hhybnf6 hkmjakhpgpwe =”“T4”用作备用钥匙。
第三针**最大年龄= 51000** 告知客户端将此信息保存两个月(此时限由 IETF RFC 提供)。
第四个引脚**包含子域**表示密钥对所有子域有效。
最后最后一个 pin**report-uri = " https://www . geeksforgeeks . org/hpkp-report "**说明了在哪里报告 pin 验证失败。**

**浏览器兼容性:**与**公钥密码头**兼容的浏览器如下:

*   谷歌 Chrome
*   歌剧
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   微软边缘
*   旅行队