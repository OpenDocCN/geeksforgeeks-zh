# 在 GoLang

中使用 regexp 进行匹配

> Original: [https://www.geeksforgeeks.org/matching-using-regexp-in-golang/](https://www.geeksforgeeks.org/matching-using-regexp-in-golang/)

Regexp 是正则表达式的简称。 人们通常将 regexp 与 regex 混淆，这一点很明显，因为其他编程语言(如 Python)使用正则表达式库术语 regex，但 Go 使用**regexp**，记住它作为 regexp 很重要，因为它是 Go with 预构建函数中提供的***正则表达式包***的名称。

### 匹配-这是什么？

嗯，不管出身如何，每个孩子一生中可能至少经历过一次，他们可能穿过搭配的衣服或配饰，然后说：“嘿，伙计，我们穿了搭配的衣服”，“同样的夹克”等等。“。 这些孩子究竟是如何决定某件东西是否与另一件相匹配的呢？ 这很简单！ 当两个事物完全相同，或者一个事物的一部分与另一个事物完全相同时，我们说这两个事物分别是匹配或次匹配。 因此，让我们更深入地研究 GoLang 中的匹配概念。

### 在 GoLang 中使用 regexp 进行匹配

Regexp(正则表达式)完全是关于字符串/模式匹配的。 某个地方的每个函数、regexp 函数的每个部分都需要文本匹配。 让我们来看看一些对于直接或间接匹配很重要的函数。

请参阅**表 1.1**以了解有关用于编译和存储 regex 对象的方法的更多信息。 请参阅**表 1.2**，了解有关直接实现 Match 接口的函数的更多信息，仅此而已。 参见**表 1.3**。 了解有关执行查找、替换等操作的 regexp 的其他预构建方法的更多信息。 它们首先间接实现 Match 接口，然后执行它们的操作。

你怀疑他们是如何做到这一点的吗？ 好的，考虑一下这个例子：如果你的母亲让你在厨房里找东西，只需要提供一个物体的描述，你会怎么做？ 你会去厨房，然后寻找符合你母亲描述的物品，然后挑选出来交给她。 这意味着你只是简单地先匹配描述，然后报告给你的母亲(尽管你的主要关注点是找到它，但你必须间接地匹配才能找到它)。 明白了?。 现在让我们更深入地了解这些函数。

<figure class="table">

| 

_

 | 

**功能说明**

 |
| --- | --- |
| *regexp.Compile()* | 此方法创建一个 regex 对象，该对象可以在没有发生错误的情况下与第一个输入中提供的文本匹配。 如果发生任何错误，则此方法返回错误。 此方法返回一个 regex 对象和一条错误消息(如果有)。 |
| *regexp.CompilePOSIX()* | 它的功能与 Compile()相同，但不同之处在于它将文本限制为 POSIX 格式。 |
| *regexp.MustCompile()* | 此方法创建一个 regex 对象，该对象可以匹配输入中提供的文本，以防出现错误。 Compile()和 MustCompile()之间的主要区别在于，在出现错误的情况下，MustCompile()只向第二个 err 变量返回一条错误消息，而 MustCompile()会死机并引发问题。 此外，MustCompile()只返回要匹配或死机的对象，而不返回第二个变量。 |
| *regexp.MustCompilePOSIX()* | 它的功能与 MustCompile()相同，但不同之处在于它将文本限制为 POSIX 格式。 |

</figure>

*表 1.1。 编译方法*

<figure class="table">

| 

**直接匹配函数**

 | 

**函数描述**

 |
| --- | --- |
| **regexp.Match()** | Match. () accepts a byte array as input and checks that the full-byte array text matches the text saved by the regex object that called Match (). If there is a match, the method returns a Boolean value of true, otherwise it returns a Boolean value of false. |
| **regexp.MatchString()** | It works the same way as Match (). The main difference is that it collects text of type string as input and returns Boolean values based on their respective matches / mismatches. |
| **regexp.MatchReader()**

 | It works the same way as Match (). The main difference is that it collects runes of the reader type as input and returns the maximum Boolean value based on their respective matches / mismatches. |

</figure>

*表 1.2。 实现 Match 接口的直接匹配函数。*

<figure class="table">

| 

**Find Functions**

 | 

**函数说明**

 |
| --- | --- |
| *regexp.Find()* | Returns the first occurrence of the byte array / slice. |
| *regexp.FindString()* | Returns the string with the input text of the regex object that appears for the first time. |
| *regexp.FindSubMatch()* | Returns the first occurrence of a byte array / fragment where the input text matches any subset of the regex object text. |
| *regexp.FindStringSubMatch()* | Returns the first occurrence of the string where the input text matches any subset of the text of the regex object. |
| *regexp.FindAll()* | Returns a byte array of all byte arrays / fragments that appear in all input text with the text of the regex object. |
| *regexp.FindAllString()* | Returns an array of all strings with all matches of the input text of the regex object. |
| *regexp.FindAllSubMatch()* | Returns a byte array of all byte arrays / slices whose input text matches a subset of the regex object text. |
| *regexp.FindAllStringSubMatch()* | Returns an array of all subset strings of all matches of input text with regex object text. |
| *regexp.FindIndex()* | Returns the index of the first occurrence of the byte array / slice input text that matches the text of the regex object. |
| *regexp.FindStringIndex()* | Returns the index of the first occurrence of the string input text that matches the text of the regex object. |
| *regexp.FindSubmatchIndex()* | Returns the index that the input slice matches the first subset of the text of the respective regular expression object. |
| *regexp.FindStringSubmatchIndex()* | Returns the index at which the input string matches the first subset of the text of the corresponding regex object. |
| *regexp.FindAllIndex()* | Returns an array of all such indexes that match the input slice text with the text of the regex object. |
| *regexp.FindAllStringIndex()* | Returns an array of all indexes that match the text of the input string to the text of the regex object. |
| *regexp.FindAllSubmatchIndex()* | Returns an array of all such indexes that match the text portion of the regex object. |
| *regexp.FindAllStringSubmatchIndex()* | Returns an array of all indexes that partially match the text of the input string and the text of the regex object. |
| *regexp.FindReaderIndex()* | Returns a set of integers that define the position in the TRuneReader text of the first full occurrence of the regex object text. |
| *regexp.FindReaderSubmatchIndex()* | Returns an integer fragment that defines where the first part of the regex object text in the RuneReader text appears. |
| *regexp.ReplaceAll()* | As the name implies, this function replaces all values in the input Arg1 with all values in the input Arg2 by matching the text mentioned in the regex object with the text in the input Arg2\. It returns a copy of Slice, which has been modified. In addition, in arg2, all'{content} # x2019; symbols are interpreted in the same way as in Expand. |
| *regexp.ReplaceAllFunc()* | It's almost the same as ReplaceAll (), except that the slices in arg2 are not entered directly by the user, but call a function to return the slices that replace arg2\. It returns a copy of Slice, which has been modified. |
| *regexp.ReplaceAllString()* | It's the same as ReplaceAll (), but the only difference is that in collects string parameters and also returns a string copy of the modified slice. |
| *regexp.ReplaceAllWrital()* | As the name implies, this function replaces all values in the input Arg1 with all values in the input Arg2 by matching the text mentioned in the regex object with the text in the input Arg2\. Literally, the text in arg2 is considered to be completely different from ReplaceAll (), which has different conventions for defining certain symbols, such as'{content} # x2019.' It returns the modified slice. |
| *regexp.ReplaceAllStringFunc()* |

</figure>

*表 1.3。 执行不同操作但间接实现各自操作的 Match 接口的其他函数。*

**注意：****我们一直在提到 _ 的一个副本，修改过的和没有修改过的 _。之所以这样，是因为不会直接对源字符串执行更改。相反，默认情况下会传递一个副本，并在副本上执行修改。**

**正如我们前面提到的，regexp 本身是一组处理字符串匹配的操作。 因此，regexp 包中几乎每个函数都直接或间接地处理匹配。 没有必要惊慌，因为所有这些操作都是完全实时且易于理解的。**

### **例如：**

****代码 1：直接实现匹配方法****

## **行走 / 离开 / 变成 / 走**

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

****要在命令提示符上运行的命令：****

```go
:/Directory where the go file is present/> **go run (file_name).go** 
```

**发帖主题：Re：Колибри0.7.0**

```go
--------Reference strings--------

My name is Geeks for geeks.
I am a computer science portal for geeks.
You can find anything here, if not tell us and we'll add it for you!

--------Match functions--------

regex.Match returns -> true and error(if any) ---> <nil>

regex.Match returns -> true and error(if any) ---> <nil>

regex.MatchString returns -> false and error(if any) ---> <nil> 
```

****代码 2：直接实现匹配方法****

## **行走 / 离开 / 变成 / 走**

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

****要在命令提示符上运行的命令：****

```go
:/Directory where the go file is present/> **go run (file_name).go** 
```

**发帖主题：Re：Колибри0.7.0**

> **初始字节数组-->[72 101 108 108 111 32 71 101 107 83 44 32 49 50 51 52]
> 初始字符串->极客们好，1234
> MatchReader->False
> ReplaceAllFunc()Work in Process…。
> 最终字符串->Hello GNEWkS，1234
> 最终字节数组->[72 101 108 108 111 32 71 69 87 107 83 44 32 49 50 51 52]**

****代码 3：间接实现匹配方法****

## **行走 / 离开 / 变成 / 走**

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

****要在命令提示符上运行的命令：****

```go
:/Directory where the go file is present/> **go run (file_name).go** 
```

**发帖主题：Re：Колибри0.7.0**

> **-引用字符串**
> 
> **我的名字是极客代表极客。
> 我是极客的计算机科学门户。
> 你可以在这里找到任何东西，如果不能告诉我们，我们会为你添加！**
> 
>  **-编译函数
> 
> 已将 regexp 对象初始化为 MusComp…
> 
> -查找函数
> 
> 必发 Compile.Find->[71 101 101 107]
> 必发 Compile.FindString->JEek
> 必选 Compile.FindSubMatch->[[71 101 101 107]]
> Mumed Compile.FindStringSubMatch->和[Geek]
> 必选 Compile.FindAll-
> MUSET Compile.FindStringSubMatch->[Geek]
> 必选 Compile.FindAll。
> mastCompile.FindAllString->n[Geek Geek]
> mastCompile.FindAllSubMatch->n[[71 101 101 107]][[103 101 101 107]
> mastCompile.FindAllStringSubMatch-->e[[Geek][Geek]]
> mastCompile.FindIndex-[。 [11 15]
> 必填 Compile.FindSubmatchIndex->[11 15]
> 必填 Compile.FindStringSubmatchIndex-->[11 15]
> 必填 Compile.FindAllIndex->[[11 15][21 25]]
> 必填 Compile.FindAllStringIndex->[[11 15][。 ][21 25]]
> 必填 Compile.FindAllStringSubmatchIndex->[[11 15][21 25]]
> 
> -替换函数
> 
> MUSET Compile.ReplaceAll->[77 121 32 110 97 109 101 32 105 115 32 66 111 119 32 98 111 119 33 115 32 102 111 114 32 66 111 119 32 98 111 119 33 115 46]
> MUSET Compile.ReplaceAllStirng->n 我的名字是 BOW BOW！S for BOW BOW！s.
> MUSID Compile.ReplaceAllWrital->n[77 121。 MUSET Compile.ReplaceAllWritalString-->我的名字是 ts，代表 ts。**