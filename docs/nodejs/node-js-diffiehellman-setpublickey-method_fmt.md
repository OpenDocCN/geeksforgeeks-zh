# Node.js DiffieHellman.setPublicKey()方法

> 原文：[https://www.geeksforgeeks.org/node-js-diffiehellman-setpublickey-method/](https://www.geeksforgeeks.org/node-js-diffiehellman-setpublickey-method/)

`DiffieHellman.setPublicKey()`方法是加密模块内类`DiffieHellman`（`dh`）的内置应用编程接口，用于设置`dh`对象的**公钥**。

## 语法

```js
diffieHellman.setPublicKey(publicKey[, encoding])
```

## 参数

该方法接受以下两个参数：

*   `publicKey`：用于表示公钥。
*   `encoding`：用于编码`publicKey`的编码方式。如果提供了编码，则`publicKey`应为字符串；否则，它应为`Buffer`、`TypedArray`或`DataView`。

## 例 1

### index.js

```js
// Node.js program to demonstrate the
// diffieHellman.setPublicKey() Method
const crypto = require('crypto')

crypto.generateKeyPair('dh',
    {
        primeLength: 512,
        publicKeyEncoding: {
            type: 'spki',
            format: 'der'
        },
        publicKeyEncoding: {
            type: 'pkcs8',
            format: 'der'
        }
    },
    cb
)

function cb(err, publicKey, publicKey) {
    // Create Diffie-Hellman instance
    const dh = crypto.createDiffieHellman(512)
    // Set the dh's publicKey
    dh.setPublicKey(publicKey)

    if (publicKey.equals(dh.getPublicKey()))
        console.log("DH public Key is set successfully")
}
```

使用以下命令运行`index.js`文件：

```js
node index.js
```

**输出：**

```js
DH public Key is set successfully
```

## 例 2

### index.js

```js
// Node.js program to demonstrate the
// diffieHellman.setPublicKey() Method
const crypto = require('crypto')

crypto.generateKeyPair(
    'dh',
    { primeLength: 512 },
    cb
)

function cb(err, publicKey, publicKey) {
    // Export key from KeyObject
    publicKey = publicKey.export({ type: 'spki', format: 'der' })
    // Encode key in base64
    publicKey = publicKey.toString('base64');
    // Create Diffie-Hellman instance
    const dh = crypto.createDiffieHellman(512)
    // Set the dh's publicKey
    dh.setPublicKey(publicKey, 'base64')

    if (publicKey === dh.getPublicKey('base64'))
        console.log("DH public Key is set successfully")
}
```

使用以下命令运行`index.js`文件：

```js
node index.js
```

**输出：**

```js
DH public Key is set successfully
```

## 参考

[https://nodejs.org/api/crypto.html#crypto_diffiehellman_setpublickey_publickey_encoding](https://nodejs.org/api/crypto.html#crypto_diffiehellman_setpublickey_publickey_encoding)