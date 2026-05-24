# Java 中的 BitSet 类方法，带示例 | Set 3

> 原文：[https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-3/](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-3/)

```java
                       BitSet class methods in Set 3.
               /      /      |       |     |       \      \
            and  notand    flip  isEmpty  equal   get   intersect
```

[Java 中的 BitSet 类方法，带示例 | Set 2](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-2/)

## BitSet 类方法解释如下：

### 1. and/notand
`java.util.BitSet.and()` 和 `java.util.BitSet.andNot()` 方法是 `java.util.BitSet` 类方法。
- `and()` 方法执行位集（目标）的逻辑与运算，位集作为参数传递。当且仅当两个被操作的位都为真时，这将返回一个位（置位）。
- `notand()` 方法 – 使用此方法清除所有设置了相应位的位。

```java
    Syntax:
    public void and(BitSet bitset)
               or
    public void andNot(BitSet bitset)
    Parameters:
    bitset - set to perform the operation
```

### 2. equals
`java.util.BitSet.equals()` 方法在比较两个 `BitSet` 时发挥作用。它是通过比较一个对象和其他对象来实现的。

```java
    Syntax:
    public boolean equals(Object o)
    Parameters: 
    o - the object to compare with
    Overrides: equals in class Object
    Return: if objects are same then true; otherwise false
```

### 3. get()
`java.util.BitSet.get()` 方法创建一个新的 `BitSet`，其元素来自给定的 `BitSet` 中从 `fromIndex`（包含）到 `toIndex`（不包含）位置。

```java
    Syntax:
    public BitSet get(int fromIndex, int toIndex)
    Parameters:
    fromIndex - index of the first bit of given BitSet to include
    toIndex - index after the last bit of the BitSet to include
    Throws:
    IndexOutOfBoundsException - if fromIndex is negative, or toIndex is negative,
                                or fromIndex is larger than toIndex
```

**解释 `and()`，`andNot()`，`equals()`，`get()` 方法使用的 Java 代码。**

```java
    // Java program explaining BitSet class methods
    // and(), andNot(), equals(), get()
    import java.util.*;
    public class GFG
    {
        public static void main(String[] args)
        {
            BitSet bs1 = new BitSet();
            BitSet bs2 = new BitSet();

            // assign values to bs1 using set()
            bs1.set(7);
            bs1.set(1);
            bs1.set(2);
            bs1.set(4);
            bs1.set(3);
            bs1.set(6);

            // assign values to bs2
            bs2.set(4);
            bs2.set(6);
            bs2.set(3);
            bs2.set(9);
            bs2.set(2);

            // Printing the Bitsets
            System.out.println("bs1         : " + bs1);
            System.out.println("bs2         : " + bs2);

            // use of get() to get index 3 to 6 of bs1
            System.out.println("\nUse of get() on bs1 : "
                                     + bs1.get(1,4));

            // use of get() to get index 1 to 4 of bs2
            System.out.println("Use of get() on bs2 : "
                                    + bs2.get(1,4));

            // perform not operation in b/w the sets
            bs1.andNot(bs2);
            System.out.println("\nNot b/w bs1 and bs2 : " + bs1);

            // perform and operation between two bitsets
            bs1.and(bs2);
            System.out.println("And b/w bs1 and bs2 : "  + bs1);

            // equals() method to compare the bs1 and bs2
            if (bs1.equals(bs2))
                System.out.println("\nUsing equals method : Equal");
            else
                System.out.println("\nUsing equals method : Not Equal");
        }
    }
```

输出：

```java
    bs1         : {1, 2, 3, 4, 6, 7}
    bs2         : {2, 3, 4, 6, 9}

    Use of get() on bs1 : {0, 1, 2}
    Use of get() on bs2 : {1, 2}

    Not b/w bs1 and bs2 : {1, 7}
    And b/w bs1 and bs2 : {}

    Using equals method : Not Equal
```

### 4. flip()
`java.util.BitSet.flip(fromIndex, toIndex)` 方法将从给定的 `fromIndex`（包含）到指定的 `toIndex`（不包含）的每个位设置为当前值的补码。

```java
    Syntax:
    public void flip(int fromIndex, int toIndex)
    Parameters:
    fromIndex - index of the first bit of the given BitSet to flip
    toIndex - index after the last bit of the given BitSet to flip
    Throws:
    IndexOutOfBoundsException - if fromIndex is negative, or toIndex is negative, 
                                or fromIndex is larger than toIndex
```

### 5. intersects()
`java.util.BitSet.intersects()` 方法如果目标 `BitSet` 和给定 `BitSet` 中的位都被设置，则返回 `true`。

```java
    Syntax:
    public boolean intersects(BitSet set)
    Parameters:
    set - BitSet to intersect with
    Returns: true if the given BitSet intersects the target BitSet
```

### 6. isEmpty()
`java.util.BitSet.isEmpty()` 方法检查给定的 `BitSet` 中是否有任何位被设置为 `true`。

```java
    Syntax:
    public boolean isEmpty()
    Return: boolean indicating whether the given BitSet is empty
```

**解释 `intersects()`，`isEmpty()`，`flip()` 方法使用的 Java 代码。**

```java
    // Java program explaining BitSet class methods
    // intersects(), isEmpty(), flip() methods
    import java.util.*;
    public class NewClass
    {
        public static void main(String[] args)
        {
            BitSet bs1 = new BitSet();
            BitSet bs2 = new BitSet();

            // assign values to bs1 using set()
            bs1.set(7);
            bs1.set(1);
            bs1.set(2);
            bs1.set(4);
            bs1.set(3);
            bs1.set(6);

            // assign values to bs2
            bs2.set(4);
            bs2.set(6);
            bs2.set(3);
            bs2.set(9);
            bs2.set(2);

            // Printing the Bitsets
            System.out.println("bs1      : " + bs1);
            System.out.println("bs2      : " + bs2);
            System.out.println("");

            // use of intersects() to check if the bitsets
            // intersects
            System.out.println("Using intersects() : "
                         + bs2.intersects(bs1));

            // use of flip() from_index - 1 to_index - 5
            bs1.flip(1,5);
            System.out.println("\nbs1 using flip : " + bs1);

            // use of flip() from_index - 2 to_index - 4
            bs2.flip(2,4);
            System.out.println("bs2 using flip : " + bs2);
            System.out.println("");

            // use of isEmpty() to check if bitsets are empty
            System.out.println("Use of isEmpty() : "
                                + bs1.isEmpty());
            System.out.println("Use of isEmpty() : "
                                 + bs2.isEmpty());
        }
    }
```

输出：

```java
    bs1      : {1, 2, 3, 4, 6, 7}
    bs2      : {2, 3, 4, 6, 9}

    Using intersects() : true

    bs1 using flip : {6, 7}
    bs2 using flip : {4, 6, 9}

    Use of isEmpty() : false
    Use of isEmpty() : false
```

**参考文献：**
[https://docs.oracle.com/javase/7/docs/api/java/util/BitSet.html](https://docs.oracle.com/javase/7/docs/api/java/util/BitSet.html)

本文由 **莫希特·古普塔** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。