# Java中的ConcurrentHashMap compute()方法示例

> 原文：[https://www.geeksforgeeks.org/concurrenthashmap-compute-method-in-java-with-examples/](https://www.geeksforgeeks.org/concurrenthashmap-compute-method-in-java-with-examples/)

`ConcurrentHashMap`类的`compute(key, BiFunction)`方法用于计算指定键及其当前映射值的映射（如果没有找到当前映射，则为空）。

*   此方法用于自动更新`ConcurrentHashMap`中给定键的值。
*   如果重映射函数抛出异常，则再次抛出异常，且当前映射保持不变。
*   在计算期间，此映射被其他线程更新的过程已被阻塞，因此计算不得尝试更新此映射的任何其他映射。
*   例如，此映射追加映射的字符串值：

```java
ConcurrentHashMap.compute(key, 
    (key, value) -> (value == null) ? msg : value.concat(msg))
```

## 语法

```java
public V compute(K key,
                 BiFunction<? super K, ? super V, ? extends V> remappingFunction)
```

## 参数

该方法接受两个参数：

*   `key`：与数值相关联的键。
*   `remappingFunction`：对数值进行运算的功能。

## 返回值

该方法返回与指定键关联的**新值，如果没有则返回空值**。

## 异常

如果指定的键或`remappingFunction`为空，此方法将引发以下异常：

*   `NullPointerException`：如果键或`remappingFunction`为空。
*   `IllegalStateException`：如果计算尝试递归更新映射，否则更新将永远不会完成。
*   `RuntimeException`：如果`remappingFunction`执行此操作，则映射在此情况下不会更改。

以下程序说明了`compute(key, BiFunction)`方法：

### 示例程序1

```java
// Java program to demonstrate
// compute(Key, BiFunction) method.

import java.util.concurrent.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // create a ConcurrentHashMap and add some values
        ConcurrentHashMap<String, Integer>
            map = new ConcurrentHashMap<>();
        map.put("Book1", 10);
        map.put("Book2", 500);
        map.put("Book3", 400);

        // print map details
        System.out.println("ConcurrentHashMap: "
                           + map.toString());

        // remap the values of ConcurrentHashMap
        // using compute method
        map.compute("Book2", (key, val)
                                 -> val + 100);
        map.compute("Book1", (key, val)
                                 -> val + 512);

        // print new mapping
        System.out.println("New ConcurrentHashMap: "
                           + map);
    }
}
```

**输出：**

```java
ConcurrentHashMap: {Book3=400, Book1=10, Book2=500}
New ConcurrentHashMap: {Book3=400, Book1=522, Book2=600}
```

### 示例程序2

```java
// Java program to demonstrate
// compute(Key, BiFunction) method.

import java.util.concurrent.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // create a ConcurrentHashMap and add some values
        ConcurrentHashMap<Integer, String>
            map = new ConcurrentHashMap<>();
        map.put(1, "Kolkata");
        map.put(2, "Nadia");
        map.put(3, "Howrah");

        // print map details
        System.out.println("ConcurrentHashMap: "
                           + map.toString());

        // remap the values of ConcurrentHashMap
        // using compute method
        map.compute(2, (key, val)
                           -> val.concat(" (West-Bengal)"));
        map.compute(3, (key, val)
                           -> val.concat(" (West-Bengal)"));

        // print new mapping
        System.out.println("New ConcurrentHashMap: "
                           + map);
    }
}
```

**输出：**

```java
ConcurrentHashMap: {1=Kolkata, 2=Nadia, 3=Howrah}
New ConcurrentHashMap: {1=Kolkata, 2=Nadia (West-Bengal), 3=Howrah (West-Bengal)}
```

### 示例程序3：显示空指针异常

```java
// Java program to demonstrate NullPointerException
// for compute(Key, BiFunction) method.

import java.util.concurrent.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // create a ConcurrentHashMap and add some values
        ConcurrentHashMap<Integer, String>
            map = new ConcurrentHashMap<>();
        map.put(1, "Kolkata");
        map.put(2, "Nadia");
        map.put(3, "Howrah");

        try {
            // remap the values of ConcurrentHashMap
            // using compute method
            map.compute(null, (key, val)
                                  -> val.concat(" (West-Bengal)"));
        }
        catch (NullPointerException e) {
            // print Exception
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出：**

```java
Exception: java.lang.NullPointerException
```

参考文献：[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentHashMap.html#compute-K-java.util.function.BiFunction-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentHashMap.html#compute-K-java.util.function.BiFunction-)