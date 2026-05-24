# Java中的Locale.Builder.clear()方法示例

> 原文：[https://www.geeksforgeeks.org/locale-builder-clear-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-builder-clear-method-in-java-with-examples/)

`java.util.Locale.Builder`类的`clear()`方法用来重置这个`Locale.Builder`，这意味着这个方法会创建`Locale`的另一个实例。生成器将所有属性重置为初始状态并返回。

**语法：**

```java
public Locale.Builder clear()
```

**参数：** 此方法不接受任何参数。

**返回值：** 这个方法返回一个`Locale.Builder`实例，它是此区域设置生成器的重置状态，设置为其初始状态。

**异常：** 这个方法不抛出任何异常。

**程序：**

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

        // Clearing Locale.Builder
        System.out.println("Clearing the LocaleBuilder");
        localeBuilder = localeBuilder.clear();

        // Displaying Locale.Builder
        System.out.println("Cleared LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出：**

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Clearing the LocaleBuilder
Cleared LocaleBuilder: java.util.Locale$Builder@232204a1
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#clear--](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#clear--)