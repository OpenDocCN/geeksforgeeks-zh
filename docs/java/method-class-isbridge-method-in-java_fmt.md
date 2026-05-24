# 方法类 | Java 中的 `isBridge()` 方法

> 原文：[https://www.geeksforgeeks.org/method-class-isbridge-method-in-java/](https://www.geeksforgeeks.org/method-class-isbridge-method-in-java/)

`isBridge()` 方法用于检查一个函数是否是桥函数。如果方法对象是桥方法，此方法返回 `true`，否则返回 `false`。

**桥接方法：** 这些是在源函数和目标函数之间创建中间层的方法。它通常用作类型擦除过程的一部分。这意味着桥方法需要作为类型安全接口。

例如，在下面的示例中，以 `Object` 为参数的 `compare()` 方法表现为桥接方法。它会将 `Object` 转换为 `String`，并调用以 `String` 为参数的比较函数。所以 `compare(Object a, Object b)` 在源（调用 `compare()` 的方法）和目标（`compare(String, String)`）之间起桥梁作用。

**示例：**

```java
public class compareValues implements Comparator {

    // target method
    public int compare(String a, String b) {
    }

    // bridge method
    public int compare(Object a, Object b) {
        return compare((String) a, (String) b);
    }
}
```

**语法：**

```java
public boolean isBridge()
```

**返回值：** 如果方法对象是 JVM 规范定义的桥方法，该方法返回 `true`，否则返回 `false`。

下面的程序说明了 `Method` 类的 `isBridge()` 方法：

**程序 1：** 程序返回 `BigInteger` 类的所有桥方法。

**解释：** 在这个方法中，首先创建一个 `BigInteger` 类对象。创建对象后，通过调用类对象的 `getMethods()` 创建 `Method` 对象列表。现在，对提取的方法列表进行迭代，并检查 `isBridge()`。因此我们得到桥方法。最后打印桥接方法名称。

```java
/*
 * Program Demonstrate isBridge() method
 * of Method Class.
 */
import java.lang.reflect.Method;
import java.math.BigInteger;
public class GFG {

    // create main method
    public static void main(String args[]) {
        try {
            // create BigInteger class object
            Class bigInt = BigInteger.class;

            // get list of Method object
            Method[] methods = bigInt.getMethods();

            System.out.println("Bridge Methods of BigInteger Class are");

            // Loop through Methods list
            for (Method m : methods) {
                // check whether the method is Bridge Method or not
                if (m.isBridge()) {
                    // Print Method name
                    System.out.println("Method: " + m.getName());
                }
            }
        } catch (Exception e) {
            // print Exception is any Exception occurs
            e.printStackTrace();
        }
    }
}
```

**输出：**

```java
Bridge Methods of BigInteger Class are
Method: compareTo
```

**程序 2：** 检查自定义方法是否是 `isBridge()`。

**解释：** 当子类从父类继承方法时，继承的方法充当桥接方法。在这段代码中，首先创建一个包含 `draw` 方法的 `Shape` 类，然后创建一个扩展 `Shape` 类的 `Rectangle` 类。在主方法中，创建了 `Rectangle` 类 `draw` 方法的 `Method` 对象。现在检查它是否是 `isBridge()` 方法。最后打印结果。

```java
// Program Demonstrate isBridge() method
// of Method Class.
// In this program a custom bridge method is created
// and by use of isBridge(), checked for Bridge Method

import java.lang.reflect.Method;

public class GFG {

    // create class
    protected class Shape {
        public void draw() {}
    }

    // create a class which extends Shape class
    public class Rectangle extends Shape {
    }

    // create main method
    public static void main(String args[]) {
        try {
            // create class object for class
            // Rectangle and get method object
            Method m = Rectangle.class.getDeclaredMethod("draw");

            // check method is bridge or not
            boolean isBridge = m.isBridge();

            // print result
            System.out.println(m + " method is Bridge Method :"
                               + isBridge);
        } catch (NoSuchMethodException | SecurityException e) {
            // Print Exception if any Exception occurs
            e.printStackTrace();
        }
    }
}
```

**输出：**

```java
public void GFG$Rectangle.draw() method is Bridge Method :true
```

**参考：**
- [`https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#isBridge--`](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#isBridge--)
- [`https://stackoverflow.com/questions/5007357/java-generics-bridge-method`](https://stackoverflow.com/questions/5007357/java-generics-bridge-method)
- [`http://stas-blogspot.blogspot.com/2010/03/java-bridge-methods-explained.html`](http://stas-blogspot.blogspot.com/2010/03/java-bridge-methods-explained.html)