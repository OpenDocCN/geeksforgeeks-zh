# Java 中的 CopyOnWriteArrayList lastIndexOf() 方法

> 原文：[https://www.geeksforgeeks.org/copyonwritearraylist-lastindexof-method-in-java/](https://www.geeksforgeeks.org/copyonwritearraylist-lastindexof-method-in-java/)

## `lastIndexOf(Object o)` 方法

`CopyOnWriteArrayList` 的 `lastIndexOf(Object o)` 方法返回传入元素在列表中最后一次出现的位置。如果列表中不存在该元素，则返回 -1。

**语法：**

```java
public int lastIndexOf(Object o)
```

**参数：** 该函数接受一个参数 `o`，该参数的最后一次出现位置将被返回。

**返回值：** 函数返回元素最后一次出现的索引。如果该元素不在列表中，则返回 -1。

以下程序说明了上述功能：

**程序 1：**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// lastIndexOf() method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args) {
        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(32);
        ArrLis.add(67);
        ArrLis.add(67);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        // last occurrence of 67
        System.out.println("lastIndexOf value: " + ArrLis.lastIndexOf(67));
    }
}
```

**Output：**

```java
CopyOnWriteArrayList: [32, 67, 67, 100]
lastIndexOf value: 2
```

**程序 2：**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// lastIndexOf() method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args) {
        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(32);
        ArrLis.add(67);
        ArrLis.add(67);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        // 200 is not present
        System.out.println("lastIndexOf value: " + ArrLis.lastIndexOf(200));
    }
}
```

**Output：**

```java
CopyOnWriteArrayList: [32, 67, 67, 100]
lastIndexOf value: -1
```

## `lastIndexOf(E e, int index)` 方法

`CopyOnWriteArrayList` 的 `lastIndexOf(E e, int index)` 方法返回在指定位置 `index` 之后，传入元素在列表中最后一次出现的位置。如果列表中不存在该元素，则返回 -1。

**语法：**

```java
public int lastIndexOf(E e, int index)
```

**参数：** 该函数接受两个参数，如下所述：

*   `index`：指定从中开始向前搜索的起始索引。
*   `e`：指定要查找的元素，将返回其在位置 `index` 之前最后一次出现的索引。

**返回值：** 函数返回在指定索引 `index` 之前，元素最后一次出现的索引。如果该元素不在列表中，则返回 -1。

**异常：** 如果指定的索引为负，该函数将抛出 `ArrayIndexOutOfBoundsException`。

以下程序说明了上述功能：

**程序 1：**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// lastIndexOf() method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args) {
        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(32);
        ArrLis.add(67);
        ArrLis.add(67);
        ArrLis.add(67);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        // last occurrence of 67 from 2nd index
        System.out.println("lastIndexOf value: " + ArrLis.lastIndexOf(67, 2));
    }
}
```

**Output：**

```java
CopyOnWriteArrayList: [32, 67, 67, 67]
lastIndexOf value: 2
```

**程序 2：**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// lastIndexOf() method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args) {
        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(32);
        ArrLis.add(67);
        ArrLis.add(67);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        // -1 is out of range, hence exception
        System.out.println("lastIndexOf value: " + ArrLis.lastIndexOf(-1, 200));
    }
}
```

**输出：**

```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: -1
    at java.util.concurrent.CopyOnWriteArrayList.lastIndexOf(CopyOnWriteArrayList.java:198)
    at java.util.concurrent.CopyOnWriteArrayList.lastIndexOf(CopyOnWriteArrayList.java:263)
    at GFG.main(GFG.java:24)
```

**参考：** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#lastIndexOf-E-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#lastIndexOf-E-int-)