# Node.js crypto.hkdfSync()方法

> 原文: [https://www.geeksforgeeks.org/node-js-crypto-hkdfsync-method/](https://www.geeksforgeeks.org/node-js-crypto-hkdfsync-method/)

该方法提供了基于同步 HMAC 的提取和扩展密钥派生函数密钥派生。给定`key`、`salt`和`info`，使用`digest`导出`keylen`字节的密钥。

## 语法

```js
crypto.hkdfSync(digest, key, salt, info, keylen)
```

## 参数

该方法有 5 个参数。

*   `digest`: 必须是一个字符串。
*   `key`: 最小长度 1 字节，类型可以是字符串、Buffer、ArrayBuffer、TypedArray、KeyObject 或 DataView。
*   `salt`: 必须提供，但可以是零长度且唯一的。可以是字符串、ArrayBuffer、Buffer、TypedArray 或 DataView。
*   `info`: 必须提供，但可以是零长度且不能超过 1024 字节。其类型是字符串、Buffer、ArrayBuffer、TypedArray、KeyObject 或 DataView。
*   `keylen`: 是要生成的密钥的长度，必须大于 0。必须是一个数字。

## 返回类型

以 Buffer 的形式返回派生键。

## 示例 1

### app.js

```js
// Node.js program to demonstrate the
// crypto.hkdfSync() Method.

// Including crypto module
import crypto from 'crypto'

//Implementing hkdfSync()
const Key = crypto.hkdfSync('sha512', 'key', 'salt', 'info', 64);

// Prints Buffer.
console.log(Key);
```

### 输出

```js
ArrayBuffer {
 [Uint8Contents]: <24 15 6e 2c 35 52 5b
 aa f3 d0 fb b9 2b 73 4c 80 32 a1 10 a3 f1 2e
 25 96 e4 41 e1 92 48 70 d8 4c 3a 50 06 52 a7
 23 73 80 24 43 24 51 04 6f d2 37 ef ad 83 92
 fb 68 6c 52 77 a5 9e 01 05 39 16 53>,
 byteLength: 64
}
```

## 示例 2

### app.js

```js
// Node.js program to demonstrate the
// crypto.hkdfSync() Method.

// Including crypto module
import crypto from 'crypto'

// Implementing hkdfSync()
const Key = crypto.hkdfSync('sha512', 'key', 'salt', 'info', 16);

// Prints Buffer.
console.log(Buffer.from(Key).toString('hex'));
```

### 输出

```js
24156e2c35525baaf3d0fbb92b734c80
```

## 示例 3

### JavaScript

```js
// Node.js program to demonstrate the
// crypto.hkdfSync() Method.

// Including crypto module
import crypto from 'crypto'

//Implementing hkdfSync()
const Key = crypto.hkdfSync('sha512', 'key', 'salt', 'info', 32);

// Prints Buffer.
console.log(Buffer.from(Key).toString('base64'));
```

### 输出

```js
JBVuLDVSW6rz0Pu5K3NMgDKhEKPxLiWW5EHhkkhw2Ew=
```

## 示例 4

### JavaScript

```js
// Node.js program to demonstrate the
// crypto.hkdfSync() Method.

// Including crypto module
import crypto from 'crypto'

// Implementing hkdfSync()
const Key = crypto.hkdfSync('sha512', 'key', 'salt', 'info', 32);

// Prints Buffer.
console.log(Buffer.from(Key).toString('ascii'));
```

### 输出

```js
$n,5R[*sP{9+sL 2!#q.%dAaHpXL
```

## 参考

[https://nodejs.org/api/crypto.html#crypto_crypto_hkdfsync_digest_key_salt_info_keylen](https://nodejs.org/api/crypto.html#crypto_crypto_hkdfsync_digest_key_salt_info_keylen)