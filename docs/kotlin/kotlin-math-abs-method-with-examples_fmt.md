# Kotlin | Math.abs()方法举例

> 原文: [https://www.geeksforgeeks.org/kotlin-math-abs-method-with-examples/](https://www.geeksforgeeks.org/kotlin-math-abs-method-with-examples/)

函数的作用是: 返回给定参数的绝对值。如果参数是非负数，则返回参数本身。反之，如果参数为负，则返回其否定值。基本上，它作为数学中的`模数`函数。

> **语法:** `abs(x : DataType) : DataType`
>
> **参数:** 可以取数据类型`int`、`double`、`long`、`float`的值。
>
> **返回:** 返回参数的绝对值，不改变数据类型。
>
> **异常:**
>
> *   如果参数是`NaN`，结果就是`NaN`。
> *   如果参数是`Int.MIN_VALUE`，结果是相同的值，`Int.MIN_VALUE`，为负。
> *   如果参数是`Long.MIN_VALUE`，结果是相同的值，`Long.MIN_VALUE`，为负。

**代码#1:** 以浮点和双数据类型为参数。

```kt
// Kotlin program to illustrate
// working of Math.abs() method
import kotlin.math.abs

fun main(args : Array<String>){

val f = -45.23f;
    val d = 999.32;

// abs() function taking float as input
    println(abs(f));

// abs() function taking double as input
    println(abs(d));
}
```

**输出:**

```kt
45.23
999.32
```

**代码#2:** 以`int`和`long`数据类型为参数。

```kt
// Kotlin program to illustrate
// working of Math.abs() method
import kotlin.math.abs

fun main(args : Array<String>){

val i = -0;
    val l = -69973688;

// abs() function taking int as input
    println(abs(i));
    println(abs(Int.MIN_VALUE));

// abs() function taking long as input
    println(abs(l));
    println(abs(Long.MIN_VALUE));
}
```

**输出:**

```kt

```