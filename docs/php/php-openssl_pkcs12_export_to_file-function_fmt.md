# PHP openssl_pkcs12_export_to_file() 函数

> Original: [https://www.geeksforgeeks.org/php-openssl_pkcs12_export_to_file-function/](https://www.geeksforgeeks.org/php-openssl_pkcs12_export_to_file-function/)

`openssl_pkcs12_export_to_file()` 函数是 PHP 中的内置函数，用于以 PKCS#12 文件格式将 x509 存储到按文件名命名的文件中。PKCS12 是公钥加密标准，它定义了用于存储服务器证书的存档文件格式。

## 语法

```php
bool openssl_pkcs12_export_to_file( mixed $x509, string $filename, mixed $priv_key, string $pass [, array $args ] )
```

## 参数

此函数接受上述参数，如下所述：

*   `$x509`: 此参数是定义公钥证书格式的标准。
*   `$filename`: 此参数是输出文件的路径。
*   `$priv_key`: 此参数用于与证书匹配的私钥。该私钥是 PKCS#12 文件的一部分。
*   `$pass`: 此参数用于解锁 PKCS#12 文件的加密密码。
*   `$args`: 此参数代表参数和变量，它们是表示其他内容的值。

## 返回值

此函数成功时返回 `TRUE`，失败时返回 `FALSE`。

## 示例程序

下面的程序演示了 PHP 中的 `openssl_pkcs12_export_to_file()` 函数：

```php
<?php
$dn = array(
    "countryName" => 'xx',
    "stateOrProvinceName" => 'uttar prradesh',
    "localityName" => 'varanasi',
    "organizationName" => 'geeksforgeeks',
    "organizationalUnitName" => 'geeks team',
    "commonName" => 'people',
    "emailAddress" => 'user@geeks.com'
);

$privateKeyPass = 'abcd1234';
$numberOfDays   = 108;

$privateKey = openssl_pkey_new();
$csr = openssl_csr_new($dn, $privateKey);

// Create a csr file, change null
// to a filename to save
$sscert = openssl_csr_sign($csr, 
    null, $privateKey, $numberOfDays);

// On success $publicKey will 
// hold the PEM content 
openssl_x509_export($sscert, $publicKey);

// Export the privateKey as a PEM content
openssl_pkey_export($privateKey, 
        $privateKey, $privateKeyPass);

$filename = dirname(__FILE__) 
        . '/certificate.pfx';

// Parses the $privateKey and used 
// by openssl_pkcs12_export_to_file
$key = openssl_pkey_get_private(
    $privateKey, $privateKeyPass);

// Save the pfx file to $filename
openssl_pkcs12_export_to_file($sscert, 
    $filename, $key, $privateKeyPass);
?>
```

**引用：**[https://www.php.net/manual/en/function.openssl-pkcs12-export-to-file.php](https://www.php.net/manual/en/function.openssl-pkcs12-export-to-file.php)