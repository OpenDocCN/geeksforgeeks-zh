# 从 Java 中的数组列表中获取唯一值

> 原文: [https://www.geeksforgeeks.org/get-unique-values-from-arraylist-in-java/](https://www.geeksforgeeks.org/get-unique-values-from-arraylist-in-java/)

让我们看看如何从数组列表中获取唯一值。将数组列表转换为哈希集以在数组列表中插入重复的值，但另一方面，哈希集不允许插入任何重复的值。在将数组列表转换为哈希表时，所有重复的值都会被删除，从而获得唯一的值。

## 示例

```java
INPUT : ArrayList = [a, b, c, b, d, a, c]
OUTPUT: Unique = [a, b, c, d]

INPUT : ArrayList = [1, 5, 2, 4, 3, 4, 5]
OUTPUT: Unique = [1, 2, 3, 4, 5]
```

## 方法

*   创建一个数组列表。
*   向数组列表中添加元素。
*   创建 `HashSet` 并传入 `HashSet` 构造函数。
*   打印 `HashSet` 对象。

下面是上述方法的实现：

```java
// Get Unique Values from ArrayList in Java
import java.util.ArrayList;
import java.util.HashSet;

public class GFG {

    public static void main(String[] args) {
        // Create ArrayList
        ArrayList<String> ArrList = new ArrayList<String>();

        // add values in ArrayList
        ArrList.add("a");
        ArrList.add("b");
        ArrList.add("c");
        ArrList.add("b");
        ArrList.add("d");
        ArrList.add("a");
        ArrList.add("c");

        // display original ArrayList
        System.out.println("Original ArrayList is : " + ArrList);

        // convert ArrayList to HastSet.
        HashSet<String> hset = new HashSet<String>(ArrList);

        // display HastSet
        System.out.println("ArrayList Unique Values is : " + hset);
    }
}
```

**输出**

**时间复杂度:** `O(n)`，其中 `n` 是原始数组列表的长度。