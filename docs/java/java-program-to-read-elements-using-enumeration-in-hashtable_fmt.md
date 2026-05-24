# 在哈希表中使用枚举读取元素的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-read-elements-using-enumeration-in-hashtable/](https://www.geeksforgeeks.org/java-program-to-read-elements-using-enumeration-in-hashtable/)

Java 中的[枚举](https://www.geeksforgeeks.org/enum-in-java/)是预定义的接口之一，其对象用于从集合框架变量（如栈、向量、哈希表等）中仅向前方向检索数据，而非向后方向。

[`Hashtable`](https://www.geeksforgeeks.org/hashtable-in-java/)是一个类，`Hashtable`类实现了一个将键映射到值的`Map`。它将键/值对存储在哈希表中。在这个数据结构中，我们指定了一个用作键的对象，以及我们想要与该键关联的值。然后对该键进行哈希运算，得到的哈希代码用作该值在表中存储的索引。`Hashtable`不提供任何枚举，而`Hashtable`不提供快速枚举。`Hashtable`的层次结构如下：

![](img/2763f630a6c4324dbc85c72dcb08a438.png)

**语法：**

```java
public class Hashtable<K,V> extends Dictionary<K,V> implements Map<K,V>, Cloneable, Serializable
```

**参数：**

*   `K`：键的类型。
*   `V`：分配给键的值的类型。

为了创建哈希表，从`java.util.Hashtable`中导入`Hashtable`，其中`K`、`V`是整数、字符串、浮点数等数据类型。

**语法：** 创建哈希表

```java
Hashtable<K, V> ht = new Hashtable<K, V>();
```

**实现：** 大学生信息

**示例**

### Java 代码

```java
// Java Program to read elements
// using enumeration in hashtable

// Importing enumeration class
import java.util.Enumeration;
// Importing hash table
import java.util.Hashtable;

// Class
public class GFG {

// Main driver method
    public static void main(String a[])
    {

// Creating hash table
        Hashtable<String, String> hm
            = new Hashtable<String, String>();

// Add key-value pair to Hashtable
        // Custom inputs
        hm.put("Name", "Bahubali");
        hm.put("College", "Amarnath");
        hm.put("Department", "Vedics");

// enum
        Enumeration<String> keys = hm.keys();

// Condition check whether element(K,V) is present
        // using hasMoreElements()
        while (keys.hasMoreElements()) {
            String key = keys.nextElement();

// Print corresponding key-value pair
            System.out.println("Value of " + key
                               + " is: " + hm.get(key));
        }

System.out.println();

// Creating a new Hashtable
        Hashtable<String, String> hm1
            = new Hashtable<String, String>();

// Adding key-value pair to Hashtable
        // Custom inputs
        hm1.put("Name", "Ravaan");
        hm1.put("College", "SriLanka");
        hm1.put("Department", "CS");

// Enum
        Enumeration<String> keys1 = hm1.keys();

// Condition check whether element(K,V) is present
        // using hasMoreElements()
        while (keys1.hasMoreElements()) {
            String key = keys1.nextElement();

// Print corresponding key-value pair
            System.out.println("Value of " + key
                               + " is: " + hm1.get(key));
        }

System.out.println();

// Creating a new Hashtable
        Hashtable<String, String> hm2
            = new Hashtable<String, String>();

// Adding key-value pair to Hashtable
        // Custom inputs
        hm2.put("Name", "Kattappa");
        hm2.put("College", "Beardo");
        hm2.put("Department", "War");

/// enum
        Enumeration<String> keys2 = hm2.keys();

// Condition check whether element(K,V) is present
        // using hasMoreElements()
        while (keys2.hasMoreElements()) {
            String key = keys2.nextElement();

// Print corresponding key-value pair
            System.out.println("Value of " + key
                               + " is: " + hm2.get(key));
        }
    }
}
```

**输出**

```java
Value of Name is: Bahubali
Value of College is: Amarnath
Value of Department is: Vedics

Value of Name is: Ravaan
Value of College is: SriLanka
Value of Department is: CS

Value of Name is: Kattappa
Value of College is: Beardo
Value of Department is: War
```