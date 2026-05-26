# PHP openssl_get_curve_names() 函数

> Original: [https://www.geeksforgeeks.org/php-openssl_get_curve_names-function/](https://www.geeksforgeeks.org/php-openssl_get_curve_names-function/)

`openssl_get_curve_names()` 函数是 PHP 中的一个内置函数，用于在**椭圆曲线密码术**中对名称进行曲线化。两条最广泛标准化或支持的曲线是 `prime256v1` (NIST P-256) 和 `secp384r1` (NIST P-384)。曲线名称通常包含一个数字，该数字是二进制表示法中的位数。

## AES, RSA, DSA 和 ECC 密钥大小

| AES symmetric key size (bit) | RSA and DSA key size (bits) | ECC key size (bit) |
| :--- | :--- | :--- |
| 80 | 1024 | 160 |
| 128 | 2048 | 224 |
| 192 | 3072 | 256 |
| 256 | 7680 | 384 |
| | 15360 | 512 |

## 语法

```php
openssl_get_curve_names ( void ): array
```

**参数：** 此函数不接受任何参数。

**返回值：** 此函数返回可用曲线名称的数组。

下面的程序演示了 PHP 中的 `openssl_get_curve_names()` 函数。

## 示例

```php
<?php {
    // available curve names for ECC
    $curve_names = openssl_get_curve_names();

    // print all curve names
    print_r($curve_names);
}
?>
```

**引用：** [https://www.php.net/manual/en/function.openssl-get-curve-names.php](https://www.php.net/manual/en/function.openssl-get-curve-names.php)