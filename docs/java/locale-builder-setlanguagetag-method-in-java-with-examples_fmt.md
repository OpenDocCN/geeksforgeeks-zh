# Java Locale.Builder setLanguageTag() 方法详解与示例

> 原文：[https://www.geeksforgeeks.org/locale-builder-setlanguagetag-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setlanguagetag-method-in-java-with-examples/)

[`java.util`](https://www.geeksforgeeks.org/java-util-package-java/) 包中 [`Locale.Builder`](https://www.geeksforgeeks.org/tag/java-locale-builder/) 类的 [`setLanguageTag(String)`](https://www.geeksforgeeks.org/locale-builder-setlanguagetag-method-in-java-with-examples/) 方法用于将此 `Locale.Builder` 重置为指定的 IETF BCP 47 语言标签。这意味着此方法将重置 `Locale.Builder` 实例的当前状态，以匹配提供的语言标签并返回它。

## 语法

```java
public Locale.Builder setLanguageTag(String languageTag)
```

## 参数

该方法接受 `languageTag` 作为参数，这是要设置到此 `Locale.Builder` 实例的字符串。

## 返回值

该方法返回一个 `Locale.Builder` 实例，这是其状态被设置为指定语言标签的 `Locale.Builder`。

## 异常

此方法抛出以下异常：

*   `IllformedLocaleException`：如果指定的 `languageTag` 包含任何格式错误的字段。

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

        // Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

        // setting the languageTag
        // of Locale.Builder
        String languageTag = "FRENCH";
        System.out.println("Setting the language: "
                           + languageTag);

        localeBuilder
            = localeBuilder
                  .setLanguageTag(languageTag);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

## 输出

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the language: FRENCH
Updated LocaleBuilder: java.util.Locale$Builder@232204a1
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

        // Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

        // setting the languageTag
        // of Locale.Builder
        String languageTag = "asdasf@!vsd#";
        System.out.println("Setting the languageTag: "
                           + languageTag);

        try {
            localeBuilder
                = localeBuilder
                      .setLanguageTag(languageTag);

            // Displaying Locale.Builder
            System.out.println("Updated LocaleBuilder: "
                               + localeBuilder);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

## 输出

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the languageTag: asdasf@!vsd#
java.util.IllformedLocaleException: Invalid subtag: asdasf@!vsd# [at index 0]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setLanguageTag-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setLanguageTag-java.lang.String-)