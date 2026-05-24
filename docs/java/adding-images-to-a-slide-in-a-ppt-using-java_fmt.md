# 使用 Java 向 PPT 中的幻灯片添加图像

> 原文：[https://www.geeksforgeeks.org/adding-images-to-a-slide-in-a-ppt-using-java/](https://www.geeksforgeeks.org/adding-images-to-a-slide-in-a-ppt-using-java/)

## 方法介绍

在 Java 中，可以使用 `createPicture()` 方法将图像添加到 PPT 中的幻灯片。该方法属于 `XSLFSlide` 类。在内部，此方法接受字节数组格式的图像数据。

## 语法说明

**创建空幻灯片的语法**

```java
XMLSlideShow ppt = new XMLSlideShow();
```

**创建幻灯片的语法**

```java
XSLFSlide slide = ppt.createSlide();
```

下一个任务是读取希望插入的图像文件，然后使用 `IOUtils.toByteArray()` 方法（来自 `IOUtils` 类）将其转换为字节数组。

**使用 `addPicture()` 方法将图像添加到演示文稿中**

该方法需要两个参数：
*   要添加的图片的字节数组格式（在代码中写成 `byte[] photo`）。
*   一个静态变量，表示图像的文件格式。

**语法：**

```java
int idx = ppt.addPicture(photo, XSLFPictureData.PICTURE_TYPE_PNG);
```

最后，使用 `createPicture()` 方法将图像插入幻灯片。

```java
XSLFPictureShape pic = slide.createPicture(idx);
```

## 完整示例

```java
// Adding Images to a slide in a PPT using java
import java.io.File;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

import org.apache.poi.util.IOUtils;
import org.apache.poi.xslf.usermodel.XMLSlideShow;
import org.apache.poi.xslf.usermodel.XSLFPictureData;
import org.apache.poi.xslf.usermodel.XSLFPictureShape;
import org.apache.poi.xslf.usermodel.XSLFSlide;

public class InsertingImage {

    public static void main(String args[]) throws IOException {

        XMLSlideShow ppt = new XMLSlideShow();

        XSLFSlide slide = ppt.createSlide();

        File image = new File("C://Folder//codingisfun.png");

        byte[] photo = IOUtils.toByteArray(new FileInputStream(image));

        int idx = ppt.addPicture(photo, XSLFPictureData.PICTURE_TYPE_PNG);

        XSLFPictureShape pic = slide.createPicture(idx);

        // we are creating a file object
        File file = new File("insertingimg.pptx");
        FileOutputStream out = new FileOutputStream(file);

        // saving the changes to the file we created
        ppt.write(out);
        System.out.println("image is inserted");
        out.close();
    }
}
```

## 编译和执行命令

```bash
$ javac InsertingImage.java
$ java InsertingImage
```

## 输出

```
image is inserted
```

![](img/3ae50671213d82183111a9aed6f01239.png)