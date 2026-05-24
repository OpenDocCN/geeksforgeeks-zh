# OpenCV |加载视频

> 原文:[https://www.geeksforgeeks.org/opencv-loading-video/](https://www.geeksforgeeks.org/opencv-loading-video/)

本文旨在学习如何在 OpenCV 中显示视频。这样做是一个简单的任务，就像显示为一个单一的图像。但是在这里，帧的显示必须作为序列的一部分循环读取。

让我们一行一行地详细了解整个过程。

**代码:**

```cpp
CvCapture* capture = cvCreateFileCapture("...input\\video_file.avi");
```

cvCreateFileCapture()函数取视频的 AVI 文件的名称/路径(作为参数加载)。然后返回一个指向 CvCapture 结构的指针。关于视频文件的所有信息都包含在这个结构中。当以这种方式创建时，CvCapture 结构被初始化到视频的开头。

**代码:**

```cpp
frame = cvQueryFrame(capture);
```

视频文件的读取一旦进入 while(1)循环就开始了。cvQueryFrame()将指向 CvCapture 结构的指针作为参数。然后，下一个视频帧被带入内存，这实际上是 CvCapture 结构的一部分。那个特定的帧需要指针。cvQueryFrame 使用 CvCapture 结构中已经分配的内存，这与为图像分配实际内存的 cvLoadImage 不同。因此，调用 cvReleaseImage()对于这个“帧”指针来说不是必需的。当 CvCapture 结构被释放时，帧图像存储器将被释放。

**代码:**

```cpp
c = cvWaitKey(10);

if (c == 27)
    break;
```

帧显示后等待 10ms。如果用户按下特定的键，c 将被设置为按下的键的 ASCII 值。否则，它被设置为“-1”。如果用户按下 ESC 键(ASCII 值为 27)，则代码将退出读取循环。否则，经过 10ms 后，再次执行循环。

### **代码:使用 OpenCV 显示视频。**

```cpp
// Using OpenCV to display video

#include <highlevelmonitorconfigurationapi.h>
#include <opencv2\highgui\highgui.hpp>
#include <opencv2\opencv.hpp>

using namespace cv;
using namespace std;

iint main(int argc, char** argv)
{
    // creating window
    cvNamedWindow("Display_video", CV_WINDOW_AUTOSIZE);

    // loading video
    CvCapture* capture = cvCreateFileCapture("..input\\tree.avi");
    IplImage* frame;

    while (1) {
        frame = cvQueryFrame(capture);

        if (!frame)
            break;

        cvShowImage("Display_video", frame);

        char c = cvWaitKey(0);

        if (c == 27)
            break;
    }
    cvReleaseCapture(&capture);

    // destroying window
    cvDestroyWindow("Display_video");
}
```

**输出:**

```cpp
VIDEO OUTPUT IN THE DISPLAY WINDOW
```

在上面的代码中我们实际上是在以一种非常智能的方式控制视频的速度，我们只是依靠 cvWaitKey()中的计时器来控制要加载的帧的节奏。