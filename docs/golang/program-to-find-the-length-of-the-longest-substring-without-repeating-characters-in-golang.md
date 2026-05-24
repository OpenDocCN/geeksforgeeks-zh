# 程序在 Golang 中查找最长不重复字符的子串长度

> 原文:[https://www . geesforgeks . org/program-to-find-最长子串的长度-无重复字符-in-golang/](https://www.geeksforgeeks.org/program-to-find-the-length-of-the-longest-substring-without-repeating-characters-in-golang/)

给定一个字符串，在 Golang 中打印最长的不重复字符的子字符串。例如，“ABDEFGABEF”中没有重复字符的最长子字符串是“BDEFGA”。

**例:**

```go
Input : GEEKSFORGEEKS
Output : 
Substring: EKSFORG
Length: 7

Input : ABDEFGABEF
Output : 
Substring: BDEFGA
Length: 6

```

其思想是遍历字符串，对于每个已经访问过的字符，将其最后一次出现的位置存储在整数数组中(我们将根据字符串字符的 ASCII 值更新数组中的索引)。变量 **st** 存储当前子串的起点， **maxlen** 存储最大长度子串的长度，start 存储最大长度子串的起始索引。

遍历字符串时，通过检查数组**位置**来检查字符串中是否已经存在当前字符。如果不存在，则将当前字符的索引存储在数组中，并将值作为当前索引。如果它已经存在于数组中，这意味着当前字符可以在当前子字符串中重复。为此，请检查字符的前一次出现是在当前子字符串的起始点 st 之前还是之后。如果是在**圣**之前，那么只更新数组中的值。如果在 st 之后，那么找到当前子串 **currlen** 的长度为 **i-st** ，其中 **i 为当前**索引。

比较**柯伦**和**麦克伦**。如果 **maxlen** 小于 currlen，那么将 maxlen 更新为 **currlen** 并开始为 st，字符串遍历完成后，需要的最长不重复字符的子串是从 **s【开始】到 s【开始+maxlen-1】**。

```go
// Golang program to find the length of the
// longest substring without repeating
// characters

package main

import "fmt"

func longest_substring(s string, n int) string {

    var i int

    // starting point of
    // current substring.
    st := 0    

    // length of current substring.  
    currlen := 0 

    // maximum length substring 
    // without repeating  characters
    maxlen := 0  

    // starting index of 
    // maximum length substring.
    start := 0

    // this array works as the hash table
    // -1 indicates that element is not
    // present before else any value 
    // indicates its previous index
    pos := make([]int, 125)

    for i = 0; i < 125; i++ {

        pos[i] = -1
    }

    // storing the index
    // of first character
    pos[s[0]] = 0

    for i = 1; i < n; i++ {

        // If this character is not present in array,
        // then this is first occurrence of this
        // character, store this in array.
        if pos[s[i]] == -1 {
            pos[s[i]] = i
        } else {

            // If this character is present in hash then
            // this character has previous occurrence,
            // check if that occurrence is before or after
            // starting point of current substring.
            if pos[s[i]] >= st {

                // find length of current substring and
                // update maxlen and start accordingly.
                currlen = i - st
                if maxlen < currlen {

                    maxlen = currlen
                    start = st
                }
                // Next substring will start after the last
                // occurrence of current character to avoid
                // its repetition.

                st = pos[s[i]] + 1

            }
            // Update last occurrence of
            // current character.
            pos[s[i]] = i
        }

    }
    // Compare length of last substring 
    // with maxlen and update maxlen 
    // and start accordingly.
    if maxlen < i-st {

        maxlen = i - st
        start = st
    }

    // the required string
    ans := ""

    // extracting the string from 
    // [start] to [start+maxlen]
    for i = start; i < start+maxlen; i++ {
        ans += string(s[i])
    }

    return ans

}

func main() {

    var s string = "GEEKSFORGEEKS"
    var n int = len(s)

    // calling the function to 
    // get the required answer.
    var newString = longest_substring(s, n)

    // finding the length of the string
    var length int = len(newString)

    fmt.Println("Longest substring is: ", newString)
    fmt.Println("Length of the string: ", length)

}
```

**输出:**

```go
Longest substring is:  EKSFORG
Length of the string:  7

```

**注意:**不使用数组，我们也可以使用**弦**到 **int** 的*地图*。