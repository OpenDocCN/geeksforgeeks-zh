# Locale.Builder.setLocale(Locale)方法示例

> 原文：[https://www.geeksforgeeks.org/locale-builder-setlocalelocale-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setlocalelocale-method-in-java-with-examples/)

`java.util` 的 `setLocale(Locale)` 方法（[`Locale.Builder`](https://www.geeksforgeeks.org/tag/java-locale-builder/)类）用来重置这个`Locale.Builder`转换为指定的区域设置。这意味着此方法将重置`Locale.Builder`的当前状态实例来匹配所提供的区域设置并返回它。

## 语法

```java
public Locale.Builder setLocale(Locale locale)
```

## 参数

该方法接受`locale`作为参数，该参数是要设置到该`Locale.Builder`实例的区域设置。

## 返回值

该方法返回一个`Locale.Builder`实例，这是该`Locale.Builder`的状态设置为指定的区域设置。

## 异常

此方法抛出以下异常：

*   `IllformedLocaleException`：如果指定的区域设置有任何格式不正确的字段。
*   `NullPointerException`：如果指定的区域设置被设置为`null`。

## 程序1

```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleBuilderDemo {
    public static void main(String[] args)
    {

// Creating a new Locale.Builder
        Locale.Builder localeBuilder
            = new Builder();

// Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

// setting the locale of Locale.Builder
        Locale locale = Locale.FRANCE;
        System.out.println("Setting the Locale: "
                           + locale);

        localeBuilder
            = localeBuilder.setLocale(locale);

// Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

## 输出

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the Locale: fr_FR
Updated LocaleBuilder: java.util.Locale$Builder@232204a1
```

## 程序2

```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleBuilderDemo {
    public static void main(String[] args)
    {

// Creating a new Locale.Builder
        Locale.Builder localeBuilder
            = new Builder();

// Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

// setting the locale of Locale.Builder
        Locale locale = Locale.ENGLISH;
        System.out.println("Setting the Locale: "
                           + locale);

        localeBuilder
            = localeBuilder.setLocale(locale);

// Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

## 输出

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the Locale: en
Updated LocaleBuilder: java.util.Locale$Builder@232204a1
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setLocale-java.util.Locale-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setLocale-java.util.Locale-)