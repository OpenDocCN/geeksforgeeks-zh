# Java 中的 `ArrayList` `clear()`方法，带示例

> 原文: [https://www.geeksforgeeks.org/arraylist-clear-method-in-java-with-examples/](https://www.geeksforgeeks.org/arraylist-clear-method-in-java-with-examples/)

Java 中 [`ArrayList`](https://www.geeksforgeeks.org/arraylist-in-java/) 的 `clear()` 方法用于移除列表中的所有元素。在这个调用返回后，列表将是空的，所以每当执行这个操作时，相应数组列表的所有元素都将被删除，所以它成为从内存中删除数组列表中的元素的基本功能，从而导致优化。

**语法:**

```java
clear()
```

**返回类型:** 它不返回任何值，因为它删除了列表中的所有元素，并使其为空。

> **提示:** 确实实现了如下接口: `Serializable`、`Cloneable`、`Iterable<E>`、`Collection<E>`、`List<E>`、`RandomAccess`

**例 1:**

### Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Working of clear() Method
// of ArrayList class

// Importing required classes
import java.util.ArrayList;

// Main class
public class GFG {

// Main driiver method
    public static void main(String[] args)
    {
        // Creating an empty Integer ArrayList
        ArrayList<Integer> arr = new ArrayList<Integer>(4);

        // Adding elements to above ArrayList
        // using add() method
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);

        // Printing the elements inside current ArrayList
        System.out.println("The list initially: " + arr);

        // Clearing off elements
        // using clear() method
        arr.clear();

        // Displaying ArrayList elements
        // after using clear() method
        System.out.println(
            "The list after using clear() method: " + arr);
    }
}
```

**Output:**

```java
The list initially: [1, 2, 3, 4]
The list after using clear() method: []
```