# Java Locale.Builder setScript()方法详解与示例

> 原文：[https://www.geeksforgeeks.org/locale-builder-setscript-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setscript-method-in-java-with-examples/)

[`Locale.Builder`](https://www.geeksforgeeks.org/tag/java-locale-builder/)类的[`setScript(String)`](https://www.geeksforgeeks.org/java-util-package-java/)方法用于设置此`Locale.Builder`转换为指定的脚本。这意味着此方法将设置`Locale.Builder`实例的当前脚本，以匹配所提供的脚本并返回它。如果指定的脚本为空，则删除该`Locale.Builder`的脚本。格式良好的脚本值由ISO 15924标准定义的4个字母的脚本代码组成。

## 语法
```java
public Locale.Builder setScript(String script)
```

## 参数
该方法接受`script`作为参数，该参数是要设置到此`Locale.Builder`实例的字符串。

## 返回值
该方法返回一个`Locale.Builder`实例，其脚本已设置为指定的脚本。

## 异常
此方法抛出以下异常：
* `IllformedLocaleException`：如果指定的脚本有任何格式不正确的字段。

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

// setting the script of Locale.Builder
        String script = "Gujr";
        System.out.println("Setting the script: "
                           + script);

        localeBuilder
            = localeBuilder.setScript(script);

// Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

## 输出
```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the script: Gujr
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

// setting the script of Locale.Builder
        String script = "asda@vasdev#";
        System.out.println("Setting the script: "
                           + script);

        try{
            localeBuilder
                = localeBuilder.setScript(script);

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
Setting the script: asda@vasdev#
java.util.IllformedLocaleException:
 Ill-formed script: asda@vasdev# [at index 0]
```

## 参考
[`https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setScript-java.lang.String-`](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setScript-java.lang.String-)