# Map.Entry接口概述

> 原文：[https://www.geeksforgeeks.org/map-entry-interface-java-example/](https://www.geeksforgeeks.org/map-entry-interface-java-example/)

`Map.Entry`接口在Java中提供了一些方法来访问Map中的条目。通过进入Map的条目，我们可以很容易地操纵它们。`Map.Entry`是一个在`java.util`包中定义的泛型。

## 声明

```java
Interface Map.Entry
k -> Key
V -> Value
```

## 方法

### `equals(Object o)`
它比较对象（调用对象）和对象`o`是否相等。

**语法：**
```java
boolean equals(Object o)
Parameters :
o -> Object to which we want to compare
Returns:
true: if both objects are equals
false: otherwise
```

### `K getKey()`
返回相应Map条目的键。

**语法：**
```java
K getKey()
Parameters :
-------------
Returns:
K -> Returns the corresponding Key of a entry on which it is invoked
```

**例外：**
* 当条目从Map中移除时，将引发`IllegalStateException`。

### `V getValue()`
返回相应Map条目的值。

**语法：**
```java
V getValue()
Parameters :
-------------
Returns:
V -> Returns the corresponding value of a entry on which it is invoked
```

### `int hashCode()`
返回对应Map条目的哈希码。

**语法：**
```java
int hashCode()
Parameters :
-------------
Returns:
int -> Returns the hash-code of entry on which it is invoked
```

### `V setValue(V v)`
将Map条目的值设置为指定的值`v`。

**语法：**
```java
V setValue(V v)
Parameters :
v -> Value which was earlier stored in the entry on which it is invoked
Returns:
int -> Returns the hash-code of a entry on which it is invoked
```

**例外：**
* 如果值`v`的类不是正确的映射类型，则会引发`ClassCastException`。
* 如果`null`存储在`v`中，则抛出`NullPointerException`，映射不支持`null`。
* 如果我们不能操纵Map或者Map不支持`put`操作，就会抛出`UnsupportedOperationException`。
* 如果参数有问题，即`v`，则抛出`IllegalArgumentException`。
* 当条目从Map中移除时，抛出`IllegalStateException`。

## `Set<Map.Entry> entrySet()`
返回整个Map的Set视图。
**注：** 这不是`Map.Entry`接口的一种方法，但这里讨论是因为这个方法在使用`Map.Entry`接口时很有用。

**语法：**
```java
Set<Map.Entry> entrySet() 
Parameters :
---------------
Returns:
Set<Map.Entry> ->: Returns a Set containing the Map.Entry values
```

## 示例程序
下面的程序演示了`Map.Entry`的工作原理：

```java
// Java Program to demonstrate the
// methods of Map.Entry 
import java.util.LinkedHashMap;
import java.util.Map;
import java.util.Set;

public class GFG 
{
    public static void main(String[] args) 
    {
        // Create a LinkedHashMap
        LinkedHashMap<String,Integer> m = 
                new LinkedHashMap<String, Integer>();

        m.put("1 - Bedroom" , 25000);
        m.put("2 - Bedroom" , 50000);
        m.put("3 - Bedroom" , 75000);
        m.put("1 - Bedroom - hall", 65000);
        m.put("2 - Bedroom - hall", 85000);
        m.put("3 - Bedroom - hall", 105000);

        // Using entrySet() to get the entry's of the map
        Set<Map.Entry<String,Integer>> s = m.entrySet();

        for (Map.Entry<String, Integer> it: s)
        {
            // Using the getKey to get key of the it element
            // Using the getValue to get value of the it element
            System.out.println("Before change of value = " + 
                       it.getKey() + "   " +  it.getValue());

            // Changing the value of 1 - Bedroom.
            double getRandom = Math.random() * 100000;
            int getRoundoff = (int) Math.round(getRandom);

            // Using setValue to change the value of the
            // map element
            it.setValue(getRoundoff);

            System.out.println("After change of value = " + 
                       it.getKey() + "   " + it.getValue());
        }
    }
}
```

## 输出
```
Before change of value = 1 - Bedroom   25000
After change of value = 1 - Bedroom   59475
Before change of value = 2 - Bedroom   50000
After change of value = 2 - Bedroom   51650
Before change of value = 3 - Bedroom   75000
After change of value = 3 - Bedroom   95200
Before change of value = 1 - Bedroom - hall   65000
After change of value = 1 - Bedroom - hall   74112
Before change of value = 2 - Bedroom - hall   85000
After change of value = 2 - Bedroom - hall   41490
Before change of value = 3 - Bedroom - hall   105000
After change of value = 3 - Bedroom - hall   10902
```

本文由 **Sumit Ghosh** 供稿。如果你喜欢GeeksforGeeks并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到`write@geeksforgeeks.org`。看到你的文章出现在GeeksforGeeks博客主页上，帮助其他Geeks。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。