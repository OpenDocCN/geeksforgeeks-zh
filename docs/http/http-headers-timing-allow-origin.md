# HTTP 头|计时-允许-起源

> 原文:[https://www . geesforgeks . org/http-headers-time-allow-origin/](https://www.geeksforgeeks.org/http-headers-timing-allow-origin/)

**计时-允许-原点(TAO)** 头是响应类型头。它用于指示允许读取从资源计时应用编程接口的特性中检索的属性值的所有来源。由于跨来源限制，分配给这些属性的默认值为“零”。

TAO 头可以是通配符(*)，允许所有源同时访问与定时相关的信息。然而，最好只指定几个来源，这有助于最大限度地减少可能泄露各种用户个人信息并导致严重后果的危险攻击。

**语法:**

```html
Timing-Allow-Origin: * 

```

运筹学

```html
Timing-Allow-Origin: <origin> [, <origin>]*

```

**指令:**该标题接受两个指令，如上所述，如下所述:

*   *** :** 该指令是一个通配符，允许任何源访问定时资源。

*   **<原点> :** 该指令表示单个 URI(统一资源标识符)或一组 URIs，用逗号分隔，可以访问定时资源。

**示例:**

*   当所有资源都被允许在通配符即“*”的帮助下访问各种定时资源时:

```html
Timing-Allow-Origin: * 

```

*   仅允许“https://www.geeksforgeeks.org”访问计时资源:

```html
Timing-Allow-Origin: https://www.geeksforgeeks.org 

```

**支持的浏览器:**浏览器兼容 **HTTP 定时-允许-起源头**如下:

*   谷歌 Chrome
*   边缘
*   歌剧
*   火狐浏览器
*   旅行队