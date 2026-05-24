# 横向线刻度| Set-3

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-traversal-set-3/

**先决条件:**
[Scala 特质可穿越| Set-1](https://www.geeksforgeeks.org/scala-trait-traversable-set-1/)
[Scala 特质可穿越| Set-2](https://www.geeksforgeeks.org/scala-trait-traversable-set-2/)
建议在此 Set 之前查看(Set-1，Set-2)。
操作如下:

*   **Sub-Collection retrieval operations:**
    The operations here are *slice, drop, dropWhile, filter, filterNot, tail, take, takeWhile, and init*. These operations are utilized to return some sub collection.
    **Example :**

    ```scala
    // Scala program of Sub-Collection
    // retrieval operation

    // Creating object 
    object SubCollection
    {

        // Main method
        def main(args: Array[String]) 
        {

            // Creating List of numbers 
            val x = List(17, 19, 21, 29, 31)

            // Applying Sub-Collection 
            // retrieval operation
            val y = x.init 

            // Displays all the elements of 
            // the List except the last one
            println(y)
        }
    }
    ```

    **Output:**

    ```scala
    List(17, 19, 21, 29)

    ```

    这里， *init* 检索可遍历集合中除最后一个元素之外的所有元素。
    T3】例:

    ```scala
    // Scala program of Sub-Collection
    // retrieval operation

    // Creating object 
    object SubCollection
    {

        // Main method
        def main(args: Array[String]) 
        {

            // Creating List of numbers 
            val x = List(17, 19, 21, 29, 31)

            // Applying Sub-Collection 
            // retrieval operation
            val y = x.tail

            // Displays all the elements of 
            // the List except the first one
            println(y)
        }
    }
    ```

    **Output:**

    ```scala
    List(19, 21, 29, 31)

    ```