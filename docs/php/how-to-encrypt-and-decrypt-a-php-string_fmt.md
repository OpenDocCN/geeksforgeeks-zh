# 如何加密和解密一个 PHP 字符串？

> 原文:[https://www . geesforgeks . org/如何加密和解密 php 字符串/](https://www.geeksforgeeks.org/how-to-encrypt-and-decrypt-a-php-string/)

在 PHP 中，使用一种称为 OpenSSL 函数的加密扩展来加密和解密字符串是可能的。

## `openssl_encrypt()` 函数

`openssl_encrypt()` 函数用于对数据进行加密。

### 语法

```php
string openssl_encrypt( string $data, string $method, string $key,
                        $options = 0, string $iv, string $tag= NULL,
                        string $aad, int $tag_length = 16  )
```

### 参数

*   `$data`: 保存要加密的字符串或数据。
*   `$method`: 加密方法，采用 `openssl_get_cipher_methods()` 函数。
*   `$key`: 它保存加密密钥。
*   `$options`: 它保存了 `OPENSSL_RAW_DATA` 和 `OPENSSL_ZERO_PADDING` 标志的按位析取。
*   `$iv`: 它保存的初始化向量不为空。
*   `$tag`: 当使用 AEAD 密码模式（GCM 或 CCM）时，保存通过引用传递的认证标签。
*   `$aad`: 保存额外的认证数据。
*   `$tag_length`: 它存储认证标签的长度。对于 GCM 模式，认证标签的长度在 4 到 16 之间。

### 返回值

成功时返回加密字符串，失败时返回 `FALSE`。

## `openssl_decrypt()` 函数

`openssl_decrypt()` 函数用于解密数据。

### 语法

```php
string openssl_decrypt( string $data, string $method, string $key,
             int $options = 0, string $iv, string $tag, string $aad)
```

### 参数

*   `$data`: 保存要加密的字符串或数据。
*   `$method`: 加密方法，采用 `openssl_get_cipher_methods()` 函数。
*   `$key`: 它保存加密密钥。
*   `$options`: 它保存了 `OPENSSL_RAW_DATA` 和 `OPENSSL_ZERO_PADDING` 标志的按位析取。
*   `$iv`: 它保存的初始化向量不为空。
*   `$tag`: 它使用 AEAD 密码模式（GCM 或 CCM）存储认证标签。当认证失败时，`openssl_decrypt()` 返回 `FALSE`。
*   `$aad`: 保存额外的认证数据。

### 返回值

成功时返回解密后的字符串，失败时返回 `FALSE`。

## 方法

首先声明一个字符串并存储到变量中，使用 `openssl_encrypt()` 函数对给定的字符串进行加密，使用 `openssl_decrypt()` 函数对给定的字符串进行解密。

## 例 1

这个例子说明了字符串的加密和解密。

```php
<?php

// Store a string into the variable which
// need to be Encrypted
$simple_string = "Welcome to GeeksforGeeks\n";

// Display the original string
echo "Original String: " . $simple_string;

// Store the cipher method
$ciphering = "AES-128-CTR";

// Use OpenSSl Encryption method
$iv_length = openssl_cipher_iv_length($ciphering);
$options = 0;

// Non-NULL Initialization Vector for encryption
$encryption_iv = '1234567891011121';

// Store the encryption key
$encryption_key = "GeeksforGeeks";

// Use openssl_encrypt() function to encrypt the data
$encryption = openssl_encrypt($simple_string, $ciphering,
            $encryption_key, $options, $encryption_iv);

// Display the encrypted string
echo "Encrypted String: " . $encryption . "\n";

// Non-NULL Initialization Vector for decryption
$decryption_iv = '1234567891011121';

// Store the decryption key
$decryption_key = "GeeksforGeeks";

// Use openssl_decrypt() function to decrypt the data
$decryption=openssl_decrypt ($encryption, $ciphering, 
        $decryption_key, $options, $decryption_iv);

// Display the decrypted string
echo "Decrypted String: " . $decryption;

?>
```

### 输出

```php
Original String: Welcome to GeeksforGeeks
Encrypted String: hwB1K5NkfcIzkLTWQeQfHLNg5FlyX3PNUA==
Decrypted String: Welcome to GeeksforGeeks
```

## 示例 2

下面的示例说明了字符串的加密和解密。这里要加密的字符串和解密的字符串将是相同的，但加密的字符串是随机变化的。

```php
<?php

// Store a string into the variable which
// need to be Encrypted
$simple_string = "Welcome to GeeksforGeeks";

// Display the original string
echo "Original String: " . $simple_string . "\n";

// Store cipher method
$ciphering = "BF-CBC";

// Use OpenSSl encryption method
$iv_length = openssl_cipher_iv_length($ciphering);
$options = 0;

// Use random_bytes() function which gives
// randomly 16 digit values
$encryption_iv = random_bytes($iv_length);

// Alternatively, we can use any 16 digit
// characters or numeric for iv
$encryption_key = openssl_digest(php_uname(), 'MD5', TRUE);

// Encryption of string process starts
$encryption = openssl_encrypt($simple_string, $ciphering,
        $encryption_key, $options, $encryption_iv);

// Display the encrypted string
echo "Encrypted String: " . $encryption . "\n";

// Decryption of string process starts
// Used random_bytes() which gives randomly
// 16 digit values
$decryption_iv = random_bytes($iv_length);

// Store the decryption key
$decryption_key = openssl_digest(php_uname(), 'MD5', TRUE);

// Descrypt the string
$decryption = openssl_decrypt ($encryption, $ciphering,
            $decryption_key, $options, $encryption_iv);

// Display the decrypted string
echo "Decrypted String: " . $decryption;

?>
```

### 输出

```php
Original String: Welcome to GeeksforGeeks
Encrypted String: hwB1K5NkfcIzkLTWQeQfHLNg5FlyX3PNUA==
Decrypted String: Welcome to GeeksforGeeks
```

## 参考文献

*   [https://www.php.net/manual/en/function.openssl-encrypt.php](https://www.php.net/manual/en/function.openssl-encrypt.php)
*   [https://www.php.net/manual/en/function.openssl-decrypt.php](https://www.php.net/manual/en/function.openssl-decrypt.php)

PHP 是一种专门为 web 开发设计的服务器端脚本语言。您可以通过以下 [PHP 教程](https://www.geeksforgeeks.org/php-tutorials/)和 [PHP 示例](https://www.geeksforgeeks.org/php-examples/)从头开始学习 PHP。