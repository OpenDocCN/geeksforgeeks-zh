# Node.js DiffieHellman.setPrivateKey() 方法

> 原文: [https://www.geeksforgeeks.org/node-js-diffiehellman-setprivatekey-method/](https://www.geeksforgeeks.org/node-js-diffiehellman-setprivatekey-method/)

`DiffieHellman.setPrivateKey()` 方法是加密模块内 `DiffieHellman` (dh) 类的内置 API，用于设置 `dh` 对象的私钥。

## 语法

```js
diffieHellman.setPrivateKey(privateKey[, encoding])
```

## 参数

该方法接受以下两个参数：

*   `privateKey`：用于表示私钥。
*   `encoding`：用于编码 `privateKey` 的编码格式。如果提供了 `encoding`，则 `privateKey` 应为字符串；否则，它应为 Buffer、TypedArray 或 DataView。

## 示例 1

### index.js

```js
// Node.js program to demonstrate the
// diffieHellman.setPrivateKey() Method

const crypto = require('crypto')

// Generate DH Key pair
crypto.generateKeyPair('dh', 
    {
        primeLength: 512,
         publicKeyEncoding: {
            type: 'spki',
            format: 'der'
        },
        privateKeyEncoding: {
            type: 'pkcs8',
            format: 'der'
        }
    },
    cb
)

function cb(err, publicKey, privateKey){
    // Create Diffie-Hellman instance
    const dh = crypto.createDiffieHellman(512)
    // Set the dh's privateKey
    dh.setPrivateKey(privateKey)

    if( privateKey.equals(dh.getPrivateKey()) )
        console.log("DH private Key is set successfully")
}
```

使用以下命令运行 `index.js` 文件：

```js
node index.js
```

**输出：**

```js
DH private Key is set successfully
```

## 示例 2

### index.js

```js
// Node.js program to demonstrate the
// diffieHellman.setPrivateKey() Method

const crypto = require( 'crypto' )

crypto.generateKeyPair( 
    'dh', 
    { primeLength: 512 }, 
    cb 
)

function cb( err, publicKey, privateKey ){
    // Export key from KeyObject
    privateKey = privateKey.export( {type: 'pkcs8', format: 'der'} )
    // Encode key in base64
    privateKey = privateKey.toString('base64');
    // Create Diffie-Hellman instance
    const dh = crypto.createDiffieHellman( 512 )
    // Set the dh's privateKey
    dh.setPrivateKey( privateKey, 'base64' )

    if( privateKey === dh.getPrivateKey('base64')  )
        console.log( "DH private Key is set successfully" )
}
```

使用以下命令运行 `index.js` 文件：

```js
node index.js
```

**输出：**

```js
DH private Key is set successfully
```

## 参考

[https://nodejs.org/api/crypto.html#crypto_ecdh_setprivatekey_privatekey_encoding](https://nodejs.org/api/crypto.html#crypto_ecdh_setprivatekey_privatekey_encoding)