# GoLang 中的模板

> Original: [https://www.geeksforgeeks.org/templates-in-golang/](https://www.geeksforgeeks.org/templates-in-golang/)

Golang 中的模板是一个强大的功能，可以创建动态内容或向用户显示定制的输出。 Golang 有两个带模板的包：

*   `text/template`
*   `html/template`

## 模板的组成部分

模板主要由 3 个部分组成，具体如下：

### 1. 行动

它们是数据评估、控制结构，如循环或函数。 操作由 `{{` 和 `}}` 分隔，其中根元素使用点运算符 (`.`) 显示。 在大括号内，`{{.}}`。 这些操作控制最终输出的外观。
要放置当前结构对象的字段的值，请在字段名称前加上点运算符 (`.`)。 在花括号内，如 `{{.FieldName}}`。 在其中求值的数据称为**管道**。

### 2. 条件

*If-Else* 构造也可以在模板中使用。 例如，要仅在条件为真时执行模板，我们可以使用以下语法：

```go
{{if .condition}} temp_0 {{else if .condition}} temp_1 {{else}} temp_2 {{end}}
```

这将执行第一个模板 `temp_0`，如果第一个条件为真(如果第二个条件为真)，则将执行第二个模板 `temp_1`，否则将执行第三个模板 `temp_2`。

### 3. 循环

还可以使用 `Range` 操作在模板中使用小版本。 模板内循环的语法为：

```go
{{range .List}} temp_0 {{else}} temp_1 {{end}}
```

这里的 `list` 应该是一个数组、映射或切片，如果长度为 0，那么模板 `temp_1` 将被执行，否则它将遍历 `list` 上的元素。

模板的输入格式应为 UTF-8 编码格式。 外部的任何其他文本都会按原样打印到标准输出。 预定义变量 `os.Stdout` 指的是打印合并数据的标准输出。 `Execute()` 函数接受实现 `Writer` 接口的任何值，并将解析后的模板应用于指定的数据对象。

**示例 1：**

```go
// Golang program to illustrate the
// concept of text/templates
package main

import (
    "os"
    "fmt"
    "text/template"
)

// declaring a struct
type Student struct{

// declaring fields which are
    // exported and accessible 
    // outside of package as they 
    // begin with a capital letter
    Name string
    Marks int64
}

// main function
func main() {

// defining an object of struct
    std1 := Student{"Vani", 94}

// "New" creates a new template
    // with name passed as argument
    tmp1 := template.New("Template_1")

// "Parse" parses a string into a template
    tmp1, _ = tmp1.Parse("Hello {{.Name}}, your marks are {{.Marks}}%!")

// standard output to print merged data
    err := tmp1.Execute(os.Stdout, std1)

// if there is no error, 
    // prints the output
        if err != nil {
                fmt.Println(err)
        }
}
```

输出：

```text
Hello Vani, your marks are 94%!
```

包模板 `html/template` 提供与 `text/template` 相同的接口，但它实现了用于生成 **HTML 输出**的数据驱动模板，而不是文本输出。 此 HTML 输出不会受到任何外部代码注入的影响。

**示例 2：**

HTML 模板文件 (`index.html`)：

```html
<!DOCTYPE html>
<html>
<head>
<title>Results</title>
</head>
<body>
<h1>Hello, {{.Name}}, ID number: {{.Id}}</h1>
<p>
  You have scored {{.Marks}}!
<p>
</body>
</html>
```

Go 程序：

```go
// Golang program to illustrate the
// concept of html/templates
package main

import (
    "html/template"
    "os"
)

// declaring struct
type Student struct {

// defining struct fields
    Name string
    Marks int
    Id string
}

// main function
func main() {

// defining struct instance
    std1 := Student{"Vani", 94, "20024"}

// Parsing the required html
    // file in same directory
    t, err := template.ParseFiles("index.html")

// standard output to print merged data
    err = t.Execute(os.Stdout, std1)
}
```

输出：

```html
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
</head>
<body>
<h1>Hello, Vani, ID number: 20024</h1>
<p>
  You have scored 94!
<p>
</body>
</html>
```