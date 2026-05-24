# 在 Java 中迭代枚举值

> 原文：[https://www.geeksforgeeks.org/iterating-over-enum-values-in-java/](https://www.geeksforgeeks.org/iterating-over-enum-values-in-java/)

Java 中的 [Enum](https://www.geeksforgeeks.org/enum-in-java/) 是一个包含一组固定常量的数据类型。Java 枚举类型是一种特殊的 Java 类。枚举可以包含常数、方法等。

下面给出了如何声明枚举的演示：

## 【爪哇】

```java
// Demonstrates the declaration of enum
public enum season {
    Spring,
    Summer,
    Monsoon,
    Autumn,
    Winter
}
```

## 迭代枚举值

迭代枚举值有很多种方式：

1.  使用 `foreach()` 迭代
2.  使用 `for` 循环迭代
3.  使用 `java.util.stream` 迭代

### 使用 `forEach()` 迭代

`forEach()` 方法在列表或集合上工作。对于使用 `forEach()` 方法，将枚举转换为列表或集合。

枚举到集合（Set）和应用 `forEach` 的转换如下所示：

```java
EnumSet.allOf(seasons.class)
            .forEach(season -> System.out.println(season));
```

枚举到列表（List）的转换和 `forEach` 的应用如下所示：

```java
Arrays.asList(seasons.values()).
                forEach(season -> System.out.println(season));
```

下面的程序使用 `forEach()` 说明了枚举的迭代：

```java
// Program that demonstrates iteration
// over enums using forEach()
import java.util.Arrays;
import java.util.EnumSet;

public class GFG {
    public enum seasons {
        Spring,
        Summer,
        Monsoon,
        Autumn,
        Winter
    }
    public static void main(String[] args)
    {
        // Convert enum to set and apply forEach()
        EnumSet.allOf(seasons.class)
            .forEach(season -> System.out.println(season));

        // Convert enum to list and apply forEach()
        Arrays.asList(seasons.values())
            .forEach(season -> System.out.println(season));
    }
}
```

**输出**

```java
Spring
Summer
Monsoon
Autumn
Winter
Spring
Summer
Monsoon
Autumn
Winter
```

### 使用 `for` 循环迭代

`java.lang.Enum` 类的静态 `values()` 方法给出了一个枚举值数组。获取枚举值数组后，可以使用 `for` 循环对数组进行迭代。

下面的程序说明了使用 `for` 循环对枚举进行迭代：

```java
// Program that demonstrates iteration
// over enums using for loop
public class GFG {
    // enum of seasons
    public enum seasons {
        Spring,
        Summer,
        Monsoon,
        Autumn,
        Winter
    }
    public static void main(String[] args)
    {
        // iterate over enums using for loop
        for (seasons s : seasons.values()) {
            System.out.println(s);
        }
    }
}
```

**输出**

```java
Spring
Summer
Monsoon
Autumn
Winter
```

### 使用 `java.util.stream` 进行迭代

也可以使用 `java.util.stream` 类进行枚举迭代。通过将 `values()` 方法的返回值传递给 `Stream.of()` 方法来创建枚举值流。

下面的程序说明了使用 `java.util.stream` 对枚举的迭代：

```java
// Program that demonstrates iteration
// over enums using java.util.stream
import java.util.stream.Stream;

public class GFG {
    public enum seasons {
        Spring,
        Summer,
        Monsoon,
        Autumn,
        Winter
    }
    public static void main(String[] args)
    {
        // iteration over enum using java.util.stream
        Stream.of(seasons.values())
            .forEach(System.out::println);
    }
}
```

**输出**

```java
Spring
Summer
Monsoon
Autumn
Winter
```

**参考：**[https://docs.oracle.com/javase/tutorial/java/javaOO/enum.html](https://docs.oracle.com/javase/tutorial/java/javaOO/enum.html)