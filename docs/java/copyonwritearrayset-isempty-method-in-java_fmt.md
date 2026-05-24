# Java 中的 CopyOnWriteArraySet isEmpty() 方法

> 原文：[https://www.geeksforgeeks.org/copyonwritearrayset-isempty-method-in-java/](https://www.geeksforgeeks.org/copyonwritearrayset-isempty-method-in-java/)

[`isEmpty()`](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/) 方法用于检查集合是否为空。如果集合为空，则返回 `true`，否则返回 `false`。

**语法：**

```java
public boolean isEmpty()
```

**返回值：** 如果集合为空，则函数返回 `true`，否则返回 `false`。

以下程序说明了上述功能：

## 程序 1

```java
// Java Program to illustrate the
// isEmpty() method in CopyOnWriteArraySet

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet.add(32);
        ArrSet.add(67);
        ArrSet.add(98);
        ArrSet.add(100);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: " + ArrSet);

        // check using function
        if (ArrSet.isEmpty())
            System.out.println("\nSet is empty");
        else
            System.out.println("\nSet is not empty");
    }
}
```

**输出：**

```java
CopyOnWriteArraySet: [32, 67, 98, 100]

Set is not empty
```

## 程序 2

```java
// Java Program to illustrate the
// isEmpty() method in CopyOnWriteArraySet
import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<String> ArrSet
            = new CopyOnWriteArraySet<String>();

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // check using function
        if (ArrSet.isEmpty())
            System.out.println("\nSet is empty");
        else
            System.out.println("\nSet is not empty");
    }
}
```

**输出：**

```java
CopyOnWriteArraySet: []

Set is empty
```

**参考：** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArraySet.html#isEmpty--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArraySet.html#isEmpty--)