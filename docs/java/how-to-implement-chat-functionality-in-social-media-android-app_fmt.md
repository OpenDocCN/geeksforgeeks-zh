# 如何在社交媒体安卓 App 中实现聊天功能？

> 原文：[https://www.geeksforgeeks.org/how-to-implement-chat-functionality-in-social-media-android-app/](https://www.geeksforgeeks.org/how-to-implement-chat-functionality-in-social-media-android-app/)

这是 **【在 Android Studio 上构建社交媒体 App】** 教程的 **第 14 部分**，我们将在本文中介绍以下功能：

*   我们将为聊天创建一个布局并发送消息。
*   用户可以发送消息或图片。
*   用户可以使用相机或图库发送图片。
*   首先，需要请求权限才能使用图库或在用相机拍照后发送图片。
*   如果获得权限，用户可以发送图片或再次请求权限。

### 分步实施

**第一步：新建两个布局资源文件，命名为 `row_chat_left` 和 `row_chat_right`**

使用 `row_chat_left.xml` 文件。收到的信息将在左侧。类似地，使用 `row_chat_right.xml` 文件。发送给用户的消息将在右侧。下面是 `row_chat_left.xml` 文件和 `row_chat_right.xml` 文件的代码。

## XML

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/msglayout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    android:padding="10dp">

<LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

<de.hdodenhof.circleimageview.CircleImageView
            android:id="@+id/profilec"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:src="@drawable/profile_image"
            app:civ_border_color="@null" />

<TextView
            android:id="@+id/msgc"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:background="@drawable/bg_receiver"
            android:padding="15dp"
            android:text="His Message"
            android:textColor="@color/colorBlack"
            android:textSize="16sp"
            android:visibility="gone" />

<ImageView
            android:id="@+id/images"
            android:layout_width="200dp"
            android:layout_height="200dp"
            android:adjustViewBounds="true"
            android:background="@drawable/bg_receiver"
            android:padding="15dp"
            android:scaleType="fitCenter"
            android:src="@drawable/ic_images" />

<TextView
            android:id="@+id/timetv"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="02/01/1990 06:19PM"
            android:textColor="@color/colorBlack"
            android:textSize="12sp" />
    </LinearLayout>

<TextView
        android:id="@+id/isSeen"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="end"
        android:text="Delivered"
        android:textAlignment="textEnd"
        android:visibility="gone" />

</LinearLayout>
```