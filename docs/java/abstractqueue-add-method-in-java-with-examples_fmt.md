# Java中的AbstractQueue.add()方法详解

> 原文：[https://www.geeksforgeeks.org/abstractqueue-add-method-in-java-with-examples/](https://www.geeksforgeeks.org/abstractqueue-add-method-in-java-with-examples/)

[`AbstractQueue`](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/)的`add(E e)`方法将指定的元素插入到该队列中，如果可以在不违反容量限制的情况下立即插入。成功后返回`true`，如果当前没有可用空间，则抛出`IllegalStateException`。

## 语法

```java
public boolean add(E e)
```

## 参数

这个方法接受一个强制参数`e`，它是要插入到队列中的元素。

## 返回值

该方法返回`true`如果元素被插入到队列中，否则返回`false`。

## 异常

此方法抛出以下异常：

*   `IllegalStateException`：如果此时由于容量限制而无法添加元素。
*   `NullPointerException`：如果指定的元素为空。
*   `ClassCastException`：如果指定元素的类阻止其被添加到此队列。
*   `IllegalArgumentException`：如果指定元素的某些属性阻止其被添加到此队列。

下面程序举例说明`add()`方法：

### 示例1：基本用法

```java
// Java program to illustrate the
// AbstractQueue add() method
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        // Creating object of AbstractQueue<Integer>
        AbstractQueue<Integer>
            AQ = new LinkedBlockingQueue<Integer>();

        // Populating AQ
        AQ.add(10);
        AQ.add(20);
        AQ.add(30);
        AQ.add(40);
        AQ.add(50);

        // print AQ
        System.out.println("AbstractQueue contains : " + AQ);
    }
}
```

**输出：**

```java
AbstractQueue contains : [10, 20, 30, 40, 50]
```

### 示例2：IllegalStateException示例

```java
// Java program to illustrate the
// AbstractQueue add() method
// IllegalStateException
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {
            // Creating object of AbstractQueue<Integer>
            AbstractQueue<Integer>
                AQ = new LinkedBlockingQueue<Integer>(2);

            // Populating AQ
            AQ.add(10);
            AQ.add(20);
            AQ.add(30);
            AQ.add(40);
            AQ.add(50);

            // print AQ
            System.out.println("AbstractQueue contains : " + AQ);
        }
        catch (Exception e) {
            System.out.println("exception: " + e);
        }
    }
}
```

**输出：**

```java
exception: java.lang.IllegalStateException: Queue full
```

### 示例3：NullPointerException示例

```java
// Java program to illustrate the
// AbstractQueue add() method
// NullPointerException
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {
            // Creating object of AbstractQueue<Integer>
            AbstractQueue<Integer>
                AQ = new LinkedBlockingQueue<Integer>();

            // Populating AQ
            AQ.add(10);
            AQ.add(20);
            AQ.add(30);
            AQ.add(null);
            AQ.add(50);

            // print AQ
            System.out.println("AbstractQueue contains : " + AQ);
        }
        catch (Exception e) {
            System.out.println("exception: " + e);
        }
    }
}
```

**输出：**

```java
exception: java.lang.NullPointerException
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/AbstractQueue.html#add-E-](https://docs.oracle.com/javase/8/docs/api/java/util/AbstractQueue.html#add-E-)