# Java 枚举中 ordinal() 和 compareTo() 的区别

> 原文：`https://www.geeksforgeeks.org/difference-between-ordinal-and-compareto-in-java-enum/`

[枚举](https://www.geeksforgeeks.org/enum-in-java/)用于在编程语言中表示一组命名常数。如果我们想表示一个名为常量的组，那么我们应该选择枚举。每个枚举常数都是静态的。因此，我们可以通过使用枚举名称来访问它。

**示例：**

```java
enum Day{
  SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY;
}
```

### ordinal() 方法

`java.lang.Enum.ordinal()`讲述了**序数**（它是其枚举声明中的位置，其中初始常数被赋予零的序数）用于特定的枚举。

`ordinal()`方法是一个非静态的方法，它意味着它只能用类对象访问，如果我们试图访问另一个类的对象，它会给出错误。它是最终方法，不能被重写。

`ordinal()`方法返回枚举常量的序数。（它在 enum 声明中的位置，其中第一个常量被赋零的序数）。

**语法：**

```java
public final int ordinal();
```

**返回值：**

```java
This method returns the ordinal of this enumeration constant.
```

**示例：**

```java
Day d1 = Day.TUESDAY;
System.out.println("the ordinal value is :" + d1.ordinal());

Output:
the ordinal value is : 2
```

### 示例代码

```java
// Java program to show the usage of 
// ordinal() method of java enumeration 

enum Day{
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY;
}

class Main{

    public static void main(String args[])
    {
       Day days[] = Day.values();
       for(Day d : days)
       System.out.print(d.ordinal() + " " );
    }
}
```

**Output**

```java
0 1 2 3 4 5 6 
```

### compareTo() 方法

枚举类的 `compareTo()` 方法将此枚举对象与已定义的对象进行比较，以便排序。枚举常数只能与相同类型的其他枚举常数进行比较。

**返回：**

1.  如果此枚举小于定义的对象，则为负整数。
2.  如果此枚举等于定义的对象，则为零。
3.  如果此枚举大于定义的对象，则为正整数。

**语法：**

```java
int compareTo(Object obj)
```

**示例：**

> `Day d1 = Day.SUNDAY;`
> 
> `Day d2 = Day.MONDAY;`
> 
> `System.out.println(d1.compareTo(d2));`
> 
> 由于 `d1` 的序数小于 `d2`，因此它将返回负值。

### 示例代码

```java
// Java program to show the usage of 
// compareTo() method of java enumeration 

enum Day
{
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY;
}

class GFG{

    public static void main(String args[])
    {
        Day d1 = Day.SUNDAY;
          Day d2 = Day.MONDAY;
          Day d3 = Day.TUESDAY;

        // will return negative value since d1 < d2    
        System.out.println(d1.compareTo(d2) );

        // will return positive value since d2 > d1
          System.out.println(d2.compareTo(d1) );

        // will return 0 since d3 == d3
        System.out.println(d3.compareTo(d3) );

    }
}
```

**Output**

```java

```

| `ordinal()` 方法 | `compareTo()` 方法 |
| --- | --- |
| 返回枚举常量的位置 | *   如果枚举小于定义的对象，则返回负整数。
*   如果枚举等于定义的对象，则返回零。
*   如果枚举大于定义的对象，则返回正整数。 |
| 这不需要任何参数。 | 它以枚举常量作为参数。 |
| **示例：** `enum Day { SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY; } Day d = Day.SUNDAY; d.ordinal(); // 0` | **示例：** `enum Day { SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY; } Day d1 = Day.SUNDAY; Day d2 = Day.MONDAY; d1.compareTo(d2); // 由于 d1 < d2，输出将为 -ve` |