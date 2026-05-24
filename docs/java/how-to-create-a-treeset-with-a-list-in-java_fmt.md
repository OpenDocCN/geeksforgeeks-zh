# 如何用 Java 创建带列表的树集？

> 原文: [https://www.geeksforgeeks.org/how-to-create-a-treeset-with-a-list-in-java/](https://www.geeksforgeeks.org/how-to-create-a-treeset-with-a-list-in-java/)

[`TreeSet`](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 是 Java 中 [`SortedSet` 接口](https://www.geeksforgeeks.org/sortedset-java-examples/)的一个实现，使用[树](https://www.geeksforgeeks.org/binary-tree-data-structure/)进行存储。通过将列表传递给 Java 中的 `TreeSet` 构造函数，可以从[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)创建 `TreeSet`，或者我们可以遍历完整的列表，并将列表的每个元素添加到 `TreeSet` 中。

**例:**

```java
Input : List = [a, b, c]
Output: TreeSet = [a, b, c]

Input : List = [1, 2, 3]
Output: TreeSet = [1, 2, 3]
```

## 方法 1

1.  创建一个列表对象。
2.  在列表中输入多个元素。
3.  创建一个 `TreeSet` 对象。
4.  使用构造函数初始化对象，并在其中传递一个 `List` 对象。
5.  打印 `TreeSet`。

下面是上述方法的实现：

```java
// Java Program to Create a TreeSet with a List
import java.util.ArrayList;
import java.util.List;
import java.util.TreeSet;

public class ExampleTreeSet {
    public static void main(String a[])
    {
        // Create new List
        List<String> fruitlist = new ArrayList<String>();
        fruitlist.add("Mango");
        fruitlist.add("Apple");
        fruitlist.add("Grape");
        fruitlist.add("Papaya");

        // Printing ArrayList
        System.out.println("Fruit List : " + fruitlist);

        // Create a TreeSet with the list
        TreeSet<String> tree_set
            = new TreeSet<String>(fruitlist);

        // Print TreeSet
        System.out.println("TreeSet from List : "
                           + tree_set);
    }
}
```

**输出**

```java
Fruit List : [Mango, Apple, Grape, Papaya]
TreeSet from List : [Apple, Grape, Mango, Papaya]
```

**时间复杂度:** `O(N)`

## 方法 2

1.  创建一个列表对象。
2.  在列表中输入多个元素。
3.  创建一个 `TreeSet` 对象。
4.  开始遍历列表并将元素添加到 `TreeSet` 中。
5.  遍历完成后，打印 `TreeSet`。

下面是上述方法的实现：

```java
// Java Program to Create a TreeSet with a List
import java.util.ArrayList;
import java.util.List;
import java.util.TreeSet;

public class ExampleTreeSet {
    public static void main(String a[])
    {
        // Create new List
        List<String> fruitlist = new ArrayList<String>();
        fruitlist.add("Mango");
        fruitlist.add("Apple");
        fruitlist.add("Grape");
        fruitlist.add("Papaya");

        // Printing ArrayList
        System.out.println("Fruit List : " + fruitlist);

        // Create a TreeSet
        TreeSet<String> tree_set = new TreeSet<String>();

        // Add each element in the TreeSet
        for (String i : fruitlist)
            tree_set.add(i);

        // Print TreeSet
        System.out.println("TreeSet from List : "
                           + tree_set);
    }
}
```

**输出**

**时间复杂度:** `O(N)`