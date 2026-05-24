# Java Locale.Builder setUnicodeLocaleKeyword() 方法详解

> 原文：[https://www.geeksforgeeks.org/locale-builder-setunicodelocalekeyword-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setunicodelocalekeyword-method-in-java-with-examples/)

[`Locale.Builder`](https://www.geeksforgeeks.org/tag/java-locale-builder/) 类中的 `setUnicodeLocaleKeyword()` 方法用于为当前 `Locale.Builder` 实例设置一个 Unicode 语言环境关键字。此方法会根据提供的键（key）和类型（type）来设置 `Locale.Builder` 的 Unicode 语言环境关键字。如果指定的 `unicodeLocaleKeywordKey` 为 `null` 或空字符串，则会从该 `Locale.Builder` 中移除对应的 Unicode 语言环境关键字。

## 语法

```java
public Locale.Builder setUnicodeLocaleKeyword(
    String unicodeLocaleKeywordKey, 
    String unicodeLocaleKeywordType)
```

## 参数

此方法接受两个参数：

*   `unicodeLocaleKeywordKey`：要为该语言环境设置的关键字字符串。
*   `unicodeLocaleKeywordType`：要为该语言环境设置的类型字符串。

## 返回类型

该方法返回一个 `Locale.Builder` 实例，其 Unicode 语言环境关键字已被设置为指定的值。

## 异常

此方法可能抛出以下异常：

*   `IllformedLocaleException`：如果 `unicodeLocaleKeywordKey` 或 `unicodeLocaleKeywordType` 的格式不符合规范。

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

        // setting the unicodeLocaleKeyword
        // of Locale.Builder
        String unicodeLocaleKeywordKey = "nu";
        String unicodeLocaleKeywordType = "thai";

        System.out.println("Setting the "
                           + "unicodeLocaleKeyword: "
                           + unicodeLocaleKeywordKey + "-"
                           + unicodeLocaleKeywordType);

        localeBuilder
            = localeBuilder
                  .setUnicodeLocaleKeyword(
                      unicodeLocaleKeywordKey,
                      unicodeLocaleKeywordType);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

## 输出

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the unicodeLocaleKeyword: nu-thai
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

        // setting the unicodeLocaleKeyword
        // of Locale.Builder
        String unicodeLocaleKeywordKey = "asf@";
        String unicodeLocaleKeywordType = "afaf$";

        System.out.println("Setting the "
                           + "unicodeLocaleKeyword: "
                           + unicodeLocaleKeywordKey + "-"
                           + unicodeLocaleKeywordType);

        try {

            localeBuilder
                = localeBuilder
                      .setUnicodeLocaleKeyword(
                          unicodeLocaleKeywordKey,
                          unicodeLocaleKeywordType);

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
Setting the unicodeLocaleKeyword: asf@-afaf$
java.util.IllformedLocaleException:
 Ill-formed Unicode locale keyword key:
 asf@ [at index 0]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setUnicodeLocaleKeyword-java.lang.String-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setUnicodeLocaleKeyword-java.lang.String-java.lang.String-)