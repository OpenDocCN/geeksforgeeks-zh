# 使用 C++ 在 OpenCV 中读取和显示图像

> 原文:[https://www . geesforgeks . org/reading-and-display-in-image-open cv-using-c/](https://www.geeksforgeeks.org/reading-and-displaying-an-image-in-opencv-using-c/)

在本文中，我们将讨论如何在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中使用 [OpenCV(开源计算机视觉)](https://www.geeksforgeeks.org/top-7-most-popular-computer-vision-tools-in-2020/)打开图像。与 python 不同，C++ 中不需要任何额外的库。OpenCV C++ 自带这个神奇的图像容器 Mat，可以为我们处理一切。从标准 C++ 程序中看到的唯一变化是包含了**命名空间** **cv** ，它包含了所有的 OpenCV 函数、[类](https://www.geeksforgeeks.org/c-classes-and-objects/)和[数据结构](https://www.geeksforgeeks.org/data-structures/)。在 OPenCV 中读取和显示图像需要以下功能:

**<u>imread()</u> :** 该函数用于读取图像，取以下 2 个参数:

*   **文件名:**要加载的图像的完整地址是字符串类型。例如:“C:\ user \ downloads \ sample . jpg”
*   **标志:**它是一个可选参数，决定了读取图像的模式，可以取几个值，如
    *   **IMREAD_COLOR:** 默认模式，在该模式下，如果没有提供参数，将加载图像。它以 BGR 格式加载图像。
    *   **IMREAD_UNCHANGED:** 它以原始形式加载图像。它还包括阿尔法通道，如果存在于图像内部。
    *   **IMREAD _ GRADE:**它将图像加载为灰度图像。

**输出:**将图像作为垫子对象返回

用法:

> //读取图像文件
> Mat image = IMREAD(“C:/users/downloads/default . jpg”，IMREAD _ grade)；

**<u>imshow()</u> :** 此功能用于显示图像，取以下两个参数:

*   **winname** 或**窗口名称:**这是显示图像的窗口标题，类型为字符串。
*   **图像:**这是要显示的图像。它的类型是 **Mat** ，C++ 图像容器。

**输出:**创建显示图像的窗口。

用法:

> //在创建的窗口内显示我们的图像
> imshow(“窗口名称”，图像)；

**Mat::empty():** 这有助于我们在 **imread()** 函数无法加载图像或图像不存在于指定路径时进行错误处理，并告诉我们 Mat 容器是否为空。

**WaitKey():** 该功能通过保持窗口打开直到用户按下某个键来帮助长时间显示图像。

下面是同样的程序:

## C++

```cpp
// C++ program for the above approach
#include <iostream>
#include <opencv2/opencv.hpp>
using namespace cv;
using namespace std;

// Driver code
int main(int argc, char** argv)
{
    // Read the image file as
    // imread("default.jpg");
    Mat image = imread("Enter the Address"
                       "of Input Image",
                       IMREAD_GRAYSCALE);

    // Error Handling
    if (image.empty()) {
        cout << "Image File "
             << "Not Found" << endl;

        // wait for any key press
        cin.get();
        return -1;
    }

    // Show Image inside a window with
    // the name provided
    imshow("Window Name", image);

    // Wait for any keystroke
    waitKey(0);
    return 0;
}
```

**输入图像:**

[![](img/10f1071b87c14dc0cbb1403f2139fab8.png)](https://media.geeksforgeeks.org/wp-content/uploads/20201213022405/default.jpg)

**输出图像:**

[![](img/22334418d5ba0814abd3d00307f05eb6.png)](https://media.geeksforgeeks.org/wp-content/uploads/20201213022946/ss.jpg)