# 在社交媒体安卓应用中实现类似博文的功能

> 原文：[https://www.geeksforgeeks.org/implement-like-a-blog-post-functionality-in-social-media-android-app/](https://www.geeksforgeeks.org/implement-like-a-blog-post-functionality-in-social-media-android-app/)

这是**“在 Android Studio 上构建社交媒体应用”**教程的**第 10 部分**，我们将在本文中介绍以下功能：

*   我们将介绍“点赞博文”功能。我们使用两张图片来实现此功能，一张是白色背景的按钮，另一张是蓝色背景的按钮。
*   当用户第一次点击按钮时，我们将图片更改为蓝色背景颜色的按钮，并增加计数。当用户再次点击时，我们将减少计数并将背景更改为白色点赞按钮。

## 分步实施

### 步骤 1：使用 `row_posts.xml` 文件

添加一个相似按钮和总相似[文本视图](https://www.geeksforgeeks.org/working-with-the-textview-in-android/)。

### XML

```xml
<Button
  android:id="@+id/like"
  android:layout_width="wrap_content"
  android:layout_height="wrap_content"
  android:layout_weight="1"
  android:autoLink="all"
  android:background="@color/colorWhite"
  android:drawableStart="@drawable/ic_like"
  android:drawableLeft="@drawable/ic_like"
  android:padding="5dp"
  android:text="Like" />
```