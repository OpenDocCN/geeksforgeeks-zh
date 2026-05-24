# OpenCV C++ 程序创建单色空白图像

> 原文:[https://www . geesforgeks . org/opencv-c-plus-plus-program-to-create-single-color-blank-image/](https://www.geeksforgeeks.org/opencv-c-plus-plus-program-to-create-a-single-colored-blank-image/)

以下是对 C++ 代码的解释，该代码使用工具 OpenCV 在 C++ 中创建一个单一颜色的空白图像。

**要知道的事情:**

(1)代码只会在 Linux 环境下编译。

(2)要在 windows 中运行，请使用文件:“blank.o”并在 cmd 中运行。但是，如果它不运行(系统架构中的问题)，那么通过对代码进行适当和明显的更改，在窗口中编译它，例如:使用<iostream.h>代替<iostream>。</iostream></iostream.h>

(3)编译命令:g++-w blank . CPP-o blank ` pkg-config–libs opencv `等

(4)运行命令:。/文章

在运行代码之前，请确保您的系统上安装了 OpenCV。

**代码片段:**

```cpp
// Title: Create a coloured image in C++ using OpenCV.

// highgui - an easy-to-use interface to 
// video capturing, image and video codecs,
// as well as simple UI capabilities.
#include "opencv2/highgui/highgui.hpp"

// Namespace where all the C++ OpenCV 
// functionality resides. 
using namespace cv;

// For basic input / output operations. 
// Else use macro 'std::' everywhere.
using namespace std;

int main()
{
    // To create an image
    // CV_8UC3 depicts : (3 channels,8 bit image depth
    // Height  = 500 pixels, Width = 1000 pixels
    // (0, 0, 100) assigned for Blue, Green and Red 
    //             plane respectively. 
    // So the image will appear red as the red 
    // component is set to 100.
    Mat img(500, 1000, CV_8UC3, Scalar(0,0, 100));

    // check whether the image is loaded or not
    if (img.empty()) 
    {
        cout << "\n Image not created. You"
                     " have done something wrong. \n";
        return -1;    // Unsuccessful.
    }

    // first argument: name of the window
    // second argument: flag- types: 
    // WINDOW_NORMAL If this is set, the user can 
    //               resize the window.
    // WINDOW_AUTOSIZE If this is set, the window size
    //                is automatically adjusted to fit 
    //                the displayed image, and you cannot
    //                change the window size manually.
    // WINDOW_OPENGL  If this is set, the window will be
    //                created with OpenGL support.
    namedWindow("A_good_name", CV_WINDOW_AUTOSIZE);

    // first argument: name of the window
    // second argument: image to be shown(Mat object)
    imshow("A_good_name", img);

    waitKey(0); //wait infinite time for a keypress

    // destroy the window with the name, "MyWindow"
    destroyWindow("A_good_name");            

    return 0;
}
// END OF PROGRAM

```

 **往期发文:**
[https://www . geeksforgeeks . org/opencv-c-program-to-blur-an-image/](https://www.geeksforgeeks.org/opencv-c-program-to-blur-an-image/)

关于作者:

阿迪蒂亚·普拉卡什是瓦多达拉印度信息技术学院![Aditya](img/7f989f45758a9a92d71e2ed9f6d7af18.png)的本科生。他主要用 C++ 编写代码。他的座右铭是:目前为止一切顺利。他打板球，看超级英雄电影，踢足球，是一个回答问题的忠实粉丝。

**如果你也想在这里展示你的博客，请查看[博客](http://geeksquiz.com/gblog/)在极客博客上的客座博文。**