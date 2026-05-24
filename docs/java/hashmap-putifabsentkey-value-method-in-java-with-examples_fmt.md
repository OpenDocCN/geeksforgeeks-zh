# Java 中 HashMap putIfAbsent(key，value)方法，示例

> 原文：[https://www.geeksforgeeks.org/hashmap-putifabsentkey-value-method-in-java-with-examples/](https://www.geeksforgeeks.org/hashmap-putifabsentkey-value-method-in-java-with-examples/)

[`HashMap`](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)类的`putIfAbsent(K key, V value)`方法用于将指定的键映射到指定的值，前提是在这个`HashMap`实例中不存在这样的键（或者映射为`null`）。

**语法：**
```java
public V putIfAbsent(K key, V value)
```

**参数：**该方法接受两个参数：
*   `key`：是必须映射提供值的键。
*   `value`：如果不存在，该值必须与提供的键相关联。

**返回值：**
该方法返回`null`（如果之前没有与所提供的密钥进行映射，或者它被映射为`null`值）或与所提供的密钥相关联的当前值。

**异常：**
此方法会引发以下异常：
*   [`NullPointerException`](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)：如果指定的键或值为`null`，并且此映射不支持`null`值。
*   `IllegalArgumentException`：如果指定的键或值阻止其存储在地图中。
*   `UnsupportedOperationException` - 如果该映射不支持`put`操作（可选）
*   `ClassCastException` – 如果键或值的类型不适用于此地图（可选）

## 程序 1

```java
// Java program to demonstrate
// putIfAbsent(Key, value) method.

import java.util.HashMap;

public class TestClass {

// Main method
    public static void main(String[] args)
    {

// create a HashMap and add some values
        HashMap<String, Integer> map = new HashMap<>();
        map.put("a", 10000);
        map.put("b", 55000);
        map.put("c", 44300);
        map.put("e", 53200);

// print original map
        System.out.println("HashMap:\n " + map.toString());

// put a new value which is not mapped
        // before in map
        map.putIfAbsent("d", 77633);

        System.out.println("New HashMap:\n " + map);

// try to put a new value with existing key
        // before in map
        map.putIfAbsent("d", 55555);

// print newly mapped map
        System.out.println("Unchanged HashMap:\n " + map);
    }
}
```

**Output**
```java
HashMap:
 {a=10000, b=55000, c=44300, e=53200}
New HashMap:
 {a=10000, b=55000, c=44300, d=77633, e=53200}
Unchanged HashMap:
 {a=10000, b=55000, c=44300, d=77633, e=53200}
```

## 程序 2

```java
// Java program to demonstrate
// putIfAbsent(Key, value) method.

import java.util.*;

public class GFG {

// Main method
    public static void main(String[] args)
    {

// create a HashMap and add some values
        HashMap<String, Integer> map = new HashMap<>();
        map.put("a", 10000);
        map.put("b", 55000);
        map.put("c", 44300);
        map.put("e", null);

// print original map
        System.out.println("HashMap:\n " + map.toString());

// put a new value which is not mapped
        // before in map and store the returned
        // value in r1
        Integer r1 = map.putIfAbsent("d", 77633);

// put a new value for key 'e' which is mapped
        // with a null value, and store the returned
        // value in r2
        Integer r2 = map.putIfAbsent("e", 77633);

// print the value of r1
        System.out.println("Value of r1:\n " + r1);

// print the value of r2
        System.out.println("Value of r2:\n " + r2);

// print newly mapped map
        System.out.println("New HashMap:\n " + map);
    }
}
```

**Output**
```java
HashMap:
 {a=10000, b=55000, c=44300, e=null}
Value of r1:
 null
Value of r2:
 null
New HashMap:
 {a=10000, b=55000, c=44300, d=77633, e=77633}
```

**参考：**[https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#putIfAbsent-K-V-](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#putIfAbsent-K-V-)