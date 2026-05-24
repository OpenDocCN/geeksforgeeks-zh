# 寻找Java数组列表的最大元素

> 原文：`https://www.geeksforgeeks.org/finding-maximum-element-of-java-arraylist/`

为了找到[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)中的最大元素，需要完整遍历数组列表。`ArrayList`类中有一个内置函数，用来寻找`ArrayList`中的最大元素，即时间复杂度为`O(N)`，其中`N`是`ArrayList`的大小，我们来讨论这两种方法。

示例：

```java
Input : ArrayList = {2, 9, 1, 3, 4}
Output: Max = 9

Input : ArrayList = {6, 7, 2, 1}
Output: Max = 7
```

## 方法一：手动遍历

1.  在变量上创建并用数组列表的第一个元素初始化它。
2.  开始遍历数组列表。
3.  如果当前元素大于变量，则用数组列表中的当前元素更新变量。
4.  最后，打印该变量。

下面是上述方法的实现：

```java
// Finding Maximum Element of Java ArrayList
import java.util.ArrayList;
import java.util.Collections;

class MinElementInArrayList {

    public static void main(String[] args) {
        // ArrayList of Numbers
        ArrayList<Integer> myList = new ArrayList<Integer>();

        // adding elements to Java ArrayList
        myList.add(16);
        myList.add(26);
        myList.add(3);
        myList.add(52);
        myList.add(70);
        myList.add(12);

        int maximum = myList.get(0);
        for (int i = 1; i < myList.size(); i++) {
            if (maximum < myList.get(i))
                maximum = myList.get(i);
        }
        System.out.println("Maximum Element in ArrayList = " + maximum);
    }
}
```

输出

```java
Maximum Element in ArrayList = 70
```

## 方法二：使用Collections.max()

Java集合类的`max()`方法可以用来查找`ArrayList`。`max()`方法根据元素的自然顺序返回集合中的最大元素。

```java
// Finding Maximum Element of Java ArrayList
import java.util.ArrayList;
import java.util.Collections;

class MinElementInArrayList {

    public static void main(String[] args) {
        // ArrayList of Numbers
        ArrayList<Integer> myList = new ArrayList<Integer>();

        // adding elements to Java ArrayList
        myList.add(16);
        myList.add(26);
        myList.add(3);
        myList.add(52);
        myList.add(70);
        myList.add(12);

        // 'max' method is used to find the
        // maximum element from Collections Class
        System.out.println("Maximum Element in ArrayList = " + Collections.max(myList));
    }
}
```

输出

```java
Maximum Element in ArrayList = 70
```