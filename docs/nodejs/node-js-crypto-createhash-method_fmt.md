# Node.js crypto.createHash()方法

> 原文：[https://www.geeksforgeeks.org/node-js-crypto-createhash-method/](https://www.geeksforgeeks.org/node-js-crypto-createhash-method/)

`crypto.createHash()`方法用于创建一个`Hash`对象，该对象可用于使用所述算法创建哈希摘要。

## 语法

```js
crypto.createHash( algorithm, options )
```

## 参数

该方法接受两个参数，如上所述，描述如下：

*   `algorithm`：它取决于平台上`OpenSSL`版本支持的可用算法。它返回一个字符串。例如`sha256`、`sha512`等。
*   `option`：是一个可选参数，用于控制常见行为。它返回一个对象。此外，对于像`shake256`这样的`XOF`哈希函数，你可以使用`Output Length`选项来确定所需的输出长度（以字节为单位）。

## 返回类型

返回`Hash`对象。

下面的例子说明了`crypto.createHash()`方法在Node.js中的使用：

### 例1

```js
// Node.js program to demonstrate the     
// crypto.createHash() method

// Includes crypto module
const crypto = require('crypto');

// Defining key
const secret = 'Hi';

// Calling createHash method
const hash = crypto.createHash('sha256', secret)

// updating data
                   .update('How are you?')

// Encoding to be used
                   .digest('hex');

// Displays output
console.log(hash);
```

**输出：**

```js
df287dfc1406ed2b692e1c2c783bb5cec97eac53151ee1d9810397aa0afa0d89
```

### 例2

```js
// Node.js program to demonstrate the     
// crypto.createHash() method

// Defining filename
const filename = process.argv[2];

// Includes crypto and  fs module
const crypto = require('crypto');
const fs = require('fs');

// Creating Hash 
const hash = crypto.createHash('sha256', 'Geeksforgeeks');

// Creating read stream
const input = fs.createReadStream(filename);

input.on('readable', () => {

// Calling read method to read data
  const data = input.read();
  if (data)

// Updating
    hash.update(data);
  else
   {
    // Encoding and displaying filename
    console.log(`${hash.digest('base64')} ${filename}`);
  }
});
console.log("Program done!");
```

**输出：**

```js
Program done!
n95mt3468ZzAIwu/bbNU7dej6CoFkDRcNaJo7rGpLF4= index.js
```

**参考：**[https://nodejs.org/api/crypto.html#crypto_crypto_createhash_algorithm_options](https://nodejs.org/api/crypto.html#crypto_crypto_createhash_algorithm_options)