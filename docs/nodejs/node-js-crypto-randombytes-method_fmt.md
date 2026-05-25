# Node.js crypto.randomBytes()方法

> 原文: [https://www.geeksforgeeks.org/node-js-crypto-randombytes-method/](https://www.geeksforgeeks.org/node-js-crypto-randombytes-method/)

`crypto.randomBytes()`方法用于以密码方式生成一个构建良好的人工随机数据和要在书面代码中生成的字节数。

## 语法:

```js
crypto.randomBytes( size, callback )
```

## 参数:

该方法接受两个参数，如上所述，如下所述:

*   `size`: 类型为`number`，表示要生成的字节数。
*   `callback`: 是由两个参数组成的函数，即`err`和`buf`。然而，如果回调函数在所述代码中可用，则字节异步生成，否则这些字节同步生成。

## 返回类型:

如果给定了回调函数，则返回一个`Buffer`。

以下示例说明了在Node.js中使用`crypto.randomBytes()`方法。

## 示例 1:

```js
// Node.js program to demonstrate the
// crypto.randomBytes() method

// Including crypto module
const crypto = require('crypto');

// Calling randomBytes method with callback
crypto.randomBytes(127, (err, buf) => {
  if (err) {
    // Prints error
    console.log(err);
    return;
  }

  // Prints random bytes of generated data
  console.log("The random data is: "
             + buf.toString('hex'));
});
```

**输出:** 这里提供回调函数，所以同步生成随机字节。

> 随机数据为: 074e48c8e3c0bc19f9e22dd757037392e5d0bf80cf9dd51bb7808872a511b3c1cd91053fca873a4cb7b2549ec1010a9a1a4c2a6aceed9d115eb9d60a1630e056f3acc10574cd563376d4e

## 例 2:

```js
// Node.js program to demonstrate the
// crypto.randomBytes() method

// Including crypto module
const crypto = require('crypto');

// Calling randomBytes method without callback
const buf = crypto.randomBytes(60);

// Prints random bytes of generated data
console.log("The random bytes of data generated is: "
                + buf.toString('utf8'));
```

**输出:** 这里不提供回调函数，所以同步生成字节。

```js
The random bytes of data generated is: _??i???Z?Z?o?i?W??bEC
?F????#?-??T??jDqmm?v??7?Q?c_G?%?
```

## 参考:

[https://nodejs.org/api/crypto.html#crypto_crypto_randombytes_size_callback](https://nodejs.org/api/crypto.html#crypto_crypto_randombytes_size_callback)