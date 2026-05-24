# 枚举映射和哈希映射的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-enummap-and-hashmap/](https://www.geeksforgeeks.org/difference-between-enummap-and-hashmap/)

`EnumMap` 和 `HashMap` 都是实现 `Map` 接口的类。但是它们之间存在一些差异。所以我们试图列出 `EnumMap` 和 `HashMap` 之间的区别。

**1. `EnumMap`：** `EnumMap` 是为 `enum` 类型专门实现的 `Map` 接口。它扩展了 `AbstractMap`，在 Java 中实现了 `Map` 接口。`EnumMap` 的几个要点如下：

*   `EnumMap` 类是 `Java Collections Framework` 的成员，不同步。
*   `EnumMap` 是一个有序集合，其顺序根据其键的自然顺序（键的自然顺序指的是枚举类型内部声明枚举常量的顺序）来维护。
*   它不允许插入空键。
*   每个 `EnumMap` 实例的所有键必须是同一枚举类型的键。
*   `EnumMap` 不允许插入空键。如果我们尝试插入空键，它将抛出 `NullPointerException`。
*   `EnumMap` 在内部表示为一个数组，因此性能更好。

## EnumMap 演示

```java
// Java program to illustrate working
// of EnumMap

import java.util.*;

class EnumMapExample {

    public enum Days {
        Sunday,
        Monday,
        Tuesday,
        Wendensday;
    }

    public static void main(String[] args) {
        // Creating an EnumMap of the Days enum
        EnumMap<Days, Integer> enumMap = new EnumMap<>(Days.class);

        // Insert using put() method
        enumMap.put(Days.Sunday, 1);
        enumMap.put(Days.Monday, 2);
        enumMap.put(Days.Tuesday, 3);
        enumMap.put(Days.Wendensday, 4);

        // Printing size of EnumMap
        System.out.println("Size of EnumMap: " + enumMap.size());
        // Printing the EnumMap
        for (Map.Entry m : enumMap.entrySet()) {
            System.out.println(m.getKey() + " " + m.getValue());
        }
    }
}
```

## 输出

```java
Size of EnumMap: 4
Sunday 1
Monday 2
Tuesday 3
Wendensday 4
```