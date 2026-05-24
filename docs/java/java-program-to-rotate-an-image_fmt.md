# 旋转图像的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-rotate-an-image/](https://www.geeksforgeeks.org/java-program-to-rotate-an-image/)

## 问题陈述

将图像顺时针旋转 90 度，在这里我们将使用 `BufferedImage` 类和 `Color` 的一些内置方法。

## 执行操作所需的类

*   为了读写图像文件，我们必须导入 `File` 类。这个类通常表示文件和目录路径名。
*   为了处理错误，我们使用 `IOException` 类。
*   为了保存图像，我们使用 `BufferedImage` 类来创建 `BufferedImage` 对象。这个对象用于在内存中存储图像。
*   为了读写图像，我们将导入 `ImageIO` 类。这个类包含用于读写图像的静态方法。
*   `Graphics2D` 类扩展了 `Graphics` 类，以提供对几何、坐标变换、颜色管理和文本布局的更复杂控制。这是在 Java TM 平台上呈现 2D 形状、文本和图像的基本类。

## 示例代码

```java
// Java program to rotate image by 90 degrees clockwise

// Importing classes from java.awt package for
// painting graphics and images
import java.awt.Graphics2D;
import java.awt.image.BufferedImage;
// Importing input output classes
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;

// Main class
public class GFG {

// Method 1
    // To return rotated image
    public static BufferedImage rotate(BufferedImage img)
    {

// Getting Dimensions of image
        int width = img.getWidth();
        int height = img.getHeight();

// Creating a new buffered image
        BufferedImage newImage = new BufferedImage(
            img.getWidth(), img.getHeight(), img.getType());

// creating Graphics in buffered image
        Graphics2D g2 = newImage.createGraphics();

// Rotating image by degrees using toradians()
        // method
        // and setting new dimension t it
        g2.rotate(Math.toRadians(90), width / 2,
                  height / 2);
        g2.drawImage(img, null, 0, 0);

// Return rotated buffer image
        return newImage;
    }

// Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // try block to check for exceptions
        try {

// Reading original image
            BufferedImage originalImg = ImageIO.read(
                new File("D:/test/Image.jpeg"));

// Getting and Printing dimensions of original
            // image
            System.out.println("Original Image Dimension: "
                               + originalImg.getWidth() + "x"
                               + originalImg.getHeight());

// Creating a subimage of given dimensions
            BufferedImage SubImg = rotate(originalImg);

// Printing Dimensions of new image created
            // (Rotated image)
            System.out.println("Cropped Image Dimension: "
                               + SubImg.getWidth() + "x"
                               + SubImg.getHeight());

// Creating new file for rotated image
            File outputfile
                = new File("D:/test/ImageRotated.jpeg");

// Writing image in new file created
            ImageIO.write(SubImg, "jpg", outputfile);

// Printing executed message
            System.out.println(
                "Image rotated successfully: "
                + outputfile.getPath());
        }

// Catch block to handle the exception
        catch (IOException e) {

// Print the line number where exception
            // occurred
            e.printStackTrace();
        }
    }
}
```