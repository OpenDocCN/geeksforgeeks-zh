# 选择 Go 语言中的语句

> 原文:[https://www . geesforgeks . org/select-statement-in-go-language/](https://www.geeksforgeeks.org/select-statement-in-go-language/)

在 Go 语言中，select 语句就像 [switch 语句](https://www.geeksforgeeks.org/switch-statement-in-go/)一样，但是在 select 语句中，case 语句指的是通信，即在信道上发送或接收的操作。

**语法:**

```go
select{

case SendOrReceive1: // Statement
case SendOrReceive2: // Statement
case SendOrReceive3: // Statement
.......
default: // Statement

```

**重要点:**

*   Select statement waits until the communication(send or receive operation) is prepared for some cases to begin.

    **示例:**

    ```go
    // Go program to illustrate the
    // concept of select statement
    package main

    import("fmt"
     "time")

        // function 1
        func portal1(channel1 chan string) {

            time.Sleep(3*time.Second)
            channel1 <- "Welcome to channel 1"
        }

        // function 2
         func portal2(channel2 chan string) {

            time.Sleep(9*time.Second)
            channel2 <- "Welcome to channel 2"
        }

    // main function
    func main(){

        // Creating channels
       R1:= make(chan string)
       R2:= make(chan string)

       // calling function 1 and 
       // function 2 in goroutine
       go portal1(R1)
       go portal2(R2)

       select{

            // case 1 for portal 1
           case op1:= <- R1:
           fmt.Println(op1)

           // case 2 for portal 2
           case op2:= <- R2:
           fmt.Println(op2)
       }

    }
    ```

    **输出:**

    ```go
    Welcome to channel 1
    ```

    **说明:**在上面的程序中，传送门 1 睡眠 3 秒，传送门 2 睡眠 9 秒，在他们的睡眠时间结束后，他们将准备继续进行。现在，select 语句一直等到它们的睡眠时间，当入口 2 醒来时，它选择案例 2 并打印“欢迎来到频道 1”。如果入口 1 在入口 2 之前醒来，那么输出是“欢迎来到频道 2”。

*   If a select statement does not contain any case statement, then that select statement waits forever.

    **语法:**

    ```go
    select{}
    ```

    **示例:**

    ```go
    // Go program to illustrate the
    // concept of select statement
    package main

    // main function
    func main() {

        // Select statement 
       // without any case
       select{ }

    }
    ```

    **输出:**

    ```go
    fatal error: all goroutines are asleep - deadlock!

    goroutine 1 [select (no cases)]:
    main.main()
        /home/runner/main.go:9 +0x20
    exit status 2

    ```

*   The default statement in the select statement is used to protect select statement from blocking. This statement executes when there is no case statement is ready to proceed.

    **示例:**

    ```go
    // Go program to illustrate the
    // concept of select statement
    package main

    import "fmt"

    // main function
    func main() {

        // creating channel
        mychannel:= make(chan int)
       select{
         case <- mychannel: 

         default:fmt.Println("Not found")
    }   
    }
    ```

    **输出:**

    ```go
    Not found
    ```

*   The blocking of select statement means when there is no case statement is ready and the select statement does not contain any default statement, then the select statement block until at least one case statement or communication can proceed.

    **示例:**

    ```go
    // Go program to illustrate the
    // concept of select statement
    package main

    // main function
    func main() {

        // creating channel
        mychannel:= make(chan int)

        // channel is not ready 
       // and no default case
       select{
           case <- mychannel:

       }
    }
    ```

    **输出:**

    ```go
    fatal error: all goroutines are asleep - deadlock!

    goroutine 1 [chan receive]:
    main.main()
        /home/runner/main.go:14 +0x52
    exit status 2
    ```

*   In select statement, if multiple cases are ready to proceed, then one of them can be selected randomly.

    **示例:**

    ```go
    // Go program to illustrate the
    // concept of select statement
    package main

    import "fmt"

        // function 1
        func portal1(channel1 chan string){
            for i := 0; i <= 3; i++{
                channel1 <- "Welcome to channel 1"
            }

        }

        // function 2
         func portal2(channel2 chan string){
            channel2 <- "Welcome to channel 2"
        }

    // main function
    func main() {

        // Creating channels
       R1:= make(chan string)
       R2:= make(chan string)

       // calling function 1 and 
       // function 2 in goroutine
       go portal1(R1)
       go portal2(R2)

       // the choice of selection 
       // of case is random
       select{
           case op1:= <- R1:
           fmt.Println(op1)
           case op2:= <- R2:
           fmt.Println(op2)
       }
    }
    ```

    **输出:**

    ```go
    Welcome to channel 2
    ```