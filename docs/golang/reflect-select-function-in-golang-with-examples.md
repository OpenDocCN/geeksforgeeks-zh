# 反映。在 Golang 中选择()函数并举例

> 原文:[https://www . geesforgeks . org/reflect-select-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-select-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Select()** 函数用于执行案例列表描述的选择操作。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func Select(cases []SelectCase) (chosen int, recv Value, recvOK bool)
> 
> ```
> 
> **参数:**该函数取以下参数:
> 
> *   **病例:**此参数为病例列表。
> 
> **返回值:**该函数返回所选案例的索引。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Select() Function 

 package main

 import (
     "fmt"
     "reflect"
 )

func main() {
    c := make(chan int, 1)
    vc := reflect.ValueOf(c)
    succeeded := vc.TrySend(reflect.ValueOf(123))
    fmt.Println(succeeded, vc.Len(), vc.Cap())

    vSend, vZero := reflect.ValueOf(789), reflect.Value{}
    branches := []reflect.SelectCase{
        {Dir: reflect.SelectDefault, Chan: vZero, Send: vZero},
        {Dir: reflect.SelectRecv, Chan: vc, Send: vZero},
        {Dir: reflect.SelectSend, Chan: vc, Send: vSend},
    }

    // use of Select() method
    selIndex, vRecv, sentBeforeClosed := reflect.Select(branches)
    fmt.Println(selIndex)       
    fmt.Println(sentBeforeClosed)
    fmt.Println(vRecv.Int())   
    vc.Close()
    // Remove the send case branch this time,
    // for it may cause panic.
    selIndex, _, sentBeforeClosed = reflect.Select(branches[:2])
    fmt.Println(selIndex, sentBeforeClosed) 
}        
```

**输出:**

```go
true 1 1
1
true
123
1 false

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Select() Function 

 package main

 import (
     "fmt"
     "reflect"
 )

 func main() {
     var sendCh = make(chan int) 

     var increaseInt = func(c chan int) {
         for i := 0; i < 8; i++ {
             c <- i
         }
         close(c)
     }

     go increaseInt(sendCh)

     var selectCase = make([]reflect.SelectCase, 1)
     selectCase[0].Dir = reflect.SelectRecv
     selectCase[0].Chan = reflect.ValueOf(sendCh)

     counter := 0
     for counter < 1 {

        // use of Select() method
         chosen, recv, recvOk := reflect.Select(selectCase)
        if recvOk {
             fmt.Println(chosen, recv.Int(), recvOk)

         } else {
             counter++
         }
     }
 }
```

**输出:**

```go
0 0 true
0 1 true
0 2 true
0 3 true
0 4 true
0 5 true
0 6 true
0 7 true

```