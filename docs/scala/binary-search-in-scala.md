# 斯卡拉的二分搜索法

> 原文:[https://www.geeksforgeeks.org/binary-search-in-scala/](https://www.geeksforgeeks.org/binary-search-in-scala/)

二分搜索法是一种算法，可以帮助我们在 O(log n)时间内找到排序数组中的元素。它的算法基于分而治之的原则，只有在对可用数据进行排序时才起作用。
现在，当我们使用二分搜索法时出现三种情况:

1.  如果中间元素是要搜索的元素，我们返回中间元素的索引。
2.  如果中间元素比要搜索的元素小，我们以同样的方式在右边的子数组中搜索(从中间到结尾)(获取新的中间元素，并再次检查所有三种情况)。我们在右边的子数组中搜索，因为数据是排序的，因此中间元素之前的所有元素也将小于或等于中间元素。
3.  如果中间元素大于要搜索的元素，我们在左边的子数组中搜索(从开始到中间)。

这个过程一直持续到我们找到要搜索的元素或者子数组的大小减小到零。

示例:
![Binary Search in Scala](img/a1049b4b13d044a8c0247795694d728b.png)

在 Scala 中有三种方法来表现二分搜索法。

### 递归方法

在递归方法中，我们递归调用已实现的具有更新的开始和结束值的二分搜索法算法，直到我们将中间元素与要搜索的元素匹配或者数组大小减小到零。下面是 Scala 中二分搜索法递归方法的代码。

```scala
// Scala code for Recursive Binary Search

// Creating object
object GFG{

// Creating a recursive  Binary Search function
def RecursiveBinarySearch(arr: Array[Int],
                          Element_to_Search: Int)
                         (low: Int = 0,
                          high: Int = arr.length - 1): Int = 
{

    // If element not found                               
    if (low > high) 
        return -1

    // Getting the middle element
    var middle = low + (high - low) / 2

    // If element found
    if (arr(middle) == Element_to_Search)
        return middle

    // Searching in the left half
    else if (arr(middle) > Element_to_Search)
        return RecursiveBinarySearch(arr, 
               Element_to_Search)(low, middle - 1)

    // Searching in the right half
    else
        return RecursiveBinarySearch(arr, 
               Element_to_Search)(middle + 1, high)
}

// Creating main function
def main(args: Array[String]){

    // Calling the binary search function and
    // storing its result in index variable
    var index = RecursiveBinarySearch(Array(1, 2, 3, 4, 55, 
                                            65, 75), 4)(0, 6);

    // If value not found 
    if(index == -1)
       print("Not Found")

    // Else print the index where 
    // the value is found
    else
       print("Element found at Index " + index)
}
}
```

**输出**

```scala
Element found at Index 3
```

### 迭代方法

在迭代方法中，我们运行 while 循环，直到找到要搜索的元素或者数组大小减小到零。下面是 Scala 中二分搜索法迭代方法的代码。

```scala
// Scala code for Iterative Binary Search

// Creating object
object GFG{

// Creating Binary Search function
// Accepting the passed array and 
// element to be searched
def IterativeBinarySearch(arr: Array[Int], 
                          Element_to_Search: Int): Int =
{

    // Creating start variable to
    // point to the first value
    var low = 0

    // Creating end variable to 
    // point to the last value
    var high = arr.length - 1

    // Finding the value in the 
    // array iteratively
    while (low <= high)
    {

        // Getting middle element    
        var middle = low + (high - low) / 2

        // If element found in the middle index
        if (arr(middle) == Element_to_Search)
            return middle

        // Searching in the first half
        else if (arr(middle) > Element_to_Search)
            high = middle - 1

        // Searching in the second half  
        else
            low = middle + 1
    }

    // If value not found in the 
    // entire array , return -1 
    -1
}

// Creating main function
def main(args: Array[String])
{

    // Calling the binary search function and
    // storing its result in index variable
    var index = IterativeBinarySearch(Array(1, 2, 3, 4, 55,
                                            65, 75), 65);

    // If value not found 
    if(index == -1)
       print("Not Found")

    // Else print the index where 
    // the value is found
    else
       print("Element found at Index " + index)
}
}
```

<**输出**

```scala
Element found at Index 5
```

### 模式匹配和函数式编程方法

在这种情况下，我们首先将中间元素与要搜索的元素进行匹配。如果元素存在，我们返回它的索引。否则，我们继续用更新的参数调用创建的函数。下面是该方法的代码:

```scala
// Scala code for Iterative Binary Search

// Creating object
object GFG{

// Using the functional programming approach
def FunctionalBinarySearch(arr: Array[Int], 
                           Element_to_Search: Int): Int =
{ 
    def BinarySearch(arr: Array[Int],
                     Element_to_Search: Int, 
                     low: Int, high: Int): Int =
    {

        // If element not found
        if (low > high)
            return -1

        // Getting middle index
        var middle = low + (high - low) / 2

        // Pattern matching
        arr match
        {

            // If element found , return the index
            case(arr:Array[Int]) if (arr(middle) ==
                                     Element_to_Search) => 
                                     middle 

            // Call the function for the second half
            case(arr:Array[Int]) if (arr(middle) < 
                                     Element_to_Search) => 
                                     BinarySearch(arr, 
                                     Element_to_Search,
                                     middle + 1, high)

            // Call the function for the first half 
            case(arr:Array[Int]) if (arr(middle) > 
                                     Element_to_Search) => 
                                     BinarySearch(arr, 
                                     Element_to_Search,
                                     low, middle - 1)
        }
    } 

    // Calling the Binary Search function
    BinarySearch(arr, Element_to_Search, 0, arr.length - 1)
}

// Creating main function
def main(args: Array[String]){

    // Calling the binary search function and 
    // storing its result in index variable
    var index = FunctionalBinarySearch(Array(1, 2, 3, 4, 55,
                                             65, 75), 44);

    // If value not found 
    if(index == -1)
    print("Element not found")

    // Else print the index where 
    // the value is found
    else
    print("Element found at Index " + index)
}
}
```

**输出**

```scala
Element not found

```