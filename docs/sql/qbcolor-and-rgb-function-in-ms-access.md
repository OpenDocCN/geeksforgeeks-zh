# MS 接入中的 QBColor()和 RGB()功能

> 原文:[https://www . geesforgeks . org/qbcolor-and-RGB-function in-ms-access/](https://www.geeksforgeeks.org/qbcolor-and-rgb-function-in-ms-access/)

**1。【功能:**
QBColor()功能在 MS Access 中用于获取 RGB 色码。它返回一个 Long 数字，表示与指定颜色编号对应的 RGB 颜色代码。

**语法:**

```sql
QBColor (color)
```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **颜色:**是 0-15 范围内的整数。

**返回:**返回 RGB 色码。

**例-1 :** 色号为 7 的白色的 RGB 色码。

```sql
SELECT  QBColor( 7);
```

**输出:**

```sql
12632256 
```

**例-2 :** 色号为 2 的绿色的 RGB 色码。

```sql
SELECT  QBColor( 2);
```

**输出:**

```sql
32768 
```

**2。RGB()函数:**
利用微软 Access 中的 RGB()函数，得到一个代表 RGB 颜色值的长数字。

**语法:**

```sql
RGB (red, green, blue)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **红色:**代表颜色中的红色成分。它是 0–255(含)范围内的整数。

*   **绿色:**代表颜色中的青红成分。它是 0–255(含)范围内的整数。

*   **蓝色:**代表颜色的蓝色成分。它是 0–255(含)范围内的整数。

**返回:**返回 RGB 颜色值。

**例-1 :** 红色值为 255，绿色值为 255，蓝色值为 255 的白色的 RGB 颜色值。

```sql
SELECT  RGB(255, 255, 255);
```

**输出:**

```sql
16777215 
```

**例-2 :** 红色值为 0，绿色值为 255，蓝色值为 0 的绿色的 RGB 色码。

```sql
SELECT  RGB(0, 255, 0);
```

**输出:**

```sql
65280 
```