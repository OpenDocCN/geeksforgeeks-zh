# Java 中传统集合和并发集合的区别

> 原文: [https://www.geeksforgeeks.org/difference-traditional-collections-concurrent-collections-java/](https://www.geeksforgeeks.org/difference-traditional-collections-concurrent-collections-java/)

我们都知道传统集合（即`List`、`Set`、`Queue`及其实现的类）和并发集合（即`ConcurrentMap`接口、`ConcurrentHashMap`类、`CopyOnWriteArrayList`类等）。在这两个集合中，几乎没有什么区别，例如:

*   存在于传统集合中的大多数类（即`ArrayList`、`LinkedList`、`HashMap`等）本质上是非同步的，因此不存在线程安全。但是并发集合中的所有类本质上都是同步的。因此，在并发类中，我们不必关心线程安全。
*   而传统集合也有一些类（像`Vector`、`Stack`等）本质上是同步的，传统集合也有`SynchronizedSet`、`SynchronizedList`、`SynchronizedMap`方法，通过这些方法我们可以得到非同步对象的同步版本。但是由于宽锁定机制，上述同步类在性能方面并不好。而并发集合类的性能相对高于传统集合类。
*   在传统的集合中，如果一个线程正在迭代一个集合对象，并且如果另一个线程试图同时在该迭代对象中添加新元素，那么我们将得到`RuntimeException ConcurrentModificationException`。而在上述情况下，如果我们使用并发集合类，我们将不会得到任何运行时异常。
*   如果我们不在应用程序中处理线程，传统的集合类是一个不错的选择。而由于并发/同步收集，我们可以使用多个线程来处理收集对象。因此，如果我们在应用程序中处理多线程，并发收集是最佳选择。

## 代码示例

```java
// Java program to illustrate Traditional Collections Problem
import java.util.*;
class ConcurrentDemo extends Thread {
    static ArrayList l = new ArrayList();
    public void run()
    {
        try {
            Thread.sleep(2000);
        }
        catch (InterruptedException e) {
            System.out.println("Child Thread"
                    + " going to add element");
        }

        // Child thread trying to add new
        // element in the Collection object
        l.add("D");
    }

    public static void main(String[] args)
        throws InterruptedException
    {
        l.add("A");
        l.add("B");
        l.add("c");

        // We create a child thread that is
        // going to modify ArrayList l.
        ConcurrentDemo t = new ConcurrentDemo();
        t.start();

        // Now we iterate through the ArrayList
        // and get exception.
        Iterator itr = l.iterator();
        while (itr.hasNext()) {
            String s = (String)itr.next();
            System.out.println(s);
            Thread.sleep(6000);
        }
        System.out.println(l);
    }
}
```

输出:

```java
Exception in thread “main” java.util.ConcurrentModificationException
```

```java
// Java program to illustrate ConcurrentCollection uses
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;
class ConcurrentDemo extends Thread {
    static CopyOnWriteArrayList l = 
                         new CopyOnWriteArrayList();
    public void run()
    {
        try {
            Thread.sleep(2000);
        }
        catch (InterruptedException e) {
            System.out.println("Child Thread"
                         + " going to add element");
        }

        // Child thread trying to add new
        // element in the Collection object
        l.add("D");
    }

    public static void main(String[] args)
        throws InterruptedException
    {
        l.add("A");
        l.add("B");
        l.add("c");

        // We create a child thread that is
        // going to modify ArrayList l.
        ConcurrentDemo t = new ConcurrentDemo();
        t.start();

        // Now we iterate through the ArrayList
        // and get exception.
        Iterator itr = l.iterator();
        while (itr.hasNext()) {
            String s = (String)itr.next();
            System.out.println(s);
            Thread.sleep(6000);
        }
        System.out.println(l);
    }
}
```

输出:

```java
A
B
c
```