# HTTP 头 | 内容类型

> 原文: [https://www.geeksforgeeks.org/http-headers-content-type/](https://www.geeksforgeeks.org/http-headers-content-type/)

内容类型头用于指示资源的媒体类型。媒体类型是与文件一起发送的字符串，表示文件的格式。例如，对于图像文件，其媒体类型将像 `image/png` 或 `image/jpg` 等。

作为响应，它向客户端告知返回内容的类型。浏览器了解它必须加载到机器上的内容类型。每次浏览器通过内容类型头接收到文件的字节流时，浏览器都会执行一种称为 MIME 嗅探的操作，即它会检查正在接收的流，然后相应地加载数据。

## 语法

```
Content-Type: text/html; charset=UTF-8
Content-Type: multipart/form-data; boundary=something
```

## 指令

在 HTTP 头中有三个指令内容类型。

*   **媒体类型:** 保存数据的 MIME（多用途互联网邮件扩展）类型。
*   **字符集:** 保存字符编码标准。字符集是浏览器接收数据的编码标准。
*   **边界:** 当存在多部分实体时，需要边界指令。`Boundary` 用于由一组字符中的 70 个字符组成的多部分实体，已知这些字符通过电子邮件网关非常健壮，并且没有空格。

## 示例

本示例显示浏览器在设置或不设置内容类型标题的情况下如何读取图像。

```php
<?php
header('Content-type: image/jpeg'); //with header Content type
echo file_get_contents("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png");
?>
```

**输出:**
![](img/809ba4c1b8a40f7d6160dcba9cd06fd3.png)

现在不使用内容类型的标题，我们将获得以字节为单位的图像内容，所以它对我们没有任何用处。

```php
<?php
// Without header
echo file_get_contents("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png");
?>
```

**输出:**

```
?PNG  IHDRX??'?iCCPsRGB IEC61966-2.1(?u??+DQ??3????????????63??P????H?U????l??RDJV???9oF?
$sn????{N???pZ??^?d?Z(p?E?]??h??QEW?f??T??{, f???????????z?aE??????y???6%]>vkrA?;S?????d??M?
¡?6???`%?????&???Q-Z?j????BSZo?a???}N ?._u {??#??N?g?{-bKGD??????? pHYs.#.#x??vtIME?4_?X
IDATx??w?U??????MB$??$@@? 2t?"EDa???"? C?*C????Hq?ja??w ????????L{??}?}??w?;??{???{.4, ???j???
q10??_??h2]`P??:^?5??@?W?=????????XY??? w.??9??`z?1?!V??B????XM~^?|?1?qm???(?h??C?OV?js{e?+
L?b?{%?@`?+:sQ?@?
```

在这里，可以清楚地看到，通过应用内容类型头信息，浏览器可以知道它从服务器获得的响应类型。

## HTTP 内容类型头的所有可能值

| 类型 | 价值观念 |
| :--- | :--- |
| 应用 | `application/EDI-X12`<br>`application/EDIFACT`<br>`application/javascript`<br>`application/octet-stream`<br>`application/ogg`<br>`application/pdf`<br>`application/xhtml+xml`<br>`application/x-shockwave-flash`<br>`application/json`<br>`application/ld+json`<br>`application/xml`<br>`application/zip`<br>`application/x-www-form-urlencoded` |
| 声音的 | `audio/mpeg`<br>`audio/x-ms-wma`<br>`audio/vnd.rn-realaudio`<br>`audio/x-wav` |
| 图像 | `image/gif`<br>`image/jpeg`<br>`image/png`<br>`image/tiff`<br>`image/vnd.microsoft.icon`<br>`image/x-icon`<br>`image/vnd.djvu`<br>`image/svg+xml` |
| 几部分的 | `multipart/mixed`<br>`multipart/alternative`<br>`multipart/related`（通过使用 MHTML (HTML 邮件)。）<br>`multipart/form-data` |
| 文本 | `text/css`<br>`text/csv`<br>`text/html`<br>`text/javascript`（过时）<br>`text/plain`<br>`text/xml` |
| 录像 | `video/mpeg`<br>`video/mp4`<br>`video/quicktime`<br>`video/x-ms-wmv`<br>`video/x-msvideo`<br>`video/x-flv`<br>`video/webm` |
| 越南盾 | `application/vnd.oasis.opendocument.text`<br>`application/vnd.oasis.opendocument.spreadsheet`<br>`application/vnd.oasis.opendocument.presentation`<br>`application/vnd.oasis.opendocument.graphics`<br>`application/vnd.ms-excel`<br>`application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`<br>`application/vnd.ms-powerpoint`<br>`application/vnd.openxmlformats-officedocument.presentationml`<br>`application/msword` |

## 支持的浏览器

与 **HTTP 头内容类型** 兼容的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧

HTML 是网页的基础，通过构建网站和网络应用程序用于网页开发。您可以通过以下 [HTML 教程](https://www.geeksforgeeks.org/html-tutorials/) 和 [HTML 示例](https://www.geeksforgeeks.org/html-examples/) 从头开始学习 HTML。