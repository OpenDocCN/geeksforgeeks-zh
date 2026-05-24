# HashSet 中的 contains() 方法

> 原文: [https://www.geeksforgeeks.org/hashset-contains-method-in-java/](https://www.geeksforgeeks.org/hashset-contains-method-in-java/)

`java.util.HashSet.contains()` 方法用于检查 `HashSet` 中是否存在特定的元素。所以它基本上是用来检查一个集合是否包含任何特定的元素。

**语法:**

```java
Hash_Set.contains(Object element)
```

**参数:** 参数 `element` 属于 `Object` 类型。这是需要测试的元素，无论它是否存在于集合中。

**返回值:** 如果元素存在于集合中，方法返回 `true`，否则返回 `false`。

下面程序举例说明了 `contains()` 方法的用法：

```java
// Java code to illustrate HashSet.contains() method
import java.io.*;
import java.util.HashSet;

public class HashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty HashSet
        HashSet<String> set = new HashSet<String>();

        // Using add() method to add elements into the Set
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the HashSet
        System.out.println("HashSet: " + set);

        // Check for "Geeks" in the set
        System.out.println("Does the Set contains 'Geeks'? " + set.contains("Geeks"));

        // Check for "4" in the set
        System.out.println("Does the Set contains '4'? " + set.contains("4"));

        // Check if the Set contains "No"
        System.out.println("Does the Set contains 'No'? " + set.contains("No"));
    }
}
```

**输出:**

```
HashSet: [4, Geeks, Welcome, To]
Does the Set contains 'Geeks'? true
Does the Set contains '4'? true
Does the Set contains 'No'? false
```