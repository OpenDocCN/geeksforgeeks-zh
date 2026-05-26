## PHP Imagick `getImageProfiles()` 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-getimageprofiles-function/](https://www.geeksforgeeks.org/php-imagick-getimageprofiles-function/)

`Imagick::getImageProfiles()` 函数是 PHP 中的一个内置函数，用于获取图像配置文件。

### 语法

```php
array Imagick::getImageProfiles( string $pattern = "*", bool $include_values = TRUE )
```

### 参数

此函数接受两个参数，如下所述：

*   `$pattern`: 指定配置文件名称的模式。默认值为 `*`，表示获取所有可用的配置文件。
*   `$include_values`: 指定是否返回配置文件的值。默认值为 `true`。如果为 `false`，则仅返回配置文件名称。

### 返回值

此函数返回一个数组，其中包含图像配置文件或仅包含配置文件名称。

下面的程序说明了 PHP 中的 `Imagick::getImageProfiles()` 函数：

### 程序 1

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Image Profile
$imagick->setImageProfile('borderColor', 'green');
$imagick->setImageProfile('borderWidth', '20');

// Get the Image Profiles
$profiles = $imagick->getImageProfiles();
print("<pre>".print_r($profiles, true)."</pre>");
?>
```

发帖主题：Re：Колибри0.7.8.0

### 程序 2

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Image Profile
$imagick->setImageProfile('borderColor', 'green');
$imagick->setImageProfile('borderWidth', '20');

// Get the Image Profiles without values
$profiles = $imagick->getImageProfiles("*", false);
print("<pre>".print_r($profiles, true)."</pre>");
?>
```

发帖主题：Re：Колибри0.7.8.0

### 引用

[https://www.php.net/manual/en/imagick.getimageprofiles.php](https://www.php.net/manual/en/imagick.getimageprofiles.php)