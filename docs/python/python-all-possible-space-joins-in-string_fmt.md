# Python–字符串中所有可能的空间连接

> 原文: [https://www.geeksforgeeks.org/python-all-possible-space-joins-in-string/](https://www.geeksforgeeks.org/python-all-possible-space-joins-in-string/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，即我们需要在每个可能的单词结尾构造单个空格的字符串。这种应用可以出现在我们需要执行测试的领域中。让我们讨论执行这项任务的某些方法。

**方法#1: 使用循环 + `join()`**
这是可以执行这个任务的蛮力方式。在本文中，我们使用 `join()` 执行形成所有可能的连接的任务，并使用循环执行遍历所有字符串的任务。

```py
# Python3 code to demonstrate working of 
# All possible space joins in String
# Using loop + join()

# initializing string
test_str = 'Geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# All possible space joins in String
# Using loop + join()
res = []
temp = test_str.split(' ')             
strt_idx = 0
lst_idx = len(temp)
for idx in range(len(temp)-1):       
    frst_wrd = "".join(temp[strt_idx : idx + 1])   
    scnd_wrd = "".join(temp[idx + 1 : lst_idx])
    res.append(frst_wrd + " " + scnd_wrd)

# printing result 
print("All possible spaces List : " + str(res)) 
```

**输出:**

> 原始字符串是: Geeksforgeeks is best for geeks
> 所有可能的空间列表: ['Geeksforgeeks is best for geeks', 'Geeksforgeeks is best for geeks', 'Geeksforgeeks is best for geeks']