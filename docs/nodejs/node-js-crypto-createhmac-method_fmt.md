# Node.js `crypto.createHmac()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-crypto-createhmac-method/](https://www.geeksforgeeks.org/node-js-crypto-createhmac-method/)

`crypto.createHmac()` 方法用于创建使用所述“算法”和“密钥”的 Hmac 对象。

## 语法

```js
crypto.createHmac( algorithm, key, options )
```

## 参数

该方法接受如下所述的三个参数：

*   `algorithm`: 它取决于平台上 **OpenSSL** 版本支持的可用算法。返回一个字符串，例如 `sha256`、`sha512` 等。
*   `key`: 是 HMAC 密钥，用于创建加密的 `HMAC` 哈希。返回 `string`、`buffer`、`TypedArray`、`DataView` 或 `KeyObject`。如果是一个密钥对象，则其类型必须是 `secret`。
*   `options`: 是一个可选参数，用于控制常见行为。返回一个对象。

## 返回类型

返回 `Hmac` 对象。

## 示例

下面的例子说明了 `crypto.createHmac()` 方法在 Node.js 中的使用：

### 例 1

```js
// Node.js program to demonstrate the     
// crypto.createHmac() method

// Includes crypto module
const crypto = require('crypto');

// Defining key
const secret = 'GfG';

// Calling createHmac method
const hash = crypto.createHmac('sha256', secret)

// updating data
                   .update('GeeksforGeeks')

// Encoding to be used
                   .digest('hex');

// Displays output
console.log(hash);
```

**输出：**

```js
a08116905e92633e4f30eefd1276206b259305c8783642fc5b7f51c089187939
```

### 例 2

```js
// Node.js program to demonstrate the     
// crypto.createHmac() method

// Defining myfile
const myfile = process.argv[1];

// Includes crypto and  fs module
const crypto = require('crypto');
const fs = require('fs');

// Creating Hmac 
const creathmac = crypto.createHmac('sha1', 'CS-Portal!');

// Creating read stream
const readfile = fs.createReadStream(myfile);

readfile.on('readable', () => {

// Calling read method to read data
  const data = readfile.read();
  if (data)

// Updating
    creathmac.update(data);
  else
   {
    // Encoding and displaying filename
    console.log("The hmac object returns:", 
    `${creathmac.digest('hex')} ${myfile}`);
  }
});
console.log("Program done!");
console.log();
```

**输出：**

```js
Program done!
The hmac object returns: 4605d44703c2620fc2574c9a9216bd3267457324 /run_dir/interp.js
```

## 参考

[https://nodejs.org/api/crypto.html#crypto_crypto_createhmac_algorithm_key_options](https://nodejs.org/api/crypto.html#crypto_crypto_createhmac_algorithm_key_options)