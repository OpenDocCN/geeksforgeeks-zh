# Java 中的 CopyOnWriteArraySet retainAll() 方法示例

> 原文：[https://www.geeksforgeeks.org/copyonwritearrayset-retainall-method-in-java-with-example/](https://www.geeksforgeeks.org/copyonwritearrayset-retainall-method-in-java-with-example/)

`java.util.concurrent.CopyOnWriteArraySet` 类的 `retainAll()` 方法用于从该集合中保留指定集合中包含的所有元素。

## 语法

```java
public boolean retainAll(Collection c)
```

## 参数

该方法以 `Collection c` 为参数，包含从该集合中保留的元素。

## 返回值

如果该集合因调用而改变，则该方法返回 `true`。

## 异常

如果该集合包含空元素，并且指定的集合不允许空元素（可选），或者指定的集合为空，则该方法抛出 `NullPointerException`。

以下是说明 `retainAll()` 方法的例子。

### 示例 1

```java
// Java program to demonstrate
// retainAll() method for Integer value

import java.util.concurrent.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of CopyOnWriteArraySet<Integer>
            CopyOnWriteArraySet<Integer>
                set1 = new CopyOnWriteArraySet<Integer>();

            // Populating set1
            set1.add(1);
            set1.add(2);
            set1.add(3);
            set1.add(4);
            set1.add(5);

            // print set1
            System.out.println("CopyOnWriteArraySet before "
                               + "retainAll() operation : "
                               + set1);

            // Creating another object of  CopyOnWriteArraySet<Integer>
            CopyOnWriteArraySet<Integer>
                set2 = new CopyOnWriteArraySet<Integer>();
            set2.add(1);
            set2.add(2);
            set2.add(3);

            // print set2
            System.out.println("Collection Elements"
                               + " to be retained : "
                               + set2);

            // Removing elements from set
            // specified in set2
            // using retainAll() method
            set1.retainAll(set2);

            // print set1
            System.out.println("CopyOnWriteArraySet after "
                               + "retainAll() operation : "
                               + set1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**

```java
CopyOnWriteArraySet before retainAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be retained : [1, 2, 3]
CopyOnWriteArraySet after retainAll() operation : [1, 2, 3]
```

### 示例 2：适用于 `NullPointerException`

```java
// Java program to demonstrate
// retainAll() method for Integer value

import java.util.concurrent.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of CopyOnWriteArraySet<Integer>
            CopyOnWriteArraySet<Integer>
                set1 = new CopyOnWriteArraySet<Integer>();

            // Populating set1
            set1.add(1);
            set1.add(2);
            set1.add(3);
            set1.add(4);
            set1.add(5);

            // print set1
            System.out.println("CopyOnWriteArraySet before "
                               + "retainAll() operation : "
                               + set1);

            // Creating another object of  CopyOnWriteArraySet<Integer>
            CopyOnWriteArraySet<Integer>
                set2 = null;

            // print set2
            System.out.println("Collection Elements"
                               + " to be retained : "
                               + set2);

            System.out.println("\nTrying to pass "
                               + "null as a specified element\n");

            // Removing elements from set
            // specified in set2
            // using retainAll() method
            set1.retainAll(set2);

            // print set1
            System.out.println("CopyOnWriteArraySet after "
                               + "retainAll() operation : "
                               + set1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出：**

```java
CopyOnWriteArraySet before retainAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be retained : null

Trying to pass null as a specified element

Exception thrown : java.lang.NullPointerException
```