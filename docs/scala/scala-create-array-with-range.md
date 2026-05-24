# Scala |创建带范围的数组

> 原文:[https://www . geesforgeks . org/Scala-create-array-with-range/](https://www.geeksforgeeks.org/scala-create-array-with-range/)

[阵](https://www.geeksforgeeks.org/scala-arrays/)是 Scala 中一种特殊的集合。它是一种固定大小的数据结构，存储相同数据类型的元素。通过使用 **`range()`** 方法生成包含给定范围内递增整数序列的数组。我们可以使用 final 参数作为跳转来创建序列。如果我们不使用 final 参数，那么 jump 将被假定为 1。

下面是一些带范围的数组示例:

**例:**

```scala
// Scala program to create array with range 
import Array._

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String]) 
    {
        var array1 = range(1, 15)
        var array2 = range(1, 15, 3)

        // Print all the elements of array1
        for ( i <- array1 ) 
        {
            print( " " + i )
        }

        println()

        // Print all the elements of array2
        for ( i <- array2 ) 
        {
            print( " " + i )
        }
    }
}
```

**输出:**

```scala
1 2 3 4 5 6 7 8 9 10 11 12 13 14
 1 4 7 10 13

```

在上例中，数组的范围 *(1，15)* 。在这个范围内没有给出差值，所以默认范围的差值将是 **1** 元素。数组中的元素是 1、4、7、10 和 13。在这里，我们正在创建一个系列 *(1，15，3)* 。也就是说一个数组的元素在 **1** 和 **15** 之间，范围差为 **3** 。数组中的元素是 1、2、3、4、5、6、7、8、9、10、11、12、13 和 14。

对于一些集合，如列表和数组，我们也可以创建一个范围，并将其转换为所需的序列:REPL 显示了可以直接从范围创建的数组是**到数组**。我们还可以使用一个范围来创建如下的字符序列:

**例:**

```scala
// Scala program to create array with range 
import Array._

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String]) 
    {
        val array1 = ('A' to 'F').toArray
        val array2 = ('a' to 'f').by(2).toArray

        // Print all the elements of array1
        for ( i <- array1 ) 
        {
            print( " " + i )
        }

        println()

        // Print all the elements of array2
        for ( i <- array2 ) 
        {
            print( " " + i )
        }
    }
}
```

**输出:**

```scala
A B C D E F
 a c e

```

在上面的例子中，数组的范围*(“A”到“F”)。toArray* 。在这种情况下，没有给出范围差，因此默认范围差为 1 个字符。数组中的字符是 A、B、C、D、E 和 f。这里，我们正在创建一个范围为*(“A”到“f”)的数组。by(2)。toArray* 。也就是说一个字符在 **a** 和 **f** 之间的数组，范围差为 **2** 。数组中的字符是 a、c 和 e。