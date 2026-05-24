# 下一个不包含回文且包含前 k 个字符的单词

> 原文: [https://www.geeksforgeeks.org/next-word-that-does-not-contain-a-palindrome-and-has-characters-from-first-kfind-lexicographically-next-word-contains-first-k-letters-english-alphabet-not-contain-palindrome-substring-length-one/](https://www.geeksforgeeks.org/next-word-that-does-not-contain-a-palindrome-and-has-characters-from-first-kfind-lexicographically-next-word-contains-first-k-letters-english-alphabet-not-contain-palindrome-substring-length-one/)

## 问题描述

给定一个字符串 `s` 和一个极限 `K`，从字典序的角度找到下一个单词，它包含英文字母表前 `K` 个字母中的字符，并且不包含长度超过一个的回文子串。可以假设输入字符串不包含回文子串。

## 示例

```
Input : s = "cba" 
        k = 4
Output : cbd

Input : s = "cba"
        k = 3
Output : -1
we can't form such word
```

## 方法

我们的目的是找到字典序上的下一个单词，所以需要从右向左移动。当从右向左移动时，从右侧改变最后一个字母。递增最后一个字母时，确保形成的字符串包含前 `k` 个字母，并且不包含任何作为回文的子字符串。

以下是上述办法的实施情况：

### C++

```cpp
// CPP program to find lexicographically
// next word which contains first K
// letters of the English alphabet
// and does not contain a palindrome
// as it's substring of length more
// than one.
#include <bits/stdc++.h>
using namespace std;

// function to return lexicographically
// next word
void findNextWord(string s, int m)
{
    // we made m as m+97 that means
    // our required string contains
    // not more than m+97(as per ASCII
    // value) in it.
    m += 97;
    int n = s.length();
    int i = s.length() - 1;

    // increment last alphabet to make
    // next lexicographically next word.
    s[i]++;

    while (i >= 0 && i <= n - 1) {

        // if i-th alphabet not in first
        // k letters then make it as "a"
        // and then increase (i-1)th letter
        if (s[i] >= m) {
            s[i] = 'a';
            s[--i]++;
        }

        // to check whether formed string
        // palindrome or not.
        else if (s[i] == s[i - 1] ||
                 s[i] == s[i - 2])
            s[i]++;

        // increment i.
        else
            i++;
    }

    // if i less than or equals to one
    // that means we not formed such word.
    if (i <= -1)
        cout << "-1";
    else
        cout << s;
}

// Driver code for above function.
int main()
{
    string str = "abcd";
    int k = 4;
    findNextWord(str, k);
    return 0;
}
```

### Java

```java
// Java program to find lexicographically
// next word which contains first K
// letters of the English alphabet
// and does not contain a palindrome
// as it's substring of length more
// than one.

public class GFG
{

    // function to return lexicographically
    // next word
    static void findNextWord(char[] s, int m)
    {
        // we made m as m+97 that means
        // our required string contains
        // not more than m+97(as per ASCII
        // value) in it.
        m += 97;
        int n = s.length;
        int i = s.length - 1;

        // increment last alphabet to make
        // next lexicographically next word.
        s[i]++;

        while (i >= 0 && i <= n - 1)
        {

            // if i-th alphabet not in first
            // k letters then make it as "a"
            // and then increase (i-1)th letter
            if (s[i] >= m)
            {
                s[i] = 'a';
                s[--i]++;
            }
            // to check whether formed string
            // palindrome or not.
            else if (s[i] == s[i - 1]
                    || s[i] == s[i - 2])
            {
                s[i]++;
            }
            // increment i.
            else
            {
                i++;
            }
        }

        // if i less than or equals to one
        // that means we not formed such word.
        if (i <= -1)
        {
            System.out.println("-1");
        }
        else
        {
            System.out.println(s);
        }
    }

    // Driver code
    public static void main(String[] args)
    {
        char[] str = "abcd".toCharArray();
        int k = 4;
        findNextWord(str, k);
    }
}

// This code contributed by Rajput-Ji
```

### Python 3

```python
# Python3 program to find lexicographically
# next word which contains first K
# letters of the English alphabet and
# does not contain a palindrome as it's
# substring of length more than one.

# Function to return lexicographically next word
def findNextWord(s, m):

    # we made m as m+97 that means
    # our required string contains
    # not more than m+97(as per ASCII
    # value) in it.
    m += 97
    n = len(s)
    i = len(s) - 1

    # increment last alphabet to make
    # next lexicographically next word.
    s[i] = chr(ord(s[i]) + 1)

    while i >= 0 and i <= n - 1:

        # if i-th alphabet not in first
        # k letters then make it as "a"
        # and then increase (i-1)th letter
        if ord(s[i]) >= m:
            s[i] = 'a'
            i -= 1
            s[i] = chr(ord(s[i]) + 1)

        # to check whether formed string
        # palindrome or not.
        elif s[i] == s[i - 1] or s[i] == s[i - 2]:
            s[i] = chr(ord(s[i]) + 1)

        # increment i.
        else:
            i += 1

    # if i less than or equals to one
    # that means we not formed such word.
    if i <= -1:
        print("-1")
    else:
        print(''.join(s))

# Driver code
if __name__ == "__main__":

    string = "abcd"
    k = 4
    findNextWord(list(string), k)

# This code is contributed by Rituraj Jain
```

### C#

```csharp
// C# program to find lexicographically
// next word which contains first K
// letters of the English alphabet
// and does not contain a palindrome
// as it's substring of length more
// than one.
using System;

class GFG
{

    // function to return lexicographically
    // next word
    static void findNextWord(char[] s, int m)
    {
        // we made m as m+97 that means
        // our required string contains
        // not more than m+97(as per ASCII
        // value) in it.
        m += 97;
        int n = s.Length;
        int i = s.Length - 1;

        // increment last alphabet to make
        // next lexicographically next word.
        s[i]++;

        while (i >= 0 && i <= n - 1)
        {

            // if i-th alphabet not in first
            // k letters then make it as "a"
            // and then increase (i-1)th letter
            if (s[i] >= m)
            {
                s[i] = 'a';
                s[--i]++;
            }
            // to check whether formed string
            // palindrome or not.
            else if (s[i] == s[i - 1] ||
                     s[i] == s[i - 2])
            {
                s[i]++;
            }

            // increment i.
            else
            {
                i++;
            }
        }

        // if i less than or equals to one
        // that means we not formed such word.
        if (i <= -1)
        {
            Console.WriteLine("-1");
        }
        else
        {
            Console.WriteLine(s);
        }
    }

    // Driver code
    public static void Main(String[] args)
    {
        char[] str = "abcd".ToCharArray();
        int k = 4;
        findNextWord(str, k);
    }
}

// This code is contributed by 29AjayKumar
```

## java 描述语言

```html
<script>
// Javascript program to find lexicographically
// next word which contains first K
// letters of the English alphabet
// and does not contain a palindrome
// as it's substring of length more
// than one.

// function to return lexicographically
// next word
function findNextWord(s, m)
{
    // we made m as m+97 that means
    // our required string contains
    // not more than m+97(as per ASCII
    // value) in it.
    m += 97;
    var n = s.length;
    var i = s.length - 1;

    // increment last alphabet to make
    // next lexicographically next word.
    s[i] = String.fromCharCode(s[i].charCodeAt(0)+1);

    while (i >= 0 && i <= n - 1) {

        // if i-th alphabet not in first
        // k letters then make it as "a"
        // and then increase (i-1)th letter

        if (s[i].charCodeAt(0) >= m) {

            s[i] = 'a';
            s[i-1] = String.fromCharCode(s[i-1].charCodeAt(0)+1);
            i--;
        }

        // to check whether formed string
        // palindrome or not.
        else if (s[i] == s[i - 1] ||
                 s[i] == s[i - 2])
            s[i] = String.fromCharCode(s[i].charCodeAt(0)+1);

        // increment i.
        else
            i++;
    }

    // if i less than or equals to one
    // that means we not formed such word.
    if (i <= -1)
        document.write( "-1");
    else
        document.write( s.join(''));
}

// Driver code for above function.
var str = "abcd".split('');
var k = 4;
findNextWord(str, k);

// This code is contributed by noob2000.
</script>
```

**输出:**

```
abda
```