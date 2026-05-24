# 横向线刻度| Set-4

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-traviable-set-4/

先决条件:-
[Scala 特质可穿越| Set-1](https://www.geeksforgeeks.org/scala-trait-traversable-set-1/)
[Scala 特质可穿越| Set-2](https://www.geeksforgeeks.org/scala-trait-traversable-set-2/)
[Scala 特质可穿越| Set-3](https://www.geeksforgeeks.org/scala-trait-traversable-set-3/)
建议在此之前查看 Set-1、Set2、Set-3。
操作如下:

*   **Folds:**
    The operations here are *reduceRight, reduceLeft, /: or foldLeft, :\ or foldRight*. This methods apply binary operation to the successive elements of the Traversable collection.
    **Example :**

    ```scala
    // Scala program for operations
    // of Folds

    // Creating object 
    object Folds
    {

        // Main method
        def main(args: Array[String]) 
        {

            // Creating List of numbers 
            val x = List(8, 6, 4, 2)

            // Applying method of
            // Folds
            // val y = x.foldLeft(0)(_ - _) or
            val y = (0 /: x)(_ - _)

            // Evaluates the Expression 
            // given below and displays it
            // ((((0 - 8) - 6) - 4) - 2) 
            println(y)

        }
    }
    ```

    **Output:**

    ```scala
    -20

    ```

    这里， *foldLeft(0)* 是期望的操作，其中零是“初始值”。
    该方法在给定可遍历集合的连续元素之间应用二进制运算，从左向右移动，从初始值开始。
    **例:**

    ```scala
    // Scala program for operations
    // of Folds

    // Creating object 
    object Folds
    {

        // Main method
        def main(args: Array[String]) 
        {

            // Creating List of numbers 
            val x = List(8, 6, 4, 2)

            // Applying method of
            // Folds
            // val y = x.foldRight(0)(_ - _) or
            val y = (x :\ 0)(_ - _)

            // Evaluates the Expression 
            // given below and displays it
            // (8 - (6 - (4 - (2 - 0))))
            println(y)
        }
    }
    ```

    **Output:**

    ```scala
    4

    ```