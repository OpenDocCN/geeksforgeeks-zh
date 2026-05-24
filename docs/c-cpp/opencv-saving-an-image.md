# OpenCV |保存图像

> 原文:[https://www.geeksforgeeks.org/opencv-saving-an-image/](https://www.geeksforgeeks.org/opencv-saving-an-image/)

本文旨在学习如何使用 OpenCv 在 CPP 中将图像从一个位置保存到系统上任何其他期望的位置。使用 OpenCV，我们可以生成任何颜色的空白图像。

所以，让我们深入挖掘，用完整的解释来理解这个概念。

### **代码:用于将图像保存到 OpenCV 中任意位置的 C++ 代码。**

```cpp
// c++ code explaining how to
// save an image to a defined
// location in OpenCV

// loading library files
#include <highlevelmonitorconfigurationapi.h>
#include <opencv2\highgui\highgui.hpp>
#include <opencv2\opencv.hpp>

using namespace cv;
using namespace std;

int main(int argc, char** argv)
{

    // Reading the image file from a given location in system
    Mat img = imread("..path\\abcd.jpg");

    // if there is no image
    // or in case of error
    if (img.empty()) {
        cout << "Can not open or image is not present" << endl;

        // wait for any key to be pressed
        cin.get();
        return -1;
    }

    // You can make any changes
    // like blurring, transformation

    // writing the image to a defined location as JPEG
    bool check = imwrite("..path\\MyImage.jpg", img);

    // if the image is not saved
    if (check == false) {
        cout << "Mission - Saving the image, FAILED" << endl;

        // wait for any key to be pressed
        cin.get();
        return -1;
    }

    cout << "Successfully saved the image. " << endl;

    // Naming the window
    String geek_window = "MY SAVED IMAGE";

    // Creating a window
    namedWindow(geek_window);

    // Showing the image in the defined window
    imshow(geek_window, img);

    // waiting for any key to be pressed
    waitKey(0);

    // destroying the creating window
    destroyWindow(geek_window);

    return 0;
}
```

**输入:**
![](img/0ff7949adf85b8e12d688c944b0e613c.png)
**输出:**
![](img/943832d543ad6957fa797a38774d27f0.png)

### **说明:**

```cpp
// Reading the image file from a given location in system
Mat img = imread("..path\\abcd.jpg");

// if there is no image
// or in case of error
if (img.empty()) {
    cout << "Can not open or image is not present" << endl;

    // wait for any key to be pressed
    cin.get();
    return -1;
}
```

这部分代码从我们给它的路径中读取图像。它会处理任何错误(如果发生的话)。如果该路径上没有图像，则**“无法打开或图像不存在”**信息将显示，按下任意键，窗口将退出。

```cpp
// writing the image to a defined location as JPEG
bool check = imwrite("..path\\MyImage.jpg", img);

// if the image is not saved
if (check == false) {
    cout << "Mission - Saving the image, FAILED" << endl;

    // wait for any key to be pressed
    cin.get();
    return -1;
}

cout << "Successfully saved the image. " << endl;
```

这部分代码将图像写入定义的路径，如果不成功，它将生成**“任务–保存图像，失败”**消息，按任意键，窗口将退出。其余代码将创建窗口并在其中显示图像。它将继续在窗口中显示图像，直到按键被按下。最后，窗户会被摧毁。