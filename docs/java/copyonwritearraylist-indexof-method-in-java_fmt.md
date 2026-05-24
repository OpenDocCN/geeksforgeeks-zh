# Java 中的 CopyOnWriteArrayList indexOf()方法

> 原文: [https://www.geeksforgeeks.org/copyonwritearraylist-indexof-method-in-java/](https://www.geeksforgeeks.org/copyonwritearraylist-indexof-method-in-java/)

`indexOf(Object o)` 方法属于 `CopyOnWriteArrayList`，它返回元素在列表中第一次出现的位置。如果列表中不存在该元素，则返回 -1。

## 语法

```java
public int indexOf(Object o)
```

## 参数

该函数接受一个参数 `o`，将返回该参数的第一次出现位置。

## 返回值

函数返回元素的第一次出现位置。如果该元素不在列表中，则返回 -1。

以下程序说明了上述功能:

### 程序 1

```java
// Java Program to illustrate the CopyOnWriteArrayList
// indexOf() method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(32);
        ArrLis.add(67);
        ArrLis.add(67);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        // first occurrence of 67
        System.out.println("indexOf value: " + ArrLis.indexOf(67));
    }
}
```

### 输出

```java
CopyOnWriteArrayList: [32, 67, 67, 100]
indexOf value: 1
```

### 程序 2

```java
// Java Program to illustrate the CopyOnWriteArrayList
// indexOf() method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(32);
        ArrLis.add(67);
        ArrLis.add(67);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                                    + ArrLis);

        // 200 is not present
        System.out.println("indexOf value: "
                     + ArrLis.indexOf(200));
    }
}
```

### 输出

```java
CopyOnWriteArrayList: [32, 67, 67, 100]
indexOf value: -1
```

`indexOf(E e, int index)` 方法属于 `CopyOnWriteArrayList`，它返回在指定位置 `index` 之后，元素 `e` 第一次出现的位置。如果列表中不存在该元素，则返回 -1。

## 语法

```java
public int indexOf(E e, int index)
```

## 参数

该函数接受两个参数，如下所述:

*   `index`: 指定开始搜索的索引位置。
*   `e`: 指定要返回其从位置 `index` 开始第一次出现的元素。

## 返回值

函数返回在位置 `index` 之后，元素的第一次出现位置。如果该元素不在列表中，则返回 -1。

## 异常

如果指定的索引为负，该函数将抛出 `ArrayIndexOutOfBoundsException`。

以下程序说明了上述功能:

### 程序 1

```java
// Java Program to illustrate the CopyOnWriteArrayList
// indexOf() method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(32);
        ArrLis.add(67);
        ArrLis.add(67);
        ArrLis.add(67);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                                    + ArrLis);

        // first occurrence of 67 from 2nd index
        System.out.println("indexOf value: "
                     + ArrLis.indexOf(67, 2));
    }
}
```

### 输出

```java
CopyOnWriteArrayList: [32, 67, 67, 67]
indexOf value: 2
```

### 程序 2

```java
// Java Program to illustrate the CopyOnWriteArrayList
// indexOf() method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(32);
        ArrLis.add(67);
        ArrLis.add(67);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                                    + ArrLis);

        // -1 is out of range, hence exception
        System.out.println("indexOf value: "
                  + ArrLis.indexOf(-1, 200));
    }
}
```

### 输出

```java
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: -1
    at java.util.concurrent.CopyOnWriteArrayList.indexOf(CopyOnWriteArrayList.java:198)
    at java.util.concurrent.CopyOnWriteArrayList.indexOf(CopyOnWriteArrayList.java:263)
    at GFG.main(GFG.java:24)
```

**参考:** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#indexOf-E-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#indexOf-E-int-)