# 在 GoLang 中使用 regexp 进行匹配

> Original: [https://www.geeksforgeeks.org/matching-using-regexp-in-golang/](https://www.geeksforgeeks.org/matching-using-regexp-in-golang/)

Regexp 是正则表达式的简称。人们通常将 `regexp` 与 `regex` 混淆，这一点很明显，因为其他编程语言（如 Python）使用正则表达式库术语 `regex`，但 Go 使用 `regexp`，记住它作为 `regexp` 很重要，因为它是 Go 中预构建函数提供的正则表达式包的名称。

## 匹配-这是什么？

嗯，不管出身如何，每个孩子一生中可能至少经历过一次，他们可能穿上搭配的衣服或配饰，然后说：“嘿，伙计，我们穿了搭配的衣服”，“同样的夹克”等等。这些孩子究竟是如何决定某件东西是否与另一件相匹配的呢？这很简单！当两个事物完全相同，或者一个事物的一部分与另一个事物完全相同时，我们说这两个事物分别是匹配或次匹配。因此，让我们更深入地研究 GoLang 中的匹配概念。

## 在 GoLang 中使用 regexp 进行匹配

`regexp`（正则表达式）完全是关于字符串/模式匹配的。某个地方的每个函数、`regexp` 函数的每个部分都需要文本匹配。让我们来看看一些对于直接或间接匹配很重要的函数。

请参阅表 1.1 以了解有关用于编译和存储 `regex` 对象的方法的更多信息。请参阅表 1.2，了解有关直接实现 `Match` 接口的函数的更多信息。参见表 1.3，了解有关执行查找、替换等操作的 `regexp` 的其他预构建方法的更多信息。它们首先间接实现 `Match` 接口，然后执行它们的操作。

你怀疑他们是如何做到这一点的吗？好的，考虑一下这个例子：如果你的母亲让你在厨房里找东西，只需要提供一个物体的描述，你会怎么做？你会去厨房，然后寻找符合你母亲描述的物品，然后挑选出来交给她。这意味着你只是简单地先匹配描述，然后报告给你的母亲（尽管你的主要关注点是找到它，但你必须间接地匹配才能找到它）。明白了吗？现在让我们更深入地了解这些函数。

### 表 1.1. 编译方法

| 函数 | 功能说明 |
| :--- | :--- |
| `regexp.Compile()` | 此方法创建一个 `regex` 对象，该对象可以在没有发生错误的情况下与第一个输入中提供的文本匹配。如果发生任何错误，则此方法返回错误。此方法返回一个 `regex` 对象和一条错误消息（如果有）。 |
| `regexp.CompilePOSIX()` | 它的功能与 `Compile()` 相同，但不同之处在于它将文本限制为 POSIX 格式。 |
| `regexp.MustCompile()` | 此方法创建一个 `regex` 对象，该对象可以匹配输入中提供的文本，以防出现错误。`Compile()` 和 `MustCompile()` 之间的主要区别在于，在出现错误的情况下，`MustCompile()` 只向第二个 `err` 变量返回一条错误消息，而 `MustCompile()` 会死机并引发问题。此外，`MustCompile()` 只返回要匹配或死机的对象，而不返回第二个变量。 |
| `regexp.MustCompilePOSIX()` | 它的功能与 `MustCompile()` 相同，但不同之处在于它将文本限制为 POSIX 格式。 |

### 表 1.2. 实现 Match 接口的直接匹配函数

| 直接匹配函数 | 函数描述 |
| :--- | :--- |
| `regexp.Match()` | `Match()` 接受一个字节数组作为输入，并检查完整的字节数组文本是否与调用 `Match()` 的 `regex` 对象保存的文本匹配。如果匹配，该方法返回布尔值 `true`，否则返回布尔值 `false`。 |
| `regexp.MatchString()` | 它的工作方式与 `Match()` 相同。主要区别在于它收集 `string` 类型的文本作为输入，并根据它们各自的匹配/不匹配返回布尔值。 |
| `regexp.MatchReader()` | 它的工作方式与 `Match()` 相同。主要区别在于它收集 `reader` 类型的 `rune` 作为输入，并根据它们各自的匹配/不匹配返回最大布尔值。 |

### 表 1.3. 执行不同操作但间接实现 Match 接口的其他函数

| Find 函数 | 函数说明 |
| :--- | :--- |
| `regexp.Find()` | 返回第一个出现的字节数组/切片。 |
| `regexp.FindString()` | 返回 `regex` 对象输入文本中首次出现的字符串。 |
| `regexp.FindSubMatch()` | 返回第一个出现的字节数组/片段，其中输入文本匹配 `regex` 对象文本的任何子集。 |
| `regexp.FindStringSubMatch()` | 返回第一个出现的字符串，其中输入文本匹配 `regex` 对象文本的任何子集。 |
| `regexp.FindAll()` | 返回一个字节数组，包含所有输入文本中与 `regex` 对象文本匹配的所有字节数组/片段。 |
| `regexp.FindAllString()` | 返回一个数组，包含所有输入文本中与 `regex` 对象文本匹配的所有字符串。 |
| `regexp.FindAllSubMatch()` | 返回一个字节数组，包含所有输入文本匹配 `regex` 对象文本子集的字节数组/切片。 |
| `regexp.FindAllStringSubMatch()` | 返回一个数组，包含所有输入文本与 `regex` 对象文本匹配的子集字符串。 |
| `regexp.FindIndex()` | 返回第一个出现的字节数组/切片输入文本匹配 `regex` 对象文本的索引。 |
| `regexp.FindStringIndex()` | 返回第一个出现的字符串输入文本匹配 `regex` 对象文本的索引。 |
| `regexp.FindSubmatchIndex()` | 返回输入切片匹配相应正则表达式对象文本的第一个子集的索引。 |
| `regexp.FindStringSubmatchIndex()` | 返回输入字符串匹配相应 `regex` 对象文本的第一个子集的索引。 |
| `regexp.FindAllIndex()` | 返回一个数组，包含所有匹配输入切片文本与 `regex` 对象文本的索引。 |
| `regexp.FindAllStringIndex()` | 返回一个数组，包含所有匹配输入字符串文本与 `regex` 对象文本的索引。 |
| `regexp.FindAllSubmatchIndex()` | 返回一个数组，包含所有匹配 `regex` 对象文本部分的索引。 |
| `regexp.FindAllStringSubmatchIndex()` | 返回一个数组，包含所有部分匹配输入字符串文本与 `regex` 对象文本的索引。 |
| `regexp.FindReaderIndex()` | 返回一组整数，定义 `RuneReader` 文本中 `regex` 对象文本首次完整出现的位置。 |
| `regexp.FindReaderSubmatchIndex()` | 返回一个整数片段，定义 `RuneReader` 文本中 `regex` 对象文本首次部分出现的位置。 |
| `regexp.ReplaceAll()` | 顾名思义，此函数通过将 `regex` 对象中提到的文本与输入 `Arg2` 中的文本匹配，用输入 `Arg2` 中的所有值替换输入 `Arg1` 中的所有值。它返回一个已修改的切片副本。此外，在 `arg2` 中，所有 `'{content}'` 符号的解释方式与 `Expand` 中的相同。 |
| `regexp.ReplaceAllFunc()` | 它与 `ReplaceAll()` 几乎相同，不同之处在于 `arg2` 中的切片不是由用户直接输入，而是调用一个函数来返回替换 `arg2` 的切片。它返回一个已修改的切片副本。 |
| `regexp.ReplaceAllString()` | 它与 `ReplaceAll()` 相同，唯一的区别是它收集字符串参数并返回修改后切片的字符串副本。 |
| `regexp.ReplaceAllLiteral()` | 顾名思义，此函数通过将 `regex` 对象中提到的文本与输入 `Arg2` 中的文本匹配，用输入 `Arg2` 中的所有值替换输入 `Arg1` 中的所有值。从字面上看，`arg2` 中的文本被认为与 `ReplaceAll()` 完全不同，后者对于定义某些符号（如 `'{content}'`）有不同的约定。它返回修改后的切片。 |
| `regexp.ReplaceAllStringFunc()` | （原文此处表格内容不完整） |

**注意：** 我们一直在提到切片的一个副本，修改过的和没有修改过的。之所以这样，是因为不会直接对源字符串执行更改。相反，默认情况下会传递一个副本，并在副本上执行修改。

正如我们前面提到的，`regexp` 本身是一组处理字符串匹配的操作。因此，`regexp` 包中几乎每个函数都直接或间接地处理匹配。没有必要惊慌，因为所有这些操作都是完全实时且易于理解的。

### 例如：

**代码 1：直接实现匹配方法**

# Go语言正则表达式匹配方法示例

## 代码 1：使用 Match 和 MatchString 函数

### 代码

```go
package main

import (
    f "fmt"
    "regexp"
)

func main() {
    f.Println("--------Reference strings--------\n")

    name := "My name is Geeks for geeks."
    f.Println(name)

    profession := "I am a computer science portal for geeks."
    f.Println(profession)

    message := "You can find anything here, if not tell us and we'll add it for you!"
    f.Println(message)

    //---------------------------------------------------
    f.Println("\n--------Match functions--------")
    //-------------------------------------------

    obj, err := regexp.Match("[gG]e*k.*", []byte(name))
    f.Println("\nregex.Match returns ->", obj,
        "and error(if any) --->", err)

    //-------------------------------------------
    obj, err = regexp.Match("[gG]e*k.*", []byte(profession))
    f.Println("\nregex.Match returns ->", obj,
        "and error(if any) --->", err)

    //-------------------------------------------
    obj, err = regexp.MatchString("Geek.*", message)
    f.Println("\nregex.MatchString returns ->", obj,
        "and error(if any) --->", err)

    //-------------------------------------------
}
```

### 要在命令提示符上运行的命令

```
:/Directory where the go file is present/> go run (file_name).go
```

### 输出

```
--------Reference strings--------

My name is Geeks for geeks.
I am a computer science portal for geeks.
You can find anything here, if not tell us and we'll add it for you!

--------Match functions--------

regex.Match returns -> true and error(if any) ---> <nil>

regex.Match returns -> true and error(if any) ---> <nil>

regex.MatchString returns -> false and error(if any) ---> <nil>
```

## 代码 2：直接实现匹配方法

### 代码

```go
package main

import (
    f "fmt"
    "io"
    "regexp"
)

func main() {
    obj := regexp.MustCompile("ee")
    var r io.RuneReader
    s := []byte("Hello GeekS, 1234")
    f.Println("Initial byte array -----> ", s)
    f.Println("Initial string ---------> ", string(s))
    f.Println("MatchReader ------------> ", obj.MatchReader(r))
    ex := []byte("NEW")
    f.Println("ReplaceAllFunc( ) work in progress...")
    s = obj.ReplaceAllFunc(s, func(s []byte) []byte {
        if true {
            return ex
        }
        return s
    })
    f.Println("Final string -----------> ", string(s))
    f.Println("Final byte array -------> ", s)
}
```

### 要在命令提示符上运行的命令

```
:/Directory where the go file is present/> go run (file_name).go
```

### 输出

```
初始字节数组-->[72 101 108 108 111 32 71 101 107 83 44 32 49 50 51 52]
初始字符串->极客们好，1234
MatchReader->False
ReplaceAllFunc()Work in Process…。
最终字符串->Hello GNEWkS，1234
最终字节数组->[72 101 108 108 111 32 71 69 87 107 83 44 32 49 50 51 52]
```

## 代码 3：间接实现匹配方法

### 代码

```go
package main

import (
    f "fmt"
    "regexp"
)

func main() {
    f.Println("--------Reference strings--------\n")

    name := "My name is Geeks for geeks."
    f.Println(name)

    profession := "I am a computer science portal for geeks."
    f.Println(profession)

    message := "You can find anything here, if not tell us and we'll add it for you!"
    f.Println(message)
    //---------------------------------------------------------
    f.Println("\n--------Compiling functions--------\n")
    //-------------------------------------------

    musComp := regexp.MustCompile("[gG]ee.?")
    f.Println("Initialized the regexp object to musComp...")

    //---------------------------------------------------------
    f.Println("\n--------Find functions--------\n")
    //-------------------------------------------

    f.Println("mustCompile.Find -----------------------> ",
        musComp.Find([]byte(name)))

    f.Println("mustCompile.FindString -----------------> ",
        musComp.FindString(name))

    f.Println("mustCompile.FindSubmatch ---------------> ",
        musComp.FindSubmatch([]byte(name)))

    f.Println("mustCompile.FindStringSubmatch ---------> ",
        musComp.FindStringSubmatch(name))
    //-------------------------------------------
    f.Println("mustCompile.FindAll --------------------> ",
        musComp.FindAll([]byte(name), -1))

    f.Println("mustCompile.FindAllString --------------> ",
        musComp.FindAllString(name, -1))

    f.Println("mustCompile.FindAllSubmatch ------------> ",
        musComp.FindAllSubmatch([]byte(name), -1))

    f.Println("mustCompile.FindAllStringSubmatch ------> ",
        musComp.FindAllStringSubmatch(name, -1))
    //-------------------------------------------
    f.Println("mustCompile.FindIndex ------------------> ",
        musComp.FindIndex([]byte(name)))

    f.Println("mustCompile.FindStringIndex ------------> ",
        musComp.FindStringIndex(name))

    f.Println("mustCompile.FindSubmatchIndex ----------> ",
        musComp.FindSubmatchIndex([]byte(name)))

    f.Println("mustCompile.FindStringSubmatchIndex ----> ",
        musComp.FindStringSubmatchIndex(name))
    //-------------------------------------------
    f.Println("mustCompile.FindAllIndex ---------------> ",
        musComp.FindAllIndex([]byte(name), -1))

    f.Println("mustCompile.FindAllStringIndex ---------> ",
        musComp.FindAllStringIndex(name, -1))

    f.Println("mustCompile.FindAllSubmatchIndex -------> ",
        musComp.FindAllSubmatchIndex([]byte(name), -1))

    f.Println("mustCompile.FindAllStringSubmatchIndex -> ",
        musComp.FindAllStringSubmatchIndex(name, -1))
    //------------------------------------------------------------
    f.Println("\n--------Replace functions--------\n")
    //-------------------------------------------

    f.Println("mustCompile.ReplaceAll -----------------> ",
        musComp.ReplaceAll([]byte(name), []byte("Bow bow!")))

    f.Println("mustCompile.ReplaceAllStirng -----------> ",
        musComp.ReplaceAllString(name, "Bow bow!"))

    f.Println("mustCompile.ReplaceAllLiteral ----------> ",
        musComp.ReplaceAllLiteral([]byte(name), []byte("T")))

    f.Println("mustCompile.ReplaceAllLiteralString ----> ",
        musComp.ReplaceAllLiteralString(name, "T"))
    //------------------------------------------------------------
}
```

### 要在命令提示符上运行的命令

```
:/Directory where the go file is present/> go run (file_name).go
```

### 输出

```
-引用字符串

我的名字是极客代表极客。
我是极客的计算机科学门户。
你可以在这里找到任何东西，如果不能告诉我们，我们会为你添加！

-编译函数

已将 regexp 对象初始化为 MusComp…

-查找函数

必发 Compile.Find->[71 101 101 107]
必发 Compile.FindString->JEek
必选 Compile.FindSubMatch->[[71 101 101 107]]
Mumed Compile.FindStringSubMatch->和[Geek]
必选 Compile.FindAll-
MUSET Compile.FindStringSubMatch->[Geek]
必选 Compile.FindAll。
mastCompile.FindAllString->n[Geek Geek]
mastCompile.FindAllSubMatch->n[[71 101 101 107]][[103 101 101 107]
mastCompile.FindAllStringSubMatch-->e[[Geek][Geek]]
mastCompile.FindIndex-[。 [11 15]
必填 Compile.FindSubmatchIndex->[11 15]
必填 Compile.FindStringSubmatchIndex-->[11 15]
必填 Compile.FindAllIndex->[[11 15][21 25]]
必填 Compile.FindAllStringIndex->[[11 15][。 ][21 25]]
必填 Compile.FindAllStringSubmatchIndex->[[11 15][21 25]]

-替换函数

MUSET Compile.ReplaceAll->[77 121 32 110 97 109 101 32 105 115 32 66 111 119 32 98 111 119 33 115 32 102 111 114 32 66 111 119 32 98 111 119 33 115 46]
MUSET Compile.ReplaceAllStirng->n 我的名字是 BOW BOW！S for BOW BOW！s.
MUSID Compile.ReplaceAllWrital->n[77 121。 MUSET Compile.ReplaceAllWritalString-->我的名字是 ts，代表 ts。
```