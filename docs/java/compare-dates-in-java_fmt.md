# 比较 Java 中的日期

> 原文：[https://www.geeksforgeeks.org/compare-dates-in-java/](https://www.geeksforgeeks.org/compare-dates-in-java/)

`Date`类代表特定的时间瞬间，精度为毫秒。`java.util`包的`Date`类实现了`Serializable`、`Cloneable`和`Comparable`接口。它提供了用`java`处理日期和时间的构造函数和方法。

以下是`java`中比较日期的方法：

## 1. 使用 `Date.compareTo()`
**涉及的步骤：**
1.  为`SimpleDateFormat`类创建一个对象，用格式`yyyy-mm-dd`初始化它。
2.  使用上述对象初始化日期变量。
3.  使用`Date`类的`compareTo()`函数进行日期比较。
4.  打印结果。

## 2. 使用 `Date.before()`、`Date.after()` 和 `Date.equals()`
这种方法比第一种简单。
**涉及的步骤：**
1.  为`SimpleDateFormat`类创建一个对象，用格式`yyyy-mm-dd`初始化它。
2.  使用上述对象初始化日期变量。
3.  使用`Date`类的`after()`和`before()`函数进行日期比较。
4.  打印结果。

## 3. 使用 `Calendar.before()`、`Calendar.after()` 和 `Calendar.equals()`
**涉及的步骤：**
1.  为`SimpleDateFormat`类创建一个对象，用格式`yyyy-mm-dd`初始化它。
2.  使用上述对象初始化日期变量。
3.  使用`getInstance()`函数初始化`Calendar`类对象。
4.  使用`Calendar`类的`setTime()`函数将值分配给`Calendar`对象。
5.  使用`Calendar`类的`after()`和`before()`函数进行日期比较。
6.  打印结果。

## 4. 使用 Java 8 的 `isBefore()`、`isAfter()`、`isEqual()` 和 `compareTo()` 方法
在 Java 8 中，`isBefore()`、`isAfter()`、`isEqual()`和`compareTo()`用于比较`LocalDate`、`LocalTime`和`LocalDateTime`。
**涉及的步骤：**
1.  创建`LocalDate`类的对象。
2.  使用`Date`类的`isAfter()`、`isBefore()`和`isEqual()`函数来比较日期。
3.  打印结果。