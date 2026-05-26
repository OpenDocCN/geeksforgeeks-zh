# PHP IntlChar::getPropertyValueName() 函数

> Original: [https://www.geeksforgeeks.org/php-intlchar-getpropertyvaluename-function/](https://www.geeksforgeeks.org/php-intlchar-getpropertyvaluename-function/)

`IntlChar::getPropertyValueName()` 函数是 PHP 中的内置函数，用于获取属性值的 Unicode 名称。它将根据 `PropertyValueAliases.txt`（Unicode 数据库文件）中的数据。

## 语法

```php
string IntlChar::getPropertyValueName( $property, $value, $nameChoice = IntlChar::LONG_PROPERTY_NAME )
```

## 参数

此函数接受三个参数，如下所述：

*   **`$property`**：用于基于 Unicode 属性的查找任务。它非常类似于 `IntlChar::PROPERTY_*` 常量。如果超出范围或方法与给定值不兼容，则返回 `false`。
*   **`$value`**：给定属性的选择器。如果超出范围或方法与给定值不兼容，则返回 `false`。这些值的范围将从 0 到最大值。此外，存在几个例外情况：
    *   `IntlChar::PROPERTY_CANONICAL_COMBINING_CLASS` 的值完全不连续。此外，范围将从 0 到 240。
    *   `IntlChar::PROPERTY_BLOCK` 的值以非零值 `IntlChar::BLOCK_CODE_BASIC_LATIN` 开始。
*   **`$nameChoice`**：用于选择要获取的名称。如果超出范围或方法与给定值不兼容，则返回 `false`。在大多数情况下，所有值都是长期值。有些人可能有短名称，但其他人则没有。对于其他名称，Unicode 将允许。如果存在，它们通过向 `IntlChar::LONG_PROPERTY_NAME` 添加 1、2、3 等来返回。

## 返回值

如果 `nameChoice` 或属性完全超出范围，则返回 `false`。否则，将返回该名称。如果提供了 `nameChoice`，则返回 `false`。如果 `IntlChar::SHORT_PROPERTY_NAME` 返回 `false`，则 `IntlChar::LONG_PROPERTY_NAME`（及更高版本）仍可能返回非 `false` 值。

## 程序

```php
<?php

// PHP program to uses IntlChar::getPropertyValueName()
// function

var_dump(IntlChar::getPropertyValueName
   (IntlChar::PROPERTY_INT_START, IntlChar::BLOCK_CODE_TELUGU));

var_dump(IntlChar::getPropertyValueName
                (IntlChar::PROPERTY_GENERAL_CATEGORY, IntlChar::
     BLOCK_CODE_IPA_EXTENSIONS, IntlChar::SHORT_PROPERTY_NAME));

var_dump(IntlChar::getPropertyValueName
                      (IntlChar::PROPERTY_LINE_BREAK, IntlChar::
            BLOCK_CODE_DINGBATS, IntlChar::LONG_PROPERTY_NAME));

var_dump(IntlChar::getPropertyValueName
                    (IntlChar::PROPERTY_BINARY_LIMIT, IntlChar::
           BLOCK_CODE_BAMUM, IntlChar::LONG_PROPERTY_NAME + 1));

?>
```

**引用：**[https://www.php.net/manual/en/intlchar.getpropertyvaluename.php](https://www.php.net/manual/en/intlchar.getpropertyvaluename.php)