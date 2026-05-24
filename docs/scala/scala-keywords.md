# 斯卡拉关键词

> 原文:[https://www.geeksforgeeks.org/scala-keywords/](https://www.geeksforgeeks.org/scala-keywords/)

***关键词或保留词*** 是一种语言中用于某些内部过程或代表某些预定义动作的词。因此，这些词不允许用作变量名或对象。这样做会导致编译时错误**。**

**示例:**

```scala
// Scala Program to illustrate the keywords 

// Here object, def, and var are valid keywords
object Main 
{
    def main(args: Array[String]) 
    {
        var p = 10
        var q = 30
        var sum = p + q
        println("The sum of p and q is :"+sum);
    }
}
```

**输出:**

```scala
The sum of p and q is :40

```

Scala 包含以下关键词:

| 摘要 |
| 情况 |
| 捕捉 |
| 班级 |
| 极好的 |
| 做 |
| 其他 |
| 延伸 |
| 错误的 |
| 最后的 |

| 最后 |
| 为 |
| 四人对抗赛 |
| 如果 |
| 含蓄的 |
| 进口 |
| 懒惰的 |
| 比赛 |
| 新的 |
| 空 |

| 目标 |
| 推翻 |
| 包裹 |
| 私人的 |
| 保护 |
| 返回 |
| 密封的 |
| 极好的 |
| 这 |
| 扔 |

| 特点 |
| 真实的 |
| 尝试 |
| 类型 |
| 英国压力单位 |
| 定义变量 |
| 在…期间 |
| 随着 |
| 产量 |
| >: |

| ⇒ |
| => |
| = |
|  |
| <:/> |
| ← |
|  |
| # |
| @ |
| ： |
| _ |

**示例:**

```scala
// Scala Program to illustrate the keywords 

// Here class keyword is used to create a new class
// def keyword is used to create Function
// var keyword is used to create a variable 
class GFG
{
    var name = "Priyanka"
    var age = 20
    var branch = "Computer Science"
    def show()
    {
    println("Hello! my name is " + name + "and my age is"+age);
    println("My branch name is " + branch);
    }
}

// object keyword is used to define 
// an object new keyword is used to 
// create an object of the given class
object Main 
{
    def main(args: Array[String])
    {
        var ob = new GFG();
        ob.show();
    }
}
```

**输出:**

```scala
Hello! my name is Priyankaand my age is20
My branch name is Computer Science

```