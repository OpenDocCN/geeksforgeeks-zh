# Java Integer compareTo()方法

> 原文: [https://www.geeksforgeeks.org/java-integer-compareto-method/](https://www.geeksforgeeks.org/java-integer-compareto-method/)

`java.lang`包的`Integer`类的`compareTo()`方法对两个`Integer`对象进行数值比较，如果这个`Integer`等于参数`Integer`，则返回值 0；如果该整数在数值上小于参数整数，则该值小于 0；如果此整数在数字上大于参数整数（有符号比较），则为大于 0 的值。

## 语法

```java
public int compareTo(Integer anotherInt)
```

**参数：**
`anotherInt` - 要比较的`Integer`。

**返回值：**
- 如果此`Integer`等于参数`Integer`，则此方法返回值 0；
- 如果此`Integer`在数值上小于参数`Integer`，则返回小于 0 的值；
- 如果此`Integer`在数值上大于参数`Integer`，则返回大于 0 的值（有符号比较）。

## 示例

展示`java.lang.Integer.compareTo()`方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Integer.compareTo() method
import java.lang.Integer;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        Integer a = new Integer(10);
        Integer b = new Integer(20);

        // as 10 less than 20, Output will be a value less than zero
        System.out.println(a.compareTo(b));

        Integer x = new Integer(30);
        Integer y = new Integer(30);

        // as 30 equals 30, Output will be zero
        System.out.println(x.compareTo(y));

        Integer w = new Integer(15);
        Integer z = new Integer(8);

        // as 15 is greater than 8, Output will be a value greater than zero
        System.out.println(w.compareTo(z));
    }
}
```

## 输出

```java

```