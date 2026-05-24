# Locale.setDefault(Locale.Category, Locale) 方法，示例

> 原文：[`https://www.geeksforgeeks.org/locale-setdefaultlocale-category-locale-method-in-java-with-examples/`](https://www.geeksforgeeks.org/locale-setdefaultlocale-category-locale-method-in-java-with-examples/)

`setDefault(Locale.Category cate, Locale newLoc)` 是 [`Locale`](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/) 类的方法，用于设置 JVM（Java 虚拟机）这个实例的默认区域设置，这丝毫不会影响区域设置主机。

## 语法

```java
public static void 
    setDefault(Locale.Category cate,  
               Locale newLocale)
```

## 参数

该方法取两个参数：

*   `cate`：这是 `Locale.Category` 类型，并指定默认区域设置要设置到的类别。
*   `newLoc`：这也是 `Locale` 类型，指的是新的默认区域设置。

## 返回值

该方法不返回值。

## 异常

该方法可以抛出如下异常：

*   `SecurityException`：如果安全管理器存在，并且其 `checkPermission` 方法不允许该操作，则会引发此问题。
*   [`NullPointerException`](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)：如果 `newLoc` 为空，则抛出此异常。

下面的程序说明了 `Locale` 类的 `setDefault()` 方法：

### 示例 1

```java
// Java code to illustrate setDefault() method

import java.util.*;

class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("nu", "NO", "NY");

        // Displaying first locale
        System.out.println("First Locale: "
                           + first_locale);

        // Setting the Locale
        Locale.setDefault(Locale.Category.DISPLAY,
                          new Locale("ar", "SA"));

        Locale new_locale = Locale.getDefault();

        // Displaying the default locale of new locale
        System.out.println("The default locale: "
                           + new_locale);
    }
}
```

**输出：**

```java
First Locale: nu_NO_NY
The Hash Code: en_US
```

### 示例 2

```java
// Java code to illustrate setDefault() method

import java.util.*;

class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("en", "IN");

        // Displaying first locale
        System.out.println("First Locale: "
                           + first_locale);

        // Setting the Locale
        Locale.setDefault(Locale.Category.FORMAT,
                          new Locale("en", "US"));

        Locale new_locale = Locale.getDefault();

        // Displaying the default locale of new locale
        System.out.println("The default locale: "
                           + new_locale);
    }
}
```

**输出：**

```java
First Locale: en_IN
The Hash Code: en_US
```

## 参考

[`https://docs.oracle.com/javase/9/docs/api/java/util/Locale.html#getDefault--`](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.html#getDefault--)