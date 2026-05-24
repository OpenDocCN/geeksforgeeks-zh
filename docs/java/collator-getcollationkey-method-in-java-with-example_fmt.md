# Java 中的 `Collator getCollationKey()` 方法示例

> 原文：[https://www.geeksforgeeks.org/collator-getcollationkey-method-in-java-with-example/](https://www.geeksforgeeks.org/collator-getcollationkey-method-in-java-with-example/)

`java.text.Collator` 类的 `getCollationKey()` 方法用于获取从传递到其中的字符串转换而来的一系列位。

## 语法

```java
public abstract CollationKey
       getCollationKey(String source)
```

## 参数
该方法接受 `String` 对象作为参数。

## 返回值
该方法返回从传递给它的字符串转换而来的一系列位。

以下是说明 `getCollationKey()` 方法的示例：

### 示例 1

```java
// Java program to demonstrate
// getCollationKey() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

// Creating and initializing
            // new simple rule
            String simple
                = "< a < b < c < d";

// Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

// getting series of bits
            // using getCollationKey() method
            CollationKey key
                = col.getCollationKey("Geek");

// display result
            System.out.println(
                "Series of bits are :- "
                + key.getSourceString());
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
Series of bits are :- Geek
```

### 示例 2

```java
// Java program to demonstrate
// getCollationKey() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

// Creating and initializing
            // Collator Object
            Collator col
                = Collator.getInstance(Locale.UK);

// getting series of bits
            // using getCollationKey() method
            CollationKey key
                = col.getCollationKey("CodeBlock");

// display result
            System.out.println(
                "Series of bits are :- "
                + key.getSourceString());
        }

catch (ClassCastException e) {

System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**

```java
Series of bits are :- CodeBlock
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/text/Collator.html#getCollationKey-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/text/Collator.html#getCollationKey-java.lang.String-)