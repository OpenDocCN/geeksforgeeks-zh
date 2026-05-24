# 打印链接哈希表值的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-print-linkedhashmap-values/](https://www.geeksforgeeks.org/java-program-to-print-linkedhashmap-values/)

[`LinkedHashMap`](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是 Java 中的一个预定义类，类似于 `HashMap`，包含 `key` 及其各自的 `value`。与 `HashMap` 不同，在 `LinkedHashMap` 中保留插入顺序。我们需要打印散列图的值，该值与其关键字相链接。我们必须遍历 `LinkedHashMap` 中的每个键，并使用 `for` 循环打印其各自的值。

**例:**

```java
Input:
Key- 2 : Value-5
Key- 4 : Value-3
Key- 1 : Value-10
Key- 3 : Value-12
Key- 5 : Value-6

Output: 5, 3, 10, 12, 6
```

**算法:**

*   使用 `for` 循环遍历整个 `LinkedHashMap`。
*   使用 `entrySet()` 方法，此方法给出所有映射的 `Set` 结构以便遍历整个映射。在每次迭代中打印它们各自的值。

**示例:**

## Java

```java
// Java program to print all the values
// of the LinkedHashMap

import java.util.*;
import java.io.*;

class GFG {
    public static void main (String[] args) {

        LinkedHashMap<Integer,Integer> LHM = new LinkedHashMap<>();

        LHM.put(2,5);
        LHM.put(4,3);
        LHM.put(1,10);
        LHM.put(3,12);
        LHM.put(5,6);

        // using .entrySet() which gives us the
        // list of mappings of the Map
        for(Map.Entry<Integer,Integer> it : LHM.entrySet())
            System.out.print(it.getValue()+", ");
    }
}
```

**输出**

```java
5, 3, 10, 12, 6,
```

**时间复杂度:** `O(n)`。