# 使用 for 和 foreach 循环迭代数组的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-iterate-over-arrays-using-for-and-foreach-loop/](https://www.geeksforgeeks.org/java-program-to-iterate-over-arrays-using-for-and-foreach-loop/)

`array`是一组相似类型的变量，用一个共同的名字来指代。Java 中的数组与 C/C++中的不同。在这里，我们已经解释了 `for` 循环和 `foreach` 循环来显示 Java 中的数组元素。

## 1. for 循环

`for` 循环提供了编写循环结构的简洁方式。`for` 语句在一行中消耗初始化、条件、和增量/减量，从而提供更短、更易于调试的循环结构。

**语法:**

```java
for (initialization; test condition; 
                              increment/decrement)
{
    // statements
}
```

*   **初始化:** 在代码块执行之前执行。可以使用已经声明的变量，也可以声明一个变量，只限于局部循环。
*   **测试条件:** 测试循环的退出条件并返回布尔值。在执行循环语句之前，检查测试条件。
*   **语句执行:** 一旦条件评估为真，循环体中的语句就被执行。
*   **增量/减量:** 用于更新下一次迭代的变量。

**时间复杂度:** 如果语句为 `O(1)`，则 `for` 循环的总时间为 `N * O(1)`，即 `O(N)`。

## 2. for-each 循环

`for-each` 是一种数组遍历技术，类似于 Java5 中引入的 `for` 循环、`while` 循环、`do-while` 循环。

1.  它以 `for` 的关键字开始，就像普通的 `for` 循环一样。
2.  您不是声明和初始化循环计数器变量，而是声明一个与数组的基类型相同的变量，后跟一个冒号，再跟一个数组名。
3.  在循环体中，可以使用创建的循环变量，而不是使用索引数组元素。
4.  它通常用于迭代数组或集合类(如 `ArrayList`)。

**语法**

```java
for (type var : array) 
{ 
    //statements
}
```

**时间复杂度:** `O(n)` 其中 `n` 是迭代的元素个数。

**`for` 循环和 `for-each` 循环在 Java 中的区别。**

| 用于循环 | 对于每个循环 |
| --- | --- |
| 1. 需要增量/减量语句。例如 `i=i+3` | 1. 计数器总是递增 1，不能以递减顺序迭代 |
| 2. 当数组中的数据需要修改时，这是合适的。 | 2. 当数组中的数据需要修改时不合适。 |
| 3. 它跟踪索引，这样就可以获得数组索引。 | 3. 它不跟踪索引，因此无法获得数组索引。 |

**列表中的迭代:**

### Java 代码示例

```java
// Java for and foreach loop in list
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

public class App {

    public static void main(String args[])
    {
        // creating array list
        List<String> tech = new ArrayList<>(Arrays.asList(
            "Mac", "Samsung Gear ", "iPhone 12+"));

        // iterating over List using for loop
        System.out.println(
            "iterating over a List using for loop in Java:");
        for (int i = 0; i < tech.size(); i++) {
            System.out.println(tech.get(i));
        }

        // iterating over List using forEach() loop
        System.out.println(
            "iterating over a List using forEach() loop in Java:");
        for (String gadget : tech) {
            System.out.println(gadget);
        }
    }
}
```

**输出**

```java
iterating over a List using for loop in Java:
Mac
Samsung Gear 
iPhone 12+
iterating over a List using forEach() loop in Java:
Mac
Samsung Gear 
iPhone 12+
```

**数组中的迭代:**

### Java 代码示例

```java
// Java Program for Iteration in Array
public class GFG {

    public static void main(String args[])
    {
        // created array
        int[] element = {1, 9, 27, 28, 48};

       // iterating over an array using for loop
        System.out.println(
            "iterating over an array using for loop in Java:");

        for (int i = 0; i < element.length; i++) {
            System.out.println(element[i]);
        }

        // iterating over an array using forEach() loop
        System.out.println(
            "iterating over an array using forEach() loop in Java:");
        for (int var : element) { // syntax forEach() loop
                                  // var is variable.
            System.out.println(var);
        }
    }
}
```

**输出**

```java
iterating over an array using for loop in Java:
1
9
27
28
48
iterating over an array using forEach() loop in Java:
1
9
27
28
48
```