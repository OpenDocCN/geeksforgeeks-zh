# Java 中枚举集和树集的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-enumset-and-treeset-in-java/](https://www.geeksforgeeks.org/difference-between-enumset-and-treeset-in-java/)

枚举集和树集都是在[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)中定义的类。但是他们之间几乎没有什么区别。在本文中，我们试图涵盖它们之间的所有这些差异。

**1. `EnumSet`：** `EnumSet` 是为[枚举类型](https://www.geeksforgeeks.org/enum-in-java/)设置[接口的专门实现。它扩展了抽象集，并在 Java 中实现了集合接口。`EnumSet` 的几个要点如下：](https://www.geeksforgeeks.org/set-in-java/)

*   `EnumSet` 类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的成员，不同步。
*   枚举集中的所有元素必须来自单个[枚举类型](https://www.geeksforgeeks.org/enum-in-java/)，该类型在创建集合时显式或隐式指定。
*   `EnumSet` 不允许插入空对象。如果我们尝试插入空对象，它将抛出 `NullPointerException`。
*   它使用**失败安全**迭代器，因此如果在迭代过程中修改了集合，它不会抛出 `ConcurrentModificationException`。

## 示例

```java
// Java program to demonstrate
// the EnumSet

import java.util.*;
class enumSetExample {
    enum Colors {
        Red,
        Pink,
        Grey,
        Yellow,
        Green
    }
    public static void main(String args[])
    {

        // Creating an EnumSet
        EnumSet<Colors> colors
            = EnumSet.of(Colors.Pink, Colors.Green);

        Iterator<Colors> itr = colors.iterator();

        // Iterate and print elements to
        // the console
        System.out.println("EnumSet : ");
        while (itr.hasNext()) {
            System.out.println(itr.next());
        }
    }
}
```

## 输出

```java
EnumSet : 
Pink
Green
```