# C

中的 setfillstyle()和 floodfill()

> 原文:[https://www.geeksforgeeks.org/setfillstyle-floodfill-c/](https://www.geeksforgeeks.org/setfillstyle-floodfill-c/)

头文件 graphics.h 包含 **setfillstyle()** 功能，用于设置当前填充图案和填充颜色。**洪水填充()**功能用于填充封闭区域。当前填充图案和填充颜色用于填充该区域。

**语法:**

```cpp
void setfillstyle(int pattern, int color)

void floodfill(int x, int y, int border_color)

```

**示例:**

```cpp
Input : pattern = HATCH_FILL, Color = RED 
        circle : x = 250, y = 250, radius = 100 
        floodfill : x = 250, y = 250, border color =15
Output : 

Input : pattern = LTSLASH_FILL, Color = RED
       rectangle : left = 200, top = 200, right = 450, bottom = 450
       floodfill : x = 201, y = 201, border_color = 15
Output :

```

下表显示了对应于颜色的 INT 值:

```cpp
COLOR               INT VALUES
-------------------------------
BLACK                   0
BLUE                    1
GREEN                   2
CYAN                    3   
RED                     4
MAGENTA                 5
BROWN                   6 
LIGHTGRAY               7 
DARKGRAY                8
LIGHTBLUE               9
LIGHTGREEN             10
LIGHTCYAN              11
LIGHTRED               12
LIGHTMAGENTA           13
YELLOW                 14
WHITE                  15

```

下表显示了对应于模式的整数值:

```cpp
PATTERN              INT VALUES
-------------------------------
EMPTY_FILL               0
SOLID_FILL               1
LINE_FILL                2
LTSLASH_FILL             3   
SLASH_FILL               4
BKSLASH_FILL             5
LTBKSLASH_FILL           6 
HATCH_FILL               7 
XHATCH_FILL              8
INTERLEAVE_FILL          9
WIDE_DOT_FILL           10
CLOSE_DOT_FILL          11
USER_FILL               12

```

下面是 setfillstyle()和 floodfill()函数的实现:

```cpp
// C Implementation for setfillstyle
// and floodfill function
#include <graphics.h>

// driver code
int main()
{
    // gm is Graphics mode which is 
    // a computer display mode that
    // generates image using pixels.
    // DETECT is a macro defined in
    // "graphics.h" header file
    int gd = DETECT, gm;

    // initgraph initializes the 
    // graphics system by loading
    // a graphics driver from disk
    initgraph(&gd, &gm, " ");

    // center and radius of circle
    int x_circle = 250;
    int y_circle = 250;
    int radius=100;

    // setting border color
    int border_color = WHITE;

    // set color and pattern
    setfillstyle(HATCH_FILL,RED);

    // x and y is a position and
    // radius is for radius of circle
    circle(x_circle,y_circle,radius);

    // fill the color at location 
    // (x, y) with in border color
    floodfill(x_circle,y_circle,border_color);

    getch();

    // closegraph function closes the
    // graphics mode and deallocates
    // all memory allocated by 
    // graphics system 
    closegraph();

    return 0;
}
```

输出: