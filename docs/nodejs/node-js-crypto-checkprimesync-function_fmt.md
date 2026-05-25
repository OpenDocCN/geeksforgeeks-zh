# Node.js crypto.checkPrimeSync()函数

> 原文：[https://www.geeksforgeeks.org/node-js-crypto-checkprimesync-function/](https://www.geeksforgeeks.org/node-js-crypto-checkprimesync-function/)

`checkPrimeSync()`是加密模块中加密类的内置应用编程接口，用于检查传递的缓冲区对象是否是素数。

**语法：**

```js
const crypto.checkPrimeSync(candidate[, options])
```

**参数：** 该函数采用以下参数作为参数。

*   `candidate`：这是一个缓冲区对象，表示任意长度的大八位序列。
*   `option`：将更改此函数操作的选项。

**返回值：** 当且仅当候选项是素数时，该函数返回真。

**例1：**

## index.js

```js
// Node.js program to demonstrate the
// crypto.checkPrimeSync() function

// Importing crypto module
const crypto = require('crypto')

// creating and initializing new
// ArrayBuffer object
const buffer = new ArrayBuffer(8)

// checking if the buffer object is prime or not
// by using checkPrimeSync() method
const val = crypto.checkPrimeSync(buffer)

//display the result
if(val)
console.log("candidate is a prime")
else
console.log("candidate is not a prime")
```

**使用以下命令运行`index.js`文件：**

```js
node index.js
```

**输出：**

```js
candidate is not a prime
```

**例2：**

## index.js

```js
// Node.js program to demonstrate the
// crypto.checkPrimeSync() function

// Importing crypto module
const crypto = require('crypto')

// creating and initializing new
// BigInt object
const buffer = BigInt("0o377777777777777777")

// checking if the buffer object is prime or not
// by using checkPrimeSync() method
const val = crypto.checkPrimeSync(buffer)

//display the result
if(val)
console.log("candidate is a prime")
else
console.log("candidate is not a prime")
```

**使用以下命令运行`index.js`文件：**

```js
node index.js
```

**输出：**

```js
candidate is not a prime
```

**参考：** [https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_crypto_checkprimesync_candidate_options](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_crypto_checkprimesync_candidate_options)