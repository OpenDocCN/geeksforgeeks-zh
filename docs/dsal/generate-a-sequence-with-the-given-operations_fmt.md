# 用给定的操作生成一个序列

> 原文：[https://www.geeksforgeeks.org/generate-a-sequence-with-the-given-operations/](https://www.geeksforgeeks.org/generate-a-sequence-with-the-given-operations/)

给定一个只包含`I`（增加）和`D`（减少）的字符串`S`。任务是返回整数的任意排列`【0，1，…，N】`，其中`N`≤`S`的长度，使得对于所有 `i = 0，…，N-1`：

1.  如果 `S[i] == "D"`，那么 `A[i] > A[i+1]`
2.  如果 `S[i] == "I"`，那么 `A[i] < A[i+1]`。

**注意**输出必须包含不同的元素。

**例：**

> **输入：** `S = "DDI"`
> **输出：** `【3、2、0、1】`
> **输入：** `S = "IDID"`
> **输出：** `【0、4、1、3、2】`

**进场：** 如果 `S[0] == "I"`，那么选择`0`作为第一个元素。同样，如果`S[0] == "D"`，那么选择`N`作为第一个元素。现在每进行一次`I`操作，从`【0，N】`范围中选择之前没有选择过的下一个最大元素，对于`D`操作，选择下一个最小元素。

以下是上述方法的实施：

## C++

```cpp
//C++ Implementation of above approach
#include<bits/stdc++.h>
using namespace std;
    // function to find minimum required permutation
    void  StringMatch(string s)
    {
    int lo=0, hi = s.length(), len=s.length();
    vector<int> ans;
    for (int x=0;x<len;x++)
    {
        if (s[x] == 'I')
        {
            ans.push_back(lo) ;
            lo += 1;
            }
        else
        {
            ans.push_back(hi) ;
            hi -= 1;
            }
    }
            ans.push_back(lo) ;
    cout<<"[";
    for(int i=0;i<ans.size();i++)
    {
    cout<<ans[i];
    if(i!=ans.size()-1)
    cout<<",";
    }
    cout<<"]";
}
// Driver code
int main()
{
string S = "IDID";
StringMatch(S);
return 0;
}
//contributed by Arnab Kundu
```

## Java

```java
// Java Implementation of above approach
import java.util.*;

class GFG
{

// function to find minimum required permutation
static void StringMatch(String s)
{
    int lo=0, hi = s.length(), len=s.length();
    Vector<Integer> ans = new Vector<>();
    for (int x = 0; x < len; x++)
    {
        if (s.charAt(x) == 'I')
        {
            ans.add(lo) ;
            lo += 1;
        }
        else
        {
            ans.add(hi) ;
            hi -= 1;
        }
    }
            ans.add(lo) ;
    System.out.print("[");
    for(int i = 0; i < ans.size(); i++)
    {
        System.out.print(ans.get(i));
        if(i != ans.size()-1)
            System.out.print(",");
    }
    System.out.print("]");
}

// Driver code
public static void main(String[] args)
{
    String S = "IDID";
    StringMatch(S);
}
}

// This code is contributed by Rajput-Ji
```

## Python

```python
# Python Implementation of above approach

# function to find minimum required permutation
def StringMatch(S):
    lo, hi = 0, len(S)
    ans = []
    for x in S:
        if x == 'I':
            ans.append(lo)
            lo += 1
        else:
            ans.append(hi)
            hi -= 1

    return ans + [lo]

# Driver code
S = "IDID"
print(StringMatch(S))
```

## C#

```csharp
// C# Implementation of above approach
using System;
using System.Collections.Generic;

class GFG
{

// function to find minimum required permutation
static void StringMatch(String s)
{
    int lo=0, hi = s.Length, len=s.Length;
    List<int> ans = new List<int>();
    for (int x = 0; x < len; x++)
    {
        if (s[x] == 'I')
        {
            ans.Add(lo) ;
            lo += 1;
        }
        else
        {
            ans.Add(hi) ;
            hi -= 1;
        }
    }
            ans.Add(lo) ;
    Console.Write("[");
    for(int i = 0; i < ans.Count; i++)
    {
        Console.Write(ans[i]);
        if(i != ans.Count-1)
            Console.Write(",");
    }
    Console.Write("]");
}

// Driver code
public static void Main(String[] args)
{
    String S = "IDID";
    StringMatch(S);
}
}

// This code is contributed by 29AjayKumar
```

## JavaScript

```javascript
<script>

// Javascript implementation of above approach

// function to find minimum required permutation
    function  StringMatch(s)
    {
    var lo=0, hi = s.length, len=s.length;
    var ans=[];
    for (var x=0;x<len;x++)
    {
        if (s[x] == 'I')
        {
            ans.push(lo) ;
            lo += 1;
            }
        else
        {
            ans.push(hi) ;
            hi -= 1;
            }
    }
            ans.push(lo) ;
    document.write("[");
    for(var i=0;i<ans.length;i++)
    {
     document.write(ans[i]);
    if(i!=ans.length -1)
     document.write(", ");
    }
     document.write("]");
}

var S = "IDID";
StringMatch(S);

// This code is contributed by SoumikMondal

</script>
```

**输出：**

```
[0, 4, 1, 3, 2]
```