# 将数组列表的元素复制到向量的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-copy-elements-of-arraylist-to-vector/](https://www.geeksforgeeks.org/java-program-to-copy-elements-of-arraylist-to-vector/)

`Vector` 实现了 `List` 接口，就像 `ArrayList` 一样，它也保持插入顺序，但是它很少在非线程环境中使用，因为它是同步的，因此它在元素的添加、搜索、删除和更新方面表现不佳。若要将元素从一个集合复制到其他集合，请在初始化时将数组列表的对象传递给 `Vector` 的构造函数，或者使用迭代逐元素复制。

**方法 1:**

`Vector<Integer> vector = new Vector<>(arrayList);`

1.  创建一个 `Vector` 对象，并在初始化时将 `ArrayList` 对象传递给构造函数。
2.  打印向量。

下面是上述方法的实现：

### 实现代码

```java
// Java program to copy elements from ArrayList to Vector
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Creating an ArrayList
        ArrayList<String> arrayList
            = new ArrayList<>(Arrays.asList("Rohan", "Sangeeta",
                                            "Ritik", "Yogesh"));

        // Creating a vector and copying elements
        // of arrayList to vector
        Vector<String> vector = new Vector<>(arrayList);

        // Printing the vector
        System.out.println(vector);
    }
}
```

### 输出

```java
[Rohan, Sangeeta, Ritik, Yogesh]
```