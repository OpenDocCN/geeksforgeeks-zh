# MS Access中的QBColor()和RGB()功能

> 原文: [https://www.geeksforgeeks.org/qbcolor-and-rgb-function-in-ms-access/](https://www.geeksforgeeks.org/qbcolor-and-rgb-function-in-ms-access/)

## QBColor()函数

QBColor()函数在MS Access中用于获取RGB色码。它返回一个Long数字，表示与指定颜色编号对应的RGB颜色代码。

### 语法

```sql
QBColor(color)
```

### 参数

该方法接受一个参数，如下所述：

*   `color`：是0-15范围内的整数。

### 返回值

返回RGB色码。

### 示例

**例1：** 色号为7的白色的RGB色码。

```sql
SELECT QBColor(7);
```

**输出：**

```sql

```

**例2：** 色号为2的绿色的RGB色码。

```sql
SELECT QBColor(2);
```

**输出：**

```sql

```

## RGB()函数

利用微软Access中的RGB()函数，可以得到一个代表RGB颜色值的长数字。

### 语法

```sql
RGB(red, green, blue)
```

### 参数

该方法接受三个参数，如下所述：

*   `red`：代表颜色中的红色成分。它是0–255（含）范围内的整数。
*   `green`：代表颜色中的绿色成分。它是0–255（含）范围内的整数。
*   `blue`：代表颜色中的蓝色成分。它是0–255（含）范围内的整数。

### 返回值

返回RGB颜色值。

### 示例

**例1：** 红色值为255，绿色值为255，蓝色值为255的白色的RGB颜色值。

```sql
SELECT RGB(255, 255, 255);
```

**输出：**

```sql

```

**例2：** 红色值为0，绿色值为255，蓝色值为0的绿色的RGB色码。

```sql
SELECT RGB(0, 255, 0);
```

**输出：**

```sql

```