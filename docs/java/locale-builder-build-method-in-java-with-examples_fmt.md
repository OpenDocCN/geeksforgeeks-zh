# Locale.Builder的build()方法在Java中的示例

> 原文：[https://www.geeksforgeeks.org/locale-builder-build-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-builder-build-method-in-java-with-examples/)

`build()`方法在[`Locale.Builder`](https://www.geeksforgeeks.org/tag/java-locale-builder/)类中用于从指定给此`Locale.Builder`的值构建一个`Locale`实例。此方法在构建后返回一个`Locale`实例。

## 语法
```java
public Locale build()
```

## 参数
此方法不接受任何参数。

## 返回类型
该方法返回一个[`Locale`](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)实例，该实例的值设置为`Locale.Builder`。

## 异常
此方法不抛出任何异常。

## 程序 1
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

// setting the locale of Locale.Builder
        Locale locale = Locale.FRANCE;
        System.out.println("Setting the Locale: "
                           + locale);
        localeBuilder.setLocale(locale);

// Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

// Building the Locale from Locale.Builder
        System.out.println("Building the Locale.");

        Locale builtLocale = localeBuilder.build();

// Displaying Locale.Builder
        System.out.println("Built Locale: "
                           + builtLocale);
    }
}
```

## 输出
```java
Setting the Locale: fr_FR
LocaleBuilder: java.util.Locale$Builder@232204a1
Building the Locale.
Built Locale: fr_FR
```

## 程序 2
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

// setting the locale of Locale.Builder
        Locale locale = Locale.ENGLISH;
        System.out.println("Setting the Locale: "
                           + locale);
        localeBuilder.setLocale(locale);

// Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

// Building the Locale from Locale.Builder
        System.out.println("Building the Locale.");

        Locale builtLocale = localeBuilder.build();

// Displaying Locale.Builder
        System.out.println("Built Locale: "
                           + builtLocale);
    }
}
```

## 输出
```java
Setting the Locale: en
LocaleBuilder: java.util.Locale$Builder@232204a1
Building the Locale.
Built Locale: en
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#build--](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#build--)