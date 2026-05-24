# 反映。Golang 中的 Close()函数示例

> 原文:[https://www . geesforgeks . org/reflect-close-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-close-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。关闭()**Golang 中的函数用于关闭频道 v。要访问该函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Close()
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数不返回值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate 
// reflect.Close() Function 

package main

 import (
    "fmt"
    "reflect"
 )

type T int

func IsClosed(ch <-chan T) bool {
    select {
    case <-ch:
        return true
    default:
    }

    return false
}

func main() {
    c := make(chan T)
    vc := reflect.ValueOf(c)
    fmt.Println(IsClosed(c))

    // use of Close() method
    vc.Close()
    fmt.Println(IsClosed(c))
}                    
```

**输出:**

```go
false
true

```

**例 2:**

```go
// Golang program to illustrate 
// reflect.Close() Function 

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

    selIndex, vRecv, sentBeforeClosed := reflect.Select(branches)
    fmt.Println(selIndex)       
    fmt.Println(sentBeforeClosed)
    fmt.Println(vRecv.Int())   

    // use of Close() method
    vc.Close()

}       
```

**输出:**

```go
true 1 1
1
true
123

```