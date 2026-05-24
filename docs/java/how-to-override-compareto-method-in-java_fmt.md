# 如何在 Java 中覆盖 compareTo 方法？

> 原文: [https://www.geeksforgeeks.org/how-to-override-compareto-method-in-java/](https://www.geeksforgeeks.org/how-to-override-compareto-method-in-java/)

## Java 中的排序技术

我们知道，Java 中基本上有两种排序技术：

*   首先是内部排序，即使用预定义的排序方法升序。`Arrays.sort()` 用于原始类数组和包装类数组，`Collections.sort()` 用于 `Collections`。这两种方法都以升序对元素进行排序。
*   第二种对元素进行排序的技术是使用类中的比较器或类似接口。
    *   **比较器接口**：在类中实现 `Comparator` 接口，并覆盖 `compare()` 方法，或者在排序方法中将新的比较器作为第二个参数传递，并根据需要更改排序顺序。比较器仅适用于包装类型数组和集合，如 `Vector`、`ArrayList` 等。
    *   **可比接口**：这个接口实现了单一的排序技术，影响了整个类。`Comparable` 接口提供了一个 `compareTo()` 方法来对元素进行排序。

总而言之，在 Java 中，如果对象的排序需要基于自然顺序，那么就使用 `Comparable` 接口的 `compareTo()` 方法。对于整数，默认的自然排序顺序是升序，对于字符串，则是字母顺序。然而，如果排序需要对不同对象的属性进行，或者定制排序，那么使用 `Comparator` 接口的 `compare()`。

## 超越 compareTo() 方法

为了根据操作的需要改变对象的排序，我们必须在类中实现一个 `Comparable` 接口，[重写](https://www.geeksforgeeks.org/overriding-in-java/#:~:text=In%20any%20object%2Doriented%20programming,super%2Dclasses%20or%20parent%20classes.) `compareTo()` 方法。由于我们必须对对象的数组进行排序，传统的 `Arrays.sort()` 方法将不起作用，因为它曾经在基元类型上起作用。所以当我们调用 `Arrays.sort()` 方法并传递对象数组时，它会检查我们是否覆盖了 `compareTo()` 方法。因为我们已经重写了 `compareTo()` 方法，所以将根据年龄使用这个 `compareTo()` 方法来比较对象。

## Java 代码示例

```java
// Java Program to show how to override the compareTo()
// method of comparable interface
import java.util.*;

// implementing Comparable interface
public class GFG implements Comparable<GFG> {

String name;
    int age;

// Class constructor
    GFG(String name, int age)
    {
        this.name = name;
        this.age = age;
    }
    public int getage() { return age; }
    public String getname() { return name; }
    public static void main(String[] args)
    {
        // Creating GFG class object
        GFG ob[] = new GFG[4];

// Inserting elements in the objects
        ob[0] = new GFG("Aayush", 14);
        ob[1] = new GFG("Ravi", 12);
        ob[2] = new GFG("Sachin", 19);
        ob[3] = new GFG("Mohit", 20);

// sort the array,using overriden method
        Arrays.sort(ob);

for (GFG o : ob) {

// printing the sorted array objects name and
            // age
            System.out.println(o.name + " " + o.age);
        }

// if you want to create a dynamic array ,then you
        // can create an arraylist
        ArrayList<GFG> objects = new ArrayList<>();

// creating a new GFG object
        GFG newObject1 = new GFG("Rohan Devaki", 20);

// inserting the new object into the arraylist
        objects.add(newObject1);

// creating a new GFG object
        GFG newObject2 = new GFG("Algorithammer", 22);

// inserting the new object into the arraylist
        objects.add(newObject2);

// using Collections to sort the arraylist
        Collections.sort(objects);

for (GFG o : objects) {
            // printing the sorted objects in arraylist by
            // name and age
            System.out.format("%s  %d\n", o.name, o.age);
        }
    }
    // Overriding compareTo() method
    @Override public int compareTo(GFG o)
    {
        if (this.age > o.age) {

// if current object is greater,then return 1
            return 1;
        }
        else if (this.age < o.age) {

// if current object is greater,then return -1
            return -1;
        }
        else {

// if current object is equal to o,then return 0
            return 0;
        }
    }
}
```

## 输出

```java
Ravi 12
Aayush 14
Sachin 19
Mohit 20
Rohan Devaki  20
Algorithammer  22
```