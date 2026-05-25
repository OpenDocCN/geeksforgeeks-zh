# JSON Web 令牌 (JWT)

> 原文: [https://www.geeksforgeeks.org/json-web-token-jwt/](https://www.geeksforgeeks.org/json-web-token-jwt/)

JSON 网络令牌 (JWT) 是 JSON 对象，用于通过网络 (在双方之间) 安全地传输信息。它可以用于认证系统，也可以用于信息交换。令牌主要由头部、有效载荷、签名组成。这三个部分用点 (`.`) 连接。JWT 定义了我们从一方发送到另一方的信息的结构，它有两种形式：序列化与反序列化。序列化方法主要用于通过网络传输每个请求和响应的数据。而反序列化方法用于向 web 令牌读写数据。

## 反序列化

反序列化形式的 JWT 只包含头部和有效载荷。它们都是普通的 JSON 对象。

## 头部

JWT 头部主要用于描述应用于 JWT 的加密操作，如在其上使用的签名/解密技术。它还可以包含有关我们正在发送的信息的媒体/内容类型的数据。该信息以 JSON 对象的形式出现，然后该 JSON 对象被编码为 `BASE64URL`。头部中的加密操作定义了 JWT 是有符号的/无符号的还是加密的，以及使用什么算法技术。JWT 的一个简单头部如下所示：

```json
{
    "typ": "JWT",
    "alg": "HS256"
}
```

`"alg"` 和 `"typ"` 是具有不同值和不同功能的对象键，就像 `"typ"` 告诉我们这个信息包的头部类型，而 `"alg"` 告诉我们使用的加密算法。

### 注意

`HS256` 和 `RS256` 是我们在 JWT 头部部分使用的两个主要算法。一些 JWT 也可以在没有签名或加密的情况下创建。这种令牌被称为不安全的，它的头部应该将 `alg` 对象键的值指定为 `"none"`。

```json
{
    "alg": "none"
}
```

## 有效载荷

有效载荷是 JWT 的一部分，所有的用户数据实际上都是在这里添加的。这一数据也被称为 JWT 的“声明”。任何人都可以阅读这些信息，因此建议不要将任何机密信息放在这里。这部分通常包含用户信息。该信息以 JSON 对象的形式出现，然后该 JSON 对象被编码为 `BASE64URL`。我们可以在一个有效载荷中放入任意多的声明，尽管与头部不同，有效载荷中没有强制声明。带有有效载荷的 JWT 看起来像这样：

```json
{
    "userId": "b07f85be-45da",
    "iss": "https://provider.domain.com/",
    "sub": "auth/some-hash-here",
    "exp": 153452683
}
```

上面的 JWT 包含 `userId`、`iss`、`sub` 和 `exp`。所有这些都扮演着不同的角色，因为 `userId` 是我们存储的用户标识，`"iss"` 告诉我们发行者，`"sub"` 代表主题，`"exp"` 代表到期日期。

## 序列化

序列化形式的 JWT 表示以下格式的字符串：

```
[header].[payload].[signature]
```

所有这三个部分组成了序列化的 JWT。我们已经知道什么是头部和有效载荷，以及它们的用途。我们来谈谈签名。

## 签名

这是 JWT 的第三部分，用来验证令牌的真实性。`BASE64URL` 编码的头部和有效载荷用点 (`.`) 连接，然后使用在带有密钥的头部中定义的散列算法对其进行散列。然后，使用 `dot(.)` 将该签名附加到头部和有效载荷中。这形成了我们实际的令牌 `header.payload.signature`。

**语法：**

```
HASHINGALGO(base64UrlEncode(header) + "." + base64UrlEncode(payload), secret)
```

所以以上所有的组成部分共同构成了 JWT。现在让我们看看我们实际的令牌会是什么样子：

**JWT 示例：**

```json
header:
{
  "alg": "HS256",
  "typ": "JWT"
}

Payload:
{
  "id": 123456789,
  "name": "Joseph"
}

Secret: GeeksForGeeks
```

**JSON 网络令牌**

> eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTIzNDU2Nzg5LCJuYW1lIjoiSm9zZXBoIn0.opssw7e485lop5przscxhb7sr6saomrckffwi4rp7o