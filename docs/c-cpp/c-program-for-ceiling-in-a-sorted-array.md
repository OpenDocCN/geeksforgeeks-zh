# 排序数组中天花板的 C++ 程序

> 原文:[https://www . geeksforgeeks . org/c-program-for-top-in-a-sorted-array/](https://www.geeksforgeeks.org/c-program-for-ceiling-in-a-sorted-array/)

给定一个已排序的数组和值 x，x 的上限是数组中大于或等于 x 的最小元素，下限是小于或等于 x 的最大元素，假设数组按非递减顺序排序。写高效函数求楼层和天花板的 x.
**例:**

```cpp
For example, let the input array be {1, 2, 8, 10, 10, 12, 19}
For x = 0:    floor doesn't exist in array,  ceil  = 1
For x = 1:    floor  = 1,  ceil  = 1
For x = 5:    floor  = 2,  ceil  = 8
For x = 20:   floor  = 19,  ceil doesn't exist in array
```

在下面的方法中，我们只实现了上限搜索功能。楼层搜索也可以用同样的方式实现。
**方法 1(线性搜索)**
搜索 x 上限的算法:
1)如果 x 小于或等于数组中的第一个元素，则返回 0(第一个元素的索引)
2)否则线性搜索索引 I，使 x 位于 arr[i]和 arr[i+1]之间。
3)如果在步骤 2 中没有找到索引 I，则返回-1

## C++

// C++ implementation of above approach#include <bits stdc="">using namespace std;

/*函数获取 arr 中 x 的上限索引[低..high]*/
int ceil search(int arr[]，int low，int high，int x)
{ 0

int I；

/*如果 x 小于或等于第一个元素，
则返回第一个元素*/
如果(x < = arr【低】)返回低；*否则，线性搜索上限值(i=“低；”i <高；i++){ if(arr[I]= " = " x)I；如果 x 位于 arr[i]和 arr[i+1]之间，包括 arr[i+1]，则& & > = x)
返回 I+1；
}

/*如果我们到达这里，那么 x 大于数组的最后一个元素
，在这种情况下返回-1 */
返回-1；

/*驱动程序代码*/
int main()
{
int arr[]= { 1，2，8，10，10，12，19 }；
int n = sizeof(arr)/sizeof(arr[0])；
int x = 3；
int index = ceilSearch(arr，0，n-1，x)；
if(index = =-1)
cout<<“数组中不存在”< < x < <的“天花板”；else cout < <“天花板的”< < x < <“是”< < arr【指数】；返回 0；} //这是 rathbhupendra [tabbyending]贡献的代码

**输出:**

```cpp
ceiling of 3 is 8
```

**时间复杂度:** O(n)
**方法 2(二分搜索法)**
这里不用线性搜索，而是用二分搜索法来找出索引。二分搜索法将时间复杂度降低到 0(Logn)。

=></bits>

## C++

#include <bits stdc="">using namespace std;

/*函数获取 arr 中 x 的上限
的索引[低..high]*/
int ceiliser arch(int arr[]，int low，int high，int x)
{
int mid；

/*如果 x 小于
或等于第一个元素，
则返回第一个元素*/
如果(x < = arr【低】)返回低；*如果 x 大于最后一个元素，则-1 如果(x > arr【高】)
返回-1；= >

/*获取 arr 中间元素的索引[低..高]*/
中=(低+高)/2；/*低+(高–低)/2 */

/*如果 x 与中间元素相同，
则返回 mid */
如果(arr[mid] == x)
则返回 mid；

/*如果 x 大于 arr[mid]，
则 arr[mid + 1]是 x 的上限
或者上限位于 arr[mid+1…high] */
否则 If(arr[mid]<x){ If(mid+1<= 1 high&&x<= " arr[mid "+1])返回 mid 1；else ceilsearch(arr，1，high，x)；} *如果小于 arr[mid]，则 arr[mid]上限为或位于 arr[low...mid-1]{ if(mid->= low&&x>arr【mid-1】)
返回 mid；
否则
返回 ceilSearch(arr，低，中-1，x)；
}

//驱动程序代码
int main()
{
int arr[]= { 1，2，8，10，10，12，19 }；
int n = sizeof(arr)/sizeof(arr[0])；
int x = 20；
int index = ceilSearch(arr，0，n-1，x)；
if(index = =-1)
cout<<“数组中不存在”< < x < <的“天花板”；else cout < <“天花板的”< < x < <“是”< < arr【指数】；返回 0；} //此代码由 rathbhupendra [tabbyending]提供

**输出:**

```cpp
Ceiling of 20 doesn't exist in array 
```

时间复杂度:O(Logn)

**相关文章:**
[排序数组中的 floor](https://www.geeksforgeeks.org/floor-in-a-sorted-array/)
[在未排序数组中查找 Floor 和 ceil](https://www.geeksforgeeks.org/find-floor-ceil-unsorted-array/)
如果您发现以上代码/算法中有任何一个不正确，或者找到更好的方法来解决相同的问题，或者想要为 Floor 实现共享代码，请写评论。

更多详情请参考完整文章[排序数组](https://www.geeksforgeeks.org/ceiling-in-a-sorted-array/)中的上限！

=></bits>