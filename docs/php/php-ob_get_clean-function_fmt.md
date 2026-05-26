# PHP `ob_get_clean()` 函数

> 原文：[https://www.geeksforgeeks.org/php-ob_get_clean-function/](https://www.geeksforgeeks.org/php-ob_get_clean-function/)

`ob_get_clean()` 函数是一个内置的 PHP 函数，用于清除或删除当前的输出缓冲区。它还用于在清除缓冲区后再次获取输出缓冲区的内容。`ob_get_clean()` 函数是 `ob_get_content()` 和 `ob_end_clean()` 的组合。

**语法：**

```php
string|false ob_get_clean();
```

**参数：** 不接受任何参数。

**返回值：** 此函数返回输出缓冲区的内容并结束输出缓冲区。如果输出缓冲未激活，则返回 `FALSE`。

**示例 1：** 下面是 `ob_get_clean()` 函数的简单示例。

```php
<?php

// Create an output buffer
ob_start();

echo "Welcome to GeeksforGeeks";

$out = ob_get_clean();
$out = strtolower($out);

var_dump($out);
?>
```

**示例 2：**

```php
<?php

// Declare a class
class GFG {
    public function GFG_Funcion() {
        $variable = array(
            "A" => "Welcome",
            "B" => "GeeksforGeeks",
            "C" => "Geeks"
        );

        foreach ($variable as $key => $value) {
            echo $key . " => " . $value;
            echo "<br/>";
        }
    }
}

ob_start();

// Creating an object of class GFG
$object = new GFG();

// Calling function
$object -> GFG_Funcion();

$saved_ob_level = ob_get_level();

$start_ob_level="";

while (ob_get_level() > $start_ob_level) {
    ob_end_flush();
}

// Now, it is the final output buffer
$content = ob_get_clean();

?>
```

**引用：** [https://www.php.net/manual/en/function.ob-get-clean.php](https://www.php.net/manual/en/function.ob-get-clean.php)