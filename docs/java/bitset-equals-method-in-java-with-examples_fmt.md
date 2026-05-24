# Java 中的 BitSet equals() 方法示例

> 原文：[https://www.geeksforgeeks.org/bitset-equals-method-in-java-with-examples/](https://www.geeksforgeeks.org/bitset-equals-method-in-java-with-examples/)

Java `BitSet` 类的 `equals()` 方法用于检查两个 `BitSet` 之间的相等性。它验证作为参数传递的一个集合的元素是否等于这个集合的元素。如果位集匹配则方法返回 `true`，否则返回 `false`。

## 语法

```java
Bit_Set1.equals(Bit_Set2)
```

## 参数

该方法接受一个 `BitSet` 类型的参数 `BitSet2`，并引用要用该位集检查其相等性的位集。

## 返回值

如果两个对象集相等，则方法返回 `true`，否则返回 `false`。

下面的程序说明了 `BitSet` `equals()` 方法在 Java 中的工作原理。

### 程序 1

```java
// Java code to illustrate equals()
import java.util.*;

public class BitSet_Demo {
    public static void main(String args[])
    {
        // Creating an empty BitSet
        BitSet bit_set1 = new BitSet();
        BitSet bit_set2 = new BitSet();

        // Use set() method to add elements into the Set
        bit_set1.set(40);
        bit_set1.set(25);
        bit_set1.set(80);
        bit_set1.set(95);
        bit_set1.set(5);

        // Use set() method to add elements into the Set
        bit_set2.set(25);
        bit_set2.set(40);
        bit_set2.set(5);
        bit_set2.set(95);
        bit_set2.set(80);

        // Displaying the BitSets
        System.out.println("First BitSet: " + bit_set1);
        System.out.println("Second BitSet: " + bit_set2);

        // Checking for equality
        System.out.println("Are the sets equal? "
                           + bit_set1.equals(bit_set2));
    }
}
```

**输出：**

```java
First BitSet: {5, 25, 40, 80, 95}
Second BitSet: {5, 25, 40, 80, 95}
Are the sets equal? true
```

### 程序 2

```java
// Java code to illustrate equals()
import java.util.*;

public class BitSet_Demo {
    public static void main(String args[])
    {
        // Creating an empty BitSet
        BitSet bit_set1 = new BitSet();
        BitSet bit_set2 = new BitSet();

        // Use set() method to add elements into the Set
        bit_set1.set(40);
        bit_set1.set(25);
        bit_set1.set(80);
        bit_set1.set(95);
        bit_set1.set(5);

        // Use set() method to add elements into the Set
        bit_set2.set(10);
        bit_set2.set(20);
        bit_set2.set(30);
        bit_set2.set(40);
        bit_set2.set(50);

        // Displaying the BitSets
        System.out.println("First BitSet: " + bit_set1);
        System.out.println("Second BitSet: " + bit_set2);

        // Checking for equality
        System.out.println("Are the sets equal? "
                           + bit_set1.equals(bit_set2));
    }
}
```

**输出：**

```java
First BitSet: {5, 25, 40, 80, 95}
Second BitSet: {10, 20, 30, 40, 50}
Are the sets equal? false
```