# Node.js `ecdh.getPublicKey()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-ecdh-getpublickey-method/](https://www.geeksforgeeks.org/node-js-ecdh-getpublickey-method/)

`ecdh.getPublicKey()` 方法是加密模块中 `ecdh` 类的内置应用程序编程接口，用于获取指定编码的椭圆曲线 Diffie-Hellman (ECDH) 对象的公钥。密钥的编码可以使用 `encoding` 参数指定，格式可以使用 `format` 参数指定。

必须首先使用 `generateKeys()` 方法生成密钥，然后才能使用公钥检索它们。

**语法:**
```js
ecdh.getPublicKey( encoding, format )
```

**参数:** 该方法接受两个参数，如下所述：

*   `encoding`: 这是一个字符串值，指定返回值的编码。
*   `format`: 是指定按键格式的字符串。该值可以是 `"compressed"` 或 `"uncompressed"`。

**返回值:** 返回指定编码的椭圆曲线差分赫尔曼公钥。如果不提供编码，则作为 `Buffer` 返回，否则返回字符串。

**示例 1:** 以下示例说明了该方法：

## 示例 1

```js
const crypto = require('crypto');

// Generate an ECDH object for geekA
const geekA = crypto.createECDH('secp521r1');

// Generate an ECDH object for geekB
const geekB = crypto.createECDH('secp521r1');

// Generate the keys for both the geeks
geekA.generateKeys();
geekB.generateKeys();

// Get the public key for geekA
const geekAPublicKey = geekA.getPublicKey();

console.log("Public Key of Geek A is:", geekAPublicKey);

// Generate keys for geekB
const geekBPublicKey = geekB.getPublicKey();

console.log("Public Key of Geek B is:", geekBPublicKey);
```

**输出:**
> Public Key of Geek A is: <Buffer d4 a4 ef a2 e6 bd a6 fe a7 e2 e7 ce ae cc f3 ad ab ... more bytes>
> Public Key of Geek B is: <Buffer 04 01 03 2c 43 12 21 39 D2 D5 E8 DC BF F7 C6 cf B2 a3 15 62 00 47 50 83 2e 22 ce 54 20 13 DD fa D2 0c 0f 31 Fe B0 C5 1f af 65 a1 d0 B0 49 66 42 61 99 ... 83 more bytes>

**示例 2:**

## 示例 2

```js
const crypto = require('crypto');

// Generate an ECDH object for geekA
const geekA = crypto.createECDH('secp521r1');

// Generate an ECDH object for geekB
const geekB = crypto.createECDH('secp521r1');

// Generate the keys for both the geeks
geekA.generateKeys();
geekB.generateKeys();

// Get the public key for geekA in base64
const geekAPublicKey =
  geekA.getPublicKey('base64');

console.log(
  "Public Key of Geek A is:", geekAPublicKey);

// Generate keys for geekB in hex in
// the compressed format
const geekBPublicKey =
  geekB.getPublicKey('hex', 'compressed');

console.log(
  "Public Key of Geek B is:", geekBPublicKey);
```

**输出:**
> Public Key of Geek A is: bacc88Lu8xdew2wuiluluckcch0kqc79lilcyuj92auutiymp3cfstcd5gfkbf329L2wbzr4xwugqxagye6isnanamoxs2u4eo3nscmsi2+bxssjhykim8njqn m7vgsq4d0fpmgnwgfcjoo+v0vbb3zvepfswkwyti0wlf7kxa==t0]
> Public Key of Geek B is: 0301032c43122139d2d5e8dcbff7c6cfb2a31562004750832e22ce542013ddfad20c0f31feb0c51faf65a1d0b04966426199

**参考:** [https://nodejs.org/api/crypto.html#crypto_ecdh_getpublickey_encoding_format](https://nodejs.org/api/crypto.html#crypto_ecdh_getpublickey_encoding_format)