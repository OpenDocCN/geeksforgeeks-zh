# Node.js decipher.final()方法

> 原文：[https://www.geeksforgeeks.org/node-js-decipher-final-method/](https://www.geeksforgeeks.org/node-js-decipher-final-method/)

`decipher.final()`方法是加密模块内一个内置的`Decipher`类API，用于返回包含解密对象值的缓冲区。

## 语法

```js
const decipher.final([outputEncoding])
```

## 参数

该方法以`outputEncoding`为参数。

## 返回值

该方法返回包含解密值的缓冲区对象。

## 示例 1

**文件名：`index.js`**

### JavaScript

```js
// Node.js program to demonstrate the
// decipher.final() method

// Importing crypto module
const crypto = require('crypto');

// Creating and initializing algorithm and password
const algorithm = 'aes-192-cbc';
const password = 'Password used to generate key';

// Getting key for the decipher object
const key = crypto.scryptSync(password, 'salt', 24);

// Creating and initializing the static iv
const iv = Buffer.alloc(16, 0);

// Creating and initializing the decipher object
const decipher = crypto.createDecipheriv(algorithm, key, iv);

// Encrypted using same algorithm, key and iv.
const encrypted =
'e5f79c5915c02171eec6b212d5520d44480993d7d622a7c4c2da32f6efda0ffa';

// Updating the data to tbe decipher
let decrypted = decipher.update(encrypted, 'hex', 'utf8');

// Deciphering data by using
// final() method
decrypted += decipher.final('utf8');

// Display the result
console.log(decrypted);
```

**输出：**

```js
some clear text data
```

## 示例 2

**文件名：`index.js`**

### JavaScript

```js
// Node.js program to demonstrate the
// decipher.final() method

// Importing crypto module
const crypto = require('crypto');

// Creating and initializing algorithm and password
const algorithm = 'aes-192-cbc';
const password = 'Password used to generate key';

// Getting key for the decipher object
const key = crypto.scryptSync(password, 'salt', 24);

// creating and initializing the static iv
const iv = Buffer.alloc(16, 0);

// creating and initializing the decipher object
const decipher = crypto.createDecipheriv(algorithm, key, iv);

// Encrypted using same algorithm, key and iv.
const encrypted =
'e5f79c5915c02171eec6b212d5520d44480993d7d622a7c4c2da32f6efda0ffa';

// Creating and initializing empty buffer
var buf = [];

// Updating the data to tbe decipher
let decrypted = decipher.update(encrypted, 'hex', 'utf8');

// Pushing the updated data into buffer
buf.push(decrypted);

// Pushing decrypted data into buffer
buf.push(decipher.final('utf8'));

// Display the result
console.log(buf.join(' '));
```

**输出：**

```js
some clear text  data
```

使用以下命令运行`index.js`文件：

```bash
node index.js
```

**参考：**[https://nodejs.org/dist/latest-v12.x/docs/api/crypto.html#crypto_decipher_final_outputencoding](https://nodejs.org/dist/latest-v12.x/docs/api/crypto.html#crypto_decipher_final_outputencoding)