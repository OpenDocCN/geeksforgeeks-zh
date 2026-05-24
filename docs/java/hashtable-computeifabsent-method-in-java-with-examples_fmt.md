# Java 中的哈希表 `computeIfAbsent()` 方法，示例

> 原文：[https://www.geeksforgeeks.org/hashtable-computeifabsent-method-in-java-with-examples/](https://www.geeksforgeeks.org/hashtable-computeifabsent-method-in-java-with-examples/)

`Hashtable` 类的 `computeIfAbsent(K key, Function remappingFunction)` 方法，如果键还没有与值相关联（或被映射为 `null`），该方法允许您计算指定键的映射值。

*   如果此方法的映射函数返回 `null`，则不记录该映射。
*   如果重映射函数抛出异常，则再次抛出该异常且不记录映射。
*   此方法不允许在计算过程中修改映射。
*   如果重映射函数在计算过程中修改了此映射，此方法将抛出 `ConcurrentModificationException`。

## 语法

```java
public V computeIfAbsent(K key,
                         Function<? super K, ? extends V> remappingFunction)
```

## 参数

此方法接受两个参数：

*   `key`：要与值关联的键。
*   `remappingFunction`：用于计算数值的函数。

## 返回值

此方法返回与指定键关联的当前（现有或计算的）值，如果映射返回 `null`，则返回 `null`。

## 异常

此方法抛出：

*   `ConcurrentModificationException`：如果检测到重映射函数修改了此映射。

以下程序说明了 `computeIfAbsent(K key, Function remappingFunction)` 方法：

## 程序 1

```java
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a table and add some values
        Map<String, Integer> table = new Hashtable<>();
        table.put("Pen", 10);
        table.put("Book", 500);
        table.put("Clothes", 400);
        table.put("Mobile", 5000);

        // print map details
        System.out.println("hashTable: "
                           + table.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        table.computeIfAbsent("newPen", k -> 600);
        table.computeIfAbsent("newBook", k -> 800);

        // print new mapping
        System.out.println("new hashTable: "
                           + table);
    }
}
```

## 输出

```java
hashTable: {Book=500, Mobile=5000, Pen=10, Clothes=400}
new hashTable: {newPen=600, Book=500, newBook=800, Mobile=5000, Pen=10, Clothes=400}
```

## 程序 2

```java
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a table and add some values
        Map<Integer, String> table = new Hashtable<>();
        table.put(1, "100RS");
        table.put(2, "500RS");
        table.put(3, "1000RS");

        // print map details
        System.out.println("hashTable: "
                           + table.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        table.computeIfAbsent(4, k -> "600RS");

        // this will not effect anything
        // because key 1 is present
        table.computeIfAbsent(1, k -> "800RS");

        // print new mapping
        System.out.println("new hashTable: "
                           + table);
    }
}
```

## 输出

```java
hashTable: {3=1000RS, 2=500RS, 1=100RS}
new hashTable: {4=600RS, 3=1000RS, 2=500RS, 1=100RS}
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/util/Hashtable.html#computeIfAbsent(K, java.util.function.Function)](https://docs.oracle.com/javase/10/docs/api/java/util/Hashtable.html#computeIfAbsent(K, java.util.function.Function))