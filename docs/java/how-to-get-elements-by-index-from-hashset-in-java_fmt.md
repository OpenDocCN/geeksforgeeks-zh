# 如何在 Java 中通过索引从 HashSet 获取元素？

> 原文：[https://www.geeksforgeeks.org/how-to-get-elements-by-index-from-hashset-in-java/](https://www.geeksforgeeks.org/how-to-get-elements-by-index-from-hashset-in-java/)

[`HashSet`](https://www.geeksforgeeks.org/hashset-in-java/) 扩展 [`AbstractSet`](https://www.geeksforgeeks.org/abstractset-class-in-java-with-examples/) 并实现 [`Set`](https://www.geeksforgeeks.org/set-in-java/) 接口。它创建一个使用哈希表进行存储的集合。该类不保证元素在一段时间内的顺序不变，但允许空元素。`HashSet` 的底层数据结构是 `Hashtable`。`HashSet` 还实现了 `Serializable` 和 `Cloneable` 接口。

`哈希表的声明:`

> `public class HashSet<E> extends AbstractSet<E> implements Set<E>, Cloneable, Serializable`
>
> 其中 `E` 表示要存储在 `HashSet` 中的元素类型。

我们在哈希集中通过索引获取元素的三种不同方式是：

1.  使用数组
2.  使用 `for` 循环
3.  使用 `ArrayList`

## 方法 1：使用数组

1.  导入所需的 Java 包 `java.util`
2.  使用 `Set` 接口声明 `HashSet`
3.  使用 `add()` 方法将元素添加到 `HashSet` 中
4.  显示哈希集以确定元素的顺序
5.  使用 `toArray()` 方法将哈希集转换为数组
6.  通过索引访问元素。

```java
// Java Program to get HashSet elements by index using Array

// import required package - java.util
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Declare HashSet using Set Interface
        Set<String> GFG = new HashSet<String>();

        // Add elements into HashSet using add()
        GFG.add("Welcome");
        GFG.add("To");
        GFG.add("Geeks");
        GFG.add("For");
        GFG.add("Geek");

        // Displaying HashSet
        System.out.println("HashSet contains: " + GFG);

        // Notice the order of elements may be different
        // than insertion

        // Converting HashSet to Array
        String[] Geeks = GFG.toArray(new String[GFG.size()]);

        // Accessing elements by index
        System.out.println("Element at index 3 is: "
                           + Geeks[3]);
    }
}
```

**Output**

```java
HashSet contains: [Geek, Geeks, For, Welcome, To]
Element at index 3 is: Welcome
```

## 方法 2：使用 `for` 循环

1.  导入所需的包 `java.util`
2.  使用 `Set` 接口声明 `HashSet`
3.  使用 `add()` 方法将元素添加到 `HashSet` 中
4.  显示哈希集以确定元素的顺序
5.  确定所需的索引
6.  实现一个 `for` 循环，通过索引访问元素

```java
// Java Program to get elements of HashSet by index using a
// for loop

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Declare HashSet using Set Interface
        Set<String> GFG = new HashSet<String>();

        // Add elements into HashSet using add()
        GFG.add("Welcome");
        GFG.add("To");
        GFG.add("Geeks");
        GFG.add("For");
        GFG.add("Geek");

        // Displaying HashSet
        System.out.println("HashSet contains: " + GFG);

        // Notice the order of elements may be different
        // than insertion

        // Iterator declaration
        int currentIndex = 0;

        // Desired Index
        int desiredIndex = 3;

        for (String element : GFG) {
            // Implementing for loop

            if (currentIndex == desiredIndex)
            {
                System.out.println("Element at index 3 is: "+ element);
                break;
            }
            currentIndex++;
        }
    }
}
```

**Output**

```java
HashSet contains: [Geek, Geeks, For, Welcome, To]
Element at index 3 is: Welcome
```

## 方法 3：使用 `ArrayList`

1.  导入所需的包 `java.util`
2.  使用 `Set` 接口声明 `HashSet`
3.  使用 `add()` 方法将元素添加到 `HashSet` 中
4.  显示哈希集以确定元素的顺序
5.  将哈希集转换为 `ArrayList`
6.  按索引访问元素

```java
// Java Program to get elements of HashSet by index using
// ArrayList

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Declare HashSet using Set Interface
        Set<String> GFG = new HashSet<String>();

        // Add elements into HashSet using add()
        GFG.add("Welcome");
        GFG.add("To");
        GFG.add("Geeks");
        GFG.add("For");
        GFG.add("Geek");

        // Displaying HashSet
        System.out.println("HashSet contains: " + GFG);

        // Notice the order of elements may be different
        // than insertion

        // Converting HashSet to ArrayList
        List<String> list = new ArrayList<String>(GFG);

        System.out.println("Element at index 3 is: "
                           + list.get(3));
    }
}
```

**Output**

```java
HashSet contains: [Geek, Geeks, For, Welcome, To]
Element at index 3 is: Welcome
```