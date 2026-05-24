# 求包含任意字符的文件中整数的和

> 原文:[https://www . geesforgeks . org/find-sum-integers-file-contains-characters/](https://www.geeksforgeeks.org/find-sum-integers-file-contains-characters/)

给你一个包含任何类型字符的文本文件。你必须找到整数值的和。

示例:

```cpp
Input : text.txt 
Let contents of test.txt be : 
:-,,$%^5313&^*1)(*(
464sz29>>///11!!!
(*HB%$#)(*0900

Output : 6727

Input : text1.txt 
Let contents of test.txt be : 
234***3r3r()
()(0)34

Output : 274

```

**步骤:**
1。要以只读模式打开文件，我们可以使用 ifstream 库
2。遍历文件的所有行，找到所有整数
3。如果找到整数，则将其存储在临时变量中，因为下一个字符有可能是整数
4。如果发现整数以外的任何字符，则在最终结果中添加 temp 值，并再次设置 temp = 0
5。如果最后一个元素是一个整数，那么我们必须在循环之后添加 temp，如果不是，那么 temp 的值将已经为零。所以总和不会受到影响。

```cpp
// C++ implementation of given text file which
// contains any type of characters. We have to
// find the sum of integer value.
#include <bits/stdc++.h>
using namespace std;

// a function which return sum of all integers
// find in input text file
int findSumOfIntegers()
{
    ifstream f; // to open the text file in read mode
    f.open("text.txt");

    int sum = 0, num = 0;

    // One by one read strings from file. Note that
    // f >> text works same as cin >> text.
    string text;
    while (f >> text) {

        // Move in row and find all integers
        for (int i = 0; text[i] != '\0'; i++) {

            // Find value of current integer
            if (isdigit(text[i])) 
                num = 10 * num + (text[i] - '0');            

            // If other character, add it to the
            // result
            else {
                sum += num;
                num = 0; // and now replace
                         // previous number with 0
            }
        }
    }
    sum += num;
    return sum;
}

// Driver program to test above functions
int main()
{
    cout << findSumOfIntegers();
    return 0;
}
```

输出:

```cpp
6727 (for Input 1)

```

本文由 **Harshit Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。