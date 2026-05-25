# Node.js `ecdh.computeSecret()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-ecdh-computesecret-method/](https://www.geeksforgeeks.org/node-js-ecdh-computesecret-method/)

`ecdh.computeSecret()` 方法是加密模块中 `ECDH` 类的内置应用程序编程接口，用于使用另一方的公钥创建共享秘密。输入公钥和输出密钥的编码都可以使用各自的参数来指定。

当公钥位于椭圆曲线之外时，会抛出 `ERR_CRYPTO_ECDH_INVALID_PUBLIC_KEY` 错误。

## 语法

```js
ecdh.computeSecret( otherPublicKey, inputEncoding, outputEncoding )
```

## 参数

该方法接受三个参数，如下所述：

*   `otherPublicKey`：是生成共享秘密所基于的对方的公钥。
*   `inputEncoding`：这是一个字符串值，指定对方公钥的编码。未指定此参数时，该键应为缓冲区类型或数据视图。
*   `outputEncoding`：这是一个字符串值，指定将要生成的共享秘密的编码。

## 返回值

返回指定编码的椭圆曲线 Diffie-Hellman 共享密钥。如果没有提供编码，则作为缓冲区返回，否则返回字符串。

以下示例演示了该方法：

## 示例 1

在本例中，使用双方的密钥创建两个用户的共享秘密，然后对它们进行比较，看它们是否相等。

```js
const crypto = require('crypto');

const geekA = crypto.createECDH('secp521r1');

// Generate keys for geekA
const geekAkey = geekA.generateKeys('base64');

const geekB = crypto.createECDH('secp521r1');

// Generate keys for geekB
const geekBkey = geekB.generateKeys('base64');

// Compute the secrets of both the geeks in base64
// based on the other party's key
let secretA = geekA.computeSecret(geekBkey, 'base64', 'base64');
let secretB = geekB.computeSecret(geekAkey, 'base64', 'base64');

console.log("Secret of A is:", secretA);
console.log("Secret of B is:", secretB);

// Check if the secrets match
console.log(secretA == secretB ?
    "The secrets match!" :
    "The secrets do not match")
```

**输出：**

> Secret of A is: ac7P1cxxytrdcvxx0his0jqjr3fgb7suxfgduq+xgxmpjgwks9seckff3ehy+xyve2mtwfcaxf2gq9g7k7tt5
> Secret of B is: ac7P1cxxytrdcvxx0his0jqjr3fgb7suxfgduq+xgxmpjgwks9seckff3ehy+xyve2mtwfcaxf2gq9g7k7tt5

## 示例 2

在本例中，输入编码参数作为 `null` 传递，因为 `generateKeys()` 方法在生成密钥时不会对它们进行编码。

```js
const crypto = require('crypto');

const geekOne = crypto.createECDH('secp521r1');

// Generate keys for geekOne
const geekOneKey = geekOne.generateKeys();

const geekTwo = crypto.createECDH('secp521r1');

// Generate keys for geekTwo
const geekTwoKey = geekTwo.generateKeys();

// Compute the secrets of both the geeks
// The input encoding is null
let secretGeekOne =
  geekOne.computeSecret(geekTwoKey, null, 'base64');
let secretGeekTwo =
  geekTwo.computeSecret(geekOneKey, null, 'base64');

console.log("Secret of Geek One is:", secretGeekOne);
console.log("Secret of Geek Two is:", secretGeekTwo);
```

**输出：**

> Secret of Geek One is: ACC+ske9xqmw5quzseks0OS+ohggkpqwkw13+lxhs2hnevzdCEOE/PCzdNKk3v5zqdwso0kfry1qbm8KC6
> Secret of Geek Two is: ACC+ske9xqmw5quzseks0OS+ohggkpqwkw13+lxhs2hnevzdCEOE/PCzdNKk3v5zqdwso0kfry1qbm8KC6

**参考：** [https://nodejs.org/api/crypto.html#crypto_ecdh_computeSecret_otherPublicKey_inputEncoding_outputEncoding](https://nodejs.org/api/crypto.html#crypto_ecdh_computeSecret_otherPublicKey_inputEncoding_outputEncoding)