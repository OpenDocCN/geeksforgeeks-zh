# OpenCV C++ 程序模糊图像

> 原文:[https://www . geesforgeks . org/opencv-c-program-to-blur-an-image/](https://www.geeksforgeeks.org/opencv-c-program-to-blur-an-image/)

以下是对使用 OpenCV 工具在 C++ 中模糊图像的 C++ 代码的解释。 [](https://media.geeksforgeeks.org/wp-content/cdn-uploads/bat.jpg) 

**要知道的事情:**

(1)代码只会在 Linux 环境下编译。

(2)编译命令:g++-w article . CPP-o article ` pkg-config–libs opencv `等

(3)运行命令:。/文章

(4)图像 bat.jpg 必须与代码在同一目录中。

在运行代码之前，请确保您的系统上安装了 OpenCV。

```cpp
// Title: OpenCV C++ Program to blur an image.
// Import the core header file
#include <opencv2/core/core.hpp> 

// core - a compact module defining basic data structures,
// including the dense multi-dimensional array Mat and 
// basic functions used by  all other modules.

// highgui - an easy-to-use interface to video 
// capturing, image and video codecs, as well
// as simple UI capabilities.
#include <opencv2/highgui/highgui.hpp>

// imgproc - an image processing module that 
// includes linear and non-linear image filtering,
// geometrical image transformations (resize, affine
// and perspective warping, generic table-based 
// remapping) color space conversion, histograms, 
// and so on.
#include <opencv2/imgproc/imgproc.hpp>

// The stdio.h header defines three variable types, 
// several macros, and various functions for performing
// input and output.
#include <stdio.h>
#include <iostream>

// Namespace where all the C++ OpenCV functionality resides
using namespace cv;

using namespace std;

// We can also use 'namespace std' if need be.

int main() // Main function
{
    // read the image data in the file "MyPic.JPG" and 
    // store it in 'img'
    Mat image = imread("bat.jpg", CV_LOAD_IMAGE_UNCHANGED); 

    // Mat object is a basic image container.
    // imread: first argument denotes the image to be loaded
    // the second arguments specifies the image format.
    // CV_LOAD_IMAGE_UNCHANGED (<0) loads the image as is
    // CV_LOAD_IMAGE_GRAYSCALE ( 0) loads the image as an
    //                         intensity one
    // CV_LOAD_IMAGE_COLOR (>0) loads the image in the 
    //                          BGR format
    // If the second argument is not specified, it is 
    // implied CV_LOAD_IMAGE_COLOR

    // Check for no data
    if (! image.data ) 
    {
        cout << "Could not open or find the image.\n";
        return -1; // unsuccessful
    }

    // Function to blur the image
    // first argument: input source
    // second argument: output source
    // third argument: blurring kernel size
    blur(image,image,Size(10,10)); 

    // Create a window
    // first argument: name of the window
    // second argument: flag- types:
    // WINDOW_NORMAL If this is set, the user can resize the 
    //                window.
    // WINDOW_AUTOSIZE If this is set, the window size is 
    //                 automatically adjusted to fit the 
    //                 displayed image() ), and you cannot 
    //                 change the window size manually.
    // WINDOW_OPENGL If this is set, the window will be
    //              created with OpenGL support.
    namedWindow( "bat", CV_WINDOW_AUTOSIZE ); 

    // Displays an image in the specified window.
    // first argument: name of the window
    // second argument: image to be shown(Mat object)
    imshow( "bat", image ); 

    waitKey(0); // Wait infinite time for a keypress

    return 0; // Return from the main function
}

```

[OpenCV Python 程序模糊图像](https://www.geeksforgeeks.org/opencv-python-program-to-blur-an-image/)

关于作者:

阿迪蒂亚·普拉卡什是瓦多达拉印度信息技术学院![Aditya](img/f1efc84e1327d1f39e82c99b49cb6e47.png)的本科生。他主要用 C++ 编写代码。他的座右铭是:目前为止一切顺利。他打板球，看超级英雄电影，踢足球，是一个回答问题的忠实粉丝。

如果你也想在这里展示你的博客，请查看 [GBlog](http://geeksquiz.com/gblog/) 在 GeeksforGeeks 上的客座博文。