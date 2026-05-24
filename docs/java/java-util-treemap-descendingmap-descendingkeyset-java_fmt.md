# Java中的TreeMap.descendingMap()和descendingKeySet()

> 原文：[https://www.geeksforgeeks.org/java-util-treemap-descendingmap-descendingkeyset-java/](https://www.geeksforgeeks.org/java-util-treemap-descendingmap-descendingkeyset-java/)

`java.util.TreeMap`中有两个降序视图的变体，本文将对这两个变体进行讨论。

### 1. descendingKeySet()
返回此`TreeMap`中包含的键的逆序导航集视图。

```java
Syntax:
public NavigableSet<E> descendingKeySet()
Parameters:
NA
Return Value:
It returns a reverse order navigable set view of the keys in this map.
Exception:
NA
```

```java
// Java code to demonstrate the working
// descendingKeySet()
import java.io.*;
import java.util.*;
public class descendingKeySet1 {
    public static void main(String[] args)
    {
        // Declaring the tree map of Integer and String
        TreeMap<Integer, String> treemap = new TreeMap<Integer, String>();

        // assigning the values in the tree map
        // using put()
        treemap.put(2, "two");
        treemap.put(0, "zero");
        treemap.put(3, "three");
        treemap.put(6, "six");
        treemap.put(9, "nine");
        treemap.put(7, "seven");

        // putting values in navigable set
        // use of descendingKeySet
        NavigableSet set1 = treemap.descendingKeySet();

        System.out.println("Navigable set values are: " + set1);
    }
}
```

**输出：**

```java
Navigable set values are: [9, 7, 6, 3, 2, 0]
```

### 2. descendingMap()
返回此`TreeMap`中包含的映射的逆序视图。

```java
Syntax:
public NavigableMap<K,V> descendingMap()
Parameters:
NA
Return Value:
It returns a reverse order view of the map.
Exception:
NA
```

```java
// Java code to demonstrate the working
// of descendingMap()
import java.io.*;
import java.util.*;
public class descendingMap {
    public static void main(String[] args)
    {
        // Declaring the tree map of Integer and String
        TreeMap<Integer, String> treemap = new TreeMap<Integer, String>();

        // assigning the values in the tree map
        // using put()
        treemap.put(2, "two");
        treemap.put(0, "zero");
        treemap.put(3, "three");
        treemap.put(6, "six");
        treemap.put(9, "nine");
        treemap.put(7, "seven");

        // putting values in navigable map
        // use of descendingMap()
        NavigableMap map1 = treemap.descendingMap();

        System.out.println("Navigable map values are: " + map1);
    }
}
```

**输出：**

```java
Navigable map values are: {9=nine, 7=seven, 6=six, 3=three, 2=two, 0=zero}
```

### 实际应用
本文解释的降序函数有很多可能的应用。其中一些是优先调度，或者设计一个排名系统。下面的代码演示了后一种方法。

```java
// Java code to demonstrate the application
// of descendingMap() and descendingKeySet()
import java.io.*;
import java.util.*;
public class descendingAppli {
    public static void main(String[] args)
    {
        // Declaring the tree map of Integer and String
        // to store participants info of scores with name
        TreeMap<Integer, String> participants = new TreeMap<Integer, String>();

        // assigning score of participants
        // using put()
        participants.put(30, "Ashty");
        participants.put(45, "Shavi");
        participants.put(16, "Vaish");
        participants.put(15, "Kil");
        participants.put(11, "Manju");

        // putting ranks in NavigableMap
        // use of descendingMap() to assign 1st to
        // maximum values and so on
        NavigableMap<Integer, String> Ranks = participants.descendingMap();

        System.out.println("The ranks according to scores are : ");

        // Printing values rankwise
        int count = 0;
        for (NavigableMap.Entry<Integer, String> entry : Ranks.entrySet()) {
            count++;
            String str = Integer.toString(count);
            System.out.println("Rank " + str + ": " + entry.getValue());
        }
    }
}
```

**输出：**

```java
The ranks according to scores are :
Rank 1: Shavi
Rank 2: Ashty
Rank 3: Vaish
Rank 4: Kil
Rank 5: Manju
```

本文由Shambhavi Singh供稿。如果你喜欢GeeksforGeeks并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到contribute@geeksforgeeks.org。看到你的文章出现在GeeksforGeeks博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。