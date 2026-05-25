# Node.js crypto.privateEncrypt() 方法

> 原文: [https://www.geeksforgeeks.org/node-js-crypto-privateencrypt-method/](https://www.geeksforgeeks.org/node-js-crypto-privateencrypt-method/)

`crypto.privateEncrypt()` 方法用于使用参数 `privateKey` 加密缓冲区的指定内容。

## 语法

```js
crypto.privateEncrypt( privateKey, buffer )
```

## 参数

这个方法接受上面提到的和下面描述的两个参数：

*   **privateKey**: 它可以存储 `Object`、`string`、`Buffer` 或 `KeyObject` 类型的数据。
    1.  **Key**: 是一个 PEM 编码的私钥。类型为 `string`、`Buffer` 或 `KeyObject`。
    2.  **Passphrase**: 私钥的可选密码短语，可以是 `string` 或 `Buffer`。
    3.  **padding**: 是 `crypto.constants` 中定义的一个可选填充值，可以是 `crypto.constants.RSA_NO_PADDING` 或 `crypto.constants.RSA_PKCS1_PADDING`。它是一个密码常量。
*   **buffer**: 包含 `Buffer`、`TypedArray` 或 `DataView` 类型的数据。

## 返回值

返回一个包含加密内容的新 `Buffer`。

下面的例子说明了 `crypto.privateEncrypt()` 方法在 Node.js 中的使用：

## 示例

### 例 1

```js
// Node.js program to demonstrate the
// crypto.privateEncrypt() method

// Including crypto and fs module
const crypto = require('crypto');
const fs = require("fs");

// Using a function generateKeyFiles
function generateKeyFiles() {

    const keyPair = crypto.generateKeyPairSync('rsa', {
        modulusLength: 520,
        publicKeyEncoding: {
            type: 'spki',
            format: 'pem'
        },
        privateKeyEncoding: {
            type: 'pkcs8',
            format: 'pem',
            cipher: 'aes-256-cbc',
            passphrase: ''
        }
    });

    // Creating private key file
    fs.writeFileSync("private_key", keyPair.privateKey);
}

// Generate keys
generateKeyFiles();

// Creating a function to encrypt string
function encryptString(plaintext, privateKeyFile) {
    const privateKey = fs.readFileSync(privateKeyFile, "utf8");

    // privateEncrypt() method with its parameters
    const encrypted = crypto.privateEncrypt(
        privateKey, Buffer.from(plaintext));

    return encrypted.toString("base64");
}

// Defining a text to be encrypted
const plainText = "GfG";

// Defining encrypted text
const encrypted = encryptString(plainText, "./private_key");

// Prints plain text
console.log("Plaintext:", plainText);

// Prints encrypted text
console.log("Encrypted: ", encrypted);
```

**输出:**

```js
Plaintext: GfG
Encrypted:  c60eR17GTQFkTI1ipTq5qFbYS58lIQqpDiou2UlYeOUE+u7agbtHvvwKaBpzBx4SvTCh5abpaqmyXCyGcUpGc7s=
```

### 例 2

```js
// Node.js program to demonstrate the
// crypto.privateEncrypt() method

// Including crypto and fs module
const crypto = require('crypto');
const fs = require("fs");

// Using a function generateKeyFiles
function generateKeyFiles() {

    const keyPair = crypto.generateKeyPairSync('rsa', {
        modulusLength: 520,
        publicKeyEncoding: {
            type: 'spki',
            format: 'pem'
        },
        privateKeyEncoding: {
            type: 'pkcs8',
            format: 'pem',
            cipher: 'aes-256-cbc',
            passphrase: ''
        }
    });

    // Creating private key file
    fs.writeFileSync("private_key", keyPair.privateKey);
}

// Generate keys
generateKeyFiles();

// Creating a function to encrypt string
function encryptString(plaintext, privateKeyFile) {
    const privateKey = fs.readFileSync(privateKeyFile, "utf8");

    // privateEncrypt() method with its parameters
    const encrypted = crypto.privateEncrypt(
        privateKey, Buffer.from(plaintext));

    // Returns buffer as its not encoded
    return encrypted;
}

// Defining a text to be encrypted
const plainText = "GfG";

// Defining encrypted text
const encrypted = encryptString(plainText, "./private_key");

// Prints plain text
console.log("Plaintext:", plainText);

// Prints encrypted text
console.log("Encrypted buffer: ", encrypted);
```

**输出:**

```js
Plaintext: GfG
Encrypted buffer:  <Buffer 14 e5 84 05 2f b5 59 64
22 d2 19 99 f9 66 e5 18 50 76 27 df 0b e6 9f 50 1d a2
51 6a 93 21 04 7b 8f 50 ba 11 82 fd 3c 6e c0 81 be 58
f9 d6 a6 c7 19 da ... >
```

## 参考

[https://nodejs.org/api/crypto.html#crypto_crypto_privateencrypt_privatekey_buffer](https://nodejs.org/api/crypto.html#crypto_crypto_privateencrypt_privatekey_buffer)