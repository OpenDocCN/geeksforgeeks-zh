# Java 中的迭代器

> 原文: [https://www.geeksforgeeks.org/iterators-in-java/](https://www.geeksforgeeks.org/iterators-in-java/)

Java 中的[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)中使用迭代器来逐个检索元素。Java 中有`三个迭代器`：

1.  `Enumeration`
2.  `Iterator`
3.  `ListIterator`

## 迭代器类型

### 1. `Enumeration`

这是一个用于获取遗留集合（`Vector`，`Hashtable`）元素的接口。`枚举`是 JDK 1.0 中出现的第一个迭代器，`Iterator`包含在 JDK 1.2 中，功能更多。`枚举`也用于指定`序列输入流`的输入流。我们可以通过在任何`Vector`对象上调用`Vector`类的`elements()`方法来创建`枚举`对象。

```java
// Here "v" is an Vector class object. e is of
// type Enumeration interface and refers to "v"
Enumeration e = v.elements();
```

`枚举`接口有两种`方法，即:`

```java
// Tests if this enumeration contains more elements
public boolean hasMoreElements();

// Returns the next element of this enumeration 
// It throws NoSuchElementException
// if no more element present
public Object nextElement();
```

### 2. `Iterator`

`Iterator`接口是Java集合框架中用于遍历集合的现代迭代器。它取代了`枚举`，并增加了通过`remove()`方法在迭代期间安全删除元素的能力。

```java
// Iterator 方法
boolean hasNext();
Object next();
void remove();
```

### 3. `ListIterator`

`ListIterator`是一个扩展了`Iterator`的迭代器，专为`List`设计。它允许双向遍历（向前和向后），并在迭代期间修改列表。

```java
// ListIterator 部分方法
boolean hasNext();
Object next();
int nextIndex();
boolean hasPrevious();
Object previous();
int previousIndex();
void set(Object e);
void add(Object e);
```

## Java 语言示例

```java
// Java program to demonstrate Enumeration

// Importing Enumeration and Vector classes
// from java.util package
import java.util.Enumeration;
import java.util.Vector;

// Main class
public class Test
{
    // Main driver method
    public static void main(String[] args)
    {
        // Creating a vector object
        Vector v = new Vector();

        // Iterating over vector object
        for (int i = 0; i < 10; i++)
            v.addElement(i);

        // Printing elements in vector object 
        System.out.println(v);

        // At beginning e(cursor) will point to
        // index just before the first element in v
        Enumeration e = v.elements();

        // Checking the next element availability where
        // condition holds true till threre is a single element
        // remaining in the List
        while (e.hasMoreElements())
        {
            // Moving cursor to next element
            int i = (Integer)e.nextElement();

            // Print above elements in object
            System.out.print(i + " ");
        }
    }
}
```