# zlib.createInflate() 方法

> 原文：[https://www.geeksforgeeks.org/node-js-zlib-createinflate-method/](https://www.geeksforgeeks.org/node-js-zlib-createinflate-method/)

`zlib.createInflate()` 方法是 `zlib` 模块的内置 API，用于创建一个新的 Inflation 对象。

## 语法

```js
zlib.createInflate( options )
```

## 参数

该方法接受单个参数 `options`，这是一个保存 `zlib` 选项的可选参数。

## 返回值

返回一个新的 Inflation 对象。

下面的例子说明了在 Node.js 中使用 `zlib.createInflate()` 方法：

## 示例 1

```js
// Node.js program to demonstrate the
// createInflate() method

// Including zlib module
var zlib = require('zlib');

// Calling deflate function to compress data
zlib.deflate('Hello World!', function(err, data)
{
  if (err)
  {
    return console.log('err', err);
  }

  // Calling createInflate method
  // to decompress the data again
  var gunzip = zlib.createInflate();
  gunzip.write(data);
  gunzip.on('data', function (data)
  {
    console.log(data.toString());
  });
});
```

**输出：**

```js
Hello World!
```

## 示例 2

```js
// Node.js program to demonstrate the
// createInflate() method

// Including zlib module
var zlib = require('zlib');

// Calling deflate function to compress data
zlib.deflate('Decompressed..', function(err, data)
{
  if (err)
  {
    return console.log('err', err);
  }

  // Calling createInflate method
  // to decompress the data again
  var gunzip = zlib.createInflate();
  gunzip.write(data);
  gunzip.on('data', function (data)
  {
    console.log(data.toString('hex'));
  });
});
```

**输出：**

```js
4465636f6d707265737365642e2e
```

## 参考资料

[https://nodejs.org/api/zlib.html#zlib_zlib_createinflate_options](https://nodejs.org/api/zlib.html#zlib_zlib_createinflate_options)