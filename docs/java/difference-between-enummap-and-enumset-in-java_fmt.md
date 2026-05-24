# Java 中 EnumMap 和 EnumSet 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-enummap-and-enumset-in-java/](https://www.geeksforgeeks.org/difference-between-enummap-and-enumset-in-java/)

`EnumMap` 和 `EnumSet` 都是 Java [`集合`](https://www.geeksforgeeks.org/collections-in-java-2/)中定义的类。在本文中，我们将学习 `EnumMap` 和 `EnumSet` 之间的区别。`EnumMap` 是[`地图`](https://www.geeksforgeeks.org/map-interface-java-examples/)接口的专门实现，`EnumSet` 是 [`Set`](https://www.geeksforgeeks.org/set-in-java/) 接口的专门实现。他们之间存在一些差异。所以我们试图列出 `EnumMap` 和 `EnumSet` 之间的区别。

## 1. EnumMap

`EnumMap` 是[`映射接口`](https://www.geeksforgeeks.org/map-interface-java-examples/)对[`枚举类型`](https://www.geeksforgeeks.org/enum-in-java/)的专门实现。实现了[`映射`](https://www.geeksforgeeks.org/map-interface-java-examples/)接口，用 Java 扩展了抽象映射。

*   `EnumMap` 类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的成员。
*   `EnumMap` 是一个有序集合，其顺序根据其键的自然顺序来维护。
*   每个枚举实例的所有键必须是同一[`枚举`](https://www.geeksforgeeks.org/enum-in-java/)类型的键。
*   `EnumMap` 不允许插入空键。如果我们尝试插入空键，将抛出 `NullPointerException`。
*   `EnumMap` 在内部表示为一个数组以获得更好的性能。

下面是 `EnumMap` 的实现：

```java
// Java program to illustrate working of EnumMap

import java.util.*;

class EnumMapExample {

    public enum Fruits {
        Apple,
        Mango,
        Orange,
        Banana;
    }

    public static void main(String[] args)
    {
        // Creating an EnumMap of the Fruits enum
        EnumMap<Fruits, Integer> enumMap
            = new EnumMap<>(Fruits.class);

        // Insert using put() method
        enumMap.put(Fruits.Apple, 1);
        enumMap.put(Fruits.Mango, 2);
        enumMap.put(Fruits.Orange, 3);
        enumMap.put(Fruits.Banana, 4);

        // Printing size of EnumMap
        System.out.println("Size of EnumMap: "
                           + enumMap.size());
        // Printing the EnumMap
        for (Map.Entry m : enumMap.entrySet()) {
            System.out.println(m.getKey() + " "
                               + m.getValue());
        }
    }
}
```

输出

```java
Size of EnumMap: 4
Apple 1
Mango 2
Orange 3
Banana 4
```