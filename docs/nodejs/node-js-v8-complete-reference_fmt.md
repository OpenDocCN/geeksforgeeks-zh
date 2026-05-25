# Node.js V8 完整参考

> 原文：[https://www.geeksforgeeks.org/node-js-v8-complete-reference/](https://www.geeksforgeeks.org/node-js-v8-complete-reference/)

`v8` 模块公开了特定于构建在 Node.js 二进制文件中的 V8 版本的 API。

## V8 的完整列表如下

### V8 模块 API

*   [`Node.js v8.cachedDataVersionTag()` 方法](https://www.geeksforgeeks.org/node-js-v8-cacheddataversiontag-method/)
*   [`Node.js v8.getHeapSpaceStatistics()` 方法](https://www.geeksforgeeks.org/node-js-v8-getheapspacestatistics-method/)
*   [`Node.js v8.getHeapStatistics()` 方法](https://www.geeksforgeeks.org/node-js-v8-getheapstatistics-method/)
*   Serialization API
    *   [`Node.js v8.Serializer()` 方法](https://www.geeksforgeeks.org/node-js-v8-serializer-method/)
    *   [`Node.js v8.Serializer.writeHeader()` 方法](https://www.geeksforgeeks.org/node-js-v8-serializer-writeheader-method/)
    *   [`Node.js v8.Serializer.writeValue()` 方法](https://www.geeksforgeeks.org/node-js-v8-serializer-writevalue-method/)
    *   [`Node.js v8.Serializer.releaseBuffer()` 方法](https://www.geeksforgeeks.org/node-js-v8-serializer-releasebuffer-method/)
    *   [`Node.js v8.Serializer.writeUint32()` 方法](https://www.geeksforgeeks.org/node-js-v8-serializer-writeuint32-method/)
    *   [`Node.js v8.Serializer.writeUint64()` 方法](https://www.geeksforgeeks.org/node-js-v8-serializer-writeuint64-method/)
    *   [`Node.js v8.Serializer.writeDouble()` 方法](https://www.geeksforgeeks.org/node-js-v8-serializer-writedouble-method/)
    *   [`Node.js v8.Serializer.writeRawBytes()` 方法](https://www.geeksforgeeks.org/node-js-v8-serializer-writerawbytes-method/)

### Class: `v8.Serializer`

*   [`Node.js v8.Deserializer.readHeader()` 方法](https://www.geeksforgeeks.org/node-js-v8-deserializer-readheader-method/)
*   [`Node.js v8.Deserializer.readValue()` 方法](https://www.geeksforgeeks.org/node-js-v8-deserializer-readvalue-method/)
*   [`Node.js v8.Deserializer.readUint32()` 方法](https://www.geeksforgeeks.org/node-js-v8-deserializer-readuint32-method/)
*   [`Node.js v8.Deserializer.readUint64()` 方法](https://www.geeksforgeeks.org/node-js-v8-deserializer-readuint64-method/)
*   [`Node.js v8.Deserializer.readRawBytes()` 方法](https://www.geeksforgeeks.org/node-js-v8-deserializer-readrawbytes-method/)