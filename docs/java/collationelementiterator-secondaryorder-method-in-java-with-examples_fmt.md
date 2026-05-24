# Java 中的 `CollationElementIterator.secondaryOrder()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/collationelementiterator-secondaryorder-method-in-java-with-examples/](https://www.geeksforgeeks.org/collationelementiterator-secondaryorder-method-in-java-with-examples/)

类的 `secondaryOrder()` 方法用于提供 `CollationElementIterator` 对象的每个归类元素的辅助组件。

**语法：**

```java
public static final short secondaryOrder(int order)
```

**参数：** 该方法以整数格式的归类元素作为参数，必须为其找到二次成分。
**返回值：** 该方法返回特定归类元素的二级组件。

以下是举例说明 `secondaryOrder()` 方法的例子：

**例 1：**

## Java 语言示例

```java
// Java program to demonstrate
// secondaryOrder() method

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

            // getting secondary component of every element
            // using secondaryOrder() method
            int value
                = CollationElementIterator
                      .secondaryOrder(cel.next());

            // display the result
            System.out.println("secondary order "
                               + "for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**Output：**

```java
secondary order for order 1 is 0
secondary order for order 2 is 0
secondary order for order 3 is 0
secondary order for order 4 is 0
secondary order for order 5 is 0
secondary order for order 6 is 0
secondary order for order 7 is 0
secondary order for order 8 is 0
secondary order for order 9 is 0
secondary order for order 10 is 0
secondary order for order 11 is 0
secondary order for order 12 is 0
secondary order for order 13 is 0
```

**例 2：**

## Java 语言示例

```java
// Java program to demonstrate
// secondaryOrder() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing testString
        String test
            = "Code Geeks 123<>?";

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

            // getting secondary component of every element
            // using secondaryOrder() method
            int value
                = CollationElementIterator
                      .secondaryOrder(cel.next());

            // display the result
            System.out.println("secondary order "
                               + "for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**Output：**

```java
secondary order for order 1 is 0
secondary order for order 2 is 0
secondary order for order 3 is 0
secondary order for order 4 is 0
secondary order for order 5 is 1
secondary order for order 6 is 0
secondary order for order 7 is 0
secondary order for order 8 is 0
secondary order for order 9 is 0
secondary order for order 10 is 0
secondary order for order 11 is 1
secondary order for order 12 is 0
secondary order for order 13 is 0
secondary order for order 14 is 0
secondary order for order 15 is 0
secondary order for order 16 is 0
secondary order for order 17 is 0
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#secondaryOrder-int-](https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#secondaryOrder-int-)