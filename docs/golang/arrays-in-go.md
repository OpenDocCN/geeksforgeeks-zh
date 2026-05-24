# Go 中的数组

> 原文:[https://www.geeksforgeeks.org/arrays-in-go/](https://www.geeksforgeeks.org/arrays-in-go/)

Golang 或 [Go 编程语言](https://www.geeksforgeeks.org/go-programming-language-introduction/)中的数组与其他编程语言非常相似。在程序中，有时我们需要存储一组相同类型的数据，比如学生成绩列表。这种类型的集合存储在使用数组的程序中。数组是固定长度的序列，用于在内存中存储同类元素。由于它们的固定长度数组不太受欢迎，像围棋语言中的切片。
在数组中，可以存储零个或零个以上的元素。数组的元素通过使用[]索引操作符以其从零开始的位置进行索引，这意味着第一个元素的索引是*数组【0】*，最后一个元素的索引是*数组【len(array)-1】*。

![arrays-in-golang](img/a2ed807c5a622b569aa27447be3d88ba.png)

#### 创建和访问阵列

在 Go 语言中，数组以两种不同的方式创建:

1.  **Using [var](https://www.geeksforgeeks.org/var-keyword-in-go/) keyword:** In Go language, an array is created using the var keyword of a particular type with name, size, and elements.

    **语法:**

    ```go
    Var array_name[length]Type
    or
    var array_name[length]Typle{item1, item2, item3, ...itemN}

    ```

    **要点:**

    *   In Go language, arrays are mutable, so that you can use array[index] syntax to the left-hand side of the assignment to set the elements of the array at the given index.

        ```go
        Var array_name[index] = element
        ```

        ![](img/360de6e8c5a5ec740cfc34efe41926ff.png)

    *   您可以使用索引值或 for 循环来访问数组的元素。
    *   在 Go 语言中，数组类型是一维的。
    *   数组的长度是固定不变的。
    *   You are allowed to store duplicate elements in an array.

        **示例:**

        ```go
        // Go program to illustrate how to 
        // create an array using the var keyword 
        // and accessing the elements of the
        // array using their index value
        package main

        import "fmt"

        func main() {

        // Creating an array of string type 
        // Using var keyword
        var myarr[3]string

        // Elements are assigned using index
        myarr[0] = "GFG"
        myarr[1] = "GeeksforGeeks"
        myarr[2] = "Geek"

        // Accessing the elements of the array 
        // Using index value
        fmt.Println("Elements of Array:")
        fmt.Println("Element 1: ", myarr[0])
        fmt.Println("Element 2: ", myarr[1])
        fmt.Println("Element 3: ", myarr[2])
        }
        ```

        **输出:**

        ```go
        Elements of Array:
        Element 1:  GFG
        Element 2:  GeeksforGeeks
        Element 3:  Geek

        ```

2.  **Using shorthand declaration:** In Go language, arrays can also declare using shorthand declaration. It is more flexible than the above declaration.

    **语法:**

    ```go
    array_name:= [length]Type{item1, item2, item3,...itemN}
    ```

    ![](img/78e60d3a74520987d72be99059cf3beb.png)

    **示例:**

    ```go
    // Go program to illustrate how to create
    // an array using shorthand declaration 
    // and accessing the elements of the 
    // array using for loop
    package main

    import "fmt"

    func main() {

    // Shorthand declaration of array
    arr:= [4]string{"geek", "gfg", "Geeks1231", "GeeksforGeeks"}

    // Accessing the elements of 
    // the array Using for loop
    fmt.Println("Elements of the array:")

    for i:= 0; i < 3; i++{
    fmt.Println(arr[i])
    }

    }
    ```

    **输出:**

    ```go
    Elements of the array:
    geek
    gfg
    Geeks1231

    ```

#### 多维数组

我们已经知道数组是一维的，但是你可以创建多维数组。多维数组是同类型数组的 ***数组**。*在 Go 语言中，可以使用以下语法创建多维数组:

```go
Array_name[Length1][Length2]..[LengthN]Type
```

您可以使用 Var 关键字或使用速记声明创建多维数组*，如下例所示。*

**注意:**在多维数组中，如果一个单元格没有被用户用某个值初始化，那么编译器会自动用零初始化。Golang 中没有未初始化的概念。

**示例:**

```go
// Go program to illustrate the
// concept of multi-dimension array
package main

import "fmt"

func main() {

// Creating and initializing 
// 2-dimensional array 
// Using shorthand declaration
// Here the (,) Comma is necessary
arr:= [3][3]string{{"C#", "C", "Python"}, 
                   {"Java", "Scala", "Perl"},
                    {"C++", "Go", "HTML"},}

// Accessing the values of the 
// array Using for loop
fmt.Println("Elements of Array 1")
for x:= 0; x < 3; x++{
for y:= 0; y < 3; y++{
fmt.Println(arr[x][y])
}
}

// Creating a 2-dimensional
// array using var keyword
// and initializing a multi
// -dimensional array using index
var arr1 [2][2] int
arr1[0][0] = 100
arr1[0][1] = 200
arr1[1][0] = 300
arr1[1][1] = 400

// Accessing the values of the array
fmt.Println("Elements of array 2")
for p:= 0; p<2; p++{
for q:= 0; q<2; q++{
fmt.Println(arr1[p][q])

}
}
}
```

**输出:**

```go
Elements of Array 1
C#
C
Python
Java
Scala
Perl
C++
Go
HTML
Elements of array 2
100
200
300
400

```

#### 关于数组的重要观察

1.  In an array, if an array does not initialized explicitly, then the **default value of this array is 0**.

    **示例:**

    ```go
    // Go program to illustrate an array
    package main

    import "fmt"

    func main() {

    // Creating an array of int type
    // which stores, two elements
    // Here, we do not initialize the 
    // array so the value of the array
    // is zero
    var myarr[2]int 
    fmt.Println("Elements of the Array :", myarr)

    }
    ```

    **输出:**

    ```go
    Elements of the Array : [0 0]
    ```

2.  In an array, you can **find the length of the array using *len() method*** as shown below:

    **示例:**

    ```go
    // Go program to illustrate how to find
    // the length of the array
    package main

    import "fmt"

    func main() {

    // Creating array
    // Using shorthand declaration    
    arr1:= [3]int{9,7,6}
    arr2:= [...]int{9,7,6,4,5,3,2,4}
    arr3:= [3]int{9,3,5}

    // Finding the length of the 
    // array using len method
    fmt.Println("Length of the array 1 is:", len(arr1))
    fmt.Println("Length of the array 2 is:", len(arr2))
    fmt.Println("Length of the array 3 is:", len(arr3))
    }
    ```

    **输出:**

    ```go
    Length of the array 1 is: 3
    Length of the array 2 is: 8
    Length of the array 3 is: 3

    ```

3.  In an array, ***if ellipsis ‘‘…’’*** become visible at the place of length, then the length of the array is determined by the initialized elements. As shown in the below example:

    **示例:**

    ```go
    // Go program to illustrate the
    // concept of ellipsis in an array
    package main

    import "fmt"

    func main() {

    // Creating an array whose size is determined 
    // by the number of elements present in it
    // Using ellipsis
    myarray:= [...]string{"GFG", "gfg", "geeks",
                        "GeeksforGeeks", "GEEK"}

    fmt.Println("Elements of the array: ", myarray)

    // Length of the array
    // is determine by 
    // Using len() method
    fmt.Println("Length of the array is:", len(myarray))
    }
    ```

    **输出:**

    ```go
    Elements of the array:  [GFG gfg geeks GeeksforGeeks GEEK]
    Length of the array is: 5

    ```

4.  In an array, **you are allowed to iterate over the range of the elements of the array**. As shown in the below example:

    **示例:**

    ```go
    // Go program to illustrate 
    // how to iterate the array
    package main

    import "fmt"

    func main() {

    // Creating an array whose size
    // is represented by the ellipsis
    myarray:= [...]int{29, 79, 49, 39,
                       20, 49, 48, 49}

    // Iterate array using for loop
    for x:=0; x < len(myarray); x++{
    fmt.Printf("%d\n", myarray[x])
    }
    }
    ```

    **输出:**

    ```go
    29
    79
    49
    39
    20
    49
    48
    49

    ```

5.  In Go language, **an array is of value type not of reference type**. So when the array is assigned to a new variable, then the changes made in the new variable do not affect the original array. As shown in the below example:

    **示例:**

    ```go
    // Go program to illustrate value type array
    package main

    import "fmt"

    func main() {

    // Creating an array whose size 
    // is represented by the ellipsis
    my_array:= [...]int{100, 200, 300, 400, 500}
    fmt.Println("Original array(Before):", my_array)

    // Creating a new variable 
    // and initialize with my_array
    new_array := my_array

    fmt.Println("New array(before):", new_array)

    // Change the value at index 0 to 500
    new_array[0] = 500

    fmt.Println("New array(After):", new_array)

    fmt.Println("Original array(After):", my_array)
    }
    ```

    **输出:**

    ```go
    Original array(Before): [100 200 300 400 500]
    New array(before): [100 200 300 400 500]
    New array(After): [500 200 300 400 500]
    Original array(After): [100 200 300 400 500]

    ```

6.  In an array, if the element type of the array is comparable, then the array type is also comparable. So **we can directly compare two arrays using == operator**. As shown in the below example:

    **示例:**

    ```go
    // Go program to illustrate 
    // how to compare two arrays
    package main

    import "fmt"

    func main() {

    // Arrays    
    arr1:= [3]int{9,7,6}
    arr2:= [...]int{9,7,6}
    arr3:= [3]int{9,5,3}

    // Comparing arrays using == operator
    fmt.Println(arr1==arr2)
    fmt.Println(arr2==arr3)
    fmt.Println(arr1==arr3)

    // This will give and error because the 
    // type of arr1 and arr4 is a mismatch 
    /*
    arr4:= [4]int{9,7,6}
    fmt.Println(arr1==arr4)
    */
    }
    ```

    **输出:**

    ```go
    true
    false
    false

    ```