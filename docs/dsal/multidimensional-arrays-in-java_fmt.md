# Java 中的多维数组

> 原文：[https://www.geeksforgeeks.org/multidimensional-arrays-in-java/](https://www.geeksforgeeks.org/multidimensional-arrays-in-java/)

[数组 Java 中的基础](https://www.geeksforgeeks.org/arrays-in-java/)

`多维数组`可以简单的定义为数组的数组。多维数组中的数据以表格形式存储（按行主顺序）。

**语法：**

> `数据类型[][]...[] 数组名 = new 数据类型[大小1][大小2]...[大小N];`

其中：

*   `数据类型`：数组中要存储的数据类型。例如：`int`、`char` 等。
*   `维度`：创建的数组的维度。比如：1D、2D 等。
*   `数组名`：数组名
*   `大小1`、`大小2`、…、`大小N`：各维度的大小。

**示例：**

```
Two dimensional array:
int[][] twoD_arr = new int[10][20];

Three dimensional array:
int[][][] threeD_arr = new int[10][20][30];
```

**多维数组的大小**：一个多维数组可以存储的元素总数可以通过乘以所有维度的大小来计算。

**例如：**
数组 `int[][] x = new int[10][20]` 总共可以存储 `(10*20) = 200` 个元素。
同样，数组 `int[][][] x = new int[5][10][20]` 总共可以存储 `(5*10*20) = 1000` 个元素。

## 二维数组（2D 数组）

二维数组是多维数组的最简单形式。为了便于理解，二维数组可以看作一维数组的数组。

**间接声明方式：**

*   **声明 – 语法：**

```
data_type[][] array_name = new data_type[x][y];
For example: int[][] arr = new int[10][20];
```

*   **初始化 – 语法：**

```
array_name[row_index][column_index] = value;
For example: arr[0][0] = 1;
```

**示例：**

```
class GFG {
    public static void main(String[] args)
    {
        int[][] arr = new int[10][20];
        arr[0][0] = 1;

        System.out.println("arr[0][0] = " + arr[0][0]);
    }
}
```

**输出：**

```
arr[0][0] = 1
```

**直接声明方式：**

**语法：**

```
data_type[][] array_name = {
                             {valueR1C1, valueR1C2, ....},
                             {valueR2C1, valueR2C2, ....}
                           };
For example: int[][] arr = {{1, 2}, {3, 4}};
```

**示例：**

```
class GFG {
    public static void main(String[] args)
    {
        int[][] arr = { { 1, 2 }, { 3, 4 } };

        for (int i = 0; i < 2; i++)
            for (int j = 0; j < 2; j++)
                System.out.println("arr[" + i + "][" + j + "] = "
                                   + arr[i][j]);
    }
}
```

**输出：**

```
arr[0][0] = 1
arr[0][1] = 2
arr[1][0] = 3
arr[1][1] = 4
```

### 访问二维数组的元素

二维数组中的元素通常用 `x[i][j]` 表示，其中 `i` 是行号，`j` 是列号。

**语法：**

```
x[row_index][column_index]
```

例如：

```
int[][] arr = new int[10][20];
arr[0][0] = 1;
```

上面的示例表示第一行第一列中的元素。

**注**：在数组中，如果数组的大小为 `N`，其索引将从 `0` 到 `N-1`。因此，对于 `row_index` 2，实际行数是 `2+1 = 3`。

**示例：**

```
class GFG {
    public static void main(String[] args)
    {
        int[][] arr = { { 1, 2 }, { 3, 4 } };

        System.out.println("arr[0][0] = " + arr[0][0]);
    }
}
```

**输出：**

```
arr[0][0] = 1
```