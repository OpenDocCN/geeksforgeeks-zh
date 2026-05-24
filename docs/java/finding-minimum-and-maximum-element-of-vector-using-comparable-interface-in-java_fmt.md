# 用 Java 中的 Comparable 接口求向量的最小和最大元素

> 原文：[https://www.geeksforgeeks.org/finding-minimum-and-maximum-element-of-vector-using-comparable-interface-in-java/](https://www.geeksforgeeks.org/finding-minimum-and-maximum-element-of-vector-using-comparable-interface-in-java/)

Java 中的 [`Vector`](https://www.geeksforgeeks.org/java-util-vector-class-java/) 类实现了一个动态数组，即它可以根据我们向其中插入或从中移除的元素来增长和收缩。它实现了 [`List`](https://www.geeksforgeeks.org/list-interface-java-examples/) 接口，因此支持 `List` 接口提供的所有方法。

在本文中，我们将讨论如何使用 Java 中的 [`Comparable`](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/) 接口来找到向量的最小和最大元素。

我们可以使用 [`Collections.min()`](https://www.geeksforgeeks.org/collections-min-method-in-java-with-examples/) 和 [`Collections.max()`](https://www.geeksforgeeks.org/collections-max-method-in-java-with-examples/) 方法来找到向量中的最小和最大元素。但是当我们使用我们的定制类并且我们想要使用 `Collections.min()` 和 `Collections.max()` 方法时，那么我们首先需要重写 `Comparable` 接口的 `compareTo()` 方法，以便 Java 能够比较我们定制类的实例。同样，因为我们想要比较对象，而不是原始数据类型，所以我们必须使用 `Comparable` 接口的自定义 `compareTo()` 方法。

**实现 `Comparable<T>` 接口的语法：**

```java
class Account implements Comparable<Account>
```

使用上面的语法，我们可以为我们的定制类，即 `Account` 类实现 `Comparable` 接口。

**覆盖 `compareTo()` 方法的语法：**

```java
@Override
public int compareTo(Account o) {
    // this refers to the current object(child object)
    // and o is the parent object.
    return this.balance - o.balance;
}
```

上面的 `compareTo()` 根据 `Account` 对象的 `balance` 属性对其进行比较。我们的 `compareTo()` 方法必须返回：

*   **零：** 当两个对象相等时。
*   **负值：** 当前对象小于传递对象即 `o` 时。
*   **正值：** 当前对象大于传递对象时。

下面是使用 `Comparable` 接口查找向量的最小和最大元素的代码实现。

## Java 代码示例

```java
// Java Program to find Minimum And Maximum Element of
// Vector using Comparable Interface in Java?
import java.util.Collections;
import java.util.Vector;

// The class Account implements the Comparable<T>
// interface
class Account implements Comparable<Account> {
    private String name;
    private int balance;

    // Creating parameterized constructor for
    // Account class
    public Account(String name, int balance) {
        this.name = name;
        this.balance = balance;
    }

    // Creating getters for Account class
    public String getName() { return name; }
    public int getBalance() { return balance; }

    // We are overriding the compareTo method of the
    // Comparable interface to be able to compare the
    // objects of the Account class. compareTo method should
    // return 0 when two Objects are equal, negative value
    // when current object is less than 'o' otherwise
    // returns positive value
    @Override
    public int compareTo(Account o) {
        return this.balance - o.balance;
    }
}

public class GFG {
    public static void main(String[] args) {
        // Creating a Vector of Account type
        Vector<Account> accountVector = new Vector<>();

        // Inserting some Objects inside the accountVector
        accountVector.add(new Account("Rahul", 10000));
        accountVector.add(new Account("Anjali", 2000));
        accountVector.add(new Account("Rohan", 5000));
        accountVector.add(new Account("Pooja", 50000));
        accountVector.add(new Account("Nandini", 50));

        // Finding the Accounts with minimum and maximum
        // balance using the Collections.min() and
        // Collections.max() method
        Account minAccount = Collections.min(accountVector);
        Account maxAccount = Collections.max(accountVector);

        // Displaying the account details of the
        // Accounts having minimum and maximum balance
        System.out.println(
            minAccount.getName()
            + " has the minimum balance of Rs "
            + minAccount.getBalance());

        System.out.println(
            maxAccount.getName()
            + " has the maximum balance of Rs "
            + maxAccount.getBalance());
    }
}
```

**输出**

```java
Nandini has the minimum balance of Rs 50
Pooja has the maximum balance of Rs 50000
```