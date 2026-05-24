# Locale.Builder 类的 setExtension() 方法示例

> 原文: [https://www.geeksforgeeks.org/locale-builder-setextension-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setextension-method-in-java-with-examples/)

`Locale.Builder` 类的 `setExtension()` 方法用于为当前 `Locale.Builder` 实例设置扩展。这意味着此方法将设置 `Locale.Builder` 的当前扩展，使其匹配所提供的扩展键和值，并返回该实例。如果指定的扩展值为空，则删除该 `Locale.Builder` 的扩展。指定的扩展会对照 **LDML BCP 47 兼容扩展**进行检查。

**语法:**

```java
public Locale.Builder setExtension(
                          char extensionKey, 
                          String extensionValue)
```

**参数:** 此方法接受两个参数:
*   `extensionKey` : 要设置到此 `Locale.Builder` 实例的字符值。
*   `extensionValue` : 要设置到此 `Locale.Builder` 实例的字符串值。

**返回值:** 该方法返回一个 `Locale.Builder` 实例，其扩展已设置为指定的扩展。

**异常:** 此方法抛出以下异常:
*   `IllformedLocaleException` : 如果指定的扩展包含任何格式错误的字段。

**程序 1:**

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

// setting the extension of Locale.Builder
        char extensionKey = 'u';
        String extensionValue = "ca-japanese";
        System.out.println("Setting the extension: "
                           + extensionKey + "/"
                           + extensionValue);

        localeBuilder
            = localeBuilder
                  .setExtension(extensionKey,
                                extensionValue);

// Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the extension: u/ca-japanese
Updated LocaleBuilder: java.util.Locale$Builder@232204a1
```

**程序 2:**

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

// setting the extension of Locale.Builder
        char extensionKey = '@';
        String extensionValue = "fsdf#";
        System.out.println("Setting the extension: "
                           + extensionKey + "/"
                           + extensionValue);

        try {

            localeBuilder
                = localeBuilder
                      .setExtension(extensionKey,
                                    extensionValue);

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

**输出:**

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the extension: @/fsdf#
java.util.IllformedLocaleException:
 Ill-formed extension key:
 @ [at index 0]
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setExtension-char-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setExtension-char-java.lang.String-)