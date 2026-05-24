# 如何用 Java 构建自定义收集器？

> 原文：[https://www.geeksforgeeks.org/how-to-build-a-custom-collector-in-java/](https://www.geeksforgeeks.org/how-to-build-a-custom-collector-in-java/)

Java `Collector` 是为收集器接口提供很多有用的方法和函数的实用程序类。收集器实现主要与 `stream` `collect()` 方法一起使用。收集器接口是由 Java 8 在新引入的 Java Stream API 的部分下提供的。这个接口提供了各种方法来执行相互归约操作。可变归约操作对流中的数学信息执行算术函数，以找到流的最小、最大、平均或累加元素到一个集合中，或者连接流中的所有字符串元素。

## 创建自定义收集器的步骤

为了编写自定义收集器，我们应该用下面提到的方法实现接口。收集通常分四个步骤进行，由 Streams API 提供。

*   **`supplier()`**：这是元素收集过程的第一步，其中创建一个容器来保存流中的元素。此方法的返回类型是容器类型的供应者。
*   **`Accumulator()`**：这是将每个元素添加到由供应者步骤创建的容器中的第二步。在此方法中，我们必须返回一个双消费者函数，该函数接受容器和流中的每个元素。
*   **`combinator()`**：这是一个可选步骤，只能在并行处理流时执行。如果流是顺序的，则跳过此步骤。组合步骤用于将所有元素组合到一个容器中。在此方法中，我们应该返回一个二元运算符函数，用于组合两个累积容器。
*   **`Finish()`**：是收集过程的最后一步。只有当流中的所有元素都成功累积到供应者容器中时，它才会执行。在此方法中，我们可以返回一个函数，将累积和组合后的容器转换为最终输出。

除了这些方法之外，我们还有 `characteristics()` 方法来指定收集器的特性以及一组特性的返回类型 `Enum` 值。

## 例子

为了说明这个例子，为了更好地理解，我们将把代码分成三个部分。让我们举一个例子，我们有一个 `Employee` 对象的列表，我们想从中创建一个流，并将 `Employee` 对象收集为一个不可变的三元组列表。列表中的每个三元组将代表一名员工，并且它将具有该员工的年龄、名字和姓氏。

## 爪哇

```java
public class Employee_GFG {
    private long id;
    private String firstName;
    private String lastName;
    private int year;

    public Employee_GFG(long id, String firstName,
                        String lastName, int year) {
        this.id = id;
        this.firstName = firstName;
        this.lastName = lastName;
        this.year = year;
    }

    public long getId() { return id; }

    public void setId(long id) { this.id = id; }

    public String getFirstName() { return firstName; }

    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    public String getLastName() { return lastName; }

    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    public int getYear() { return year; }

    public void setYear(int year) { this.year = year; }
}
```