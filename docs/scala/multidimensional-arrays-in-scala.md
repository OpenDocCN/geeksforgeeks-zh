# Scala 中的多维数组

> 原文:[https://www . geesforgeks . org/多维数组-in-scala/](https://www.geeksforgeeks.org/multidimensional-arrays-in-scala/)

**多维数组**基本上是以*矩阵格式*存储数据的数组。对于矩阵和表格，我们需要多维数组。我们可以用**阵**和**阵**的方法创建多维阵。

**语法**

> val Array name = Array . ofdim[data _ type](行数、列数)
> 或
> var arrayname = Array(Array(元素)，Array(元素))

**多维数组通过使用 Array.ofDim**
Scala 有一个方法 *Array.ofDim* 来创建多维数组。这种方法可以用来创建多达五个维度的数组。我们需要知道创建时的行数和列数。声明数组后，我们向其中添加元素。
**示例:**

```scala
// Scala Program of Multidimensional array 
// using Array.ofDim
object MultiArr
{
    def main(args: Array[String])
    {
        //creating the array of 2 rows and 2 columns
        val mymultiarr= Array.ofDim[Int](2, 2) 

        //Assigning the values
        mymultiarr(0)(0) = 2                 
        mymultiarr(0)(1) = 7
        mymultiarr(1)(0) = 3
        mymultiarr(1)(1) = 4

        for(i<-0 to 1; j<-0 until 2)
        {
            print(i, j)

           //Accessing the elements
           println("=" + mymultiarr(i)(j))     
        }
    }
}
```

**输出**

```scala
(0,0)=2
(0,1)=7
(1,0)=3
(1,1)=4
```

**多维数组通过使用数组的数组**
这给了过程更多的控制，并让我们创建“参差不齐”的数组(其中每个包含的数组可能大小不同)。我们也可以使用*数组*来创建多维数组。在下面的例子中，我们使用数组的数组创建了一个多维数组。

**示例:**

```scala
// Scala Program of Multidimensional array 
// using Array of Array
object MultiArr
{
    def main(args: Array[String])
    {
        // Creating and assigning the values 
        // to the array
        var arr= Array(Array(0, 2, 4, 6, 8),
                    Array(1, 3, 5, 7, 9)) 

        for(i<-0 to 1)
        {
            for(j<- 0 to 4)
            {
                // Accessing the values
                print(" "+arr(i)(j)) 
            }
            println()
        }
    }
}
```

**输出:**

```scala
 0 2 4 6 8
 1 3 5 7 9
```

现在，让我们考虑一个用(行，列)
**显示元素的示例:**

```scala
// Scala Program of Multidimensional array 
// using Array of Array
object Mad
{
    def main(args: Array[String])
    {

        // Creating and assigning the values to the array
        var arr= Array(Array(0, 2, 4, 6, 8), 
                    Array(1, 3, 5, 7, 9)) 

        for(i<-0 to 1; j<-0 until 5)
        {
            print(i, j)

            //Accessing the elements
            println("=" + arr(i)(j)) 
        }
    }
}
```

**输出:**

```scala
(0,0)=0
(0,1)=2
(0,2)=4
(0,3)=6
(0,4)=8
(1,0)=1
(1,1)=3
(1,2)=5
(1,3)=7
(1,4)=9
```