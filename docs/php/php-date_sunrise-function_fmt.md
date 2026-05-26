# PHP date_sunrise()函数

> Original: [https://www.geeksforgeeks.org/php-date_sunrise-function/](https://www.geeksforgeeks.org/php-date_sunrise-function/)

`date_sunrise()`是 PHP 中的一个内置函数，用于查找指定日期和地点的日出时间。此函数用于以指定格式返回成功时的日出时间。失败时为 `false`。

## 语法

```php
date_sunrise ( $timestamp, $format, $latitude, $longitude, $zenith, $gmtoffset )
```

## 参数

`date_sunrise()`函数接受四个参数，如上所述，如下所述：

*   `$timestamp`：这是一个必需的参数，指定要获取日出时间的日期的时间戳。
*   `$format`：可选参数，指定返回结果的格式。
    *   `SUNFUNCS_RET_STRING`：返回一个字符串。例如，`16:46`（默认）
    *   `SUNFUNCS_RET_DOUBLE`：返回一个浮点数。例如，`16.78243132`
    *   `SUNFUNCS_RET_TIMESTAMP`：以整数（时间戳）形式返回结果，例如`1095034606`。
*   `$latitude`：可选参数，指定位置的纬度。默认为北纬。要指定南纬的值，请传入负值。
*   `$longitude`：可选参数，指定位置的经度。默认为东经。要修改为西经的值，请传入负值。
*   `$zenith`：可选参数。[天顶](https://en.wikipedia.org/wiki/Zenith)是太阳中心与地球表面垂线之间的角度。默认为 `date.sunrisezenith`。
*   `$gmtoffset`：可选参数，指定格林尼治标准时间与本地时间之间的时差（以小时为单位）。

## 返回值

返回成功时指定格式的日出时间。失败时为 `false`。

## 异常

如果日期/时间函数无效，此函数会生成 `E_NOTICE` 错误，如果使用系统设置或 `TZ` 环境变量，则会生成 `E_STRICT` 或 `E_WARNING`。

下面的程序演示了`date_sunrise()`函数。

## 示例

### 程序 1

```php
<?php
// PHP program to show sunrise time 
// of New delhi india for current day

// Longitude and latitude of Delhi India
// 28.6139° N, 77.2090° E
// GMT(Greenwich Mean Time) +5.30
// Zenith ~= 90

echo date("D M d Y");
echo("\nsunrise time: ");
echo(date_sunrise(time(), SUNFUNCS_RET_STRING,
                  28.6139, 77.2090, 90, 5.30));
?>
```

**输出：**

```php
Tue Jun 26 2018
sunrise time: 05:16
```

### 程序 2

```php
<?php
// PHP program to show sunrise time 
// of GFG Noida for a Current day

// Longitude and latitude of GeeksforGeeks Noida
// 28°30'04.0"N 77°24'36.0"E
// GMT(Greenwich Mean Time) +5.30
// Zenith ~= 90

echo date("D M d Y");
echo("\nsunrise time: ");
echo(date_sunrise(time(), SUNFUNCS_RET_STRING,
              28.501120, 77.409989, 90, 5.30));
?>
```

**输出：**

```php
Tue Jun 26 2018
sunrise time: 05:15
```

## 引用

[http://php.net/manual/en/function.date-sunrise.php](http://php.net/manual/en/function.date-sunrise.php)