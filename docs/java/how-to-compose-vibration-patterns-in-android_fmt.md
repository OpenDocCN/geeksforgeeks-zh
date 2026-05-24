# 如何在安卓中合成振动模式？

> 原文：[https://www.geeksforgeeks.org/how-to-compose-vibration-patterns-in-android/](https://www.geeksforgeeks.org/how-to-compose-vibration-patterns-in-android/)

正如本文前面的[如何在安卓中以编程方式振动设备](https://www.geeksforgeeks.org/how-to-vibrate-a-device-programmatically-in-android/)所讨论的。因此，在本文中，我们讨论了如何制作振动模式，从而产生不同波形的振动。该实现可以是当有来电并且设备产生各种振动模式时产生的振动的复制品。注意，我们也将使用`Java`语言来实现这个项目。

## 在安卓中实现振动模式的步骤

### 第一步：创建一个空的活动安卓工作室项目

*   创建一个空的活动 Android Studio 项目。并选择`Java`作为编程语言。
*   参考 [Android | 如何在 Android Studio 中创建/启动一个新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 来学习如何创建一个空的活动 Android Studio 项目。

### 步骤 2：使用 `activity_main.xml` 文件

*   在布局中实现一个按钮，用于在按下时创建振动波形。
*   在`activity_main.xml`文件中调用以下代码。

### XML

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    tools:ignore="HardcodedText">

<!--button to compose vibration waveforms when pressed-->
    <Button
        android:id="@+id/makeVibrationCompositionButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:backgroundTint="@color/colorPrimary"
        android:text="COMPOSE VIBRATION"
        android:textColor="@android:color/white" />

</RelativeLayout>
```