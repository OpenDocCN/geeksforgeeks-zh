# PHP 中 `array_merge()` 和 `array_combine()` 函数的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-array_merge-and-array-combine-functions-in-php/](https://www.geeksforgeeks.org/difference-between-array_merge-and-array-combine-functions-in-php/)

## `array_merge()` 函数

`array_merge()` 函数用于将两个或多个数组合并为一个数组。该函数用于将两个或多个数组的元素或值合并成一个数组。合并的方式是将一个数组的值附加在前一个数组的末尾。该函数将逗号分隔的数组列表作为需要合并的参数，并返回一个新数组，该数组包含参数中传递的数组的合并值。

### 语法

```php
array array_merge( $array1, $array2, ...., $arrayn)
```

其中，`$array1`，`$array2`，...是需要合并的输入数组。

### 示例 1：合并两个数组

```php
<?php

// Define array1 with keys and values
$array1 = array("subject1" => "Python","subject2" => "sql");

// Define array2 with keys and values
$array2 = array("subject3" => "c/c++","subject4" => "java");

// Merge both array1 and array2
$final = array_merge($array1, $array2);

// Display merged array
print_r($final);

?>
```

**Output**

```php
Array
(
    [subject1] => Python
    [subject2] => sql
    [subject3] => c/c++
    [subject4] => java
)
```

### 示例 2：合并多个数组

```php
<?php

// Define array1 with keys and values
$array1 = array("subject1" => "Python", "subject2" => "sql");

// Define array2 with keys and values
$array2 = array("subject3" => "c/c++", "subject4" => "java");

// Define array3 with keys and values
$array3 = array("subject5" => "CN", "subject6" => "OS");

// Define array4 with keys and values
$array4 = array("subject7" => "data mining", "subject8" => "C#");

// Merge all arrays
$final = array_merge($array1, $array2, $array3, $array4);

// Display merged array
print_r($final);

?>
```

**Output**

```php
Array
(
    [subject1] => Python
    [subject2] => sql
    [subject3] => c/c++
    [subject4] => java
    [subject5] => CN
    [subject6] => OS
    [subject7] => data mining
    [subject8] => C#
)
```

## `array_combine()` 函数

`array_combine()` 函数用于组合两个数组，并通过使用一个数组作为键，另一个数组作为值来创建一个新数组，即一个数组的所有元素都将是新数组的键，第二个数组的所有元素都将是这个新数组的值。

### 语法

```php
array_combine(array1, array2)
```

其中，`array1` 是包含键的第一个数组，`array2` 是包含值的第二个数组。

### 示例 1：组合数组

```php
<?php

// Define array1 with keys
$array1 = array("subject1" ,"subject2");

// Define array2 with values
$array2 = array( "c/c++", "java");

// Combine two arrays
$final = array_combine($array1, $array2);

// Display merged array
print_r($final);

?>
```

**Output**

```php
Array
(
    [subject1] => c/c++
    [subject2] => java
)
```

### 示例 2

```php
<?php

// Define array1 with keys
$array1 = array("subject1", "subject2", "subject3", "subject4");

// Define array2 with values
$array2 = array( "c/c++", "java", "Python", "HTML");

// Combine two arrays
$final = array_combine($array1, $array2);

// Display merged array
print_r($final);

?>
```

**Output**

```php
Array
(
    [subject1] => c/c++
    [subject2] => java
    [subject3] => Python
    [subject4] => HTML
)
```

## `array_merge()` 与 `array_combine()` 函数的区别

| **`array_merge()` 函数** | **`array_combine()` 函数** |
| :--- | :--- |
| 此函数合并两个或多个数组。 | 此函数仅组合两个数组。 |
| 此函数合并数组，因此所有数组都包含键和值。 | 此函数将一个包含键的数组与另一个包含值的数组组合。 |
| 数组被附加到第一个数组的末尾。 | 数组被组合在一起。 |