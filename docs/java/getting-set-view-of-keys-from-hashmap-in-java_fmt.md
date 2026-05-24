# 从Java中的HashMap获取键的集合视图

> 原文：[https://www.geeksforgeeks.org/getting-set-view-of-keys-from-hashmap-in-java/](https://www.geeksforgeeks.org/getting-set-view-of-keys-from-hashmap-in-java/)

Java的[`HashMap`](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)类提供了哈希表数据结构的功能。这个类可以在[`java.util`](https://www.geeksforgeeks.org/java-util-package-java/)包中找到。它实现了[`Map`](https://www.geeksforgeeks.org/map-interface-java-examples/)接口。它将元素存储在（键，值）对中，您可以通过另一种类型的索引（例如整数/字符串）来访问它们。这里，键被用作标识符，用于关联`Map`上的每个值。它可以存储不同的类型：整数键和字符串值，也可以存储相同的类型：整数键和整数值。

**示例：**

```java
Given : HashMap = {[a, 1], [b, 3], [C, 1]}
Output: Keys = [a, b, c]

Given : HashMap<Key, Value> = {[2, "hello"], [1, "world"]} 
Output: Keys = [2, 1]
```

`HashMap`类似于`HashTable`，但是不同步。它也允许存储空键，但是只能有一个空键，并且可以有任意数量的空值。

```java
HashMap<Integer, String> GFG = new HashMap<Integer, String>();
// 以上是带有整数键和字符串值的HashMap对象的声明
```

`java.util`包中的`Set`接口是一个无序的对象集合，其中不能存储重复的值。

```java
Set<Obj> set = new HashSet<Obj>();
// Obj是要存储在Set中的对象类型
```

散列表中的键的集合视图以`Set`的形式返回散列表中所有键的集合。

**打印键：**

*   使用迭代器对象在`while`循环中打印所有键。
*   直接将`Set`对象传入`System.out.println()`进行打印。

**实现：**

## Java实现代码

```java
// Getting Set view of keys from HashMap in Java
import java.io.*;
import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        HashMap<Integer, String> GFG
            = new HashMap<Integer, String>();

        // Inserting 1 as key and Geeks as the value
        GFG.put(1, "Geeks");

        // Inserting 2 as key and For as the value
        GFG.put(2, "For");

        // Inserting 3 as key and Geeks as the value
        GFG.put(3, "Geeks");
        Set<Integer> Geeks = GFG.keySet();
        System.out.println("Set View of Keys in HashMap : "
                           + Geeks);
    }
}
```

**输出**

```java
Set View of Keys in HashMap : [1, 2, 3]
```