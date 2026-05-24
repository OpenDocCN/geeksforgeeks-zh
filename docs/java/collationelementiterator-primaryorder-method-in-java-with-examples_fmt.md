# Java 中的排序器 `primaryOrder()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/collationelementiterator-primaryorder-method-in-java-with-examples/](https://www.geeksforgeeks.org/collationelementiterator-primaryorder-method-in-java-with-examples/)

`CollationElementIterator` 类的 `primaryOrder()` 方法用于提供 `CollationElementIterator` 对象的每个排序元素的主要组件。

**语法：**

```java
public static final int primaryOrder(int order)
```

**参数：** 该方法以整数格式的**排序元素**作为参数，必须找到其主成分。

**返回值：** 该方法返回特定排序元素的**主分量**。

以下是说明 `primaryOrder()` 方法的示例：

**例 1：**

### Java 语言示例

```java
// Java program to demonstrate
// primaryOrder() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing testString
        String test = "GeeksForGeeks";

        // creating and initializing
        // RuleBasedCollator object
        RuleBasedCollator rbc
            = (RuleBasedCollator)(Collator.getInstance());

        // creating and initializing
        // CollationElementIterator
        CollationElementIterator cel
            = rbc.getCollationElementIterator(test);

        // for iteration
        for (int i = 1; i <= test.length(); i++) {

            // getting primary component of every elmenet
            // using primaryOrder() method
            int value
                = CollationElementIterator
                      .primaryOrder(cel.next());

            // display the reslut
            System.out.println("primary order "
                               + "for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**输出：**

```java
primary order for order 1 is 89
primary order for order 2 is 87
primary order for order 3 is 87
primary order for order 4 is 93
primary order for order 5 is 101
primary order for order 6 is 88
primary order for order 7 is 97
primary order for order 8 is 100
primary order for order 9 is 89
primary order for order 10 is 87
primary order for order 11 is 87
primary order for order 12 is 93
primary order for order 13 is 101
```

**例 2：**

### Java 语言示例

```java
// Java program to demonstrate
// primaryOrder() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing testString
        String test
            = "Code Geeks 123";

        // creating and initializing
        // RuleBasedCollator object
        RuleBasedCollator rbc
            = (RuleBasedCollator)(Collator.getInstance());

        // creating and initializing
        // CollationElementIterator
        CollationElementIterator cel
            = rbc.getCollationElementIterator(test);

        // for iteration
        for (int i = 1; i <= test.length(); i++) {

            // getting primary component of every elmenet
            // using primaryOrder() method
            int value
                = CollationElementIterator
                      .primaryOrder(cel.next());

            // display the reslut
            System.out.println("primary order "
                               + "for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**输出：**

```java
primary order for order 1 is 84
primary order for order 2 is 97
primary order for order 3 is 85
primary order for order 4 is 87
primary order for order 5 is 0
primary order for order 6 is 89
primary order for order 7 is 87
primary order for order 8 is 87
primary order for order 9 is 93
primary order for order 10 is 101
primary order for order 11 is 0
primary order for order 12 is 70
primary order for order 13 is 71
primary order for order 14 is 72
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#primaryOrder-int-](https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#primaryOrder-int-)