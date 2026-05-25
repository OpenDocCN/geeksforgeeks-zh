# Node.js crypto.createDecipheriv() 方法

> 原文: [https://www.geeksforgeeks.org/node-js-crypto-createdecipheriv-method/](https://www.geeksforgeeks.org/node-js-crypto-createdecipheriv-method/)

`crypto.createDecipheriv()` 方法是一个内置的加密模块 API，用于创建一个解密对象，具有所述的算法、密钥和初始化向量（即 iv）。

## 语法

```js
crypto.createDecipheriv( algorithm, key, iv, options )
```

## 参数

该方法接受上述四个参数，描述如下：

*   **algorithm**: 一个字符串类型的值，依赖于 `OpenSSL`。示例包括 `AES-192`、`AES-256` 等。
*   **key**: 算法和 iv 使用的原始密钥。它可以是 `string`、`Buffer`、`TypedArray` 或 `DataView` 类型。密钥也可以是一个可选的密钥对象（`KeyObject`）。
*   **iv**: 初始化向量，必须是不可预测且唯一的。理想情况下，iv 应该是密码学安全的随机值。无需保密。它可以存储 `string`、`Buffer`、`TypedArray` 或 `DataView` 类型的数据。如果密码不需要 `iv`，可以设置为 `null`。
*   **options**: 一个可选参数，用于控制行为。除非密码用于 CCM 或 OCB 模式（例如 `"aes-128-ccm"`），否则它是可选的。在这种情况下，需要 `authTagLength` 选项来定义认证标签的长度（字节）。在 `GCM` 模式下，不需要 `authTagLength` 选项，但可用于设置 `getAuthTag()` 方法将返回的认证标签长度，默认值为 16 字节。

## 返回值

返回一个 `Decipher` 对象。

## 示例

以下示例说明了在 Node.js 中使用 `crypto.createDecipheriv()` 方法：

### 例 1

```js
// Node.js program to demonstrate the
// crypto.createDecipheriv() method

// Includes crypto module
const crypto = require('crypto');

// Defining algorithm
const algorithm = 'aes-192-cbc';

// Defining password
const password = 'bncaskdbvasbvlaslslasfhj';

// Defining key
const key = crypto.scryptSync(password, 'GfG', 24);

// Defining iv
const iv = Buffer.alloc(16, 0);

// Creating decipher
const decipher = crypto.createDecipheriv(algorithm, key, iv);

// Declaring decrypted
let decrypted = '';

// Reading data
decipher.on('readable', () => {
  let chunk;
  while (null !== (chunk = decipher.read())) {
    decrypted += chunk.toString('utf8');
  }
});

// Handling end event
decipher.on('end', () => {
  console.log(decrypted);
});

// Encrypted data which is to be decrypted
const encrypted = 'MfHwhG/WPv+TIbG/qM78qA==';

decipher.write(encrypted, 'base64');
decipher.end();

console.log("done");
```

### 输出

```js
done
CS-Portal
```

### 例 2

```js
// Node.js program to demonstrate the
// crypto.createDecipheriv() method

// Includes crypto module
const crypto = require('crypto');

// Defining algorithm
const algorithm = 'aes-256-cbc';

// Defining key
const key = crypto.randomBytes(32);

// Defining iv
const iv = crypto.randomBytes(16);

// An encrypt function
function encrypt(text) {
  // Creating Cipheriv with its parameter
  let cipher = crypto.createCipheriv('aes-256-cbc', Buffer.from(key), iv);

  // Updating text
  let encrypted = cipher.update(text);

  // Using concatenation
  encrypted = Buffer.concat([encrypted, cipher.final()]);

  // Returning iv and encrypted data
  return {
    iv: iv.toString('hex'),
    encryptedData: encrypted.toString('hex')
  };
}

// A decrypt function
function decrypt(text) {
  let iv = Buffer.from(text.iv, 'hex');
  let encryptedText = Buffer.from(text.encryptedData, 'hex');

  // Creating Decipher
  let decipher = crypto.createDecipheriv(
    'aes-256-cbc',
    Buffer.from(key),
    iv
  );

  // Updating encrypted text
  let decrypted = decipher.update(encryptedText);
  decrypted = Buffer.concat([decrypted, decipher.final()]);

  // returns data after decryption
  return decrypted.toString();
}

// Encrypts output
var output = encrypt("GeeksforGeeks");
console.log(output);

// Decrypts output
console.log(decrypt(output));
```

### 输出

```js
{ iv: '6bbc47a2756d6d6bf315cfd3cc0b711a', encryptedData: 'fae9a6fb31c0b0668da8c3be1b1da81a' }
GeeksforGeeks
```

## 参考

[https://nodejs.org/api/crypto.html#crypto_crypto_createdecipheriv_algorithm_key_iv_options](https://nodejs.org/api/crypto.html#crypto_crypto_createdecipheriv_algorithm_key_iv_options)