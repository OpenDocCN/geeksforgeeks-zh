# STD::c++ 中的 next _ 置换和 prev _ 置换

> 哎哎哎:# t0]https://www . geeksforgeeks . org/STD next _ switching-prev _ switching-c/

**标准::下一个 _ 排列**

它用于将范围[第一个，最后一个]中的元素重新排列到下一个字典顺序更大的排列中。一个排列就是 N 个中的每一个！元素可以采用的可能排列(其中 N 是该范围内的元素数量)。不同的排列可以根据它们在字典上的相互比较来排序。代码的复杂度为 O(n*n！)这也包括打印所有排列。

**语法:**

```cpp
template 
bool next_permutation (BidirectionalIterator first,
 BidirectionalIterator last);
Parameters: 
first, last : Bidirectional iterators to the initial
and final positions of the sequence. The range 
used is [first, last), which contains all the elements 
between first and last, including the element pointed 
by first but not the element pointed by last.

return value: 
true : if the function could rearrange 
the object as a lexicographically greater permutation.
Otherwise, the function returns false to indicate that 
the arrangement is not greater than the previous, 
but the lowest possible (sorted in ascending order).
```

**应用:**next _ replacement 是为给定的值数组寻找下一个字典上更大的值。

**示例:**

```cpp
Input : next permutation of 1 2 3 is 
Output : 1 3 2

Input : next permutation of 4 6 8 is 
Output : 4 8 6
```

## c++

```cpp
// C++ program to illustrate
// next_permutation example

// this header file contains next_permutation function
#include <algorithm>
#include <iostream>
using namespace std;

int main()
{
    int arr[] = { 1, 2, 3 };

    sort(arr, arr + 3);

    cout << "The 3! possible permutations with 3 elements:\n";
    do {
        cout << arr[0] << " " << arr[1] << " " << arr[2] << "\n";
    } while (next_permutation(arr, arr + 3));

    cout << "After loop: " << arr[0] << ' '
         << arr[1] << ' ' << arr[2] << '\n';

    return 0;
}
```

**输出:**

```cpp
The 3! possible permutations with 3 elements:
1 2 3
1 3 2
2 1 3
2 3 1
3 1 2
3 2 1
After loop: 1 2 3
```

**STD::prev _ switching**

它用于将范围[第一个，最后一个]中的元素重新排列成先前的字典顺序排列。一个排列就是 N 个中的每一个！元素可以采用的可能排列(其中 N 是该范围内的元素数量)。不同的排列可以根据它们在字典上的相互比较来排序。

**语法:**

```cpp
template 
bool prev_permutation (BidirectionalIterator first,
 BidirectionalIterator last );
parameters: 
first, last : Bidirectional iterators to the initial
and final positions of the sequence. The range 
used is [first, last), which contains all the
elements between first and last, including 
the element pointed by first but not the element
pointed by last.

return value: 
true : if the function could rearrange 
the object as a lexicographically smaller permutation.
Otherwise, the function returns false to indicate that 
the arrangement is not less than the previous, 
but the largest possible (sorted in descending order).
```

**应用:**prev _ replacement 是为给定的值数组寻找先前的字典上较小的值。

**示例:**

```cpp
Input : prev permutation of 3 2 1 is 
Output : 3 1 2 

Input : prev permutation of 8 6 4 is 
Output :8 4 6
```

## c++

```cpp
// C++ program to illustrate
// prev_permutation example

// this header file contains prev_permutation function
#include <algorithm>

#include <iostream>
using namespace std;
int main()
{
    int arr[] = { 1, 2, 3 };

    sort(arr, arr + 3);
    reverse(arr, arr + 3);

    cout << "The 3! possible permutations with 3 elements:\n";
    do {
        cout << arr[0] << " " << arr[1] << " " << arr[2] << "\n";
    } while (prev_permutation(arr, arr + 3));

    cout << "After loop: " << arr[0] << ' ' << arr[1]
         << ' ' << arr[2] << '\n';

    return 0;
}
```

**输出:**

```cpp
The 3! possible permutations with 3 elements:
3 2 1
3 1 2
2 3 1
2 1 3
1 3 2
1 2 3
After loop: 3 2 1
```