# Node.js KeyObject.from()方法

> 原文：[https://www.geeksforgeeks.org/node-js-keyobject-from-method/](https://www.geeksforgeeks.org/node-js-keyobject-from-method/)

`KeyObject.from()`方法是加密模块中`KeyObject`类的内置API，用于将其他加密密钥对象转换为`KeyObject`实例。它是`KeyObject`类的静态方法。

## 语法

```js
KeyObject.from(key)
```

## 参数

该方法只接受一个参数：

*   `Key`：此参数持有密钥值。

## 返回值

该方法返回一个`KeyObject`实例。

## 示例

**文件名：`index.js`**

```js
// Node.js program to demonstrate the
// keyObject.from() method

// Importing the crypto module
const { webcrypto: { subtle }, KeyObject }
    = require('crypto');

// Generating the crypto key that is
// not a keyObject instance
(async function () {
    const key = await subtle.generateKey({
        name: 'HMAC',
        hash: 'SHA-256',
        length: 256
    }, true, ['sign', 'verify']);

    try {
        // Calling KeyObject.from() method to
        // get the instance to KeyObject
        const keyObject = KeyObject.from(key);
        console.log("Successfully converted a "
            + "cryptoKey to instance of keyObject");
    }
    catch (error) {
        console.log("Error has been occured");
    }
})();
```

## 运行命令

使用以下命令运行`index.js`文件：

```bash
node index.js
```

## 输出

```
Successfully converted a cryptoKey to instance of keyObject.
```

## 参考

[https://nodejs.org/api/crypto.html#crypto_class_keyobject](https://nodejs.org/api/crypto.html#crypto_class_keyobject)