# Java中的`IntPredicate`接口详解及示例

> 原文：[https://www.geeksforgeeks.org/java-util-function-intpredicate-interface-in-java-with-examples/](https://www.geeksforgeeks.org/java-util-function-intpredicate-interface-in-java-with-examples/)

在`JDK 8`中引入了`IntPredicate`接口。该接口封装在`java.util.function`包中。它对整数值进行运算，并根据条件返回谓词值。这是一个[函数式接口](https://www.geeksforgeeks.org/functional-interfaces-java/)，因此也可以用于[Lambda表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)。

```java
public interface IntPredicate
```

**方法：**

1.  `test()`：该函数对`int`值进行条件检查，并返回一个表示结果的布尔值。

```java
boolean test(int value)
```

2.  `and()`：这个函数对当前对象和作为参数接收的对象应用`and`运算，并返回新形成的谓词。此方法有默认实现。

```java
default IntPredicate and(IntPredicate other)
```

3.  `negate()`：此函数返回当前谓词的逆，即反转测试条件。此方法有默认实现。

```java
default IntPredicate negate()
```

4.  `or()`：此函数对当前对象和作为参数接收的对象应用`or`运算，并返回新形成的谓词。此方法有默认实现。

```java
default IntPredicate or(IntPredicate other)
```

**示例：**

```java
// Java example to demonstrate IntPredicate interface

import java.util.function.IntPredicate;

public class IntPredicateDemo {
    public static void main(String[] args)
    {
        // Predicate to check a value is less than 544331
        IntPredicate intPredicate = (x) ->
        {
            if (x <= 544331)
                return true;
            return false;
        };

        System.out.println("544331 is less than 544331 "
                           + intPredicate.test(544331));

        // Predicate to check a value is equal to 544331
        IntPredicate predicate = (x) ->
        {
            if (x == 544331)
                return true;
            return false;
        };

        System.out.println("544331 is equal to 544331 "
                           + predicate.test(544331));

        // ORing the two predicates
        IntPredicate intPredicate1 = intPredicate.or(predicate);
        System.out.println("544331 is less than equal to 544331 "
                           + intPredicate1.test(544331));

        // ANDing the two predicates
        intPredicate1 = intPredicate.and(predicate);
        System.out.println("544331 is equal to 544331 "
                           + intPredicate1.test(544331));

        // Negating the predicate
        intPredicate1 = intPredicate.negate();
        System.out.println("544331 is greater than 544331 "
                           + intPredicate1.test(544331));
    }
}
```

**输出：**

```java
544331 is less than 544331 true
544331 is equal to 544331 true
544331 is less than equal to 544331 true
544331 is equal to 544331 true
544331 is greater than 544331 false
```

**参考：**