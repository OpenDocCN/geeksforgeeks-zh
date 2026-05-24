# OpenCV C++ 程序播放视频

> 原文:[https://www . geesforgeks . org/opencv-c-plus-plus-program-to-play-a-video/](https://www.geeksforgeeks.org/opencv-c-plus-plus-program-to-play-a-video/)

以下是使用工具 OpenCV 用 C++ 播放视频的 C++ 代码说明。
要知道的事情:
(1)代码只会在 Linux 环境下编译。
(2)要在 windows 中运行，请使用文件:“play_video.o”并在 cmd 中运行。但是，如果它不运行(系统架构有问题)，那么通过对代码进行适当且明显的更改，在
窗口中编译它，例如:使用
< iostream.h >代替< iostream >。
(3)编译命令:g++-w vid . CPP-o vid ` pkg-config–libs opencv `
(4)运行命令:。/vid
(5)请确认视频:“bubble . MP4”在同一个位置。
在运行代码之前，请确保您的系统上安装了 OpenCV。
代码片段:

```cpp
#include "opencv2/highgui/highgui.hpp"
// highgui - an interface to video and image capturing.

#include 
// The header files for performing input and output.

using namespace cv;
// Namespace where all the C++ OpenCV functionality resides.

using namespace std;
// For input output operations.

int main()
{
    VideoCapture cap("Bumpy.mp4");
    // cap is the object of class video capture that tries to capture Bumpy.mp4
    if ( !cap.isOpened() )  // isOpened() returns true if capturing has been initialized.
    {
        cout << "Cannot open the video file. \n";
        return -1;
    }

    double fps = cap.get(CV_CAP_PROP_FPS); //get the frames per seconds of the video
    // The function get is used to derive a property from the element.
    // Example:
    // CV_CAP_PROP_POS_MSEC :  Current Video capture timestamp.
    // CV_CAP_PROP_POS_FRAMES : Index of the next frame.

    namedWindow("A_good_name",CV_WINDOW_AUTOSIZE); //create a window called "MyVideo"
    // first argument: name of the window.
    // second argument: flag- types: 
    // WINDOW_NORMAL : The user can resize the window.
    // WINDOW_AUTOSIZE : The window size is automatically adjusted to fitvthe displayed image() ), and you cannot change the window size manually.
    // WINDOW_OPENGL : The window will be created with OpenGL support.

    while(1)
    {
        Mat frame;
        // Mat object is a basic image container. frame is an object of Mat.

        if (!cap.read(frame)) // if not success, break loop
        // read() decodes and captures the next frame.
        {
            cout<<"\n Cannot read the video file. \n";
            break;
        }

        imshow("A_good_name", frame);
        // first argument: name of the window.
        // second argument: image to be shown(Mat object).

        if(waitKey(30) == 27) // Wait for 'esc' key press to exit
        { 
            break; 
        }
    }

    return 0;
}
// END OF PROGRAM
```

关于作者:

阿迪蒂亚·普拉卡什是瓦多达拉印度信息技术学院![Aditya](img/7f989f45758a9a92d71e2ed9f6d7af18.png)的本科生。他主要用 C++ 编写代码。他的座右铭是:目前为止一切顺利。他打板球，看超级英雄电影，踢足球，是一个回答问题的忠实粉丝。

**如果你也想在这里展示你的博客，请查看[博客](http://geeksquiz.com/gblog/)在极客博客上的客座博文。**