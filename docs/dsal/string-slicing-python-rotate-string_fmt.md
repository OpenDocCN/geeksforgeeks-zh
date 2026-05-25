# Python 中的字符串切片旋转字符串

> 原文：`https://www.geeksforgeeks.org/string-slicing-python-rotate-string/`

给定大小为 n 的字符串，编写函数对字符串执行以下操作。

1.  将给定字符串的 d 个元素向左（或逆时针）旋转（其中 d <= n）。
2.  将给定字符串的 d 个元素向右（或顺时针）旋转（其中 d <= n）。

## 示例

```
Input : s = "GeeksforGeeks"
        d = 2
Output : Left Rotation  : "eksforGeeksGe" 
         Right Rotation : "ksGeeksforGee"

Input : s = "qwertyu" 
        d = 2
Output : Left rotation : "ertyuqw"
         Right rotation : "yuqwert"
```

这个问题我们已经有了解决方案，请参考[弦的左旋转和右旋转](https://www.geeksforgeeks.org/left-rotation-right-rotation-string-2/)链接。我们将使用[字符串切片](https://www.geeksforgeeks.org/interesting-facts-about-strings-in-python-set-2/)在 python 中快速解决这个问题。方法很简单，

1.  将字符串分成两部分，第一部分和第二部分。对于**左旋转**，`Lfirst = str[0:d]` 且 `Lsecond = str[d:]`。对于**右旋转**，`Rfirst = str[0:len(str)-d]` 且 `Rsecond = str[len(str)-d:]`。
2.  现在将这两部分的第二部分与第一部分**对应地**连接起来。

## 解决方案

```
# Function to rotate string left and right by d length
def rotate(input,d):
    # slice string in two parts for left and right 
    Lfirst = input[0 : d] 
    Lsecond = input[d :] 
    Rfirst = input[0 : len(input)-d] 
    Rsecond = input[len(input)-d : ]

    # now concatenate two parts together 
    print ("Left Rotation : ", (Lsecond + Lfirst) )
    print ("Right Rotation : ", (Rsecond + Rfirst))

# Driver program 
if __name__ == "__main__": 
    input = 'GeeksforGeeks'
    d=2
    rotate(input,d)
```

输出：

```
Left Rotation  : eksforGeeksGe 
Right Rotation : ksGeeksforGee
```