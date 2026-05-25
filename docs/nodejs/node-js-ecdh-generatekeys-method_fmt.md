# Node.js `ecdh.generateKeys()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-ecdh-generatekeys-method/](https://www.geeksforgeeks.org/node-js-ecdh-generatekeys-method/)

`ecdh.generateKeys()` 方法是加密模块中 `ecdh` 类的内置应用程序编程接口，用于生成椭圆曲线 Diffie-Hellman (ECDH) 对象的私钥和公钥值。它只返回给定格式和编码的公钥。

## 语法

```js
ecdh.generateKeys( encoding, format )
```

## 参数

该方法接受两个参数，如下所述：

*   `encoding`: 这是一个字符串值，指定返回值的编码。
*   `format`: 是指定按键格式的字符串。该值可以是 `"compressed"` 或 `"uncompressed"`。

## 返回值

返回指定编码的椭圆曲线差分赫尔曼公钥。如果没有提供编码，则作为 `Buffer` 返回，否则返回字符串。

以下示例演示了这种方法：

### 例 1

```js
const crypto = require('crypto');

// Generate an ECDH object for geekA
const geek = crypto.createECDH('secp521r1');

// Generate keys for geek and return
// the public key
const geekAPublicKey = geek.generateKeys();

console.log(
  "Public Key of Geek A is:", geekAPublicKey);

// Get the private key of geek
const geekAPrivateKey = geek.getPrivateKey();
console.log(
  "Private Key of Geek A is:", geekAPrivateKey);
```

**输出:**

> Public Key of Geek A is: <Buffer e4 ad d9 a4 a6 e3 db a9 dc c8 c9 bb de b7 c4 c6 f9 e7 ... more bytes>
> Private Key of Geek A is: <Buffer 01 8f af 82 49 30 70 E0 47 1f 46 7d 3 99 50 8b 14 47 97 04 9d 3e 46 C7 B1 8e D1 C1 ad 6f de ea C7 A0 BC A8 af F2 C3 E0 46 df 74 BF 07 a3 36 a2 AC ... 16 more bytes>

### 例 2

```js
const crypto = require('crypto');

// Generate an ECDH object for geekA
const geekA = crypto.createECDH('secp521r1');

// Generate keys for geekA in base64 encoding
const geekAkey =
  geekA.generateKeys('base64');

console.log(
  "Public Key of Geek A is:", geekAkey);

// Generate an ECDH object for geekB
const geekB = crypto.createECDH('secp521r1');

// Generate keys for geekB in base64
// encoding and compressed
const geekBkey =
  geekB.generateKeys('base64', 'compressed');

console.log(
  "Public Key of Geek B is:", geekBkey);
```

**输出:**

> Public Key of Geek A is: bahbkh6uv0hazphqr+bva/GC8vrqtf0ltpnweoph+pdklhhhne9/xyi2pjdq1nhum/gekojksmead51q0ehge2y+iihb2gsluy7ho0oomlfrlm8ypaxnv6skbqsbngnyh/hebilillznfgurnsvsh4Rui0useoh/V6nfpefua==
> Public Key of Geek B is: ...

**参考:** [https://nodejs.org/api/crypto.html#crypto_ecdh_generatekeys_encoding_format](https://nodejs.org/api/crypto.html#crypto_ecdh_generatekeys_encoding_format)