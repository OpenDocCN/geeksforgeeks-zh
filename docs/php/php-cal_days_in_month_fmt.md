# PHP `cal_days_in_month()` 函数

> 原文：[https://www.geeksforgeeks.org/php-cal_days_in_month/](https://www.geeksforgeeks.org/php-cal_days_in_month/)

`cal_days_in_month()` 是一个内置函数，它返回指定日历中特定月份的天数。我们必须传递日历类型、月份和年份作为参数，函数将返回日历中指定年份的月份中的天数。

## 语法

```php
int cal_days_in_month ( int $calendar, int $month, int $year )
```

## 参数

*   `calendar`：用于计算的日历类型。此值是必需的。
*   `month`：所选日历中的月。此值是必需的。
*   `year`：所选日历中的年。该值也是必需的。

下面是 `calendar` 参数可以保存的可能值列表：

*   `CAL_GREGORIAN`
*   `CAL_JULIAN`
*   `CAL_JOSIPH`
*   `CAL_FRENCH`
*   `CAL_NUM_CALS`
*   `CAL_DOW_NOON`
*   `CAL_DOW_SHORT`
*   `CAL_DOW_LONG`
*   `CAL_MONTH_GREGORIAN_SHORT`
*   `CAL_MONTH_GREGORIAN_LONG`
*   `CAL_MONTH_JULIAN_SHORT`
*   `CAL_MONTH_JULIAN_LONG`
*   `CAL_MONTH_JOSIPH`
*   `CAL_MONTH_FRANCIS`
*   `CAL_EASTER_DEFAULT`
*   `CAL_EASTER_ROMAN`
*   `CAL_EASTER_ALWAYS_GREGORIAN`
*   `CAL_EASTER_ALWAYS_JULIAN`
*   `CAL_JOSIPH_ADD_ALAFIM_GERESH`
*   `CAL_JOSIPH_ADD_ALAFIM`
*   `CAL_JOSIPH_ADD_GERESHAYIM`

## 返回值

返回指定日历一年中某月的天数。

## PHP 示例

```php
<!DOCTYPE html>
<html>
<body>

<?php
$d = cal_days_in_month(CAL_GREGORIAN, 2, 1965); // Calendar Type - Gregorian
echo "There was $d days in February 1965.<br>";

$d = cal_days_in_month(CAL_GREGORIAN, 2, 2004); // Calendar Type - Gregorian
echo "There was $d days in February 2004.";
?>
</body>
</html>
```

## 输出

```
There was 28 days in February 1965.
There was 29 days in February 2004.
```