# Kerberos 和 NTLM 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-kerberos-and-ntlm/](https://www.geeksforgeeks.org/difference-between-kerberos-and-ntlm/)

## 1. Kerberos
`Kerberos` 是一种基于票证的身份验证系统，用于用户登录系统时的信息验证。`Kerberos` 基于对称密钥加密，依赖于可靠的第三方，在身份验证阶段使用私钥加密。为增强身份验证的安全性，开发了不同版本的 `Kerberos`。`Kerberos` 通常在微软产品中实现，如 `Windows 2000`、`Windows XP` 和更高版本的 `Windows`。

## 2. NTLM
`NTLM`（新技术局域网管理器）是微软专有的认证协议。`NTLM` 还基于对称密钥加密技术，需要资源服务器为用户提供身份验证、完整性和保密性。`NTLM` 不支持授权认证和双因素认证。`NTLM` 通常在较早的 `Windows` 版本中实现，如 `Windows 95`、`Windows 98`、`Windows ME`、`NT 4.0`。

## Kerberos 和 NTLM 的区别

| 序号 | Kerberos | NTLM |
| :--- | :--- | :--- |
| 1. | `Kerberos` 是一个开源软件，提供免费服务。 | `NTLM` 是微软专有的认证协议。 |
| 2. | `Kerberos` 支持多层应用程序中的身份验证委托。 | `NTLM` 不支持授权认证。 |
| 3. | `Kerberos` 支持双因素身份验证，如智能卡登录。 | `NTLM` 不提供智能卡登录。 |
| 4. | `Kerberos` 具有相互认证的特性。 | `NTLM` 没有相互认证的特点。 |
| 5. | `Kerberos` 提供了很高的安全性。 | 而与 `Kerberos` 相比，`NTLM` 的安全性较低。 |
| 6. | 微软 `Windows 2000`、`Windows XP` 和更高版本的 `Windows` 支持 `Kerberos`。 | `Windows 95`、`Windows 98`、`Windows ME`、`NT 4.0` 等较早的 `Windows` 版本也支持 `NTLM`。 |