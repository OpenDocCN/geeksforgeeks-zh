# Java AWT Image RescaleOp 类详解与示例

> 原文：[https://www.geeksforgeeks.org/java-awt-image-rescaleop-class-in-java-with-examples/](https://www.geeksforgeeks.org/java-awt-image-rescaleop-class-in-java-with-examples/)

`RescaleOp` 是 `java.awt.image` 包中的一个类，实现了 `BufferedImageOp` 和 `RasterOp` 接口。此类通过将每个像素的样本值乘以一个比例因子，然后加上一个偏移量，对源图像中的数据执行逐个像素的重新缩放。缩放后的样本值被裁剪为目标图像中的最小/最大表示。这个类用于图片处理。

*   对于 `Raster`，对波段进行重新缩放。缩放常数集的数量可以是一个，在这种情况下，相同的常数将应用于所有波段，或者它必须等于源栅格波段的数量。
*   对于 `BufferedImage`，重新缩放对颜色进行操作。缩放常数集的数量可以是一个，在这种情况下，相同的常数被应用于所有颜色分量。
*   带有 `IndexColorModel` 的图像不能重新缩放。
*   如果在构造函数中指定了一个 `RenderingHints` 对象，当需要颜色转换时，可以使用颜色渲染提示和抖动提示。

## 语法

```java
public class RescaleOp
    extends Object
    implements BufferedImageOp, RasterOp
```

## 构造方法

*   `public RescaleOp(float[] scaleFactors, float[] offset, RenderingHints hints)`: 具有所需的 `scaleFactors` 和 `offset` 的构造函数。`hints` 可以为 `null`。
*   `public RescaleOp(float scaleFactor, float offset, RenderingHints hints)`: 带有单个缩放因子和偏移的构造函数。`hints` 可以为 `null`。

## 方法

*   `BufferedImage createCompatibleDestImage(BufferedImage src, ColorModel destCM)`: 此方法创建一个带区大小和数量正确的归零目标图像。
*   `WritableRaster createCompatibleDestRaster(Raster src)`: 在给定该源的情况下，该方法创建具有正确大小和波段数的零目标栅格。
*   `BufferedImage filter(BufferedImage src, BufferedImage dst)`: 此方法重新缩放源 `BufferedImage`。
*   `WritableRaster filter(Raster src, WritableRaster dst)`: 此方法重新调整源栅格中的像素数据。
*   `Rectangle2D getBounds2D(BufferedImage src)`: 此方法返回重新缩放的目标图像的边界框。
*   `Rectangle2D getBounds2D(Raster src)`: 此方法返回重新缩放后的目标栅格的边界框。
*   `int getNumFactors()`: 此方法返回此重缩放中使用的缩放因子和偏移量的数量。
*   `float[] getOffset(float[] offset)`: 此方法返回给定数组中的偏移量。
*   `Point2D getPoint2D(Point2D srcPt, Point2D dstPt)`: 此方法返回源中给定点的目标点的位置。
*   `RenderingHints getRenderingHints()`: 此方法返回此操作的渲染提示。
*   `float[] getScaleFactors(float[] scaleFactors)`: 此方法返回给定数组中的比例因子。

## 示例 1

在给定的示例中，我们将使用单个比例因子和偏移来设置图片的对比度。以下代码将亮度降低 25%，像素暗 3.6 倍。

### Java 代码

```java
import java.awt.image.*;
import java.net.*;
import java.awt.*;
import java.io.*;
import javax.imageio.*;

public class DemoOnRescaleOp {

    public static void main(String[] args) throws Exception
    {
        // picking the image from the url
        URL url
            = new URL("https://media.geeksforgeeks.org"
                      + "/wp-content/uploads/geeksforgeeks-9.png");

        // Reading the image from url
        Image image = ImageIO.read(url);

        // Setting up the scaling and
        // the offset parameters for processing
        RescaleOp rop = new RescaleOp(.75f, 3.6f, null);

        // applying the parameters on the image
        // by using filter() method, it takes the
        // Source and destination objects of buffered reader
        // here our destination object is null
        BufferedImage bi
            = rop.filter((BufferedImage)image, null);
        ImageIO.write(bi, "png",
                      new File("processed.png"));
    }
}
```

**输入：**![Original Image](img/c6e0a168008bc4a43314f9fb895e5c7c.png)

**输出：**

![processed.png](img/696fdbdde7bb7125cfde7daf66b9e469.png)

使用的方法 `filter(BufferedImage src, BufferedImage dst)` 将源 `BufferedImage` 重新缩放到目标 `BufferedImage`，并返回相同的值。在这里，我们没有提到任何目的地图像，并写 `null` 来代替它。这里，我们已经为 `BufferedImage` 对象分配了重新缩放的结果。

## 示例 2

在给定的示例中，我们将使用比例因子和偏移量的数组来设置图片的对比度。每个数组的大小为 3，表示每个像素的红色、绿色和蓝色分量。在下面的代码中，整体亮度增加了 45%，所有像素颜色都向绿色偏移。偏移 150 会将每个像素的绿色分量增加 58.6%（150/256）。请记住，偏移会添加到颜色值中，因此必须是 0 到 255 之间的值，而不是比例因子，比例因子是百分比。

### Java 代码

```java
import java.awt.image.*;
import java.net.*;
import java.awt.*;
import java.io.*;
import javax.imageio.*;

public class DemoOnRescaleOp {

    public static void main(String[] args) throws Exception
    {
        // picking the image from the URL
        URL url
            = new URL("https://media.geeksforgeeks.org"
                      + "/wp-content/uploads/geeksforgeeks-9.png");

        // Reading the image from url
        Image image = ImageIO.read(url);

        // Setting up the scaling and
        // the offset parameters for processing
        float[] factors = new float[] {
            // RGB each value for 1 color
            1.45f, 1.45f, 1.45f
        };

        float[] offsets = new float[] {
            0.0f, 150.0f, 0.0f
        };

        RescaleOp rop
            = new RescaleOp(factors, offsets, null);

        // applying the parameters on the image
        // by using filter() method, it takes the
        // Source and destination objects of buffered reader
        // here our destination object is null
        BufferedImage bi
            = rop.filter((BufferedImage)image, null);
        ImageIO.write(bi, "png",
                      new File("processed.png"));
    }
}
```

**输入：**![Original Image](img/c6e0a168008bc4a43314f9fb895e5c7c.png)

**输出：**

![](img/7a9ca0d9fd976d82705cd2779eed2722.png)

使用的方法 `filter(BufferedImage src, BufferedImage dst)` 将源 `BufferedImage` 重新缩放到目标 `BufferedImage`，并返回相同的值。在这里，我们没有提到任何目的地图像，并写 `null` 来代替它。这里，我们已经为 `BufferedImage` 对象分配了重新缩放的结果。

**参考：**[https://docs.oracle.com/javase/9/docs/api/java/awt/image/RescaleOp.html](https://docs.oracle.com/javase/9/docs/api/java/awt/image/RescaleOp.html)