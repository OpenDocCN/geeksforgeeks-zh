# Java中的Builder setRegion()方法示例

> 原文：`https://www.geeksforgeeks.org/locale-builder-setregion-method-in-java-with-examples/`

`setRegion(String region)`方法在`java.util.Locale.Builder`类中用于为当前`Locale.Builder`实例设置区域。这意味着此方法将设置当前`Locale.Builder`实例的区域以匹配提供的区域，并返回该实例。如果指定的区域为空，则该区域将被删除。格式良好的区域值包括由ISO 3166标准定义的**2个字母的区域代码或3位联合国M.49区号**。

## 语法
```java
public Locale.Builder setRegion(String region)
```

## 参数
该方法接受`region`作为参数，该参数是要设置到该`Locale.Builder`实例的区域字符串。

## 返回值
该方法返回一个具有此区域设置的`Locale.Builder`实例。

## 异常
此方法抛出以下异常：
* `IllformedLocaleException`：如果指定的区域中有任何格式不正确的字段。

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

// setting the region of Locale.Builder
        String region = "IN";
        System.out.println("Setting the region: "
                           + region);

        localeBuilder
            = localeBuilder.setRegion(region);

// Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

## 输出
```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the region: IN
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

// setting the region of Locale.Builder
        String region = "asdasf@!vsd#";
        System.out.println("Setting the region: "
                           + region);

        try {
            localeBuilder
                = localeBuilder.setRegion(region);

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
Setting the region: asdasf@!vsd#
java.util.IllformedLocaleException:
 Ill-formed region:
 asdasf@!vsd# [at index 0]
```

## 参考
`https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setRegion-java.lang.String-`