# Java 互操作性——从 Kotlin 调用 Java

> 原文：[https://www.geeksforgeeks.org/java-interoperability-calling-java-from-kotlin/](https://www.geeksforgeeks.org/java-interoperability-calling-java-from-kotlin/)

因为开发 Kotlin 时考虑到了与 [Java](https://www.geeksforgeeks.org/java/) 的互操作性。它使得从内部使用 Java 代码变得更加容易。一个 Kotlin [类](https://www.geeksforgeeks.org/kotlin-class-and-objects/)或者一个[函数](https://www.geeksforgeeks.org/kotlin-functions/)可以简单的引用 [Java 类](https://www.geeksforgeeks.org/classes-objects-java/)及其方法。

## Java 中的获取器和设置器

Java 类中定义的所有类型的 getters 和 setters 在 Kotlin 中表示为属性。因此，要访问 Java 类的数据成员的获取器和设置器，它必须作为属性在 Kotlin 中引用。

**Java 文件声明为 `myjava.java`**

```java
// Java class
public class myjava {
  private int value;
  public int getValue(){
       return value;
  }
  public void setValue(int value){
       this.value = value;
  }
}
```

**Kotlin 文件声明为 `mykotlin.kt`**

```kt
// Kotlin file
fun main(){
   val obj = myjava()
   obj.value = 5 // This will call the setter function
   println(obj.value) // This will call the getter function
}
```

**输出：**

```kt

```

## 方法

从 Kotlin 内部调用 Java 方法是一个简单的概念。在 Java 和 Kotlin 中，要提供的参数类型是相同的，函数的返回类型也是如此。此规则的唯一例外是 `void` 返回类型。Java 中那些有 `void` 返回类型的函数，在 Kotlin 中返回一个 `Unit` 类型。因此，该值可以存储在 Kotlin 中，因为 `Unit` 作为一种类型存在。

**Java 文件声明为 `myjava.java`**

```java
// Java code
public class myjava {
    public int add(int a, int b){
        return a+b;
    }
}
```

**Kotlin 文件声明为 `mykotlin.kt`**

```kt
// Kotlin file
fun main(args: Array<String>) {
    val obj = myjava()
    val ans = obj.add(4, 5)
    println("The sum of two numbers is "+ans)
}
```

**输出：**

```kt
The sum of two numbers is 9
```

**注意：** Kotlin 的一些关键字在 Java 中很容易被用作有效的标识符。例如——`any`、`sealed`、`object` 等。如果碰巧是这种情况，那么在 Kotlin 中使用标识符，用一个倒勾字符(`)将它们括起来。
例如，如果一个 Java 类 `XYZ` 恰好有一个名为 `any` 的方法，那么这个方法可以在 Kotlin 中调用为：

```kt
obj.`any`() // obj is the instance of the class XYZ
```

## 静态成员

Java 中一个类的静态成员变成了 Kotlin 中一个伴随对象的成员。但是，这些伴随对象不能直接在表达式中使用。要访问其成员，使用 Java 中定义的成员的完全限定名。

**Java 文件声明为 `myjava.java`**

```java
// Java Code
package mypackage;
    public class myjava {
    public static void display() {
        System.out.println("Call successful")
    }
}
```

**Kotlin 文件声明为 `mykotlin.kt`**

```kt
// declare kotlin package
package myktpackage
// import java class using java package
import mypackage.myjava 

fun main(args: Array<String>) {
    // calling static member of java class
    val str = myjava.display()
    println(str)
}
```

**输出：**

```kt
Call successful
```

## Java 数组

Kotlin 支持一种**不可变**形式的数组，即特定类型的数组不能赋给 Kotlin 中任何类型的数组，这与可以赋给 `Object` 类型数组的 Java 数组不同。
另外，Kotlin 不支持将子类类型的数组分配给超类类型的数组。
现在，由于 Kotlin 不提供基元类型的数组，所以它提供了几个专门的类来表示 Java 中基元类型的数组。这些类与 `Array` 类没有任何关系，为了获得最佳性能，它们被编译成基本的 Java 数组。无论数组的使用方式如何，这种到字节码的转换都不会引入额外的开销。

**Java 文件声明为 `myjava.java`**

```java
// Java Code
public class myjava {
    int result = 0;
    public int compute(int[] array)
    {
        for(int a: array){
            result = result + a;
        }
        return result;
    }
}
```

**Kotlin 文件声明为 `mykotlin.kt`**

```kt
// Kotlin code
fun main(args: Array<String>) {
    // Kotlin code
    val obj = myjava()
    val array = intArrayOf(1, 2, 3, 4, 5, 6)
    var sum = obj.compute(array)
    println("The sum of an array is "+sum)
}
```

**输出：**

```kt
The sum of an array is 21
```

## Java varargs

Java 支持函数中变长参数的概念，即当一个函数的参数数量事先未知，但其类型已知时，我们声明一个 `varargs` 参数。Kotlin 不提供 `varargs` 参数，但是，要想在 Java 中完全运行，它支持一个特殊的扩展运算符(`*`)来调用具有 `varargs` 参数的函数。

**Java 文件声明为 `myjava.java`**

```java
// Java code
public class myjava {
    public void myfunc(String str,int... numbers) {
        System.out.println("Passed string is " + str);
        for (int n : numbers) {
            System.out.print(" "+n);
        }
    }
}
```

**Kotlin 文件声明为 `mykotlin.kt`**

```kt
// Kotlin code
fun main(args: Array<String>) {
    val obj = myjava()
    val array = intArrayOf(10, 20, 30)
    obj.myfunc("Geeks", *array)
}
```

**输出：**

```kt
Passed string is Geeks
 10 20 30
```

## Java 和 Kotlin 映射类型

Kotlin 中的类型不同于 Java 中的类型。然而，为了保持互操作性，Kotlin 提供了从 Java 类型到 Kotlin 类型的映射。这种映射发生在编译时，并且没有观察到运行时性能的显著变化。

**Java 原语类型映射到以下原语类型：**

| **Java 类型** | **Kotlin 类型** |
| :--- | :--- |
| `byte` | `kotlin.Byte` |
| `short` | `kotlin.Short` |
| `int` | `kotlin.Int` |
| `long` | `kotlin.Long` |
| `char` | `kotlin.Char` |
| `float` | `kotlin.Float` |
| `double` | `kotlin.Double` |
| `boolean` | `kotlin.Boolean` |

**`java.lang` 包中定义的一些内置类也映射到了 Kotlin 类。**

| **Java 类型** | **Kotlin 类型** |
| :--- | :--- |
| `java.lang.Object` | `kotlin.Any!` |
| `java.lang.Cloneable` | `kotlin.Cloneable!` |
| `java.lang.Comparable` | `kotlin.Comparable!` |
| `java.lang.Enum` | `kotlin.Enum!` |
| `java.lang.annotation.Annotation` | `kotlin.Annotation!` |
| `java.lang.CharSequence` | `kotlin.CharSequence!` |
| `java.lang.String` | `kotlin.String!` |
| `java.lang.Number` | `kotlin.Number!` |
| `java.lang.Throwable` | `kotlin.Throwable!` |

**Java 原语数据类型的装箱类型被映射到 Kotlin 中的可空类型。**

| **Java 类型** | **Kotlin 类型** |
| :--- | :--- |
| `java.lang.Byte` | `kotlin.Byte?` |
| `java.lang.Short` | `kotlin.Short?` |
| `java.lang.Integer` | `kotlin.Int?` |
| `java.lang.Long` | `kotlin.Long?` |
| `java.lang.Character` | `kotlin.Char?` |
| `java.lang.Float` | `kotlin.Float?` |
| `java.lang.Double` | `kotlin.Double?` |
| `java.lang.Boolean` | `kotlin.Boolean?` |