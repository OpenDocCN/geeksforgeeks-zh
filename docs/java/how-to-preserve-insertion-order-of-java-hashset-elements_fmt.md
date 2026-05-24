# 如何保持 Java HashSet 元素的插入顺序？

> 原文：`https://www.geeksforgeeks.org/how-to-preserve-insertion-order-of-java-hashset-elements/`

当元素从`HashSet`中获取时，由于散列，它们插入的顺序在检索时不会被维护。`HashSet`通过使用一种称为散列的机制来存储元素。我们可以使用`LinkedHashSet`实现给定的任务。`LinkedHashSet`类实现了一个双链表，这样它就可以遍历所有的元素。

**示例：**

```java
Input : HashSetInput = {c, a, b}
Output: HashSetPrint = {c, a, b}

Input : HashSetInput = {"first", "second"}
Output: HashSetPrint = {"first", "second"}
```

## 使用 HashSet 实现（顺序未维护）

**语法：**

```java
HashSet<String> num = new HashSet<String>();
```

**进场：**

1.  创建`HashSet`对象。
2.  在哈希集中插入多个元素。
3.  打印哈希表。（未维护订单）

下面是上述方法的实现：

```java
// Preserve insertion order of Java HashSet elements
// Order not maintained because HashSet used
import java.util.HashSet;
import java.util.Set;

public class PreserveHashSetOrderExample {

    public static void main(String[] args) {
        Set<Integer> hSetNumbers = new HashSet<Integer>();

        hSetNumbers.add(1);
        hSetNumbers.add(13);
        hSetNumbers.add(2);
        hSetNumbers.add(4);

        for (Integer number : hSetNumbers) {
            System.out.println(number);
        }
    }
}
```

**Output**

```java

```

## 使用 LinkedHashSet 实现（维持顺序）

**语法：**

```java
HashSet<String> num = new LinkedHashSet<String>();
```

**进场：**

1.  创建一个`HashSet`对象，并用`LinkedHashSet`的构造函数初始化它。
2.  在哈希集中插入多个元素。
3.  打印哈希表。（维持秩序）

下面是上述方法的实现：

```java
// Preserve insertion order of Java HashSet elements
// Using LinkedHashSet
import java.util.LinkedHashSet;
import java.util.Set;

public class PreserveHashSetOrderExample {

    public static void main(String[] args) {
        Set<Integer> setNumbers = new LinkedHashSet<Integer>();

        setNumbers.add(1);
        setNumbers.add(13);
        setNumbers.add(2);
        setNumbers.add(4);

        for (Integer number : setNumbers) {
            System.out.println(number);
        }
    }
}
```

**Output**

```java

```