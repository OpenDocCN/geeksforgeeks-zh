# Java 中使用 OpenCV 的图像处理 | 第 15 集 (锐度增强)

> 原文: [https://www.geeksforgeeks.org/image-processing-using-opencv-in-java-set-14-sharpness-enhancement/](https://www.geeksforgeeks.org/image-processing-using-opencv-in-java-set-14-sharpness-enhancement/)

在本文中，我们将学习如何使用 OpenCV 库增强图像的清晰度。
为了增强清晰度，我们将使用[高斯滤波器](https://en.wikipedia.org/wiki/Gaussian_filter)。高斯滤波器降低了图像中的噪声，使其看起来更好（或更高的分辨率）。

## 环境设置

首先，我们需要为 Java 设置 OpenCV，我们建议同样使用 Eclipse，因为它易于使用和设置。安装参考 [http://docs.opencv.org/2.4/doc/tutorials/introduction/java_eclipse/java_eclipse.html](http://docs.opencv.org/2.4/doc/tutorials/introduction/java_eclipse/java_eclipse.html)。

## 锐度增强所需的方法

### 1. `GaussianBlur()`

该方法驻留在 OpenCV 的 `Imgproc` 包中。

语法：
```java
Imgproc.GaussianBlur(source, destination, new Size(0, 0), sigmaX)
```
参数：
- `source` - 源图像
- `destination` - 目标图像
- `new Size(0, 0)` - 高斯核大小
- `sigmaX` - X方向上的高斯核标准差

### 2. `addWeighted()`

该方法驻留在 OpenCV 的 `Core` 包中。

语法：
```java
Core.addWeighted(InputArray src1, alpha, src2, beta, gamma, OutputArray dst)
```
参数：
- `src1` - 第一个输入数组
- `alpha` - 第一个数组元素的权重
- `src2` - 第二个输入数组，其大小和通道数与 `src1` 相同
- `beta` - 第二个数组元素的权重
- `gamma` - 添加到每个和的标量
- `dst` - 输出数组，其大小和通道数与输入数组相同

### 3. `imread()`

该方法用于将图像读取为由 OpenCV 渲染的 `Mat` 对象。

语法：
```java
Imgcodecs.imread(filename);
```
参数：
- `filename`：图像文件的文件名。如果图像在另一个目录中，则必须提及图像的完整路径。

### 4. `imwrite()`

该方法用于将 `Mat` 对象写入图像文件。

语法：
```java
Imgcodecs.imwrite(filename, mat_img);
```
参数：
- `filename`：图像文件的文件名。如果图像在另一个目录中，则必须提及图像的完整路径。
- `mat_img`：生成的 `Mat` 对象。

## 完整示例代码

```java
package ocv;

import org.opencv.core.Core;
import org.opencv.core.Mat;
import org.opencv.core.Size;
import org.opencv.imgcodecs.Imgcodecs;
import org.opencv.imgproc.Imgproc;

public class Main {
    public static void main(String[] args) {
        try {
            // For proper execution of native libraries
            // Core.NATIVE_LIBRARY_NAME must be loaded before
            // calling any of the opencv methods
            System.loadLibrary(Core.NATIVE_LIBRARY_NAME);

            // Input image
            Mat source = Imgcodecs.imread("E://input.jpg", Imgcodecs.CV_LOAD_IMAGE_COLOR);
            Mat destination = new Mat(source.rows(), source.cols(), source.type());

            // filtering
            Imgproc.GaussianBlur(source, destination, new Size(0, 0), 10);
            Core.addWeighted(source, 1.5, destination, -0.5, 0, destination);

            // writing output image
            Imgcodecs.imwrite("E://output.jpg", destination);
        } catch (Exception e) {
        }
    }
}
```

## 输出与注意事项

**注意：** 该代码在在线 IDE 中无法工作，因为它需要硬盘中的图像。

输出：
```
input.jpg
output.jpg
```
尝试注意分辨率上的微小改进。

## 作者与投稿

本文由 [Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](http://www.write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。