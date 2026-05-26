# 打字稿中的标识符和关键词

> 原文: [https://www.geeksforgeeks.org/identifiers-and-keywords-in-typescript/](https://www.geeksforgeeks.org/identifiers-and-keywords-in-typescript/)

## 标识符

标识符只不过是给任何类的成员起的名字，如变量、方法名、类名、数组名等。声明标识符时应遵循的某些规则:

*   名称可以以大写字母和小写字母开头，但不能以数字开头。
*   标识符只能使用 `_` 和 `$` 符号命名，除了这些符号，不能使用其他特殊符号。
*   关键词与标识符不同。
*   标识符区分大小写且不包含空格。

## 有效和无效标识符示例

| 有效 | 无效 |
| --- | --- |
| `GeeksforGeeks` | `1$GeeksforGeeks` |
| `Geek_for_geek` | `#Geek` |
| `$geek` | `Geek-for-geek` |

## 关键词

关键词是负责执行某一特定任务的词或代表某一特定功能的词。下表列出了一些关键词:

| `break` | `for` | `any` | `switch` | `case` | `if` |
| `var` | `let` | `const` | `get` |
| `module` |

## 注释

注释是提高程序可读性的一种方式。在编码时，我们使用注释来帮助其他用户更好地理解代码。在执行代码时，编译器忽略注释并编译代码的其余部分。使用注释有两种方式:

*   单行注释 (`//`)
*   多行注释 (`/* */`)

## 示例

*   [打字稿中的 Hello World](https://www.geeksforgeeks.org/hello-world-in-typescript-language/)