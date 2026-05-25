# Node.js `crypto.publicEncrypt()`方法

> 原文: [https://www.geeksforgeeks.org/node-js-crypto-publicencrypt-method/](https://www.geeksforgeeks.org/node-js-crypto-publicencrypt-method/)

`crypto.publicEncrypt()`方法是加密模块的内置应用程序编程接口，用于使用参数`key`加密`buffer`的指定内容。

## 语法

```js
crypto.publicEncrypt( key, buffer )
```

## 参数

该方法接受两个参数，如下所述：

*   **`key`**: 此参数持有`object`、`string`、`buffer`或`key object`类型的数据，并包含以下五个参数：
    1.  **`key`**: 一个 PEM 编码的公钥或私钥。类型为`string`、`buffer`或`key object`。
    2.  **`oaepHash`**: 一个`string`类型的哈希函数，用于 "oaep" 填充。默认值是 `"sha1"`。
    3.  **`label`**: 一个用于 "OAEP" 填充的标签。如果未指定，则不使用标签。类型为`buffer`、`TypedArray`或`DataView`。
    4.  **`passphrase`**: 私钥的可选密码短语，可以是`string`或`buffer`。
    5.  **`padding`**: 可选的填充值，在 `crypto.constants` 中定义，可以是 `crypto.constants.RSA_NO_PADDING`、`crypto.constants.RSA_PKCS1_PADDING` 或 `crypto.constants.RSA_PKCS1_OAEP_PADDING`。类型为`crypto.constants`。
*   **`buffer`**: 类型为`buffer`、`TypedArray`或`DataView`。

## 返回值

返回一个包含加密内容的新`Buffer`。

## 示例

下面的例子说明了 `crypto.publicEncrypt()`方法在 Node.js 中的使用：

### 例 1

```js
// Node.js program to demonstrate the
// crypto.publicEncrypt() method

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

    // Creating public key file
    fs.writeFileSync("public_key", keyPair.publicKey);
}

// Generate keys
generateKeyFiles();

// Creating a function to encrypt string
function encryptString(plaintext, publicKeyFile) {
    const publicKey = fs.readFileSync(publicKeyFile, "utf8");

    // publicEncrypt() method with its parameters
    const encrypted = crypto.publicEncrypt(
        publicKey, Buffer.from(plaintext));
    return encrypted.toString("base64");
}

// Defining a text to be encrypted
const plainText = "GfG";

// Defining encrypted text
const encrypted = encryptString(plainText, "./public_key");

// Prints plain text
console.log("Plaintext:", plainText);

// Prints encrypted text
console.log("Encrypted: ", encrypted);
```

### 输出

```js
Plaintext: GfG
Encrypted:  l0touwFaNv1DIgPE365VQD0G4rg+IbRD5G6IBQ1arLgWtFOStKO7duYJ6/JzlOJl3eBG7obqzAEJ0V2WrxtYRTg=
```

### 例 2

```js
// Node.js program to demonstrate the
// crypto.publicEncrypt() method

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

    // Creating public key file
    fs.writeFileSync("public_key", keyPair.publicKey);
}

// Generate keys
generateKeyFiles();

// Creating a function to encrypt string
function encryptString(plaintext, publicKeyFile) {
    const publicKey = fs.readFileSync(publicKeyFile, "utf8");

    // publicEncrypt() method with its parameters
    const encrypted = crypto.publicEncrypt(
        publicKey, Buffer.from(plaintext));
    return encrypted;
}

// Defining a text to be encrypted
const plainText = "Hello!";

// Defining encrypted text
const encrypted = encryptString(plainText, "./public_key");

// Prints plain text
console.log("Plaintext:", plainText);

// Prints buffer
console.log("Buffer: ", encrypted);
```

### 输出

```js
Plaintext: Hello!
Buffer: <Buffer 1b 2a c7 4d 10 44 45 8e 9d e6
53 9d 8a 5e 39 0f ea e2 96 00 d7 d3 b3 eb 54 7e
74 7d a4 62 b8 eb 68 85 cb 8e 85 a5 f7 71 2f b7
93 d6 14 1c 38 cd 45 85 ... >
```

## 参考

[https://nodejs.org/api/crypto.html#crypto_crypto_publicencrypt_key_buffer](https://nodejs.org/api/crypto.html#crypto_crypto_publicencrypt_key_buffer)