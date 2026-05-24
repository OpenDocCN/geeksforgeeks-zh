# Scala |注释

> 原文:[https://www.geeksforgeeks.org/scala-annotation/](https://www.geeksforgeeks.org/scala-annotation/)

Scala 注释是添加到程序源代码中的元数据。任何类型的定义或声明都允许注释，包括 val、vars、类、对象、特征、def 和类型。注释用于将元信息与定义相关联。
**语法:**

> @annot(exp_{1}、exp_{2}、…) {val name_{1}=const_{1}、…、val name_{n}=const_{n}}

所有注释都必须包含“annot”，因为它指定了注释类。没有参数的注释使用空的()。

**Predefined Annotations in Scala**

scala 中的预定义注释是内置的 Scala 注释，它将元信息与定义相关联。一些预定义的 scala 注释包括:

1.  **Java 平台注释:**
    *   **@transient:** 用于将字段标记为非持久。
    *   **@volatile:** 用于标记一个可以在程序控制之外改变其值的字段。
    *   **@SerialVersionUID():** 它将一个串行版本标识符(一个长常量)附加到一个类上。
        T3】例:

```scala
private final static SerialVersionUID = < longlit >

```

*   **Java bean 注释:**
    *   **@ Scala . beans . bean property:**这个注释，当前缀到某个变量 X 的定义时，会导致 Java bean 样式的 getter 和 setter 方法 getX、setX 被添加到包含该变量的类中。使用 get 或 set 后，变量的第一个字母看起来是大写的。
    *   **@ Scala . beans . booleanbeanproperty:**这个注释相当于 scala.reflect.BeanProperty，但是生成的 getter 方法的名字是 isX 而不是 getX。*   **折旧注释:**
    *   **@deprecated(message: , since: ):** This annotation is used to mark a definition as deprecated. Deprecated warnings are suppressed in code that belongs itself to a definition that is labeled deprecated.
        **Syntax:**

        ```scala
        @deprecated("deprecation message", "release # which deprecates method")

        ```

        **示例:**

        ```scala
        // Scala program of Deprecation Annotations
        import scala.deprecated;

        // Creating object
        object GFG
        {
            // Main method
            def main(args: Array[String])
            {
                // Define Deprecation Annotations:
                @deprecated def printMessage() = 
                {
                    println("This method is deprecated")
                }

                printMessage()
            }
        }
        ```

        **输出:**

        ```scala
        This method is deprecated
        ```

        *   **Scala 编译器注释:**
    *   **@uncheckedStable:** This annotation when applied to a value declaration or definition, allows the defined value to appear in a path, even if its type is volatile.
        **Syntax:**

        ```scala
         @annotation.unchecked.uncheckedStable val x: A with B = null

        ```

        **示例:**

        ```scala
        // Scala program of uncheckedStable
        // Compiler Annotations
        import scala.deprecated;

        // Creating object
        object GFG
        {
            // Main method
            def main(args: Array[String])
            {
                trait A 
                { 
                    type T = Int
                }
                trait B 
                { 
                    type T <: String 
                }
                def f(b: B)(t: b.T) = t.length

                // Define Compiler Annotations
                @annotation.unchecked.uncheckedStable val x: A with B = null

                // legal because x is A
                val y: x.T = 0 

                f(x)(y)
            }
        }
        ```

        **输出:**

        > Java . lang . class castexception:Java . lang . integer 不能强制转换为 java.lang.String

    *   **@tailrec:**This annotation ensures that a method is tail-recursive. Tail-recursion can keep memory requirements constant.
        **Syntax:**

        ```scala
         @tailrec

        ```

        **示例:**

        ```scala
        // Scala program of Compiler Annotations 
        // of tail recursion
        import scala.annotation.tailrec

        // Creating object
        object GFG
        {
            // Main method
            def main(args: Array[String])
            {
                // Define factorial method
                def factorial(x: Int): Int = 
                {
                    // Compiler Annotations of tail recursion
                    @tailrec
                    def factorialHelper(x: Int, accumulator: Int): Int = 
                    {
                        if (x == 1) accumulator 
                        else factorialHelper(x - 1, accumulator * x)
                    }
                    factorialHelper(x, 1)
                }
                println(factorial(5))
            }
        }
        ```

        **输出:**

        ```scala
        120
        ```

        **User-defined Annotations in Scala**

用户定义的注释将元信息与定义相关联。对于一个类，类文件保存了一个注释类实例，该类继承了 Scala.ClassfileAnnotation 的特性。对于我们访问注释符号的每个编译单元，这些实例对 Scala 类型检查器都是可见的，而类继承了 scala.StaticAnnotation 的特性。
**语法:**

```scala
// needed for @Documented
import java.lang.annotation.*;

@Documented
public @interface impure {}

```