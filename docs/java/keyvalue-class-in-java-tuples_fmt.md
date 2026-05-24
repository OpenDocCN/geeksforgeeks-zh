# JavaToPles 中的键值类

> 原文：[`https://www.geeksforgeeks.org/keyvalue-class-in-java-tuples/`](https://www.geeksforgeeks.org/keyvalue-class-in-java-tuples/)

一个`KeyValue`是一个来自[`JavaTuples`](https://www.geeksforgeeks.org/javatuples-introduction/)库的元组，它只处理两个元素——一个键和值。因为这个`KeyValue`是一个泛型类，所以它可以保存任何类型的值。

由于`KeyValue`是一个元组，因此它也具有`JavaTuples`的所有特征：
*   它们是型安全的
*   它们是不可改变的
*   它们是可重复的
*   它们是可序列化的
*   它们是可比的（实现`Comparable<Tuple>`）
*   它们实现了`equals()`和`hashCode()`
*   它们还实现了`toString()`

### 类别声明

```java
public final class KeyValue<A, B> extends Tuple 
           implements IValueKey<A>, IValueValue<B>
```

### 类层次

```java
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.KeyValue<A, B>
```

### 创建键值元组

*   **从构造器**:
    语法：
    ```java
    KeyValue<A, B> kv = new KeyValue<A, B>(value1, value2);
    ```
*   **示例**:
    ```java
    // Below is a Java program to create
    // a KeyValue tuple from Constructor

    import java.util.*;
    import org.javatuples.KeyValue;

    class GfG {
        public static void main(String[] args)
        {
            KeyValue<Integer, String> kv
                = new KeyValue<Integer, String>(Integer.valueOf(1), "GeeksforGeeks");

            System.out.println(kv);
        }
    }
    ```