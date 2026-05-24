# HTTP 头|保存-数据

> 原文:[https://www.geeksforgeeks.org/http-headers-save-data/](https://www.geeksforgeeks.org/http-headers-save-data/)

**保存数据**是一个 HTTP 请求类型的头。用于指示客户端是否要开启数据保存模式。在这里，数据使用是根据成本和性能来衡量的。任何浏览器的作用都是通过以最小的成本提供最高级别的性能来提供优化的用户体验。

*   **保存-数据:在**
    上，表示用户要启用数据保存模式。

*   **保存-数据:关闭**
    表示用户要禁用数据保存模式。

支持此功能的浏览器提供了切换到数据保存模式和从数据保存模式切换的选项。如果数据保存模式处于活动状态，则浏览器可以执行优化技术，如文本或图像压缩，这反过来将减少页面使用的数据量。

**语法:**

```html
Save-Data: <sd-token>
```

**指令:**该标题接受如上所述和如下所述的单个指令。

*   **< sd-token > :** 表示数据保存模式是开启还是关闭。

**示例 1:**
**使用保存数据:**使用保存数据，我们将检查标题类型“请求”和“响应”。

*   **请求标题:**

```html
GET /googlelogo.png HTTP/1.0 
Host: www.google.com
Save-Data: on
```

*   **响应标题:**

```html
HTTP/1.0 200 OK 
accept-ranges: bytes 
cache-control: private, max-age=31536000 
content-length: 5969 
content-type: image/png 
date: Thu, 14 May 2020 04:18:11 GMT 
expires: Thu, 14 May 2020 04:18:11 GMT 
last-modified: Tue, 22 Oct 2019 18:30:00 GMT 
server: sffe 
status: 200 
x-content-type-options: nosniff 
x-xss-protection: 0
```

**示例 2:**
**无保存数据:**无保存数据我们将检查标题类型“请求”和“响应”。

*   **请求标题:**

```html
GET /googlelogo.png HTTP/1.0 
Host: www.google.com
```

*   **响应标题:**

```html
HTTP/1.0 200 OK 
accept-ranges: bytes 
cache-control: private, max-age=31536000 
content-length: 1018
content-type: image/png 
date: Thu, 14 May 2020 04:18:11 GMT 
expires: Thu, 14 May 2020 04:18:11 GMT 
last-modified: Tue, 22 Oct 2019 18:30:00 GMT 
server: sffe 
status: 200 
x-content-type-options: nosniff 
x-xss-protection: 0
```

**注意:**输出的唯一区别是当保存数据模式被启用时，内容长度比保存数据模式被禁用时低得多。

**支持的浏览器:**支持的浏览器有 **HTTP 保存数据标题**如下:

*   谷歌 Chrome
*   微软边缘
*   歌剧
*   火狐浏览器