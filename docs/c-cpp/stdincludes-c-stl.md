# STD::c++ STL 中包含()

> 原文:[https://www.geeksforgeeks.org/stdincludes-c-stl/](https://www.geeksforgeeks.org/stdincludes-c-stl/)

C++ 定义了一个函数，可以用来识别一个容器中的所有数字是否也存在于其他容器中。使用“**算法**表头定义的“**包含()**”可以实现该任务。下面解释实现。

**语法 1:使用运算符“<”**

```cpp
Template :
template 
  bool includes (initer1 beg1, initer1 end1,
                        initer2 beg2, initer2 end2,)
Parameters :
beg1 :  Input iterator to initial position of first sorted sequence.
end1 :  Input iterator to final position of first sorted sequence.

beg2 :  Input iterator to initial position of second sorted sequence.
end2 :  Input iterator to final position of second sorted sequence.

Return value : 
True if every element of 2nd container lies in 1st container.

```

```cpp
// C++ code to demonstrate the working of 
// includes() implementation 1

#include<bits/stdc++.h>
using namespace std;

int main()
{
    // initializing 1st container
    vector<int> arr1 = { 1, 4, 6, 3, 2 };

    // initializing 2nd container
    vector<int> arr2 = { 1, 2, 4 };

    // sorting initial containers
    sort(arr1.begin(), arr1.end());
    sort(arr2.begin(), arr2.end());

    // using include() check if all elements 
    // of arr2 lie in arr1 
    if(includes(arr1.begin(), arr1.end(), arr2.begin(), arr2.end()))
    cout << "All elements of 2nd container are in 1st container";
    else 
    cout << "All elements of 2nd container are not in 1st container";

}
```

输出:

```cpp
All elements of 2nd container are in 1st container

```

**语法 2:使用比较器**

```cpp
Template :
template 
  bool includes (initer1 beg1, initer1 end1,
                        initer2 beg2, initer2 end2, Compare comp)
Parameters :
beg1 :  Input iterator to initial position of first sorted sequence.
end1 :  Input iterator to final position of first sorted sequence.

beg2 :  Input iterator to initial position of second sorted sequence.
end2 :  Input iterator to final position of second sorted sequence.

comp : The comparator function that returns a boolean
true/false of the each elements compared. This function 
accepts two arguments. This can be function pointer or 
function object and cannot change values.

Return value : 
True if every element of 2nd container lies in 1st container.

```

```cpp
// C++ code to demonstrate the working of 
// includes() implementation 2

#include<bits/stdc++.h>
using namespace std;

// comparator function
bool comp (int i, int j) { return i<j; }

int main()
{
    // initializing 1st container
    vector<int> arr1 = { 1, 4, 6, 3, 2 };

    // initializing 2nd container
    vector<int> arr2 = { 1, 2, 4 };

    // sorting initial containers
    sort(arr1.begin(), arr1.end());
    sort(arr2.begin(), arr2.end());

    // using include() check if all elements 
    // of arr2 lie in arr1 
    // using comparator function
    if(includes(arr1.begin(), arr1.end(), arr2.begin(), arr2.end(), comp))
    cout << "All elements of 2nd container are in 1st container";
    else 
    cout << "All elements of 2nd container are not in 1st container";

}
```

输出:

```cpp
All elements of 2nd container are in 1st container

```

**可能的应用:**在一个系统中，如果一个集合是另一个集合的子集，或者可以用来确定彩票中奖者，在这个系统中，卡中有所有彩票号码的人赢得彩票。后面一个通过代码解释。

```cpp
// C++ code to demonstrate the application of 
// includes() 

#include<bits/stdc++.h>
using namespace std;

int main()
{
    // lottery numbers
    vector<int> lottery = { 1, 4, 6, 3, 2, 54 , 32 };

    // Numbers in user's card
    vector<int> user = { 1, 2, 4, 6 };

    // sorting initial containers
    sort(lottery.begin(), lottery.end());
    sort(user.begin(), user.end());

    // using include() check if all elements 
    // of user are present as lottery numbers
    if(includes(lottery.begin(), lottery.end(), user.begin(), user.end()))
    cout << "User has won lottery ( all numbers are lottey numbers )";
    else 
    cout << "User has not won the lottery";

}
```

本文由 **[【曼吉特·辛格】](https://www.facebook.com/manjeet.04.singh)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。