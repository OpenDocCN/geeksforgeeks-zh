# 在 Golang 中查找变量类型的不同方法

> 原文:[https://www . geeksforgeeks . org/golang 中变量类型的不同查找方式/](https://www.geeksforgeeks.org/different-ways-to-find-the-type-of-variable-in-golang/)

[变量](https://www.geeksforgeeks.org/go-variables/)是运行时可以更改的信息的占位符。和变量允许检索和操作存储的信息。
有 3 种方法可以找到 Golang 中的变量类型，如下所示:

*   **使用反射。函数类型***   **使用反射。种类的值()函数***   **Using %T with Printf

    **示例:**

    ```go
    // Golang program to show the different ways
    // to find the Type of a Variable
    package main

    // import the fmt and reflect package
    import (
        "fmt"
        "reflect"
    )

    //main function

    func main() {

        // string type
        var1 := "hello world"

        // integer
        var2 := 10

        // float
        var3 := 1.55

        // boolean
        var4 := true

        // shorthand string array declaration
        var5 := []string{"foo", "bar", "baz"}

        // map is reference datatype
        var6 := map[int]string{100: "Ana", 101: "Lisa", 102: "Rob"}

        // complex64 and complex128
        // is basic datatype
        var7 := complex(9, 15)

        // using %T format specifier to
        // determine the datatype of the variables

        fmt.Println("Using Percent T with Printf")
        fmt.Println()

        fmt.Printf("var1 = %T\n", var1)
        fmt.Printf("var2 = %T\n", var2)
        fmt.Printf("var3 = %T\n", var3)
        fmt.Printf("var4 = %T\n", var4)
        fmt.Printf("var5 = %T\n", var5)
        fmt.Printf("var6 = %T\n", var6)
        fmt.Printf("var7 = %T\n", var7)

        // using TypeOf() method of reflect package
        // to determine the datatype of the variables
        fmt.Println()
        fmt.Println("Using reflect.TypeOf Function")
        fmt.Println()

        fmt.Println("var1 = ", reflect.TypeOf(var1))
        fmt.Println("var2 = ", reflect.TypeOf(var2))
        fmt.Println("var3 = ", reflect.TypeOf(var3))
        fmt.Println("var4 = ", reflect.TypeOf(var4))
        fmt.Println("var5 = ", reflect.TypeOf(var5))
        fmt.Println("var6 = ", reflect.TypeOf(var6))
        fmt.Println("var7 = ", reflect.TypeOf(var7))

        // using ValueOf() method of reflect package
        // to determine the value of the variable
        // Kind() method returns the datatype of the
        // value fetched by the ValueOf() method
        fmt.Println()
        fmt.Println("Using reflect.ValueOf.Kind() Function")
        fmt.Println()

        fmt.Println("var1 = ", reflect.ValueOf(var1).Kind())
        fmt.Println("var2 = ", reflect.ValueOf(var2).Kind())
        fmt.Println("var3 = ", reflect.ValueOf(var3).Kind())
        fmt.Println("var4 = ", reflect.ValueOf(var4).Kind())
        fmt.Println("var5 = ", reflect.ValueOf(var5).Kind())
        fmt.Println("var6 = ", reflect.ValueOf(var6).Kind())
        fmt.Println("var7 = ", reflect.ValueOf(var7).Kind())

    }
    ```

    **输出:**

    ```go
    Using Percent T with Printf

    var1 = string
    var2 = int
    var3 = float64
    var4 = bool
    var5 = []string
    var6 = map[int]string
    var7 = complex128

    Using reflect.TypeOf Function

    var1 =  string
    var2 =  int
    var3 =  float64
    var4 =  bool
    var5 =  []string
    var6 =  map[int]string
    var7 =  complex128

    Using reflect.ValueOf.Kind() Function

    var1 =  string
    var2 =  int
    var3 =  float64
    var4 =  bool
    var5 =  slice
    var6 =  map
    var7 =  complex128

    ```**