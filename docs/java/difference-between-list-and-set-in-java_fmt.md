# Java 中列表和集合的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-list-and-set-in-java/](https://www.geeksforgeeks.org/difference-between-list-and-set-in-java/)

[`List`](https://www.geeksforgeeks.org/list-interface-java-examples/) 接口允许存储有序集合。它是 [`Collection`](https://www.geeksforgeeks.org/collections-in-java-2/) 的子接口。它是对象的有序集合，其中允许存储重复的值。`List` 保留插入顺序，它允许位置访问和元素插入。

**声明:**

```java
public abstract interface List extends Collection
```

[`java.util`](https://www.geeksforgeeks.org/java-util-package-java/) 包中的 [`Set`](https://www.geeksforgeeks.org/set-in-java/) 接口并扩展 [`Collection`](https://www.geeksforgeeks.org/collections-in-java-2/) 接口是一个无序的对象集合，其中不能存储重复的值。这是一个实现数学集合的接口。此接口包含从 `Collection` 接口继承的方法，并添加了一个限制插入重复元素的功能。

**声明:** `Set` 接口声明为:

```java
public interface Set extends Collection
```

**示例:**

```java
Input :  Add Elements = [1, 2, 3, 1]
Output:  Set = [1, 2, 3]
     List = [1, 2, 3, 1]

Input :  Add Elements = [a, b, d, b]
Output:  Set = [a, b, d]
     List = [a, b, d, b]
```

下面是集合和列表的图示:

## Java 代码示例

```java
// Implementation of List and Set in Java
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // List declaration
        List<Integer> l = new ArrayList<>();
        l.add(5);
        l.add(6);
        l.add(3);
        l.add(5);
        l.add(4);

        // Set declaration
        Set<Integer> s = new HashSet<>();
        s.add(5);
        s.add(6);
        s.add(3);
        s.add(5);
        s.add(4);

        // printing list
        System.out.println("List = " + l);
        // printing Set
        System.out.println("Set = " + s);
    }
}
```

**输出**

```java
List = [5, 6, 3, 5, 4]
Set = [3, 4, 5, 6]
```

### 列表和集合的区别

| 目录 | 一组 |
| --- | --- |
| 1. 列表是有序的序列。 | 1. 集合是一个无序的序列。 |
| 2. 列表允许重复元素 | 2. 集合不允许重复元素。 |
| 3. 可以通过位置访问元素。 | 3. 不允许对元素进行位置访问。 |
| 4. 可以存储多个空元素。 | 4. `Null` 元素只能存储一次。 |
| 5. 列表实现有 `ArrayList`、`LinkedList`、`Vector`、`Stack`。 | 5. 集合实现有 `HashSet`、`LinkedHashSet`。 |