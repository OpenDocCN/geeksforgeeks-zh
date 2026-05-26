# PHP IntlChar::getPropertyName() 函数

> Original: [https://www.geeksforgeeks.org/php-intlchar-getpropertyname-function/](https://www.geeksforgeeks.org/php-intlchar-getpropertyname-function/)

`IntlChar::getPropertyName()` 函数是 PHP 中的内置函数，用于获取 Unicode 数据库文件 PropertyAliases.txt 中给定属性的 Unicode 名称。此函数用于将特性 `IntlChar::Property_General_Category_Mask` 映射到 PropertyAliases.txt 中不存在的合成名称“GCM”/“General_Category_Mask”。此函数是 `IntlChar::getPropertyEnum()` 函数的补充。

## 语法

```php
string IntlChar::getPropertyName( $property, $nameChoice = IntlChar::LONG_PROPERTY_NAME )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$property`：此参数保存之前的 Unicode 属性常量（`IntlChar::Property_*` 常量）。属性常量列表包括：
    *   `IntlChar::Property_Alphabetic`
    *   `IntlChar::Property_BIDI_Mirrored`
    *   `IntlChar::Property_BIDI_Class`
    *   `IntlChar::Property_Dash`
    *   `IntlChar::Property_Ideographic`
    *   `IntlChar::Property_Lowercase`
    *   `IntlChar::Property_Math`
    *   `IntlChar::Property_Uppercase`
    *   `IntlChar::Property_White_Space` 等…
*   `$nameChoice`：此参数保存用于获取哪个 Unicode 名称的选择器。

## 返回值

此函数在成功时返回名称，如果属性或名称选择超出范围，则返回 `false`。

以下程序说明 PHP 中的 `IntlChar::getPropertyName()` 函数：

## 示例

### 程序 1

```php
<?php
// Program illustrates the IntlChar::getPropertyName() function

var_dump(IntlChar::getPropertyName(IntlChar::PROPERTY_BIDI_MIRRORED));

var_dump(IntlChar::getPropertyName(IntlChar::PROPERTY_BIDI_MIRRORED,
        IntlChar::SHORT_PROPERTY_NAME));

var_dump(IntlChar::getPropertyName(IntlChar::PROPERTY_BIDI_MIRRORED,
        IntlChar::LONG_PROPERTY_NAME));

var_dump(IntlChar::getPropertyName(IntlChar::PROPERTY_BIDI_MIRRORED,
        IntlChar::LONG_PROPERTY_NAME + 1));

?>
```

### 输出

```php
string(13) "Bidi_Mirrored"
string(6) "Bidi_M"
string(13) "Bidi_Mirrored"
bool(false)
```