# Java中的`java.util.BitSet.clear()`

> 原文：[https://www.geeksforgeeks.org/java-util-bitset-clear-java/](https://www.geeksforgeeks.org/java-util-bitset-clear-java/)

`clear()`方法有三个变型：

## `clear()`

`clear()`方法将此`BitSet`中的所有位设置为`false`。

```java
public void clear()
```

**返回值**
此方法不返回任何值。

```java
// Java code to demonstrate the working
// of clear() in BitSet
import java.util.*;
public class BitClr1 {
    public static void main(String[] args)
    {
        // Declaring Bitset
        BitSet bset = new BitSet(8);

        // assigning values to bitset
        for (int i = 0; i < 5; i++)
            bset.set(i);

        // printing original bitset
        System.out.println
        ("The bitset before clear() operation is : " + bset);

        // using clear() to clear contents of bitset
        bset.clear();

        // printing bitset after clear() operation
        // empty bitset
        System.out.println
        ("The bitset after clear() operation is : " + bset);
    }
}
```

输出：

```java
The bitset before clear() operation is : {0, 1, 2, 3, 4}
The bitset after clear() operation is : {}
```

## `clear(int pos)`

`clear(int pos)`方法将指定索引处的位设置为`false`，即**从位集中移除**。

```java
public void clear(int pos)
```

**参数**
`pos`：要清除的位的索引。

**返回值**
此方法不返回任何值。

**异常**
`IndexOutOfBoundsException`：如果指定的索引为负数。

```java
// Java code to demonstrate the working
// of clear(int pos) in BitSet
import java.util.*;
public class BitClr2 {
    public static void main(String[] args)
    {
        // Declaring Bitset
        BitSet bset = new BitSet(8);

        // assigning values to bitset
        for (int i = 0; i < 5; i++)
            bset.set(i);

        // printing original bitset
        System.out.println
        ("The bitset before clear(pos) operation is : " + bset);

        // using clear(pos) to clear element at specified position
        bset.clear(3);

        // printing bitset after clear(pos) operation
        // removes 3
        System.out.println
        ("The bitset after clear(pos) operation is : " + bset);
    }
}
```

输出：

```java
The bitset before clear(pos) operation is : {0, 1, 2, 3, 4}
The bitset after clear(pos) operation is : {0, 1, 2, 4}
```

## `clear(int frompos, int topos)`

`clear(int frompos, int topos)`方法将从指定的`frompos`（包含）到指定的`topos`（不包含）的位设置为`false`，即**在范围内执行移除操作**。

```java
public void clear(int frompos, int topos)
```

**参数**
`frompos`：要清除的第一个位的索引。
`topos`：要清除的最后一个位的索引。

**返回值**
此方法不返回任何值。

**异常**
`IndexOutOfBoundsException`：如果`frompos`为负数，或`topos`为负数，或`frompos`大于`topos`。

```java
// Java code to demonstrate the working
// of clear(int frompos, int topos) in BitSet
import java.util.*;
public class BitClr3 {
    public static void main(String[] args)
    {
        // Declaring Bitset
        BitSet bset = new BitSet(8);

        // assigning values to bitset
        for (int i = 0; i < 5; i++)
            bset.set(i);

        // printing original bitset
        System.out.println
        ("The bitset before clear(frompos, topos) operation is : " + bset);

        // using clear(frompos, topos) to clear elements in range
        bset.clear(2, 4);

        // printing bitset after clear(frompos, topos) operation
        // removes 2, 3
        System.out.println
        ("The bitset after clear(frompos, topos) operation is : " + bset);
    }
}
```

输出：

```java
The bitset before clear(frompos, topos) operation is : {0, 1, 2, 3, 4}
The bitset after clear(frompos, topos) operation is : {0, 1, 4}
```

本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。