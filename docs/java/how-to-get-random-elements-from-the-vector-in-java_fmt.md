# 如何在 Java 中从向量中获取随机元素？

> 原文：[https://www.geeksforgeeks.org/how-to-get-random-elements-from-the-vector-in-java/](https://www.geeksforgeeks.org/how-to-get-random-elements-from-the-vector-in-java/)

Java 中的 [`Vector`](https://www.geeksforgeeks.org/java-util-vector-class-java/) 是 Java 集合框架的一部分。向量是对象的动态数组，即向量的大小可以根据需要修改。向量实现了 [`List`](https://www.geeksforgeeks.org/list-interface-java-examples/) 接口。它还保持插入顺序，并且可以使用索引来访问向量的元素。Java 中的向量是同步的。

我们可以通过以下方式访问向量元素：
*   使用它们的索引
*   通过使用迭代器
*   通过随机调用向量中的元素

**从向量中获取随机元素的不同方式：**

1.  `Math` 类的 `random()` 方法
2.  使用 `Random` 类
3.  使用 `ThreadLocalRandom` 类

## 方法一：使用 `Math` 类的 `random()` 方法

`java.lang` 包的 `Math` 类有一个方法 `random()`，该方法返回大于 0.0 且小于 1.0 的正双精度值。我们可以使用这个方法生成一个随机索引，并访问给定向量中该索引处的元素。

### Java 代码示例

```java
// Java program to access random elements from the vector
// using random() method of Math class

import java.util.Vector;
public class GfG {

    // Create an instance of type vector which accepts
    // elements of String type
    static Vector<String> vector;

    // getRandomElements() method which accesses random
    // elements from the vector
    static void getRandomElements()
    {
        // Run a loop as many times as the number of
        // elements you want to access
        for (int i = 0; i < vector.size(); i++)
        {
            // Generate a random int value between 0 and the
            // last index of the vector
            int index = (int)(Math.random() * vector.size());

            // get the element at the generated random index
            System.out.println(vector.get(index));
        }
    }

    // Driver method
    public static void main(String[] args)
    {
        // Instantiate the vector instance
        vector = new Vector<String>();

        // Add elements into the vector
        vector.add("Welcome");
        vector.add("To");
        vector.add("Geeks");
        vector.add("For");
        vector.add("Geeks");

        // Call the getElements() method on this vector
        // object
        getRandomElements();
    }
}
```

**输出**

```java
For
To
Welcome
Welcome
Geeks
```

## 方法二：使用 `Random` 类

为了生成随机索引，我们还可以使用 `java.util` 包的 `Random` 类。它提供了生成指定类型和指定范围内的随机数的有用方法。

### Java 代码示例

```java
// Java program to access random elements from the vector
// using random class

import java.util.Random;
import java.util.Vector;
class GFG {

    // Create a Vector instance of type String
    static Vector<String> vector;

    // getRandomElements() method which accesses the
    // random elements from the given vector
    static void getRandomElements()
    {
        // create new object of the Random class
        Random random = new Random();

        // Run a loop as many times as the number of
        // elements you want to access
        for (int i = 0; i < vector.size(); i++)
        {
            // call the nextInt() method of this random
            // object to generate a random int value
            int index = random.nextInt(vector.size());

            // Get the element present at this random index
            // in the given vector
            System.out.println(vector.get(index));
        }
    }

    // Driver method
    public static void main(String[] args)
    {
        // Instantiate the vector object
        vector = new Vector<String>();

        // Add elements into the Vector
        vector.add("Welcome");
        vector.add("To");
        vector.add("Geeks");
        vector.add("For");
        vector.add("Geeks");

        // Call the getRandomElements() method on this
        // vector object
        getRandomElements();
    }
}
```

**输出**

```java
Welcome
Geeks
To
Geeks
For
```

## 方法三：使用 `ThreadLocalRandom` 类

`java.util.concurrent` 包的 `ThreadLocalRandom` 类是一个独立于当前线程的随机数生成器。它为多线程环境中的每个线程生成指定类型和指定范围内的随机数。我们可以使用这个类的 `nextInt()` 方法生成随机索引，并从给定的向量中访问该索引处的元素。

### Java 代码示例

```java
// Java program to access random elements from the given
// vector using ThreadLocalRandom class

import java.util.*;
import java.util.concurrent.ThreadLocalRandom;
class GFG {

    // Create a Vector instance which accepts elements of
    // String type
    static Vector<String> vector;

    // getRandomElements() method which accesses random
    // elements from the given vector
    static void getRandomElements()
    {
        // Run a loop as many times as the number of
        // elements you want to access
        for (int i = 0; i < vector.size(); i++)
        {
            // Generate a random integer by calling the
            // ThreadLocalRandom.current().nextInt() method
            int index = ThreadLocalRandom.current().nextInt(vector.size());

            // Print the element present at this random
            // index in the given vector
            System.out.println(vector.get(index));
        }
    }

    // Driver method
    public static void main(String[] args)
    {
        vector = new Vector<String>();

        // Add elements into the vector
        vector.add("Welcome");
        vector.add("To");
        vector.add("Geeks");
        vector.add("For");
        vector.add("Geeks");

        // Call the getRandomElements() method on this
        // vector object
        getRandomElements();
    }
}
```

**输出**

```java
Geeks
Welcome
Geeks
To
To
```