# 如何在安卓中改变进度条颜色？

> 原文：[https://www.geeksforgeeks.org/how-to-change-the-progressbar-color-in-android/](https://www.geeksforgeeks.org/how-to-change-the-progressbar-color-in-android/)

在本文中，我们将看到如何在 `Android` 中为 [`ProgressBar`](https://www.geeksforgeeks.org/progressbar-in-kotlin/) 添加颜色。`Android` `ProgressBar` 是一个用户界面控件，用于指示操作的进度。比如下载一个文件，在网上上传一个文件我们可以看到 `ProgressBar` 估计剩余的运行时间。注意在本文中，我们将使用 `Java` 和 `XML` 来设置颜色。

## 逐步实施

### 第一步：新建项目

*   请参考 [如何在 Android Studio 中创建/启动一个新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 来创建 Android Studio 新项目。
*   注意选择 `Java` 作为编程语言。

### 步骤 2：创建自定义进度条

*   转到 `app > res > drawable`，右键单击 > 新建 > Drawable 资源文件，并将文件命名为 `progress_bg`。
*   在 `XML` 文件中添加一个 `<rotate>` 标签及一些属性（见代码）。
*   在 `<rotate>` 标签内创建一个 `<shape>` 标签，并在其中创建 `<size>` 和 `<gradient>` 标签。
*   这些标签的属性在以下代码中给出。
*   以下是 `progress_bg.xml` 文件的代码。

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--use rotate tag to rotate the drawable-->
<rotate
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:pivotX="50%"
    android:pivotY="50%"
    android:toDegrees="360">

    <!--shape tag is used to
        build a shape in XML-->
    <shape
        android:innerRadiusRatio="3"
        android:shape="ring"
        android:thicknessRatio="8"
        android:useLevel="false">

        <!--set the size of the shape-->
        <size
            android:width="76dip"
            android:height="76dip" />

        <!--set the color gradients
            of the shape-->
        <gradient
            android:angle="0"
            android:endColor="#00ffffff"
            android:startColor="#447a29"
            android:type="sweep"
            android:useLevel="false" />
    </shape>

</rotate>
```