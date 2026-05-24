# 如何在 C/C++、Python 和 Java 中拆分字符串？

> 原文：[https://www.geeksforgeeks.org/how-to-split-a-string-in-cc-python-and-java/](https://www.geeksforgeeks.org/how-to-split-a-string-in-cc-python-and-java/)

用分隔符分割字符串是一项非常常见的任务。例如，我们有一个逗号分隔的文件项目列表，我们想要一个数组中的单个项目。
几乎所有的编程语言，都提供了一个通过某种分隔符来拆分字符串的函数。

## C

在 C 语言中，使用 `strtok()` 函数。

```c
// Splits str[] according to given delimiters.
// and returns next token. It needs to be called
// in a loop to get all tokens. It returns NULL
// when there are no more tokens.
char * strtok(char str[], const char *delims);
```

下面是一个 C/C++ 程序示例：

```c
// A C/C++ program for splitting a string
// using strtok()
#include <stdio.h>
#include <string.h>

int main()
{
    char str[] = "Geeks-for-Geeks";

    // Returns first token
    char *token = strtok(str, "-");

    // Keep printing tokens while one of the
    // delimiters present in str[].
    while (token != NULL)
    {
        printf("%s\n", token);
        token = strtok(NULL, "-");
    }

    return 0;
}
```

输出：
```
Geeks
for
Geeks
```

## C++

在 C++ 中，有多种方法。

### 方法 1：使用 `stringstream` API

**先决条件**：[`stringstream`](https://www.geeksforgeeks.org/stringstream-c-applications/)。

`stringstream` 对象可以使用字符串对象进行初始化，它自动在空格字符上标记字符串。就像 `cin` 流，`stringstream` 让你把一个字符串当成一个单词流来读。

`stringstream` 的一些最常用函数：
- `clear()` — 刷新流。
- `str()` — 将单词流转换为 C++ 字符串对象。
- `operator <<` — 将字符串对象推入流。
- `operator >>` — 从流中提取一个单词。

下面的代码演示了它：

```cpp
#include <bits/stdc++.h>
using namespace std;

// A quick way to split strings separated via spaces.
void simple_tokenizer(string s)
{
    stringstream ss(s);
    string word;
    while (ss >> word) {
        cout << word << endl;
    }
}

int main(int argc, char const* argv[])
{
    string a = "How do you do!";
    // Takes only space separated C++ strings.
    simple_tokenizer(a);
    cout << endl;
    return 0;
}
```

输出：
```
How
do
you
do!
```

### 方法 2：使用 `find()` 和 `substr()` API

**先决条件**：[`find()`](https://www.geeksforgeeks.org/std-find-in-cpp/) 和 [`substr()`](https://www.geeksforgeeks.org/substring-in-cpp/)。

这个方法更健壮，可以用任何分隔符解析字符串，而不仅仅是空格（虽然默认行为是在空格上分开）。从下面的代码中，逻辑很容易理解。

```cpp
#include <bits/stdc++.h>
using namespace std;

void tokenize(string s, string del = " ")
{
    int start = 0;
    int end = s.find(del);
    while (end != -1) {
        cout << s.substr(start, end - start) << endl;
        start = end + del.size();
        end = s.find(del, start);
    }
    cout << s.substr(start);
}
int main(int argc, char const* argv[])
{
    // Takes C++ string with any separator
    string a = "Hi$%do$%you$%do$%!";
    tokenize(a, "$%");
    cout << endl;

    return 0;
}
```

输出：
```
Hi
do
you
do
!
```

### 方法 3：使用临时字符串

如果给定分隔符的长度为 1，则可以简单地使用临时字符串来拆分字符串。在方法 2 的情况下，这将节省函数开销时间。

```cpp
#include <iostream>
using namespace std;

void split(string str, char del){
    // declaring temp string to store the curr "word" upto del
    string temp = "";

    for(int i=0; i<(int)str.size(); i++){
        // If cur char is not del, then append it to the cur "word", otherwise
        // you have completed the word, print it, and start a new word.
        if(str[i] != del){
            temp += str[i];
        }
        else{
            cout << temp << " ";
            temp = "";
        }
    }

    cout << temp;
}

int main() {

    string str = "geeks_for_geeks";    // string to be split
    char del = '_';    // delimiter around which string is to be split

    split(str, del);

    return 0;
}
```

输出：
```
geeks for geeks
```

## Java

在 Java 中，`split()` 是 `String` 类中的一个方法。

```java
// regexp is the delimiting regular expression;
// limit is the number of returned strings
public String[] split(String regexp, int limit);

// We can call split() without limit also
public String[] split(String regexp)
```

下面是一个 Java 程序示例：

```java
// A Java program for splitting a string
// using split()
import java.io.*;
public class Test
{
    public static void main(String args[])
    {
        String Str = new String("Geeks-for-Geeks");

        // Split above string in at-most two strings
        for (String val: Str.split("-", 2))
            System.out.println(val);

        System.out.println("");

        // Splits Str into all possible tokens
        for (String val: Str.split("-"))
            System.out.println(val);
    }
}
```

输出：
```
Geeks
for-Geeks

Geeks
for
Geeks
```

## Python

Python 中的 `split()` 方法在用指定的分隔符断开给定的字符串后返回一个字符串列表。

```python
# regexp is the delimiting regular expression;
# limit is limit the number of splits to be made
str.split(regexp = "", limit = string.count(str))
```

下面是一个 Python 程序示例：

```python
line = "Geek1 \nGeek2 \nGeek3"
print(line.split())
print(line.split(' ', 1))
```

输出：
```
['Geek1', 'Geek2', 'Geek3']
['Geek1', '\nGeek2 \nGeek3']
```

---
本文由 **阿迪蒂亚·查特吉** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。