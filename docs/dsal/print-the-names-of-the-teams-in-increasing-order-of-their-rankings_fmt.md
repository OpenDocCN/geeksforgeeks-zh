# 按照排名的递增顺序打印队伍名称

> 原文: [https://www.geeksforgeeks.org/print-the-names-of-the-teams-in-increasing-order-of-their-rankings/](https://www.geeksforgeeks.org/print-the-names-of-the-teams-in-increasing-order-of-their-rankings/)

给定一个由字符串组成的 2D 数组 `arr[][]`，代表在一场涉及 `N` 队的比赛中进行的 `M` 场足球比赛的比分，任务是按照队的排名升序打印队名。

*   比赛规则如下:
    *   每队打 2 场比赛。
    *   获胜队得 2 分，失败队得 0 分。
    *   在平局的情况下，两队各得一分。
*   如果 `GD`、`GA`、和 `GF` 分别代表**目标差**、**目标对**、**目标对**。团队的排名按照以下优先顺序决定:
    *   **分 > `GD` > `GF` > 名的辞书顺序。**

**示例:**

> **输入:** `arr[][] = {{"Spain", "England", "3", "0"}, {"England", "France", "1", "1"}, {"Spain", "France", "0", "2"}}`，`N = 3`，`M = 3`
> **输出:** France Spain England
> *说明:3 场比赛后积分表各:*
>
> | 组 | 匹配已播放 | 女友 | 通用航空 | 权志龙 | 点 | 等级 |
> |---|---|---|---|---|---|---|
> | 西班牙 | Two | three | Two | one | Two | Two |
> | 英格兰 | Two | one | four | -3 | one | three |
> | 法国 | Two | three | one | Two | three | one |
>
> **输入:** `arr[][] = {{"Spain", "England", "3", "0"}, {"England", "France", "1", "1"}, {"Spain", "Spain", "0", "2"}}`，`N = 3`，`M = 3`
> **输出:** 无效输入

**方法:** 使用对字典进行多属性排序可以解决这个问题。
按照以下步骤解决问题:

*   遍历列表 `arr[][]`，如果 `arr[i][0]` 等于 `arr[i][1]`，则 `break` 并打印 `"无效"`。
*   初始化一个字典 `table` 来存储特定队伍的 `GA`、`GF` 和 `GD`。
*   遍历列表 `arr[][]` 并执行以下操作:
    *   将 `arr[i][0]` 的 `GF`、`table[arr[i][0]][0]` 增加 `arr[i][2]`，将 `arr[i][0]` 的 `GA`、`table[arr[i][0]][1]` 增加 `arr[i][3]`。
    *   将 `arr[i][1]`、`table[arr[i][1]][0]` 的 `arr[i][3]` 和 `arr[i][1]`、`table[arr[i][1]][1]` 的 `arr[i][2]` 递增。
    *   通过 `table[arr[i][0]][2] - table[arr[i][0]][3]`，更新 `arr[i][0]` 的 `GD`。
    *   将 `arr[i][1]` 的 `GD` 更新为 `table[arr[i][1]][2] - table[arr[i][1]][3]`。
    *   如果 `arr[i][2] == arr[i][3]`，则将 `table[arr[i][0]][0]` 和 `table[arr[i][1]][0]` 都增加 `1`。
    *   如果 `arr[i][2] > arr[i][3]`，则将 `table[arr[i][0]][0]` 增加 `2`。
    *   如果 `arr[i][2] < arr[i][3]`，则将 `table[arr[i][1]][0]` 增加 `2`。
*   现在，根据优先级 **分 > `GD` > `GF`** 对字典 `table` 进行排序，名称为:
    *   `table = sorted(table.items(), key=lambda r: (-r[1][0], -r[1][1], -r[1][2], r[0]))`
*   最后，打印排序表中的团队名称。

下面是上述方法的实现:

## Python 3

```python
# Python program for the above approach

# Function to find the ranking of teams
def RankTeams(arr):

    # Traverse the list arr
    for i in range(len(arr)):

        # arr[i][0] is equal to arr[i][1]
        if(arr[i][0] == arr[i][1]):
            print("Invalid")
            return

        # Convert the goal to integer
        arr[i][2] = int(arr[i][2])
        arr[i][3] = int(arr[i][3])

    # Stores the list of GD, GA, and GF
    table = {}

    # Traverse the list
    for i in range(len(arr)):

        # Store the list of GA, GF
        # and GD of first team
        li1 = [0] * 4

        # Store the list of GA, GF
        # and GD of second team
        li2 = [0] * 4

        # If arr[i][0] is in table
        if arr[i][0] in table:
            li1 = table[arr[i][0]]

        # If arr[i][1] is in table
        if arr[i][1] in table:
            li2 = table[arr[i][1]]

        # Increment GF by arr[i][2]
        li1[2] += arr[i][2]

        # Increment GA by arr[i][3]
        li1[3] += arr[i][3]

        # Increment GF by arr[i][3]
        li2[2] += arr[i][3]

        # Increment GA by arr[i][2]
        li2[3] += arr[i][2]

        # Update GD
        li1[1] = li1[2] - li1[3]
        li2[1] = li2[2] - li2[3]

        # If tie
        if(arr[i][2] == arr[i][3]):
            li1[0] += 1
            li2[0] += 1

        # If arr[i][0] wins
        elif(arr[i][2] > arr[i][3]):
            li1[0] += 2

        # If arr[i][1] wins
        elif(arr[i][2] < arr[i][3]):
            li2[0] += 2

        # Update list in table
        table[arr[i][0]] = li1
        table[arr[i][1]] = li2

    # Traverse the sorted table in the given priority
    for key, value in sorted(table.items(),
                             key = lambda r: (-r[1][0],
                                            -r[1][1],
                                            -r[1][2],
                                            r[0])):
        # Print the team name
        print(key, end ='\n')

# Driver Code

# Input
arr = [['Spain', 'England', '3', '0'],
       ['England', 'France', '1', '1'],
       ['Spain', 'France', '0', '2']]

RankTeams(arr)
```

**Output:**

```
France
Spain
England
```

***时间复杂度:** `O(N * log(N))`*
***辅助空间:** `O(N)`*