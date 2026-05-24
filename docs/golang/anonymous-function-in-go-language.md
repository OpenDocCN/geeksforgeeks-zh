# Go 语言中的匿名函数

> 原文:[https://www . geesforgeks . org/anonymous-function in-go-language/](https://www.geeksforgeeks.org/anonymous-function-in-go-language/)

Go 语言提供了一个被称为匿名函数的特殊功能。匿名函数是不包含任何名称的函数。当您想要创建内联函数时，它非常有用。在 Go 语言中，匿名函数可以形成闭包。一个匿名函数也被称为 ***函数字面意思*** 。

**语法:**

```go
func(parameter_list)(return_type){
// code..

// Use return statement if return_type are given
// if return_type is not given, then do not 
// use return statement
return
}()

```

**例:**

```go
// Go program to illustrate how
// to create an anonymous function
package main

import "fmt"

func main() {

    // Anonymous function
   func(){

      fmt.Println("Welcome! to GeeksforGeeks")
  }()

}
```

**输出:**

```go
Welcome! to GeeksforGeeks
```

**要点:**

*   In Go language, you are allowed to assign an anonymous function to a variable. When you assign a function to a variable, then the type of the variable is of function type and you can call that variable like a function call as shown in the below example.

    **例:**

    ```go
    // Go program to illustrate
    // use of an anonymous function
    package main

    import "fmt"

    func main() {

        // Assigning an anonymous 
       // function to a variable
       value := func(){
          fmt.Println("Welcome! to GeeksforGeeks")
      }
      value()

    }
    ```

    **输出:**

    ```go
    Welcome! to GeeksforGeeks
    ```

*   也可以在匿名函数中传递参数。

    **示例:**

    ```go
    // Go program to pass arguments 
    // in the anonymous function
    package main

    import "fmt"

    func main() {

        // Passing arguments in anonymous function
      func(ele string){
          fmt.Println(ele)
      }("GeeksforGeeks")

    }
    ```

    **输出:**

    ```go
    GeeksforGeeks
    ```

*   您也可以将一个匿名函数作为参数传递给其他函数。

    **示例:**

    ```go
    // Go program to pass an anonymous 
    // function as an argument into 
    // other function
    package main

    import "fmt"

      // Passing anonymous function
     // as an argument 
     func GFG(i func(p, q string)string){
         fmt.Println(i ("Geeks", "for"))

     }

    func main() {
        value:= func(p, q string) string{
            return p + q + "Geeks"
        }
        GFG(value)
    }
    ```

    **输出:**

    ```go
    GeeksforGeeks
    ```

*   您也可以从另一个函数返回一个匿名函数。

    **例:**

    ```go
    // Go program to illustrate
    // use of anonymous function
    package main

    import "fmt"

     // Returning anonymous function 
     func GFG() func(i, j string) string{
         myf := func(i, j string)string{
              return i + j + "GeeksforGeeks"
         }
        return myf
     }

    func main() {
        value := GFG()
        fmt.Println(value("Welcome ", "to "))
    }
    ```

    **输出:**

    ```go
    Welcome to GeeksforGeeks
    ```