# Locale.Builder.setVariant() 方法示例

> 原文：[https://www.geeksforgeeks.org/locale-builder-setvariant-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setvariant-method-in-java-with-examples/)

[`Locale.Builder`](https://www.geeksforgeeks.org/tag/java-locale-builder/) 类中的 [`setVariant(String)`](https://www.geeksforgeeks.org/java-util-package-java/) 方法用于设置此 `Locale.Builder` 转换为指定的变体。这意味着此方法将设置 `Locale.Builder` 实例的当前变体，以匹配所提供的变量并返回它。如果指定的变体为空，则删除该 `LocaleBuilder` 的变体。根据 IETF BCP 47 变体子标签的语法要求检查指定的变体，之后将其规范化为小写。

## 语法

```java
public Locale.Builder setVariant(String variant)
```

## 参数

该方法接受 `variant` 作为参数，该参数是要设置到该 `Locale.Builder` 实例的字符串。

## 返回值

该方法返回一个 `Locale.Builder` 实例，其变体已设置为指定的变体。

## 异常

此方法抛出以下异常：

*   `IllformedLocaleException`：如果指定的变体有任何格式错误的字段。

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

        // setting the variant of Locale.Builder
        String variant
            = (new Locale("nu", "NO", "NY"))
                  .getDisplayVariant();
        System.out.println("Setting the variant: "
                           + variant);

        localeBuilder
            = localeBuilder.setVariant(variant);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

## 输出

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the variant: Nynorsk
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

        // setting the variant of Locale.Builder
        String variant = "asdasf@!vsd#";
        System.out.println("Setting the variant: "
                           + variant);

        try{
            localeBuilder
                = localeBuilder.setVariant(variant);

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
Setting the variant: asdasf@!vsd#
java.util.IllformedLocaleException:
 Ill-formed variant:
 asdasf@!vsd# [at index 0]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setVariant-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setVariant-java.lang.String-)