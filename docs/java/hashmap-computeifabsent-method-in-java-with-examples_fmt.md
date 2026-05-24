# Java 中的 HashMap.computeIfAbsent() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/hashmap-computeifabsent-method-in-java-with-examples/](https://www.geeksforgeeks.org/hashmap-computeifabsent-method-in-java-with-examples/)

`HashMap`类的`computeIfAbsent(K key, Function<? super K, ? extends V> remappingFunction)`方法用于使用给定的映射函数计算给定键的值，如果键还没有与值相关联（或被映射为`null`），则在`HashMap`中输入该计算值，否则返回`null`。

*   如果此方法的映射函数返回`null`，则键不会记录映射。
*   在计算时，如果重映射函数抛出异常，则会再次抛出异常且不记录映射。
*   此方法不允许在计算期间修改映射。
*   如果重映射函数在计算期间修改了此映射，此方法将抛出`ConcurrentModificationException`。

## 语法

```java
public V computeIfAbsent(K key,
                         Function<? super K, ? extends V> remappingFunction)
```

## 参数

此方法接受两个参数：

*   `key`：我们要通过映射计算其值的键。
*   `remappingFunction`：计算数值的函数。

## 返回值

此方法返回与指定键关联的当前（现有或计算的）值，如果映射返回`null`值，则返回`null`。

以下程序说明了`computeIfAbsent(K key, Function remappingFunction)`方法：

### 程序 1

```java
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("key1", 10000);
        map.put("key2", 55000);
        map.put("key3", 44300);
        map.put("key4", 53200);

        // print map details
        System.out.println("HashMap:\n "
                           + map.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        map.computeIfAbsent("key5",
                            k -> 2000 + 33000);
        map.computeIfAbsent("key6",
                            k -> 2000 * 34);

        // print new mapping
        System.out.println("New HashMap:\n "
                           + map);
    }
}
```

**输出：**

```java
HashMap:
 {key1=10000, key2=55000, key3=44300, key4=53200}
New HashMap:
 {key1=10000, key2=55000, key5=35000, key6=68000, key3=44300, key4=53200}
```

### 程序 2

```java
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a HashMap and add some values
        HashMap<Integer, String>
            map = new HashMap<>();
        map.put(10, "Aman");
        map.put(20, "Suraj");
        map.put(30, "Harsh");

        // print map details
        System.out.println("HashMap:\n"
                           + map.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        map.computeIfAbsent(40, k -> "Sanjeet");

        // this will not effect anything
        // because key 1 is present
        map.computeIfAbsent(10, k -> "Amarjit");

        // print new mapping
        System.out.println("New HashMap:\n" + map);
    }
}
```

**输出：**

```java
HashMap:
{20=Suraj, 10=Aman, 30=Harsh}
New HashMap:
{20=Suraj, 40=Sanjeet, 10=Aman, 30=Harsh}
```

参考文献：[https://docs.oracle.com/javase/10/docs/api/java/util/HashMap.html#computeIfAbsent(K, java.util.function.Function)](https://docs.oracle.com/javase/10/docs/api/java/util/HashMap.html#computeIfAbsent(K, java.util.function.Function))