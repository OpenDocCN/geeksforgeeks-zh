# Java 中的 Builder setLanguage() 方法，带示例

> 原文: [https://www.geeksforgeeks.org/locale-builder-setlanguage-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setlanguage-method-in-java-with-examples/)

[`java.util`](https://www.geeksforgeeks.org/java-util-package-java/) 的 [`setLanguage(String)`](https://www.geeksforgeeks.org/tag/java-locale-builder/) 方法在 [`Locale.Builder`](https://www.geeksforgeeks.org/tag/java-locale-builder/) 类中，用于设置此 `Locale.Builder` 转换为指定的语言。这意味着此方法将设置 `Locale.Builder` 实例的当前语言，以匹配所提供的语言并返回它。如果指定的语言为 `null` 或空，则删除该 `LocaleBuilder` 的语言。

## 语法
```java
public Locale.Builder setLanguage(String language)
```

## 参数
该方法接受 `language` 作为参数，该参数是要设置到该 `Locale.Builder` 实例的字符串。

## 返回值
该方法返回一个 `Locale.Builder` 实例，其语言被设置为指定的语言。

## 异常
此方法抛出以下异常:
*   `IllformedLocaleException`: 如果指定的语言包含任何格式不正确的字段。

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

        // setting the language of Locale.Builder
        String language = "FRENCH";
        System.out.println("Setting the language: "
                           + language);

        localeBuilder
            = localeBuilder.setLanguage(language);

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

        // setting the language of Locale.Builder
        String language = "asdasf@!vsd#";
        System.out.println("Setting the language: "
                           + language);

        try{
            localeBuilder
                = localeBuilder.setLanguage(language);

            // Displaying Locale.Builder
            System.out.println("Updated LocaleBuilder: "
                               + localeBuilder);
        }
        catch(Exception e)
        {
            System.out.println(e);
        }
    }
}
```

## 输出
```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the language: asdasf@!vsd#
java.util.IllformedLocaleException: Ill-formed language: asdasf@!vsd# [at index 0]
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setLanguage-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setLanguage-java.lang.String-)