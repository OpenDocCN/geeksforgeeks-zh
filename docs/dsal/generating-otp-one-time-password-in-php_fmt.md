# 在 PHP 中生成一次性密码

> 原文：[https://www.geeksforgeeks.org/generating-otp-one-time-password-in-php/](https://www.geeksforgeeks.org/generating-otp-one-time-password-in-php/)

现在，OTP（一次性密码）几乎在每一项服务中都是强制性的。开发人员可以通过多种方式生成动态口令，但挑战不在于预测性，因为任何人都可以预测动态口令并利用服务。

OTP 的一些流行格式是：
*   4 位数字 OTP。
*   4 位字母（小写/大写）OTP。
*   4 位或 6 位字母数字 OTP。

n 位数字 OTP 示例：

```
Input : n = 4
Output : 8723

Input : n = 8
Output : 23914072
```

**注意：** 每次执行程序的输出都会不一样。

生成动态口令的最好方法之一是使用随机函数。但是直接使用随机函数会很危险。这里有一个方法，使用随机函数和一些算法来生成 n 位数字的动态口令。

## 程序

```php
<?php

// Function to generate OTP
function generateNumericOTP($n) {

    // Take a generator string which consist of
    // all numeric digits
    $generator = "1357902468";

    // Iterate for n-times and pick a single character
    // from generator and append it to $result

    // Login for generating a random character from generator
    //     ---generate a random number
    //     ---take modulus of same with length of generator (say i)
    //     ---append the character at place (i) from generator to result

    $result = "";

    for ($i = 1; $i <= $n; $i++) {
        $result .= substr($generator, (rand()%(strlen($generator))), 1);
    }

    // Return result
    return $result;
}

// Main program
$n = 6;
print_r(generateNumericOTP($n));

?>
```

## 输出

```
```