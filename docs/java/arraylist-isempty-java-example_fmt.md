# Java ArrayList isEmpty() 方法详解

> 原文：[https://www.geeksforgeeks.org/arraylist-isempty-java-example/](https://www.geeksforgeeks.org/arraylist-isempty-java-example/)

Java 中 [`ArrayList`](https://www.geeksforgeeks.org/arraylist-in-java/) 的 [`isEmpty()`](https://www.geeksforgeeks.org/arraylist-isempty-java-example/) 方法用于检查列表是否为空。如果列表不包含任何元素，则返回 `true`；否则，如果列表包含任何元素，则返回 `false`。

## 语法

```java
list_name.isEmpty()
```

## 参数
不接受任何参数。

## 返回值
如果列表`list_name`没有其他元素，则返回真，否则返回假。返回类型是布尔数据类型。

## 错误和异常
该方法没有错误或异常。

## 示例：用 Java 演示 isEmpty() 工作的程序

```java
// Java code to demonstrate the working of
// isEmpty() method in ArrayList

// for ArrayList functions
import java.util.ArrayList;

public class GFG {
    public static void main(String[] args)
    {

// creating an Empty Integer ArrayList
        ArrayList<Integer> arr = new ArrayList<Integer>(10);

// check if the list is empty or not using function
        boolean ans = arr.isEmpty();
        if (ans == true)
            System.out.println("The ArrayList is empty");
        else
            System.out.println("The ArrayList is not empty");

// addition of a element to the ArrayList
        arr.add(1);

// check if the list is empty or not
        ans = arr.isEmpty();
        if (ans == true)
            System.out.println("The ArrayList is empty");
        else
            System.out.println("The ArrayList is not empty");
    }
}
```

## 输出

```java
The ArrayList is empty
The ArrayList is not empty
```