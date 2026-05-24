# 通过使用 Java 中 TreeSet 上的排序逻辑从集合中获取最高和最低值元素

> 原文：[https://www.geeksforgeeks.org/getting-highest-and-lowest-value-element-from-a-set-by-using-sorting-logic-on-treeset-in-java/](https://www.geeksforgeeks.org/getting-highest-and-lowest-value-element-from-a-set-by-using-sorting-logic-on-treeset-in-java/)

[`TreeSet`](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 在 Java 中实现了 `Set` 接口，使用红黑树存储值。我们使用 `TreeSet` 进行排序，因为默认情况下 `TreeSet` 中的元素以升序存储。一旦创建了 `TreeSet`，我们就可以从 `TreeSet` 的最后一个元素获得最高元素值，从第一个元素获得最低元素值。我们必须首先传递 [`Comparator`](https://www.geeksforgeeks.org/comparator-interface-java/) 对象和 `TreeSet` 声明。现在，我们可以简单地通过创建一个 `TreeSet` 并添加元素，然后根据某个属性对元素进行排序，最后通过 `TreeSet` 上的 [`last()`](https://www.geeksforgeeks.org/treeset-last-method-in-java/) 和 [`first()`](https://www.geeksforgeeks.org/sortedset-first-method-in-java/) 方法获得最高和最低的元素。为了实现排序，我们必须覆盖 [`compare()`](https://www.geeksforgeeks.org/how-compare-method-works-in-java/) 方法。`TreeSet` 声明将遵循下面给出的语法：

## 语法

```java
TreeSet<Comparator> name = new TreeSet<Comparator>(new ComparatorClass());
```

## 参数

*   `name`：创建的 `TreeSet` 的名称。
*   `Comparator`：`Comparator` 对象。
*   `ComparatorClass()`：用于实现排序函数（`compare()` 方法）的类。

## 返回

可以添加值的 `TreeSet`。

例如，我们想要创建一个包含某个组的名称和年龄的 `TreeSet`，我们想要找到年龄最高和最低的人。

## 例 1

```java
Input :
Name - "Ramesh" Age - 20
Name - "Suresh" Age - 48
Name - "Ankit" Age - 14
Name - "Madhav" Age - 78

Output :
Highest Age Person: Name : Madhav-- Age : 78
Lowest Age Person: Name : Ankit-- Age : 14
```

## 例 2

```java
Input :
Name - "Ramesh" Age - 20
Name - "Suresh" Age - 20
Name - "Ankit" Age - 78
Name - "Madhav" Age - 78

Output :
Highest Age Person: Name : Ankit-- Age : 78
Lowest Age Person: Name : Suresh-- Age : 20
```

## 解释

在例 1 中，所有的年龄都是不同的，所以最高和最低是根据年龄值来确定的。

在例 2 中，两个最高年龄值相同，因此 `TreeSet` 中 `last()` 的人名被赋予最高值，即 “A” < ‘M’，所以 `Ankit` 具有最高年龄。而如果最低年龄值相同，则 `TreeSet` 中 `first()` 的人名被赋予最低值，即 ‘S’ > ‘R’，因此 `Suresh` 的年龄最低。

## 示例

```java
// Getting Highest and Lowest Value
// Element From a Set by Using Sorting
// Logic on TreeSet in Java

import java.util.*;
import java.io.*;
import java.util.Comparator;
import java.util.TreeSet;

// Implement sorting class using comparator to sort
class sorting implements Comparator<ages> {

    // Override the Compare Method
    @Override
    public int compare(ages age1, ages age2) {
        if (age1.value() > age2.value()) {
            return 1;
        } else {
            return -1;
        }
    }
}

// Implement ages for getting name and age
class ages {
    private String name;
    private int age;

    public ages(String name, int a) {
        this.name = name;
        this.age = a;
    }

    public String Name() {
        return name;
    }

    public void NewName(String name) {
        this.name = name;
    }

    public int value() {
        return age;
    }

    public void NewAge(int age) {
        this.age = age;
    }

    // Convert to string output
    public String toString() {
        return "Name: " + this.name + "-- age: " + this.age;
    }
}

public class GFG {
    public static void main(String[] args) {
        // Create a TreeSet with Comporator Object
        TreeSet<ages> agetree = new TreeSet<ages>(new sorting());

        // Add elements in TreeSet
        agetree.add(new ages("Ramesh", 20));
        agetree.add(new ages("Suresh", 20));
        agetree.add(new ages("Ankit", 78));
        agetree.add(new ages("Madhav", 78));

        // Output Highest Value Element
        System.out.println("Highest Age Person: " + agetree.last());

        // Output Lowest Value Element
        System.out.println("Lowest Age Person: " + agetree.first());
    }
}
```

## Output

```java
Highest Age Person: Name: Ankit-- age: 78
Lowest Age Person: Name: Suresh-- age: 20
```