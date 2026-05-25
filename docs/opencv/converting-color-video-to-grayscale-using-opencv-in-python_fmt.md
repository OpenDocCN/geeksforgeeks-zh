# 使用 Python 中的 OpenCV 将彩色视频转换为灰度

> 原文：[https://www.geeksforgeeks.org/converting-color-video-to-grayscale-using-opencv-in-python/](https://www.geeksforgeeks.org/converting-color-video-to-grayscale-using-opencv-in-python/)

[`OpenCV`](https://www.geeksforgeeks.org/opencv-python-tutorial/) 是一个巨大的开源库，用于计算机视觉、机器学习和图像处理。它可以处理图像和视频来识别物体、人脸，甚至是人类的笔迹。在本文中，我们将看到如何将彩色视频转换为灰度格式。

## 进场：
1.  导入 `cv2` 模块。
2.  使用 `cv2.VideoCapture()` 方法读取要转换的视频文件。
3.  运行无限循环。
4.  在循环中，使用 `read()` 方法提取视频的帧。
5.  将帧传递给 `cv2.cvtColor()` 方法，使用 `cv2.COLOR_BGR2GRAY` 作为参数将其转换为灰度。
6.  使用 `cv2.imshow()` 方法显示帧。

## 示例：
假设我们将视频文件 `CountdownTimer.mov` 作为输入。

## 蟒蛇 3
```py
# importing the module
import cv2

# reading the video
source = cv2.VideoCapture('Countdown Timer.mov')

# running the loop
while True:

# extracting the frames
    ret, img = source.read()

# converting to gray-scale
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

# displaying the video
    cv2.imshow("Live", gray)

# exiting the loop
    key = cv2.waitKey(1)
    if key == ord("q"):
        break

# closing the window
cv2.destroyAllWindows()
source.release()
```

**输出：**
转换后的灰度视频将显示在名为 "Live" 的窗口中。