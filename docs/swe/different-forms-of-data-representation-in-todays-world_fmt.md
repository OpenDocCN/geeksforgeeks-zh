# 当今世界不同形式的数据表示

> 原文: [https://www.geeksforgeeks.org/different-forms-of-data-representation-in-todays-world/](https://www.geeksforgeeks.org/different-forms-of-data-representation-in-todays-world/)

## 概述
数据可以是表示具体结果的任何东西，也可以是任何数字、文本、图像、音频、视频等。例如，如果你以人类为例，那么一个人的数据，如姓名、个人 id、国家、职业、银行账户细节等。是重要的数据。数据可以分为三类，即个人数据、公共数据和私人数据。

## 数据表示的形式
目前信息有以下不同形式。

1.  数字
2.  文本
3.  图像
4.  音频
5.  视频

我们一个一个来讨论。

### 1. 数字
数字不是用 ASCII 表示，而是用位模式表示。数字被直接转换为二进制表示以指定数学运算。0 和 1 用于表示数字数据。人类通常使用的数字系统是十进制。
**数字文件格式：**
整数、定点数、日期、布尔值、十进制数等。

**例：**
你可能遇到过用“展开式”表达数字的不同方式。例如，如果你想以展开形式写数字 60338，你可以把它写成 `60338=60000+300+30+8`。

### 2. 文本
文本也表示为位模式或比特序列（例如 `0001111`）。分配了各种类型的比特来表示文本符号。可以使用一种每个数字代表一个字符的代码将文本转换为二进制。
**文本文件格式：**
`.doc`、`.docx`、`.pdf`、`.rtf`、`.txt` 等。

**例：**
字母 `a` 有二进制数 `0110 0001`。

### 3. 音频
音频信号是声音或音乐的表示。音频不同于一切，即不同于文本、数字和图像。音频是数字信号的一系列二进制数。它是连续的，但不是离散的。
**音频文件格式：**
MP3、M4A 音频文件类型、FLAC、WAV、WMA、AAC 等。

### 4. 视频
视频是指录制、播放、复制或回放。视频既可以产生，也可以是连续的，有时它是运动中产生的多个图像的组合。
**视频文件格式：**
MP4、MOV、AVI、FLV 等。

### 5. 图像
图像也表示为位模式。图像由像素矩阵组成，每个像素具有不同的像素值，其中每个像素表示为点。图片的大小取决于它的分辨率。考虑一个简单的黑白图像。如果 1 是黑色（或开），0 是白色（或关），那么可以使用二进制创建一个简单的黑白图片。
**图像文件格式：**
图像可以是 jpeg、PNG、TIFF、GIF 等格式。

```
Image Data Representation -
one bit per pixel (0 or 1) - two possible colors
two bits per pixel (00 to 11) - four possible colors
three bits per pixel (000 to 111) - eight possible colors
four bits per pixel (0000 to 1111) - 16 possible colors

Example : 
An image of height 100, width 300, color depth 16 bits
100 × 300 = 30,000
30,000 × 16 = 4,80,000 bits
4,80,000 bits ÷ 8 = 60,000 bytes
60,000 ÷ 1000 = 60 kilobytes
Result : 60KB
```