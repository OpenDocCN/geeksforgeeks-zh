# 从Java TreeMap中获取子地图、头地图和尾地图

> 原文：[https://www.geeksforgeeks.org/getting-submap-headmap-and-tailmap-from-java-treemap/](https://www.geeksforgeeks.org/getting-submap-headmap-and-tailmap-from-java-treemap/)

[TreeMap](https://www.geeksforgeeks.org/treemap-in-java/) 在 Java 中实现了 [Map](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口和 [NavigableMap](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/) 接口，它基于 [AbstractMap](https://www.geeksforgeeks.org/abstractmap-in-java/) 类。可以在 TreeMap 中使用各种构造函数来维护其键的排序。

## A. TreeMap的`subMap()`方法

Java 中的 `subMap()` 方法用于返回由参数中指定范围的键定义的映射的一部分或视图。

### 语法

```java
newTreeMap = oldTreeMap.subMap(startKey, endKey)
```

*   `startKey`：地图的起点或下端，包含该点。
*   `endKey`：地图的终点或上端，不包含该点。

### 返回类型

```java
Returns another map containing the portion of the map within the specified range.
```

### 实现

```java
// Java code to illustrate submap() Method

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        TreeMap<Integer, String> tree
            = new TreeMap<Integer, String>();

        // Mapping String to Integer
        tree.put(47, "Sashi");
        tree.put(82, "Ridhi");
        tree.put(66, "Himanshu");
        tree.put(98, "Sarthak");
        tree.put(87, "Sonika");
        tree.put(85, "Ritesh");
        tree.put(89, "Yogesh");

        // printing the complete TreeMap
        System.out.println("The original map is: \n"
                           + tree);

        // printing the submap from key
        // 67(included) to 89(excluded)
        System.out.println("The subMap is: \n"
                           + tree.subMap(67, 89));

        // if start key and end key are same then
        // this method returns a null map
        System.out.println("Empty subMap: \n"
                           + tree.subMap(67, 67));
    }
}
```

### 输出

```java
The original map is: 
{47=Sashi, 66=Himanshu, 82=Ridhi, 85=Ritesh, 87=Sonika, 89=Yogesh, 98=Sarthak}
The subMap is: 
{82=Ridhi, 85=Ritesh, 87=Sonika}
Empty subMap: 
{}
```

## B. TreeMap的`headMap()`方法

TreeMap 类的 `headMap()` 方法用于获取严格小于参数 `key_value` 的地图的所有键值对或视图。

### 语法

```java
newTreeMap = oldTreeMap.headMap(specifiedKey)
```

### 返回类型

```java
The method returns the portion of the map whose keys are less than the specified key.
```

### 实现

```java
// Java code to illustrate headmap() method
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        TreeMap<Integer, String> tree
            = new TreeMap<Integer, String>();

        // Mapping String to Integer
        tree.put(47, "Sashi");
        tree.put(82, "Ridhi");
        tree.put(66, "Himanshu");
        tree.put(98, "Sarthak");
        tree.put(87, "Sonika");
        tree.put(85, "Ritesh");
        tree.put(89, "Yogesh");

        // printing the complete TreeMap
        System.out.println("The original map is: \n"
                           + tree);

        // this will print all the key-value
        // pairs which are less than 67
        System.out.println("The headMap is: \n"
                           + tree.headMap(67));
    }
}
```

### 输出

```java
The original map is: 
{47=Sashi, 66=Himanshu, 82=Ridhi, 85=Ritesh, 87=Sonika, 89=Yogesh, 98=Sarthak}
The headMap is: 
{47=Sashi, 66=Himanshu}
```

## C. TreeMap的`tailMap()`方法

Java 中的 `tailMap()` 方法用于获取参数中键大于等于 `from_key` 的地图的一部分或视图。

### 语法

```java
newMap = oldMap.tailMap(specifiedKey)
```

### 返回类型

```java
This method returns a map in which keys are greater than or equal to the specified key.
```

### 实现

```java
// Java code to illustrate tailmap() Method
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        TreeMap<Integer, String> tree
            = new TreeMap<Integer, String>();

        // Mapping String to Integer
        tree.put(47, "Sashi");
        tree.put(82, "Ridhi");
        tree.put(66, "Himanshu");
        tree.put(98, "Sarthak");
        tree.put(87, "Sonika");
        tree.put(85, "Ritesh");
        tree.put(89, "Yogesh");

        // printing the complete TreeMap
        System.out.println("The original map is: \n"
                           + tree);

        // this will print all the key-value pairs
        // which are greater than or equal to 67
        System.out.println("The tailMap is: \n"
                           + tree.tailMap(67));
    }
}
```

### 输出

```java
The original map is: 
{47=Sashi, 66=Himanshu, 82=Ridhi, 85=Ritesh, 87=Sonika, 89=Yogesh, 98=Sarthak}
The tailMap is: 
{82=Ridhi, 85=Ritesh, 87=Sonika, 89=Yogesh, 98=Sarthak}
```

**重要提示：** 对 `subMap()`、`headMap()`、`tailMap()` 方法返回的地图的任何更改也将反映在原始地图中。

### 实现

```java
// Combine operation on getting submap,
// headmap, and tailmap from Java TreeMap

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        TreeMap<Integer, String> originalTree
            = new TreeMap<Integer, String>();

        // Mapping String to Integer
        originalTree.put(82, "Ridhi");
        originalTree.put(87, "Sonika");
        originalTree.put(85, "Ritesh");
        originalTree.put(89, "Yogesh");
        originalTree.put(80, "Yashdeep");
        originalTree.put(99, "Raushan");
        originalTree.put(67, "Shishya");

        // printing the complete TreeMap
        System.out.println("The original map is: \n"
                           + originalTree);

        // submap from key 67(included) to 89(excluded)
        Map<Integer, String> newSubMap
            = originalTree.subMap(67, 89);

        // doing some modification in map named
        // newSubMap and this modification is going to
        // be refelected in the original treemap also
        newSubMap.remove(67);

        // printing the original treemap to see the
        // modification
        System.out.println(
            "The original map after remove operation is: \n"
            + originalTree);

        // creating a new map named newHeadMap
        Map<Integer, String> newHeadMap
            = originalTree.headMap(87);

        // doing some modification in map named
        // newHeadMap and this modification is going to
        // be refelected in the original treemap also
        newHeadMap.remove(82);

        // printing the original
        // treemap to see the modification
        System.out.println(
            "The original map after remove operation: \n"
            + originalTree);

        // creating a new map named newTailMap
        Map<Integer, String> newTailMap
            = originalTree.tailMap(85);

        // doing some modification in map named
        // newHeadMap and this modification is going to
        // be refelected in the original treemap also
        newTailMap.put(94, "Ankit");

        // printing the original treemap
        // to see the modification
        System.out.println(
            "The original map after put operation is: \n"
            + originalTree);
    }
}
```

### 输出

```java
The original map is: 
{67=Shishya, 80=Yashdeep, 82=Ridhi, 85=Ritesh, 87=Sonika, 89=Yogesh, 99=Raushan}
The original map after remove operation is: 
{80=Yashdeep, 82=Ridhi, 85=Ritesh, 87=Sonika, 89=Yogesh, 99=Raushan}
The original map after remove operation: 
{80=Yashdeep, 85=Ritesh, 87=Sonika, 89=Yogesh, 99=Raushan}
The original map after put operation is: 
{80=Yashdeep, 85=Ritesh, 87=Sonika, 89=Yogesh, 94=Ankit, 99=Raushan}
```