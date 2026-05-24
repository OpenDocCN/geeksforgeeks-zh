# Loops in Go Language

> 原文：[https://www.geeksforgeeks.org/loops-in-go-language/](https://www.geeksforgeeks.org/loops-in-go-language/)

Go language contains only a single loop that is for-loop. A for loop is a repetition control structure that allows us to write a loop that is executed a specific number of times. In Go language, this for loop can be used in the different forms and the forms are:

**1\. As simple for loop** It is similar that we use in other programming languages like C, C++, Java, C#, etc.

*Syntax:*

```go
for initialization; condition; post{
       // statements....
}

```

*Here,*

*   The *initialization* statement is optional and executes before for loop starts. The initialization statement is always in a simple statement like variable declarations, increment or assignment statements, or function calls.
*   The *condition* statement holds a boolean expression, which is evaluated at the starting of each iteration of the loop. If the value of the conditional statement is true, then the loop executes.
*   The *post* statement is executed after the body of the for-loop. After the post statement, the condition statement evaluates again if the value of the conditional statement is false, then the loop ends.

**Example:**

```go
// Go program to illustrate the  
// use of simple for loop 
package main

import "fmt"

// Main function
func main() {

    // for loop 
    // This loop starts when i = 0 
    // executes till i<4 condition is true
    // post statement is i++
    for i := 0; i < 4; i++{
      fmt.Printf("GeeksforGeeks\n")  
    }

}
```

**Output:**

```go
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks

```

**2\. For loop as Infinite Loop:** A for loop is also used as an infinite loop by removing all the three expressions from the for loop. When the user did not write condition statement in for loop it means the condition statement is true and the loop goes into an infinite loop.

*Syntax:*

```go
for{
     // Statement...
}

```

**Example:**

```go
// Go program to illustrate the  
// use of an infinite loop 
package main

import "fmt"

// Main function
func main() {

    // Infinite loop
    for {
      fmt.Printf("GeeksforGeeks\n")  
    }

}
```

**Output:**

```go
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
...........

```

**3\. for loop as while Loop:** A for loop can also work as a while loop. This loop is executed until the given condition is true. When the value of the given condition is false the loop ends.

*Syntax:*

```go
for condition{
    // statement..
}

```

**Example:**

```go
// Go program to illustrate the  
// the for loop as while Loop
package main

import "fmt"

// Main function
func main() {

    // while loop
    // for loop executes till 
    // i < 3 condition is true
    i:= 0
    for i < 3 {
       i += 2
    }
  fmt.Println(i) 
}
```

**Output:**

```go
4
```

**4\. Simple range in for loop:** You can also use the range in the for loop.

*Syntax:*

```go
for i, j:= range rvariable{
   // statement..
}
```

*Here,*

*   i and j are the variables in which the values of the iteration are assigned. They are also known as iteration variables.
*   The second variable, i.e, j is optional.
*   The range expression is evaluated once before the starting of the loop.

**Example:**

```go
// Go program to illustrate the  
// use of simple range loop 
package main

import "fmt"

// Main function
func main() {

    // Here rvariable is a array
    rvariable:= []string{"GFG", "Geeks", "GeeksforGeeks"} 

    // i and j stores the value of rvariable
    // i store index number of individual string and
    // j store individual string of the given array
    for i, j:= range rvariable {
       fmt.Println(i, j) 
    }

}
```

**Output:**

```go
0 GFG
1 Geeks
2 GeeksforGeeks

```

**5\. Using for loop for strings:** A for loop can iterate over the Unicode code point for a string.

*Syntax:*

```go
for index, chr:= range str{
     // Statement..
}

```

Here, The index is the variable which store the first byte of UTF-8 encoded code point and *chr* store the characters of the given string and *str* is a string.

**Example:**

```go
// Go program to illustrate the  
// use for loop using string
package main

import "fmt"

// Main function
func main() {

    // String as a range in the for loop
    for i, j:= range "XabCd" {
       fmt.Printf("The index number of %U is %d\n", j, i) 
    }

}
```

**Output:**

```go
The index number of U+0058 is 0
The index number of U+0061 is 1
The index number of U+0062 is 2
The index number of U+0043 is 3
The index number of U+0064 is 4

```

**6\. For Maps:** A for loop can iterate over the key and value pairs of the map.

*Syntax:*

```go
for key, value := range map { 
     // Statement.. 
}

```

**Example:**

```go
// Go program to illustrate the  
// use for loop using maps
package main

import "fmt"

// Main function
func main() {

    // using maps
    mmap := map[int]string{
        22:"Geeks",
        33:"GFG",
        44:"GeeksforGeeks",
    }
    for key, value:= range mmap {
       fmt.Println(key, value) 
    }

}
```

**Output:**

```go
22 Geeks
33 GFG
44 GeeksforGeeks

```

**7\. For Channel:** A for loop can iterate over the sequential values sent on the channel until it closed.

*Syntax:*

```go
for item := range Chnl { 
     // statements..
}

```

**Example:**

```go
// Go program to illustrate the  
// use for loop using channel
package main

import "fmt"

// Main function
func main() {

    // using channel
    chnl := make(chan int)
    go func(){
        chnl <- 100
        chnl <- 1000
       chnl <- 10000
       chnl <- 100000
       close(chnl)
    }()
    for i:= range chnl {
       fmt.Println(i) 
    }

}
```

**Output:**

```go
100
1000
10000
100000

```

**Important Points:**

*   Parentheses are not used around the three statements of a for loop.
*   The curly braces are mandatory in for loop.
*   The opening brace should be in the same line in which post statement exists.
*   If the array, string, slice, or map is empty, then for loop does not give an error and continue its flow. Or in other words, if the array, string, slice, or map is nil then the number of iterations of the for loop is zero.