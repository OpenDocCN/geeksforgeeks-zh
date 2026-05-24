# Java.util.ArrayList.indexOf() 方法应用

> 原文链接：[https://www.geeksforgeeks.org/java-util-arraylist-index-of-java/](https://www.geeksforgeeks.org/java-util-arraylist-index-of-java/)

[`ArrayList`](https://www.geeksforgeeks.org/arraylist-in-java/) 的 `indexOf()` 方法返回该列表中指定元素第一次出现的索引，如果该列表不包含该元素，则返回 `-1`。

## 语法

```java
public int indexOf(Object o)
```
`obj`：要搜索的元素。

## 代码示例

```java
// Java code to demonstrate the working of
// indexOf in ArrayList

// for ArrayList functions
import java.util.ArrayList;

public class IndexOfEx {
  public static void main(String[] args) {

    // creating an Empty Integer ArrayList
    ArrayList<Integer> arr = new ArrayList<Integer>(5);

    // using add() to initialize values
    arr.add(1);
    arr.add(2);
    arr.add(3);
    arr.add(4);

    // printing initial value
    System.out.print("The initial values in ArrayList are : ");
    for (Integer value : arr) {
      System.out.print(value);
      System.out.print(" ");
    }

    // using indexOf() to find index of 3
    int pos = arr.indexOf(3);

    // prints 2
    System.out.println("\nThe element 3 is at index : " + pos);
  }
}
```

输出：

```java
The initial values in ArrayList are : 1 2 3 4 
The element 3 is at index : 2
```

## 实际应用

`indexOf` 方法主要用于确定事件的第一次或最后一次出现，例如骰子掷出 6 的第一次出现，或名称中某个字母的第一次出现等。

## 另一个例子

```java
// Java code to demonstrate the application of
// index functions in ArrayList

// for ArrayList functions
import java.util.ArrayList;

public class AppliIndex {
  public static void main(String[] args) {

    // creating an Empty Integer ArrayList
    ArrayList<Integer> arr = new ArrayList<Integer>(10);

    // using add() to initialize dice values
    arr.add(1);
    arr.add(2);
    arr.add(4);
    arr.add(6);
    arr.add(5);
    arr.add(2);
    arr.add(6);
    arr.add(1);
    arr.add(6);
    arr.add(4);

    // using indexOf() to find first index of 6
    int pos1 = arr.indexOf(6);

    // using lastIndexOf() to find last index of 6
    int pos2 = arr.lastIndexOf(6);

    // to balance 0 based indexing
    pos1 = pos1 + 1;
    pos2 = pos2 + 1;

    // printing first index of 6
    System.out.println("The first occurrence of 6 is  : " + pos1);

    // printing last index of 6
    System.out.println("The last occurrence of 6 is  : " + pos2);
  }
}
```

输出：

```java
The first occurrence of 6 is  : 4
The last occurrence of 6 is  : 9
```

本文由 **香巴拉维·辛格** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在 GeeksforGeeks 主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。