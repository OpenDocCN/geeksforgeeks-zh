## HashMap 和 ConcurrentHashMap 的区别

> 原文: [https://www.geeksforgeeks.org/difference-hashmap-concurrenthashmap/](https://www.geeksforgeeks.org/difference-hashmap-concurrenthashmap/)

[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 是传统集合下的类，`ConcurrentHashMap` 是并发集合下的类，除此之外，它们之间还有各种不同之处，分别是:

*   `HashMap` 本质上是非同步的，即 `HashMap` 不是线程安全的，而 `ConcurrentHashMap` 本质上是线程安全的。
*   `HashMap` 的性能相对较高，因为它本质上是非同步的，任何数量的线程都可以同时执行。但是 `ConcurrentHashMap` 的性能有时很低，因为有时需要线程来等待 `ConcurrentHashMap`。
*   当一个线程正在迭代 `HashMap` 对象时，如果其他线程尝试添加/修改对象的内容，我们将得到一个运行时异常，称为 `ConcurrentModificationException`。而在 `ConcurrentHashMap` 中，在迭代期间执行任何修改时，我们不会得到任何异常。

**使用 `HashMap`**

```java
// Java program to illustrate
// HashMap drawbacks
import java.util.HashMap;

class HashMapDemo extends Thread
{
    static HashMap<Integer,String> l=new HashMap<Integer,String>();

    public void run()
    {
        try
        {
            Thread.sleep(1000);
            // Child thread trying to add
            // new element in the object
            l.put(103,"D");
        }
        catch(InterruptedException e)
        {
            System.out.println("Child Thread going to add element");
        }
    }

    public static void main(String[] args) throws InterruptedException
    {
        l.put(100,"A");
        l.put(101,"B");
        l.put(102,"C");
        HashMapDemo t=new HashMapDemo();
        t.start();

        for (Object o : l.entrySet())
        {
            Object s=o;
            System.out.println(s);
            Thread.sleep(1000);
        }
        System.out.println(l);
    }
}
```

**输出:**

```java
100=A
Exception in thread "main" java.util.ConcurrentModificationException
```

**使用 `ConcurrentHashMap`**

```java
// Java program to illustrate
// HashMap drawbacks
import java.util.HashMap;
import java.util.concurrent.*;

class HashMapDemo extends Thread
{
    static ConcurrentHashMap<Integer,String> l =
                           new ConcurrentHashMap<Integer,String>();

    public void run()
    {
        // Child add new element in the object
        l.put(103,"D");

        try
        {
            Thread.sleep(2000);
        }
        catch(InterruptedException e)
        {
            System.out.println("Child Thread going to add element");
        }
    }

    public static void main(String[] args) throws InterruptedException
    {
        l.put(100,"A");
        l.put(101,"B");
        l.put(102,"C");
        HashMapDemo t=new HashMapDemo();
        t.start();

        for (Object o : l.entrySet())
        {
            Object s=o;
            System.out.println(s);
            Thread.sleep(1000);
        }
        System.out.println(l);
    }
}
```

**输出:**

```java
100=A
101=B
102=C
103=D
{100=A, 101=B, 102=C, 103=D}
```

*   在 `HashMap` 中，键和值都允许为 `null`，而在 `ConcurrentHashMap` 中，键和值都不允许为 `null`，否则我们将得到一个运行时异常，称为 `NullPointerException`。

**使用 `HashMap`**

```java
//Java Program to illustrate ConcurrentHashMap behaviour
import java.util.*;
class ConcurrentHashMapDemo
{
    public static void main(String[] args)
    {
        HashMap m=new HashMap();
        m.put(100,"Hello");
        m.put(101,"Geeks");
        m.put(102,"Geeks");
        m.put(null,"World");
        System.out.println(m);
    }
}
```

输出:

```java
{null=World, 100=Hello, 101=Geeks, 102=Geeks}
```

**使用 `ConcurrentHashMap`**

```java
//Java Program to illustrate HashMap behaviour
import java.util.concurrent.*;
class ConcurrentHashMapDemo
{
    public static void main(String[] args)
    {
        ConcurrentHashMap m=new ConcurrentHashMap();
        m.put(100,"Hello");
        m.put(101,"Geeks");
        m.put(102,"Geeks");
        m.put(null,"World");
        System.out.println(m);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.NullPointerException
```

*   `HashMap` 是在 JDK 1.2 中引入的，而 `ConcurrentHashMap` 是由 SUN 微系统在 JDK 1.5 中引入的。