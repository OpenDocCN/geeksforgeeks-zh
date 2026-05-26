# PHP中有没有切换用例的替代？

> 原文：[https://www.geeksforgeeks.org/is-there-any-alternate-of-switch-case-in-php/](https://www.geeksforgeeks.org/is-there-any-alternate-of-switch-case-in-php/)

PHP在第8版的发布中引入了[`switch-case`](https://www.geeksforgeeks.org/how-to-use-a-switch-case-or-in-php/)的替代方案。

在PHP第8版的发布中，引入了`match()`功能，这是`switch-case`的新替代。这是一个强大的功能，通常是最好的选择，而不是使用`switch-case`。`match()`功能的工作原理也与`switch`类似，即根据传递给它的参数找到匹配的案例。

## 语法

```php
$variable = match() {
    somecase => 'match_value' ,
    anothercase => 'match_value',
    default => 'match_value',
};
```

## 示例

```php
$value = match(1){
    1 => 'Hii..',
    2 => 'Hello..',
    default => 'Match not found !',
};
```

## match()函数与switch-case有何不同？

*   它使用箭头符号而不是冒号。
*   它不需要`break`语句。
*   案例用逗号而不是`break`语句分隔。
*   `match()`的语法以分号结束。
*   它根据提供的参数返回一些值。
*   严格的类型检查，区分大小写。
*   当没有默认值和匹配值时，会抛出一个错误。
*   复杂的条件实现和改进的性能。

### 注意

功能`match()`在PHP 8版本及以上支持。

## PHP代码示例

以下示例演示了`switch-case`，它将根据在`switch()`的参数中传递的值为变量`$message`赋值。

```php
<?php

$day = 7;

switch ($day) {
    case 1 : $message = 'Monday';
             break;
    case 2 : $message = 'Tuesday';
             break;
    case 3 : $message = 'Wednesday';
             break;
    case 4 : $message = 'Thursday';
                break;
    case 5 : $message = 'Friday';
             break;
    case 6 : $message = 'Saturday';
             break;
    case 7 : $message = 'Sunday';
             break;
    default : $message = 'Invalid Input !';
              break;
}

echo $message;
?>
```

### 输出

```php
Sunday
```

## PHP代码示例

下面的代码演示了`match()`函数，该函数只在PHP 8或更高版本中执行。

```php
<?php

$day = 7;

$message = match ($day) {
    1 => 'Monday',
    2 => 'Tuesday',
    3 => 'Wednesday',
    4 => 'Thursday',
    5 => 'Friday',
    6 => 'Saturday',
    7 => 'Sunday',
    default => 'Invalid Input !',
};

echo $message;
?>
```

### 输出

```php
Sunday
```