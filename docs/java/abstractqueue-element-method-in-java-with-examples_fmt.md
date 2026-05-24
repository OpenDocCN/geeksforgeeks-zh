# Java 中的 `AbstractQueue.element()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/abstractqueue-element-method-in-java-with-examples/](https://www.geeksforgeeks.org/abstractqueue-element-method-in-java-with-examples/)

[`AbstractQueue.element()`](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/) 方法检索但不移除该队列的头。

## 语法

```java
public E element()
```

## 参数
此方法不接受任何参数。

## 返回
该方法返回队列的头。

## 异常
如果队列为空，函数抛出 `NoSuchElementException`。

以下程序说明 `element()` 方法：

## 程序 1

```java
// Java program to illustrate the
// AbstractQueue element() method
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        // Creating object of AbstractQueue<Integer>
        AbstractQueue<Integer>
            AQ1 = new LinkedBlockingQueue<Integer>();

        // Populating AQ1
        AQ1.add(10);
        AQ1.add(20);
        AQ1.add(30);
        AQ1.add(40);
        AQ1.add(50);

        // print AQ
        System.out.println("AbstractQueue1 contains : " + AQ1);

        System.out.println("head : " + AQ1.element());
    }
}
```

## 输出

```java
AbstractQueue1 contains : [10, 20, 30, 40, 50]
head : 10
```

## 程序 2

```java
// Java program to illustrate the
// AbstractQueue element() method
// NoSuchElementException
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {
            // Creating object of AbstractQueue<Integer>
            AbstractQueue<Integer>
                AQ1 = new LinkedBlockingQueue<Integer>();

            System.out.println("AbstractQueue1 : " + AQ1.element());
        }
        catch (Exception e) {
            System.out.println("Exception is" + e);
        }
    }
}
```

## 输出

```java
Exception isjava.util.NoSuchElementException
```

## 参考
[https://docs.oracle.com/javase/8/docs/api/java/util/AbstractQueue.html#element--](https://docs.oracle.com/javase/8/docs/api/java/util/AbstractQueue.html#element--)