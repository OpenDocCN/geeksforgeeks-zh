# C++ 程序打印文件中唯一的单词

> 原文:[https://www . geesforgeks . org/c-程序转打印-文件中的唯一单词/](https://www.geeksforgeeks.org/c-program-to-print-unique-words-in-a-file/)

编写一个函数，以文件名作为参数，打印其中所有唯一的单词。

**我们强烈建议您最小化浏览器，先自己尝试一下**

这个想法是使用 STL 中的[地图来跟踪已经出现的单词。](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)

```cpp
// C++ program to print unique words in a string
#include <bits/stdc++.h>
using namespace std;

// Prints unique words in a file
void printUniquedWords(char filename[])
{
    // Open a file stream
    fstream fs(filename);

    // Create a map to store count of all words
    map<string, int> mp;

    // Keep reading words while there are words to read
    string word;
    while (fs >> word)
    {
        // If this is first occurrence of word
        if (!mp.count(word))
            mp.insert(make_pair(word, 1));
        else
            mp[word]++ ;
    }

    fs.close();

    // Traverse map and print all words whose count
    //is 1
    for (map<string, int> :: iterator p = mp.begin();
         p != mp.end(); p++)
    {
        if (p->second == 1)
            cout << p->first << endl;
    }
}

// Driver program
int main()
{
    // Create a file for testing and write something in it
    char filename[] = "test.txt";
    ofstream fs(filename, ios::trunc);
    fs << "geeks for geeks quiz code geeks practice for qa";
    fs.close();

    printUniquedWords(filename);
    return 0;
}
```

输出:

```cpp
code
practice
qa
quiz
```

感谢 Utkarsh 对以上代码的建议。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论