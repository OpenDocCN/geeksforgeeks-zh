# 将 PGM 格式的图像内容反转(负片化)的程序

> 原文:[https://www . geesforgeks . org/c-program-to-invert-making-negative-a-image-content-in-PGM-format/](https://www.geeksforgeeks.org/c-program-to-invert-making-negative-an-image-content-in-pgm-format/)

给定一个 PGM 格式的图像，任务是反转 PGM 格式的图像颜色(制作负片)。
**先决条件:**[c-程序写图像格式](https://www.geeksforgeeks.org/c-program-to-write-an-image-in-pgm-format/)

PGM 图像代表灰度图形图像。PGM 是便携式灰色地图的缩写。该图像文件包含一个或多个 PGM 图像文件。

**数据块的意义:**用于创建 PGM 映像的数据如下:

*   P2 是一种灰色图像
*   4 4 是图像尺寸
*   255 是最大灰度
*   因为，图像数据以矩阵格式存储，并且每行指示图像行，并且该值指示相应像素的灰度级。最大值(255)用于白色，最小值(0)用于黑色。

**示例:**

```cpp
P2
4 4
255
255 0   255 0
0   255 0   255
100 200 150 100
50  150 200 0

```

输入图像看起来像:
![pgm image](img/ca0d839dc8500075a630d5fb9ffa8434.png)

**如何反转图像数据？**
反转灰度图像意味着使用(255–gray lavel)改变图像的灰度，即如果像素的灰度为 150，则负片图像的灰度为(255–150)= 105。这意味着 255 将随着 0 而改变，0 将随着 255 而改变。它改变了黑色和白色在灰色中的比例。
**例:**

```cpp
P2
4 4
255
0   255 0   255
255 0   255 0
155 55  105 155
205  105 55 255

```

输出图像看起来像:
![invert image](img/c413010a44efa3692a8519242f063808.png)

```cpp
#include<stdio.h>
#include<process.h>
#include<stdlib.h>
void main()
{ 
    int i, j, temp = 0;
    int width = 4, height = 4;

    // Suppose the 2D Array to be converted to Image 
    // is as given below 
    int img[10][10] = {
        {255, 0, 255, 0},
        {0, 255, 0, 255},
        {100, 200, 150, 100},
        {50, 150, 200, 0}
    };

    // file pointer to store image file
    FILE *pgmfile, *negative_pgmfile;

    // Open an image file
    pgmfile = fopen("img.pgm", "wb");

    // Open an negative image file
    negative_pgmfile = fopen("neg_img.pgm", "wb");

    fprintf(pgmfile, "P2 \n %d %d \n 255 \n", width, height);
    fprintf(negative_pgmfile, "P2 \n %d %d \n 255 \n", width, height);

    // Create PGM image using pixel value
    for(i = 0; i < height; i++) {
        for(j = 0; j < width; j++)
            fprintf(pgmfile, "%d ", img[i][j]);
        fprintf(pgmfile, "\n");
    }

    // Create negative PGM image using pixel value
    for(i = 0; i < height; i++) {
        for(j = 0; j < width; j++) 
            fprintf(negative_pgmfile, "%d ", (255 - img[i][j]));
        fprintf(negative_pgmfile, "\n");
    }

    fclose(pgmfile);
    fclose(negative_pgmfile);
}
```

**输出:**
原图
![pgm image](img/ca0d839dc8500075a630d5fb9ffa8434.png)

负(反转)图像
![invert image](img/c413010a44efa3692a8519242f063808.png)