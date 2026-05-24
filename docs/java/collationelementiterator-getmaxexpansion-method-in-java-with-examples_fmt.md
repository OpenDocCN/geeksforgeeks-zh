# Java 中的 `CollationElementIterator.getMaxExpansion()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/collationelementiterator-getmaxexpansion-method-in-java-with-examples/](https://www.geeksforgeeks.org/collationelementiterator-getmaxexpansion-method-in-java-with-examples/)

`java.text.CollationElementIterator` 类的 `getMaxExpansion()` 方法用于获取任意指定序列结尾可以达到的最大扩展。

**语法：**
```java
public int getMaxExpansion(int order)
```

**参数：** 该方法以整数格式的 `order`（排序元素）为参数，必须找到最大长度。
**返回值：** 该方法返回任意指定序列结尾可以达到的 `max expansion`（最大展开）。

以下是举例说明 `getMaxExpansion()` 方法：

### 示例 1

```java
// Java program to demonstrate
// getMaxExpansion() method

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

            // getting maximum expansion
            // using getMaxExpansion() method
            int value
                = cel.getMaxExpansion(cel.next());

            // display the reslut
            System.out.println("maximum expansion "
                               + "for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**输出**
```java
maximum expansion for order 1 is 1
maximum expansion for order 2 is 1
maximum expansion for order 3 is 1
maximum expansion for order 4 is 1
maximum expansion for order 5 is 1
maximum expansion for order 6 is 1
maximum expansion for order 7 is 1
maximum expansion for order 8 is 1
maximum expansion for order 9 is 1
maximum expansion for order 10 is 1
maximum expansion for order 11 is 1
maximum expansion for order 12 is 1
maximum expansion for order 13 is 1
```

### 示例 2

```java
// Java program to demonstrate
// getMaxExpansion() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing testString
        String test
            = "Code Geeks 123";

        // creating and intiallizing
        // RuleBasedCollator object
        RuleBasedCollator rbc
            = (RuleBasedCollator)(Collator
                                  .getInstance());

        // creating and initializing
        // CollationElementIterator
        CollationElementIterator cel
            = rbc.getCollationElementIterator(test);

        // for iteration
        for (int i = 1; i <= test.length(); i++) {

            // getting maximum expansion
            // using getMaxExpansion() method
            int value
                = cel.getMaxExpansion(cel.next());

            // display the reslut
            System.out.println("maximum expansion"
                               + " for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**输出**
```java
maximum expansion for order 1 is 1
maximum expansion for order 2 is 1
maximum expansion for order 3 is 1
maximum expansion for order 4 is 1
maximum expansion for order 5 is 1
maximum expansion for order 6 is 1
maximum expansion for order 7 is 1
maximum expansion for order 8 is 1
maximum expansion for order 9 is 1
maximum expansion for order 10 is 1
maximum expansion for order 11 is 1
maximum expansion for order 12 is 1
maximum expansion for order 13 is 1
maximum expansion for order 14 is 1
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#getMaxExpansion-int-](https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#getMaxExpansion-int-)