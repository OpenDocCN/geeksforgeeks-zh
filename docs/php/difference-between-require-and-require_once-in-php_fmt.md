# PHP 中 `require()` 和 `require_once()` 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-require-and-require_once-in-php/](https://www.geeksforgeeks.org/difference-between-require-and-require_once-in-php/)

## PHP `require()` 函数

PHP 中的 `require()` 函数主要用于将一个 PHP 文件的代码/数据包含到另一个文件中。在这个过程中，如果有任何类型的错误，那么这个 `require()` 函数将显示一个警告和一个致命错误，它将立即停止脚本的执行。

为了使用这个 `require()` 函数，我们首先需要创建两个 PHP 文件。使用 `include()` 功能将一个 PHP 文件包含到另一个 PHP 文件中。这两个 PHP 文件合并成一个 HTML 文件。这个 `require()` 函数不会看到代码之前是否包含在指定的文件中，而是会像使用 `require()` 函数一样多次包含代码。

### 示例

#### HTML

```php
<html>

<body>
    <h1>Welcome to geeks for geeks!</h1>
    <p>Myself, Gaurav Gandal</p>

    <p>Thank you</p>

    <?php require 'requiregfg.php'; ?>
</body>

</html>
```

#### `requiregfg.php`

```php
<?php

    echo "<p>visit Again-" . date("Y") 
        . " geeks for geeks.com</p>";

?>
```

### 输出

![](img/a6cda40c395987378171506c68acc054.png)

## PHP `require_once()` 函数

PHP 中的 `require_once()` 函数用于将一个 PHP 文件包含到另一个 PHP 文件中。它为我们提供了一个特性，如果一个 PHP 文件中的代码已经包含在指定的文件中，那么如果我们使用 `require_once()` 函数，它将不会再次包含该代码。这意味着这个函数只会将一个文件添加到另一个文件中一次。

如果这个函数没有找到一个指定的文件，那么它将产生一个致命的错误，并将立即停止执行。

### 示例

#### PHP

```php
<?php
    require_once('demo.php');
    require_once('demo.php');
?>
```

上面的 PHP 代码中使用了以下代码。

#### `demo.php`

```php
<?php
    echo "Hello from Geeks for Geeks";
?>
```

### 输出

![](img/b25b6b73cfb1bb2bdae22d1ec45a3fa8.png)

## `require()` 和 `require_once()` 的区别

| `require()` | `require_once()` |
| :--- | :--- |
| `require()` 函数用于将一个 PHP 文件包含到另一个文件中，无论该文件之前是否已被包含。 | `require_once()` 会首先检查该文件是否已被包含，如果已被包含，则不会再次包含。 |
| 此函数主要用于需要反复包含某段代码的场景。 | 此函数主要用于只需要包含某段代码一次的场景。 |
| 使用 `require()` 来加载类似模板的文件。 | 使用 `require_once()` 来加载依赖项（类、函数、常量）。 |
| 每次调用 `require()` 函数都会执行。 | `require_once()` 函数不会在每次调用时都执行（如果要包含的文件之前已被包含，则不会执行）。 |