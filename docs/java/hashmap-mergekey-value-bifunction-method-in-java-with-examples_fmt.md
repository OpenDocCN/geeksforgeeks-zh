# Java 中的 HashMap `merge(K key, V value, BiFunction remappingFunction)` 方法示例

> 原文：[https://www.geeksforgeeks.org/hashmap-merge-key-value-bifunction-method-in-java-with-examples/](https://www.geeksforgeeks.org/hashmap-merge-key-value-bifunction-method-in-java-with-examples/)

[`HashMap`](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 类的 `merge(K key, V value, BiFunction remappingFunction)` 方法用于使用给定的映射函数组合一个键的多个映射值。Bucket 实际上是数组的索引，这个数组在 `HashMap` 实现中叫做 `table`。因此，`table[0]` 称为 bucket0，`table[1]` 称为 bucket1，依此类推。

*   如果键不存在或与 `null` 关联，则只需将该键及其对应的值作为新条目输出到 `HashMap` 中。
*   然而，如果该键已经保存了一些值，重映射函数将根据给定的键匹配旧值和新值。
*   合并。如果键为空，它将始终映射到 bucket 0，因为空键的哈希值为 0，且没有为空键计算哈希。

## 语法

```java
public V merge(K key, V value,
    BiFunction remappingFunction)
```

## 参数

这个方法接受三个参数：

*   `key`：是我们要操作的键。如果两个键相同，它们的值将被合并。
*   `value`：是与特定键关联的值，存储在 bucket 中。
*   `BiFunction`：是一个具有两个参数的函数，用于根据旧值和给定值计算新的映射。

## 返回值

如果键不存在或与 `null` 相关联，则该方法返回该键及其值。否则，如果键已经保存了任何值，它会使用映射技术将旧值与新值合并。

以下程序说明了 `merge(K key, V value, BiFunction remappingFunction)` 方法：

### 程序 1

```java
// Java program to demonstrate
// merge(K key, V value, BiFunction remappingFunction) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a HashMap and add some values
        HashMap<Integer, String>
            map1 = new HashMap<>();
        map1.put(1, "L");
        map1.put(2, "M");
        map1.put(3, "N");

        HashMap<Integer, String>
            map2 = new HashMap<>();
        map2.put(1, "B");
        map2.put(2, "G");
        map2.put(3, "R");

        // print map details
        System.out.println("HashMap1: "
                           + map1.toString());

        System.out.println("HashMap2: "
                           + map2.toString());

        // provide value for new key which is absent
        // using merge method
        map2.forEach(
            (key, value)
                -> map1.merge(
                    key,
                    value,
                    (v1, v2)
                        -> v1.equalsIgnoreCase(v2)
                               ? v1
                               : v1 + ", " + v2));

        // print new mapping
        System.out.println("New HashMap: " + map1);
    }
}
```

### 输出

```java
HashMap1: {1=L, 2=M, 3=N}
HashMap2: {1=B, 2=G, 3=R}
New HashMap: {1=L, B, 2=M, G, 3=N, R}
```

### 程序 2

```java
// Java program to demonstrate
// merge(K key, V value, BiFunction remappingFunction) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a HashMap and add some values
        HashMap<Integer, String>
            map1 = new HashMap<>();
        map1.put(1, "Ram");
        map1.put(2, "Rohan");
        map1.put(3, "Shivam");

        HashMap<Integer, String>
            map2 = new HashMap<>();
        map2.put(1, "Tushar");
        map2.put(10, "Satya");
        map2.put(12, "Sundar");

        // print map details
        System.out.println("HashMap1: "
                           + map1.toString());

        System.out.println("HashMap2: "
                           + map2.toString());

        // provide value for new key which is absent
        // using merge method
        map2.forEach(
            (key, value)
                -> map1.merge(
                    key,
                    value,
                    (v1, v2)
                        -> v1.equalsIgnoreCase(v2)
                               ? v1
                               : v1 + ", " + v2));

        // print new mapping
        System.out.println("New HashMap: " + map1);
    }
}
```

### 输出

```java
HashMap1: {1=Ram, 2=Rohan, 3=Shivam}
HashMap2: {1=Tushar, 10=Satya, 12=Sundar}
New HashMap: {1=Ram, Tushar, 2=Rohan, 3=Shivam, 10=Satya, 12=Sundar}
```

## 参考文献

[https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#merge-K-V-java.util.function.BiFunction-](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#merge-K-V-java.util.function.BiFunction-)