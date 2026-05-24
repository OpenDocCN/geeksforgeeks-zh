# 如何在安卓的 RecyclerView 中插入“从底部滑动”动画

> 原文：[https://www.geeksforgeeks.org/how-to-insert-slide-from-bottom-animation-in-recyclerview-in-android/](https://www.geeksforgeeks.org/how-to-insert-slide-from-bottom-animation-in-recyclerview-in-android/)

在本文中，将向 `RecyclerView` 添加使项目从底部滑入的动画。这里我们不使用任何其他库来添加动画。添加动画使应用程序更具吸引力，并提供更好的用户体验。

## 进场

**第一步：** 创建 `anim` 资源目录。
右键单击 `res` 文件夹并遵循路径：
> res -> 新建 -> 安卓资源目录

从**资源类型**中，选择 `anim`。不要更改**目录名**，然后按确定。

**第二步：** 创建动画文件。
右键点击 `anim` 目录，新建一个动画资源文件。
> anim -> 新建 -> 动画资源文件 -> 创建 `slide_from_bottom` XML 文件。

在 `slide_from_bottom.xml` 文件中添加以下代码。这里定义了动画。

```xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:duration="600">
    <translate
        android:fromYDelta="50%p"
        android:interpolator="@android:anim/accelerate_decelerate_interpolator"
        android:toYDelta="0"/>
    <alpha
        android:fromAlpha="0"
        android:interpolator="@android:anim/accelerate_decelerate_interpolator"
        android:toAlpha="1"/>
</set>
```

**步骤 3：** 再创建一个动画文件来保存 `slide_from_bottom.xml`。
> anim -> 新建 -> 动画资源文件 -> 创建 `layout_animation_slide_from_bottom` xml 文件

在刚刚创建的 XML 文件中添加下面的代码。这里，添加了上一步中定义的动画 `slide_from_bottom`。

```xml
<?xml version="1.0" encoding="utf-8"?>
<layoutAnimation
  xmlns:android="http://schemas.android.com/apk/res/android"
  android:animation="@anim/slide_from_bottom"
  android:animationOrder="normal"
  android:delay="15%">
</layoutAnimation>
```

**第四步（最终）：** 在你的 `RecyclerView` 中调用那个动画。
在标签 `layoutAnimation` 中，添加 `layout_animation_slide_from_bottom.xml`。现在，当在 `RecyclerView` 中显示列表项时，这些项将添加由 `layout_animation_slide_from_bottom.xml` 携带并在 `slide_from_bottom.xml` 中定义的动画。

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#6F6A6A"
    tools:context=".MainActivity">

    <androidx.recyclerview.widget.RecyclerView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layoutAnimation="@anim/layout_animation_slide_from_bottom"
        android:orientation="vertical"
        android:id="@+id/recyclerView"
        />

</androidx.constraintlayout.widget.ConstraintLayout>
```

## 输出

[演示视频](https://media.geeksforgeeks.org/wp-content/uploads/20200705235158/slide_from_bottom_animation_android_demo.mp4)