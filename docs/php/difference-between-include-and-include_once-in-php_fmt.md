# PHP 中 `include()` 和 `include_once()` 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-include-and-include_once-in-php/](https://www.geeksforgeeks.org/difference-between-include-and-include_once-in-php/)

PHP 中的 [`include()`](https://www.geeksforgeeks.org/php-inclusion/) 函数主要用于将一个 PHP 文件的代码/数据包含到另一个文件中。在此过程中，如果有任何类型的错误，那么这个 `require()` 函数将显示/给出警告，但是与执行停止的 [`require()`](https://www.geeksforgeeks.org/php-include-and-require/) 函数不同的是，`include()` 函数不会停止脚本的执行，而是脚本将继续其过程。

为了使用 `include()` 函数，我们首先需要创建两个 PHP 文件。然后使用 `include()` 函数将一个 PHP 文件放入另一个文件中。之后，您将看到两个 PHP 文件合并成一个 HTML 文件。此 `include()` 不会查看该代码是否已经包含在指定文件中，而是会包含使用 `include()` 的代码次数。

**示例：** 假设我们有一个名为 `includegfg.php` 的文件。

## `includegfg.php`

```php
<?php
   echo "<p>Visit Again; " . date("Y") . " Geeks for geeks.com</p>";
?>
```

我们已经创建了一个文件 `demo.php`。使用 `include()` 方法，我们将把 `includegfg.php` 文件包含到 `demo.php` 文件中。

## `demo.php`

```php
<html>
<body>
  <h1>Welcome to geeks for geeks!</h1>
  <p>Myself, Gaurav Gandal</p>
  <p>Thank you</p>

  <?php 
    include 'includegfg.php';
  ?>
</body>
</html>
```

**输出：**

![](img/a599b9654dfd2036d329bf468fe9dd13.png)

## `include_once()`

PHP 中的 [`include_once()`](https://www.geeksforgeeks.org/php-include_once-require_once/) 函数主要用于将一个 PHP 文件包含到另一个 PHP 文件中。它为我们提供了一个特性，如果一个 PHP 文件中的代码已经包含在一个指定的文件中，那么它将不再包含该代码。这意味着这个函数只会将一个文件添加到另一个文件中一次。如果这个函数找到一个错误，那么它将产生一个警告，但不会停止执行。

如果 `ABC.php` 文件使用 `include_once()` 调用 `XYZ.php` 文件，并且出现任何错误，那么它将产生警告，但是不会停止脚本执行。

**示例：** 下面我们创建了一个名为 `demo.php` 的示例 PHP 文件，其中显示了消息“极客们，大家好”。

### `demo.php`

```php
<?php
   echo "Hello from Geeks for Geeks";
?>
```

在下面的 PHP 文件 `require_once_demo.php` 中，我们已经使用 [`require_once()`](https://www.geeksforgeeks.org/php-include_once-require_once/) 调用了 `demo.php` 文件两次，但是它不会执行第二次调用。

### `require_once_demo.php`

```php
<?php
   include_once('demo.php');
   include_once('demo.php');
?>
```

**输出：**

![](img/1571cbeee27d89f0f8bead956d38a3e0.png)

## `include()` 和 `include_once()` 的区别

| `include()` | `include_once()` |
| :--- | :--- |
| `include()` 函数用于将一个 PHP 文件包含到另一个文件中，无论该文件之前是否已被包含。 | `include_once()` 会首先检查文件是否已被包含，如果已经包含，则不会再次包含。 |
| `include()` 函数主要用于你希望反复包含某段代码的场景。 | `include_once()` 函数主要用于你希望某段代码只被包含一次的场景。 |
| `include()` 函数在程序中每次被调用时都会执行。 | `include_once()` 函数不会在每次被调用时都执行（即，如果要包含的文件之前已被包含，则不会执行）。 |
| 在大多数情况下，`include()` 函数用于加载可选的模板类文件。 | 大多数 `include_once()` 函数用于加载可选的依赖项（类、函数、常量）。 |