# Scala |数组

> 原文:[https://www.geeksforgeeks.org/scala-arrays/](https://www.geeksforgeeks.org/scala-arrays/)

数组是 scala 中一种特殊的集合。它是一种固定大小的数据结构，存储相同数据类型的元素。数组的第一个元素的索引是零，最后一个元素是元素总数减一。它是可变值的集合。它对应于 java 中的数组(就语法而言)，但同时它又不同于 java(就功能而言)。

**一些要点:**

*   Scala 数组可以是通用的。这意味着我们可以有一个数组，其中 T 是类型参数或抽象类型。
*   Scala 数组与 Scala 序列兼容——我们可以在需要序列的地方传递一个数组。
*   Scala 数组也支持所有的序列操作。

下图显示了如何按顺序将值存储在数组中:
[![Arrays](img/8cb539709f616ce76d2904a850a3c608.png)](https://media.geeksforgeeks.org/wp-content/uploads/Arrays1.png)

Scala 支持一维数组和多维数组。一维数组是一个只有一行 n 列的数组，而二维数组实际上是一个维度矩阵(n * m)。

**One Dimensional Array**

在这个数组中只包含一行用于存储值。该数组的所有值从 0 到数组大小连续存储。
**语法:**

```scala
var arrayname = new Array[datatype](size)
```

在这里，数据类型指定要分配的数据类型，大小指定数组中的元素数量，var 是链接到数组的数组变量的名称。
**例:**

```scala
// Scala program to creating an array 
// of the string as week days, store  
// day values in the weekdays, 
// and prints each value. 
object GFG
{
    // Main method
    def main(args: Array[String]) 
    {
        // allocating memory of 1D Array of string. 
        var days = Array("Sunday", "Monday", "Tuesday", 
                    "Wednesday", "Thursday", "Friday",
                    "Saturday" )

        println("Array elements are : ")
        for ( m1 <-days )
        {
            println(m1 )
        }

    }
}
```

**Output:**

```scala
Array elements are : 
Sunday
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday

```

在这里，我们创建了一个数组来存储一周中的日子，并打印所有的日子。

**Basic Operation On An Array**

1.  **Accessing array elements:**
    **Example:**

    ```scala
    // Scala program to accessing an array 
    // of the string as name.
    object GFG
    {
        // Main method
        def main(args: Array[String]) 
        {
            // allocating memory of 1D Array of string. 
            var name = Array("gfg", "geeks", "GeeksQuize", 
                        "geeksforgeeks" )

            println("second element of an array is: ")

            // Accessing an array element
            println(name(1) )
        }
    }
    ```

    **输出:**

    ```scala
    second element of an array is: 
    geeks
    ```

2.  **Updating an element in array:**
    **Example:**

    ```scala
    // Scala program to updating an array 
    // of the string as name.
    object GFG
    {
        // Main method
        def main(args: Array[String]) 
        {
            // allocating memory of 1D Array of string. 
            var name = Array("gfg", "geeks", "GeeksQuize", 
                        "geeksforgeeks" )

            // Updating anelement in an array             
            name(1)="employee"
            println("After updation array elements are: ")

            for ( m1 <-name )
            {
                println(m1 )
            }
        }
    }
    ```

    **输出:**

    ```scala
    After updation array elements are: 
    gfg
    employee
    GeeksQuize
    geeksforgeeks
    ```

3.  **在数组中添加元素:**
    **示例:**

```scala
// Scala program to adding elements in an array 
// of the string as name.
object GFG
{
    // Main method
    def main(args: Array[String]) 
    {
        var name = new Array[String](4)

        // Adding element in an array 
        name(0)="gfg"
        name(1)="geeks"
        name(2)="GeeksQuize"
        name(3)="geeksforgeeks"
        println("After adding array elements : ")

        for ( m1 <-name )
        {
            println(m1 )
        }

    }
}
```

**输出:**

```scala
After adding array elements : 
gfg
geeks
GeeksQuize
geeksforgeeks
```

9.  **Concatenate Arrays:**
    We can concatenate two arrays by using concat() method. In concat() method we can pass more than one array as arguments.
    **Example:**

    ```scala
    // Scala program to concatenate two array 
    // by using concat() method
    import Array._

    // Creating object
    object GFG
    {

        // Main method
    def main(args: Array[String])
    {
        var arr1 = Array(1, 2, 3, 4)
        var arr2 = Array(5, 6, 7, 8)

        var arr3 = concat( arr1, arr2)

        // Print all the array elements
        for ( x <- arr3 ) 
        {
            println( x )
        }
    }
    }
    ```

    **输出:**

    ```scala
    1
    2
    3
    4
    5
    6
    7
    8
    ```

    这里，arr1 是一个由四个元素组成的数组，arr2 是另一个由四个元素组成的数组。

**Multidimensional Arrays**

多维数组包含多行来存储值。Scala 有一个方法 *Array.ofDim* 在 Scala 中创建[多维数组。在像矩阵和表格这样的结构中，可以使用多维数组。
**语法:**](https://www.geeksforgeeks.org/multidimensional-arrays-in-scala/)

```scala
var array_name = Array.ofDim[ArrayType](N, M)
 or  
var array_name = Array(Array(elements), Array(elements)
```

这是一个二维数组。这里 N 是行数，M 是列数。

**示例:**

```scala
// Scala program to creating a 
// multidimension array of the 
// string as names, store  
// values in the names, 
// and prints each value. 
object GFG
{
    // Main method
    def main(args:Array[String]) 
    {
        val rows = 2
        val cols = 3

        // Declaring Multidimension array
        val names = Array.ofDim[String](rows, cols)

        // Allocating values
        names(0)(0) = "gfg"
        names(0)(1) = "Geeks"
        names(0)(2) = "GeeksQuize"
        names(1)(0) = "GeeksForGeeks"
        names(1)(1) = "Employee"
        names(1)(2) = "Author"
        for
        {
            i <- 0 until rows
            j <- 0 until cols
        }

        // Printing values
        println(s"($i)($j) = ${names(i)(j)}")
    }
}
```

**Output:**

```scala
(0)(0) = gfg
(0)(1) = Geeks
(0)(2) = GeeksQuize
(1)(0) = GeeksForGeeks
(1)(1) = Employee
(1)(2) = Author

```

**Append and Prepend elements to an Array in Scala**

将结果赋给新变量时，使用这些运算符(方法)将元素追加到数组中并在数组前添加元素:

| 方法 | 功能 | 例子 |
| --- | --- | --- |
| :+ | 追加 1 个项目 | old_array :+ e |
| ++ | 追加 N 个项目 | old_array ++ new_array |
| +: | 前置 1 个项目 | e +:旧数组 |
| ++: | 前置 N 个项目 | new_array ++: old_array |

示例显示如何使用上述方法向数组追加和预先添加元素:

```scala
object GFG
{

  // Main method
  def main(args: Array[String])
  {

    // Declaring an array
    val a = Array(45, 52, 61) 
    println("Array a ")
    for ( x <- a ) 
    {
      println( x )
    }

    // Appending 1 item
    val b = a :+ 27 
    println("Array b ")
    for ( x <- b ) 
    {
      println( x )
    }

    // Appending 2 item
    val c = b ++ Array(1, 2)
    println("Array c ")
    for ( x <- c ) 
    {
       println( x )
    }

    // Prepending 1 item
    val d = 3 +: c 
    println("Array d ")
    for ( x <- d ) 
    {
      println( x )
    }

    // Prepending 2 item
    println("Array e ")
    val e = Array(10, 25) ++: d
    for ( x <- e ) 
    {
      println( x )
    }
  }
}
```

输出:

```scala
Array a 
45
52
61
Array b 
45
52
61
27
Array c 
45
52
61
27
1
2
Array d 
3
45
52
61
27
1
2
Array e 
10
25
3
45
52
61
27
1
2

```