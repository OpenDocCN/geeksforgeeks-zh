# Java BitSet 类方法示例（第 2 部分）

> 原文：[https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-2/](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-2/)

本文讨论的方法：
`BitSet` 类方法：`set()`、`xor()`、`clone()`、`clear()`、`length()`、`cardinality()`

我们强烈建议将以下第 1 组作为先决条件。
[Java 中的 BitSet 类 | 第 1 部分](https://www.geeksforgeeks.org/bitset-class-java-set-1/)

## 1. `set()`
`java.util.BitSet.set()` 方法用于将指定索引处的位设置为指定值。

**语法：**
```java
public void set(int bitpos)
public void set(int bitpos, boolean val)
```
**参数：**
- `bitpos`：位索引
- `val`：要设置的布尔值

**返回值：** 无
**抛出异常：** `IndexOutOfBoundsException` - 如果指定的索引为负数

## 2. `clone()`
`java.util.BitSet.clone()` 方法克隆一个 `BitSet`，产生一个与其相等的新 `BitSet`。该位集的克隆是另一个位集，它具有与该位集完全相同的设为真的位。

**语法：**
```java
public Object clone()
```
**返回值：** 此位集的一个克隆

## 3. `cardinality()`
`java.util.BitSet.cardinality()` 方法用于查找 `BitSet` 中设置为 `true` 的位的数量。

**语法：**
```java
public int cardinality()
```
**返回值：** 此 `BitSet` 中设置为 `true` 的位的数量

### 示例代码
```java
// Java program explaining BitSet class methods
// set(), clone(), cardinality()
import java.util.*;
public class NewClasss
{
    public static void main(String[] args)
    {
        BitSet bs1 = new BitSet();
        BitSet bs2 = new BitSet(8);
        BitSet bs3 = new BitSet();

        // assign values to bs1 using set()
        bs1.set(0);
        bs1.set(1);
        bs1.set(2);
        bs1.set(4);

        // assign values to bs2
        bs2.set(4);
        bs2.set(6);
        bs2.set(5);

        // Here we are using .clone() method to make
        // bs3 as bs1
        bs3 = (BitSet) bs1.clone();

        // Printing the 3 Bitsets
        System.out.println("bs1 : " + bs1);
        System.out.println("bs2 : " + bs2);
        System.out.println("bs3 cloned from bs1 : " + bs3);

        // Using .cardinality() method to print the no. of
        // elements of Bitset
        System.out.println("Cardinality of bs1 : " +
                           bs1.cardinality());
        System.out.println("Cardinality of bs2 : " +
                           bs2.cardinality());
    }
}
```
**输出：**
```
bs1 : {0, 1, 2, 4}
bs2 : {4, 5, 6}
bs3 cloned from bs1 : {0, 1, 2, 4}
Cardinality of bs1 : 4
Cardinality of bs2 : 3
```

## 4. `clear()`
`java.util.BitSet.clear()` 方法用于清除元素，即将所有 `BitSet` 元素设置为 `false`。

**语法：**
```java
public void clear(int frompos, int topos)
public void clear(int bitIndex)
public void clear()
```
**参数：**
- `frompos`：要清除的第一个位的索引
- `topos`：要清除的最后一个位之后的索引
- `bitIndex`：要清除的位的索引

**抛出异常：**
- `IndexOutOfBoundsException` - 如果 `pos` 值为负数，或者 `frompos` 大于 `topos`

## 5. `xor()`
`java.util.BitSet.xor()` 方法对位集执行逻辑异或（Xor）操作。
此位集被修改，使得其中的位在以下情况下值为 `true`：
- 该位最初的值为 `true`，参数中对应的位的值为 `false`。
- 该位最初的值为 `false`，参数中对应的位的值为 `true`。

**语法：**
```java
public void xor(BitSet set)
```
**参数：**
- `set`：需要与之执行操作的 `BitSet`

## 6. `length()`
`java.util.BitSet.length()` 方法返回位集的逻辑大小。
即位集中最高设置位的索引加一。如果位集不包含任何设置位，则返回零。

**语法：**
```java
public int length()
```
**返回值：** 此 `BitSet` 的逻辑大小

### 示例代码
```java
// Java program explaining BitSet class methods
// xor(), length(), clear() methods
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
        System.out.println("bs1 : " + bs1);
        System.out.println("bs2 : " + bs2);

        // use of length() method
        System.out.println("use of length() : " + bs1.length());

        // use of xor() to perform logical Xor operation
        bs1.xor(bs2);
        System.out.println("Use of xor() : " + bs1);
        bs2.xor(bs1);
        System.out.println("Use of xor() : " + bs2);

        // clear from index 2 to index 4 in bs1
        bs2.clear(1, 2);
        System.out.println("bs2 after clear method : " + bs2);

        // clear complete Bitset
        bs1.clear();
        System.out.println("bs1 after clear method : " + bs1);
    }
}
```
**输出：**
```
bs1 : {1, 2, 3, 4, 6, 7}
bs2 : {2, 3, 4, 6, 9}
use of length() : 8
Use of xor() : {1, 7, 9}
Use of xor() : {1, 2, 3, 4, 6, 7}
bs2 after clear method : {2, 3, 4, 6, 7}
bs1 after clear method : {}
```

**相关文章：**
[Java 中的 BitSet 类方法示例 | 第 3 部分](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-3/)

**参考文献：**
[https://docs.oracle.com/javase/7/docs/api/java/util/BitSet.html](https://docs.oracle.com/javase/7/docs/api/java/util/BitSet.html)

本文由 **莫希特·古普塔** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。