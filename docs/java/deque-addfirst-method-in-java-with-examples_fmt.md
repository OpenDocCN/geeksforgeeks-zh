# Java 中的 Deque addFirst()方法，带示例

> 原文: [https://www.geeksforgeeks.org/deque-addfirst-method-in-java-with-examples/](https://www.geeksforgeeks.org/deque-addfirst-method-in-java-with-examples/)

[`Deque`](https://www.geeksforgeeks.org/deque-interface-java-example/)接口的`addFirst(E e)`方法将参数中传递的元素插入到Deque的前面，如果有空间的话。如果Deque容量受限，并且没有空间可供插入，它将抛出一个`IllegalStateException`。函数在成功插入时返回`true`。

## 语法
```java
void addFirst(E e)
```

## 参数
该方法接受一个强制参数`e`，它是要插入到Deque前面的元素。

## 返回
该方法在成功插入时返回`true`。

## 异常
函数抛出四个异常，描述如下:

*   `ClassCastException`: 当要插入的元素的类阻止其被添加到此容器时。
*   `IllegalStateException`: 当容器容量已满且插入操作完成时。
*   `IllegalArgumentException`: 当元素的某些属性阻止其被添加到Deque时。
*   `NullPointerException`: 当要插入的元素作为`null`传递，并且Deque接口不允许`null`元素时。

下面的程序说明了`addFirst()`的方法:

### 程序 1: 借助 [`LinkedList`](https://www.geeksforgeeks.org/linked-list-in-java/)
```java
// Java Program Demonstrate addFirst()
// method of Deque
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new LinkedList<Integer>();

        // Add numbers to end of Deque
        DQ.addFirst(7855642);
        DQ.addFirst(35658786);
        DQ.addFirst(5278367);
        DQ.addFirst(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);
    }
}
```
**输出:**
```java
Deque: [74381793, 5278367, 35658786, 7855642]
```

### 程序 2: 借助 [`ArrayDeque`](https://www.geeksforgeeks.org/array-deque-in-java/)
```java
// Java Program Demonstrate addFirst()
// method of Deque
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ArrayDeque<Integer>();

        // Add numbers to end of Deque
        DQ.addFirst(7855642);
        DQ.addFirst(35658786);
        DQ.addFirst(5278367);
        DQ.addFirst(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);
    }
}
```
**输出:**
```java
Deque: [74381793, 5278367, 35658786, 7855642]
```

### 程序 3: 在 [`ConcurrentLinkedDeque`](https://www.geeksforgeeks.org/concurrentlinkeddeque-in-java/) 的帮助下
```java
// Java Program Demonstrate addFirst()
// method of Deque
import java.util.*;
import java.util.concurrent.ConcurrentLinkedDeque;
public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ConcurrentLinkedDeque<Integer>();

        // Add numbers to end of Deque
        DQ.addFirst(7855642);
        DQ.addFirst(35658786);
        DQ.addFirst(5278367);
        DQ.addFirst(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);
    }
}
```
**输出:**
```java
Deque: [74381793, 5278367, 35658786, 7855642]
```