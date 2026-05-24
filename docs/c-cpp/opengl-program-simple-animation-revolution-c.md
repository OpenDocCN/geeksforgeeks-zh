# C

中简单动画(Revolution)的 OpenGL 程序

> 原文:[https://www . geesforgeks . org/OpenGL-program-simple-animation-revolution-c/](https://www.geeksforgeeks.org/opengl-program-simple-animation-revolution-c/)

[**OpenGL**](https://www.geeksforgeeks.org/getting-started-with-opengl/) 是一个跨语言、跨平台的渲染 2D 和 3D 矢量图形的 API。利用这个，我们可以做很多设计以及动画。下面是使用 **OpenGL** 制作的简单动画。
**进场:**
要让画面动起来，需要了解一个用来显示的功能的工作流程，即**glClear(GL _ COLOR _ BUFFER _ BIT)**。它的任务是在一定时间后(通常在 1/30 秒或 1/60 秒后)用默认值清除屏幕。因此，如果坐标发生任何变化，那么它将看起来是移动的，因为人眼只能分辨相隔 1/16 秒的图像(视觉暂留)。
现在圆的坐标是 X = r*cos(θ)和 Y = r*sin(θ)或者对于椭圆 X = rx*cos(θ)和 Y = ry*cos(θ)，其中 rx 和 ry 是 X 和 Y 方向的半径， **θ** 是角度。
如果我们以很小的增量(比如 1 度)将 **θ** 从 0 变化到 2 *π(360 度)，并在那个坐标上画点，我们就可以做一个完整的圆或椭圆。我们也可以通过改变 **θ** (角度)的起止值来做半圆或任意圆弧或椭圆。
这些概念用来绘制如下动画:

*   7 个水平椭圆部分和 3 个垂直完整椭圆以及 1 个外圆和 1 个外椭圆用于显示通过调整 **θ** 和半径绘制的轨道。
*   画一条垂直线来构成这个图形。然后，为了使它移动，给出了另一个循环，其中 j 的值以非常小的量变化，以使运动更平滑。
*   因为，我们必须使所有的点以相同的运动类型运动，以保持图形在一起，所以运动方程，即**glvertex 2i(x/2–600 * cos(j)，y/2–100 * sin(j))**在循环的每个内部**中给出，因此它可以应用于所有的点。**

**在 Ubuntu 操作系统上工作:**

```cpp
gcc filename.c -lGL -lGLU -lglut -lm 
where filename.c is the name of the file
with which this program is saved.
```

下面是在 C.
中的实现

## C

```cpp
// C Program to illustrate
// OpenGL animation for revolution

#include<stdio.h>
#include<GL/glut.h>
#include<math.h>

// global declaration
int x, y;
float i, j;

// Initialization function
void myInit (void)
{
    // Reset background color with black (since all three argument is 0.0)
    glClearColor(0.0, 0.0, 0.0, 1.0);

    // Set picture color to green (in RGB model)
    // as only argument corresponding to G (Green) is 1.0 and rest are 0.0
    glColor3f(0.0, 1.0, 0.0);

    // Set width of point to one unit
    glPointSize(1.0);
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();

    // Set window size in X- and Y- direction
    gluOrtho2D(-780, 780, -420, 420);
}

// Function to display animation
void display (void)
{
    // Outer loop to make figure moving
    // loop variable j iterated up to 10000,
    // indicating that figure will be in motion for large amount of time
    // around 10000/6.29 = 1590 time it will revolve
    // j is incremented by small value to make motion smoother
    for (j = 0; j < 10000; j += 0.01)
    {
        glClear(GL_COLOR_BUFFER_BIT);
        glBegin(GL_POINTS);

        // Iterate i up to 2*pi, i.e., 360 degree
        // plot point with slight increment in angle,
        // so, it will look like a continuous figure

        // Loop is to draw outer circle
        for (i = 0;i < 6.29;i += 0.001)
        {
            x = 200 * cos(i);
            y = 200 * sin(i);
            glVertex2i(x, y);

            // For every loop, 2nd glVertex function is
            // to make smaller figure in motion
            glVertex2i(x / 2 - 600 * cos(j), y / 2 - 100 * sin(j));
        }

        // 7 loops to draw parallel latitude
        for (i = 1.17; i < 1.97; i += 0.001)
        {
            x = 400 * cos(i);
            y = -150 + 300 * sin(i);
            glVertex2i(x, y);
            glVertex2i(x / 2 - 600 * cos(j), y / 2 - 100 * sin(j));
        }

        for (i = 1.07; i < 2.07; i += 0.001)
        {
            x = 400 * cos(i);
            y = -200 + 300 * sin(i);
            glVertex2i(x, y);
            glVertex2i(x / 2 - 600 * cos(j), y / 2 - 100 * sin(j));
        }

        for (i = 1.05; i < 2.09; i += 0.001)
        {
            x = 400 * cos(i);
            y = -250 + 300 * sin(i);
            glVertex2i(x, y);
            glVertex2i(x / 2 - 600 * cos(j), y / 2 - 100 * sin(j));
        }

        for (i = 1.06; i < 2.08; i += 0.001)
        {
            x = 400 * cos(i);
            y = -300 + 300 * sin(i);
            glVertex2i(x, y);
            glVertex2i(x / 2 - 600 * cos(j), y / 2 - 100 * sin(j));
        }

        for (i = 1.10; i < 2.04; i += 0.001)
        {
            x = 400 * cos(i);
            y = -350 + 300 * sin(i);
            glVertex2i(x, y);
            glVertex2i(x / 2 - 600 * cos(j), y / 2 - 100 * sin(j));
        }

        for (i = 1.16; i < 1.98; i += 0.001)
        {
            x = 400 * cos(i);
            y = -400 + 300 * sin(i);
            glVertex2i(x, y);
            glVertex2i(x / 2 - 600 * cos(j), y / 2 - 100 * sin(j));
        }

        for (i = 1.27; i < 1.87; i += 0.001)
        {
            x = 400 * cos(i);
            y = -450 + 300 * sin(i);
            glVertex2i(x, y);
            glVertex2i(x / 2 - 600 * cos(j), y / 2 - 100 * sin(j));
        }

        // Loop is to draw vertical line
        for (i = 200; i >=- 200; i--)
        {
            glVertex2i(0, i);
            glVertex2i(-600 * cos(j), i / 2 - 100 * sin(j));
        }

        // 3 loops to draw vertical ellipse (similar to longitude)
        for (i = 0;i < 6.29; i += 0.001)
        {
            x = 70 * cos(i);
            y = 200 * sin(i);
            glVertex2i(x, y);
            glVertex2i(x / 2 - 600 * cos(j), y / 2 - 100 * sin(j));
        }

        for (i = 0; i < 6.29; i += 0.001)
        {
            x = 120 * cos(i);
            y = 200 * sin(i);
            glVertex2i(x, y);
            glVertex2i(x / 2 - 600 * cos(j), y / 2 - 100 * sin(j));
        }

        for (i = 0; i < 6.29; i += 0.001)
        {
            x = 160 * cos(i);
            y = 200 * sin(i);
            glVertex2i(x, y);
            glVertex2i(x / 2 - 600 * cos(j), y / 2 - 100 * sin(j));
        }

        // Loop to make orbit of revolution
        for (i = 0; i < 6.29; i += 0.001)
        {
            x = 600 * cos(i);
            y = 100 * sin(i);
            glVertex2i(x, y);
        }
        glEnd();
        glFlush();
    }
}

// Driver Program
int main (int argc, char** argv)
{
    glutInit(&argc, argv);

    // Display mode which is of RGB (Red Green Blue) type
    glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB);

    // Declares window size
    glutInitWindowSize(1360, 768);

    // Declares window position which is (0, 0)
    // means lower left corner will indicate position (0, 0)
    glutInitWindowPosition(0, 0);

    // Name to window
    glutCreateWindow("Revolution");

    // Call to myInit()
    myInit();
    glutDisplayFunc(display);
    glutMainLoop();
}
```

本文由[阿迪蒂亚·库马尔](https://www.linkedin.com/in/aditya-kumar-837315100/)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。