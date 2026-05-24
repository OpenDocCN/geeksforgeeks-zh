# 反映。用例子在 Golang 中尝试 end()函数

> 原文:[https://www . geesforgeks . org/reflect-trysend-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-trysend-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。TrySend()**Golang 中的函数尝试在 v 通道上发送 x，但不会阻塞。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) TrySend(x Value) bool
> 
> ```
> 
> **参数:**该函数接受值类型(x)的一个参数。
> 
> **返回值:**该函数返回值是否被发送。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate 
// reflect.TrySend() Function 

package main

 import (
    "fmt"
    "reflect"
 )

func main() {
    c := make(chan int, 1)
    vc := reflect.ValueOf(c)

    // use of TrySend() method
    succeeded := vc.TrySend(reflect.ValueOf(123))

    fmt.Println(succeeded, vc.Len(), vc.Cap())

}    
```

**输出:**

```go
true 1 1

```

**例 2:**

```go
// Golang program to illustrate
// reflect.TrySend() Function 

 package main

 import (
    "fmt"
    "reflect"
 )

func main() {
    c := make(chan int, 1)
    vc := reflect.ValueOf(c)

     // use of TrySend() method
    succeeded := vc.TrySend(reflect.ValueOf(123))
    fmt.Println(succeeded, vc.Len(), vc.Cap())

    vSend, vZero := reflect.ValueOf(789), reflect.Value{}
    branches := []reflect.SelectCase{
        {Dir: reflect.SelectDefault, Chan: vZero, Send: vZero},
        {Dir: reflect.SelectRecv, Chan: vc, Send: vZero},
        {Dir: reflect.SelectSend, Chan: vc, Send: vSend},
    }

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