# PHP 过滤与过滤常量

> 原文：[https://www.geeksforgeeks.org/php-filter-and-filter-constant/](https://www.geeksforgeeks.org/php-filter-and-filter-constant/)

PHP Filter 是一个扩展，它通过清理或验证数据来过滤数据。它在网站的安全方面起着至关重要的作用，当数据来自未知或外来来源（如用户提供的输入）时，它尤其有用。例如，来自 HTML 表单的数据。

过滤器主要有两种类型，如下所示：

*   **验证（Verification）：** 用于验证或检查数据是否满足特定条件。例如，传入 `FILTER_VALIDATE_URL` 可以确定数据是否为有效的 URL，但它不会改变数据本身。
*   **清理（Cleanup）：** 与验证不同，清理通过删除或更改数据来确保不出现不需要的字符。例如，传入 `FILTER_SANITIZE_EMAIL` 会删除所有不适合电子邮件地址的字符。也就是说，它不验证数据。

## 示例

### 示例 1：使用 `FILTER_VALIDATE_URL` 过滤器验证 URL 的 PHP 程序

```php
<?php
// PHP program to validate URL

// Declare variable and initialize it to URL
$url = "https://www.geeksforgeeks.org";

// Use filter function to validate URL
if (filter_var($url, FILTER_VALIDATE_URL)) {
    echo("valid URL");
} 
else {
    echo("Invalid URL");
}

?>
```

### 示例 2：使用 `FILTER_VALIDATE_EMAIL` 过滤器验证电子邮件的 PHP 程序

```php
<?php
// PHP program to validate email

// Declare variable and initialize it to email
$email = "xyz@gmail.com";

// Use filter function to validate email
if (filter_var($email, FILTER_VALIDATE_EMAIL)) {
    echo "Valid Email";
} 
else {
    echo "Invalid Email";
}

?>
```

## 过滤功能

过滤功能用于过滤来自不安全来源的数据。

*   `filter_var()`：筛选特定变量。
*   `filter_var_array()`：过滤多个变量，即变量数组。
*   `filter_has_var()`：检查特定输入类型的变量是否存在。
*   `filter_id()`：帮助获取指定筛选器名称的筛选器 ID。
*   `filter_list()`：以数组形式返回支持的筛选器名称列表。
*   `filter_input()`：获取外部变量并对其进行过滤（如果设置为这样做的话）。
*   `filter_input_array()`：与 `filter_input()` 相同，但这里获取多个变量，即变量数组，如果设置为这样做，则对其进行过滤。

## 预定义筛选器常量

下面列出了许多预定义筛选器常量：

### 验证过滤器常量

*   `FILTER_VALIDATE_BOOLEAN`：验证布尔值。
*   `FILTER_VALIDATE_INT`：验证整数。
*   `FILTER_VALIDATE_FLOAT`：验证浮点数。
*   `FILTER_VALIDATE_REGEXP`：验证正则表达式。
*   `FILTER_VALIDATE_IP`：验证 IP 地址。
*   `FILTER_VALIDATE_EMAIL`：验证电子邮件地址。
*   `FILTER_VALIDATE_URL`：验证 URL。

### 清理过滤器常量

*   `FILTER_SANITIZE_EMAIL`：从电子邮件地址中删除所有非法字符。
*   `FILTER_SANITIZE_ENCODED`：删除/编码特殊字符。
*   `FILTER_SANITIZE_MAGIC_QUOTES`：应用 `addslashes()` 函数。
*   `FILTER_SANITIZE_NUMBER_INT`：删除除数字、`+`、`-` 外的所有字符。
*   `FILTER_SANITIZE_SPECIAL_CHARS`：删除特殊字符。
*   `FILTER_SANITIZE_FULL_SPECIAL_CHARS`：等效于 `htmlspecialchars()`，可使用 `FILTER_FLAG_` 来禁用编码引号。
*   `FILTER_SANITIZE_STRING`：从字符串中删除标签/特殊字符。
*   `FILTER_SANITIZE_STRIPPED`：同 `FILTER_SANITIZE_STRING`。
*   `FILTER_SANITIZE_URL`：从 URL 中删除所有非法字符。
*   `FILTER_UNSAFE_RAW`：不做任何处理，可选择性地剥离/编码特殊字符。
*   `FILTER_CALLBACK`：调用用户自定义函数来过滤数据。

**注意：** 在 PHP 5.2.0 及更新版本中，默认情况下启用 PHP 筛选器。较旧版本需要安装。

**引用：** [http://php.net/manual/en/filter.filters.sanitize.php](http://php.net/manual/en/filter.filters.sanitize.php)