# Java 中的十进制格式符号 getAvailableLocales() 方法示例

> 原文: [https://www.geeksforgeeks.org/decimalformatsymbols-getavailablelocales-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getavailablelocales-method-in-java-with-examples/)

`getAvailableLocales()` 方法属于 `DecimalFormatSymbols` 类，用于获取该类所有可用区域设置的列表。此方法返回可用区域设置的数组。

## 语法

```java
public static Locale[] getAvailableLocales()
```

## 参数

此方法不接受任何参数。

## 返回值

该方法返回 `DecimalFormatSymbols` 的所有可用区域设置的数组。

## 异常

此方法不抛出任何异常。

## 程序

## 输出

```
可用的地方: [, ar_AE, ar_JO, ar_SY, hr_HR, fr_BE, es_PA, mt_MT, es_VE, bg, zh_TW, it, ko, uk, lv, da_DK, ar_SD, en, ro, en_PH, ca, ar_TN, sr_ME_#Latn, es_GT, sl, ko_KR, el_CY, es_MX, ru_RU, es_HN, zh_HK, NO_NY, hu_HU, th_TH, ar_IQ, es_CL, fi, ar_MA, ga_IE, mk, tr_TR, et_EE, ar_QA, sr__#Latn, pt_PT, fr_LU, ar_OM]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getAvailableLocales--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getAvailableLocales--)