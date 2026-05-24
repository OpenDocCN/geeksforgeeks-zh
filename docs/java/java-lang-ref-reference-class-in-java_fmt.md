# java 中的 `java.lang.ref.Reference` 类

> 原文：[https://www.geeksforgeeks.org/java-lang-ref-reference-class-in-java/](https://www.geeksforgeeks.org/java-lang-ref-reference-class-in-java/)

`java.lang.ref.Reference` 类是一个抽象基类，为引用对象而设。此类包含用于获取引用对象信息的方法。这个类不是直接的子类，因为对引用对象的操作是与垃圾收集器紧密配合的。

### 类声明

```java
public abstract class Reference<T>
extends Object
```

### 方法

| 方法 | 描述 |
| --- | --- |
| `clear()` | 此方法通过清除此引用对象来防止此对象入队。只有 Java 代码可以调用这个方法。垃圾收集器可以直接清除引用。垃圾收集器不需要调用这个方法来清除引用。 |
| `enqueue()` | 此方法将此对象添加到其注册队列中。 |
| `get()` | 此方法用于获取此引用所引用的对象。如果 Java 代码或垃圾收集器清除了该引用处的对象，则返回 `null`。 |
| `isEnqueued()` | 这个方法用来知道这个引用对象是否在任何队列中注册。 |

### 1. `public void clear()`

此方法通过清除此引用对象来防止此对象入队。只有 Java 代码可以调用这个方法。垃圾收集器可以直接清除引用。垃圾收集器不需要调用这个方法来清除引用。

### 2. `public boolean enqueue()`

此方法将此对象添加到其注册队列中。

**返回：** 如果此引用对象已成功添加到注册队列，则为 `true`。如果此引用对象在创建时未注册到任何队列，则为 `false`。

### 3. `public T get()`

此方法用于获取此引用所引用的对象。如果 Java 代码或垃圾收集器清除了该引用处的对象，则返回 `null`。

**返回：** 该引用所指的对象，如果该对象被清除，则为 `null`。

### 4. `public boolean isEnqueued()`

这个方法用来知道这个引用对象是否在任何队列中注册。

**返回：** 如果该引用对象已经入队，则返回 `true`，否则返回 `false`。

## Java 示例

```java
// Java program to illustrate working of Reference Class
import java.lang.ref.Reference;
import java.lang.ref.ReferenceQueue;
import java.lang.ref.SoftReference;
class Gfg {
}

public class GFG {

    public static void main(String[] args)
    {
        // Strong Reference
        Gfg g = new Gfg();

        ReferenceQueue<Gfg> q = new ReferenceQueue<Gfg>();

        // Creating Soft Reference to Gfg-type object to
        // which 'g' is also pointing and registering it
        // with q
        Reference<Gfg> softref
            = new SoftReference<Gfg>(g, q);

        g = softref.get();
        System.out.println(g.toString());
        // enqueue softref to its registered queue i.e q

        if (softref.enqueue()) {
            System.out.println(
                "Object successfully enqueued");
        }
        else {
            System.out.println("Object not enqueued");
        }

        // checking if softref is enqueued or not
        if (softref.isEnqueued()) {
            System.out.println("Object is enqueued");
        }
        else {
            System.out.println("Object not enqueued");
        }

        // clearing this reference object
        softref.clear();

        System.out.println("Object cleared");

        // trying to enqueue after clearing
        if (softref.enqueue()) {
            System.out.println(
                "Object successfully enqueued");
        }
        else {
            System.out.println("Object not enqueued");
        }
    }
}
```

**输出**

```
Gfg@214c265e
Object successfully enqueued
Object is enqueued
Object cleared
Object not enqueued
```