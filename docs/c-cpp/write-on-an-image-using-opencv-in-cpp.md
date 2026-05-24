# 在 C++ 中使用 openCV 在图像上书写

> 原文:[https://www . geesforgeks . org/write-on-a-image-using-opencv-in-CPP/](https://www.geeksforgeeks.org/write-on-an-image-using-opencv-in-cpp/)

在本文中，我们将讨论如何使用 [OpenCV](https://www.geeksforgeeks.org/opencv-c-program-face-detection/) [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 在图像上书写。来自 OpenCV C++ 库的函数 **putText()** 将用于在图像上书写文本。

**程序 1:**

下面的程序展示了如何在空白背景图像上书写文字:

## c++

T5

```cpp
// C++ program to demonstrate the
// above approach
#include <iostream>
#include <opencv2/core/core.hpp>

// Library to include for
// drawing shapes
#include <opencv2/highgui/highgui.hpp>
#include <opencv2/imgproc.hpp>
using namespace cv;
using namespace std;

// Driver Code
int main(int argc, char** argv)
{
    // Create a blank image of size
    // (500 x 500) with white background
    // (B, G, R) : (255, 255, 255)
    Mat image(500, 500, CV_8UC3,
              Scalar(255, 255, 255));

    // Check if the image is created
    // successfully.
    if (!image.data) {
        cout << "Could not open or"
             << " find the image"
             << endl;
        return 0;
    }

    // Writing over the Image
    Point org(30, 100);
    putText(image, "Text On Image", org,
            FONT_HERSHEY_SCRIPT_COMPLEX, 2.1,
            Scalar(0, 0, 255), 2, LINE_AA);

    // Show our image inside a window.
    imshow("Output", image);
    waitKey(0);

    return 0;
}
```