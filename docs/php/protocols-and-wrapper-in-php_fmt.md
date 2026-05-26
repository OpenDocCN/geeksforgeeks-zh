# PHP 中的协议和包装器

> Original: [https://www.geeksforgeeks.org/protocols-and-wrapper-in-php/](https://www.geeksforgeeks.org/protocols-and-wrapper-in-php/)

## 概述

PHP 中有针对不同类型 URL 样式协议的各种内置包装器。这些包装器还用于许多其他文件系统函数。在 PHP 中也允许注册自定义包装器。这可以通过 `stream_wrapper_register()` 函数来完成。

在 PHP 中，支持的 URL 语法为 `SCHEMA://`。

PHP 中不支持的 URL 语法为：
*   `Scheme: /`
*   `Scheme:`

PHP 中有 12 个包装器。

## 包装器列表

| 包装器 | 用途 | 描述 |
| --- | --- | --- |
| `file://` | 访问本地文件系统 | PHP 用来表示本地文件系统的默认包装器。 |
| `http://` | HTTP | 通过它应用相对路径到当前工作目录。 |
| `ftp://` | 访问 FTP URL | 用于通过 FTP 创建新文件和访问已有文件。如果服务器不支持被动模式 FTP，连接将失败。 |
| `php://` | 访问各种 I/O 流 | 可以读写各种 Unix I/O 流、错误描述符、内存中的数据等。 |
| `zlib://` | 流压缩 | 以类似的方式压缩流。 |
| `data://` | 数据 (RFC 2397) | 读取内容或稍后打印的媒体类型。 |
| `glob://` | 查找匹配模式的路径名 | 最常见的用途包括搜索目录、打印文件名和大小。 |
| `phar://` | 归档文件的读写操作 | PHP 中的归档文件可以单独或同时执行读写操作，但不能追加。 |
| `ssh2://` | SSH2 安全外壳 | 此包装器在 PHP 中默认不可用，用于访问它。需要下载 [SSH2 扩展](https://pecl.php.net/package/ssh2)。 |
| `rar://` | RAR | 获取指向 RAR 归档文件的 URL 路径（编码），路径可以是相对或绝对。归档中存储的其他选项包括星号 (`*`)、井号 (`#`) 和条目名称。可以通过它访问目录和文件。 |
| `ogg://` | 音频流 | 在 `ogg://` 包装器中打开的文件是由 ogg/Vorbis 编解码器编码的压缩音频。即使附加了文件，它们也是压缩音频。此包装器在 PHP 中默认不可用。要访问它，需要下载 Ogg/Vorbis 扩展。 |
| `expect://` | 交互流处理 | 此包装器使 stderr、进程的 stdio 和 stdout 可访问。此包装器在 PHP 中默认不可用，因为要访问它，需要下载 [expect 扩展](https://pecl.php.net/package/expect)。 |

## 代码示例

```
if (condVar > someVal) {console.log("xxx")}
```