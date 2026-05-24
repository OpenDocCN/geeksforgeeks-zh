# Java 中的 Collator 类 getAvailableLocales() 方法示例

> 原文：[https://www.geeksforgeeks.org/collator-getavailablelocales-method-in-java-with-example/](https://www.geeksforgeeks.org/collator-getavailablelocales-method-in-java-with-example/)

`java.text.Collator` 类的 `getAvailableLocales()` 方法用于在初始化 Collator 对象时获取传递的 Locales 实例下所有可用的 Locales。

**语法：**

```java
public static Locale[] getAvailableLocales()
```

**参数：** 此方法不接受任何参数。
**返回值：** 该方法返回该实例下所有可用的地区（`Locale`）。

以下是举例说明 `getAvailableLocales()` 方法：

## 示例 1

```java
// Java program to demonstrate
// getAvailableLocales() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing new simple rule
            String simple = "< a< b< c< d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // getting all the available locale
            // using getAvailableLocales() method
            Locale[] locale = col.getAvailableLocales();

            // display result
            System.out.println("Equivalent Locales are ");
            for (int i = 1; i <= 5; i++)
                System.out.println(locale[i]);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ParseException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**

```java
Equivalent Locales are 
ar_AE
ar_JO
ar_SY
hr_HR
fr_BE
```

## 示例 2

```java
// Java program to demonstrate
// getAvailableLocales() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing Collator Object
            Collator col = Collator.getInstance(Locale.UK);

            // getting all the available locale
            // using getAvailableLocales() method
            Locale[] locale = col.getAvailableLocales();

            // display result
            System.out.println("Equivalent Locales are ");
            for (int i = 6; i <= 10; i++)
                System.out.println(locale[i]);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**

```java
Equivalent Locales are 
es_PA
es_VE
mt_MT
bg
zh_TW
```

**参考：** [`https://docs.oracle.com/javase/9/docs/api/java/text/Collator.html#getAvailableLocales--`](https://docs.oracle.com/javase/9/docs/api/java/text/Collator.html#getAvailableLocales--)