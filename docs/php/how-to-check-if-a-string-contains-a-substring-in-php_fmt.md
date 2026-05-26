# 如何在 PHP 中检查字符串是否包含子字符串？

> 原文：[https://www.geeksforgeeks.org/how-to-check-if-a-string-contains-a-substring-in-php/](https://www.geeksforgeeks.org/how-to-check-if-a-string-contains-a-substring-in-php/)

字符串是给定字符的集合，子字符串是给定字符串中的字符串。

在本文中，我们将使用 PHP 的 `strpos()` 函数来检查给定的字符串是否包含子字符串。

**语法：**

```php
strpos($original_string,$sub_string);
```

**参数：**

*   `原始字符串`：输入字符串。
*   `sub_string`：在原始输入字符串中搜索的子字符串。

**返回类型：** 布尔值

*   如果找到子字符串，则为 `true`。
*   如果未找到子字符串，则为 `false`。

**示例：**

## PHP 示例

```php
<?php
//input string
$input_string = "sravan kumar author at geeks for geeks ";

//sub string to be checked
$sub = "geeks";

// Test if string contains the word
if (strpos($input_string, $sub) !== false)
{
    echo "True";
}
else
{
    echo "False";
}
?>
```

**输出：**

```php
True
```

**例 2：**

## PHP 示例

```php
<?php
//input string
$input_string = "sravan kumar author at geeks for geeks ";

//sub string to be checked
$sub = "computer";

// Test if string contains the word
if (strpos($input_string, $sub) !== false)
{
    echo "True";
}
else
{
    echo "False";
}
?>
```

**输出：**

```php
False
```

**例 3：** 下面的例子也考虑了空格。

## PHP 示例

```php
<?php
//input string
$input_string = "geeks for geeks java python php";

//sub string to be checked
$sub = " ";

// Test if string contains the word
if (strpos($input_string, $sub) !== false)
{
    echo "True";
}
else
{
    echo "False";
}
?>
```

**输出：**

```php
True
```

**例 4：**

## PHP 示例

```php
<?php
//input string
$input_string = "geeks for geeks java python php";

//sub string to be checked
$sub = " dbms";

// Test if string contains the word
if (strpos($input_string, $sub) !== false)
{
    echo "True";
}
else
{
    echo "False";
}
?>
```

**输出：**

```php
False
```