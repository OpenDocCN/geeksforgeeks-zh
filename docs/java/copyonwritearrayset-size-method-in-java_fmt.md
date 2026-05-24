# Java 中的 CopyOnWriteArraySet `size()`方法

> 原文: [https://www.geeksforgeeks.org/copyonwritearrayset-size-method-in-java/](https://www.geeksforgeeks.org/copyonwritearrayset-size-method-in-java/)

`size()`方法返回集合的大小。它返回当前集合中的元素数量。

## 语法

```java
public int size()
```

## 返回值

该函数返回当前集合中的元素数量。

以下程序说明了上述功能:

## 程序 1

```java
// Java Program to illustrate the CopyOnWriteArraySet
// size() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet
            = new CopyOnWriteArraySet<Integer>();

// print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

// size value print
        System.out.println("size of ArrSet: "
                           + ArrSet.size());

// Add elements
        ArrSet.add(32);
        ArrSet.add(67);
        ArrSet.add(98);
        ArrSet.add(100);

// print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

// size value print
        System.out.println("size of ArrSet: "
                           + ArrSet.size());
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: []
size of ArrSet: 0
CopyOnWriteArraySet: [32, 67, 98, 100]
size of ArrSet: 4
```

## 程序二

```java
// Java Program to illustrate the CopyOnWriteArraySet
// size() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<String> ArrSet
            = new CopyOnWriteArraySet<String>();

// Add elements
        ArrSet.add("gopal");
        ArrSet.add("gfg");
        ArrSet.add("jgec");
        ArrSet.add("sudo");

// print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

// size value print
        System.out.println("size of ArrSet: "
                           + ArrSet.size());
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: [gopal, gfg, jgec, sudo]
size of ArrSet: 4
```

**参考:** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArraySet.html#size--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArraySet.html#size--)