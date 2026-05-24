# Java中LinkedTransferQueue removeAll()方法示例

> 原文：[https://www.geeksforgeeks.org/linkedtransferqueue-removeall-method-in-java-with-examples/](https://www.geeksforgeeks.org/linkedtransferqueue-removeall-method-in-java-with-examples/)

[`java.util.concurrent.LinkedTransferQueue`](https://www.geeksforgeeks.org/linkedtransferqueue-in-java-with-examples/)的 `removeAll()` 方法是一个内置的 Java 函数，用于从该队列中移除指定集合中包含的所有元素。

## 语法

```java
public boolean removeAll(Collection c)
```

## 参数
该方法将集合 `c` 作为包含要从该列表中移除的元素的参数。

## 返回值
如果该列表因调用而改变，则该方法返回真。

## 异常
`NullPointerException` - 如果该列表包含空元素。

下面的程序说明了 `LinkedTransferQueue` 类的 `removeAll()` 函数：

## 程序 1

```java
// Java code to illustrate
// removeAll() method of LinkedTransferQueue

import java.util.concurrent.LinkedTransferQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedTransferQueue
        LinkedTransferQueue<String> LTQ
            = new LinkedTransferQueue<String>();

        // Add numbers to end of LinkedTransferQueue
        // using add() method
        LTQ.add("GeeksforGeeks");
        LTQ.add("Geeks");
        LTQ.add("Computer Science");
        LTQ.add("Portal");
        LTQ.add("Gfg");

        // Print the Queue
        System.out.println("Linked Transfer Queue : "
                           + LTQ);

        // Get the ArrayList to be deleted
        ArrayList<String> arraylist
            = new ArrayList<String>();
        arraylist.add("GeeksforGeeks");
        arraylist.add("Gfg");
        arraylist.add("hack");

        // Print ArrayList
        System.out.println("ArrayList to be deleted : "
                           + arraylist);

        // Removing elements from the queue
        // which are common to arraylist
        // using removeAll() method.
        LTQ.removeAll(arraylist);

        // Prints the Queue
        System.out.println("Linked Transfer Queue "
                           + "after removal of ArrayList : "
                           + LTQ);
    }
}
```

**Output:**

> 链接传输队列:【极客，极客，计算机科学，门户，Gfg】
> 待删除的数组列表:【极客，极客，Gfg，黑客】
> 删除数组列表后的链接传输队列:【极客，计算机科学，门户】

## 程序 2

```java
// Java code to illustrate
// removeAll() method of LinkedTransferQueue

import java.util.concurrent.LinkedTransferQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedTransferQueue
        LinkedTransferQueue<Integer> LTQ
            = new LinkedTransferQueue<Integer>();

        // Add numbers to end of LinkedTransferQueue
        // using add() method
        LTQ.add(3);
        LTQ.add(6);
        LTQ.add(10);
        LTQ.add(125);
        LTQ.add(205);

        // print the Queue
        System.out.println("Linked Transfer Queue : "
                           + LTQ);

        // Get the ArrayList to be deleted
        ArrayList<Integer> arraylist
            = new ArrayList<Integer>();
        arraylist.add(10);
        arraylist.add(100);
        arraylist.add(125);

        // Print ArrayList
        System.out.println("ArrayList to be deleted : "
                           + arraylist);

        // Removing elements from the queue
        // which are common to arraylist
        // using removeAll() method.
        LTQ.removeAll(arraylist);

        // Prints the Queue
        System.out.println("Linked Transfer Queue "
                           + "after removal of ArrayList : "
                           + LTQ);
    }
}
```

**Output:**

> 链接传输队列:[3，6，10，125，205]
> 要删除的数组列表:[10，100，125]
> 删除数组列表后的链接传输队列:[3，6，205]

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/LinkedTransferQueue.html#removeAll-java.util.Collection-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/LinkedTransferQueue.html#removeAll-java.util.Collection-)