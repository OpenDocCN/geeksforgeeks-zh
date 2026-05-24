# 在社交媒体安卓应用中实现检索个人资料功能

> 原文：[https://www.geeksforgeeks.org/implement-retrieve-profile-data-functionality-in-social-media-android-app/](https://www.geeksforgeeks.org/implement-retrieve-profile-data-functionality-in-social-media-android-app/)

这是 **【在 Android Studio 上构建社交媒体 App】** 教程的 **第 4 部分**，我们将在本文中介绍以下功能：

*   我们将从 `Firebase` 检索用户数据。
*   这是一个简单的片段。我们将从实时数据库中检索用户的数据，例如姓名、电子邮件和个人资料显示图片，并将其显示在文本布局和图片布局中。
*   未来，我们还将在个人资料页面上显示用户的博客。

## 分步实施

### 步骤 1：处理片段文件

在此页面上将检索用户的电子邮件、姓名和个人资料图片。我们还增加了[浮动操作按钮](https://www.geeksforgeeks.org/floating-action-button-fab-in-android-with-example/)来更新数据。导航到 `app > res > 布局 > fragment_profile.xml` 并将下面的代码添加到该文件中。下面是 `fragment_profile.xml` 文件的代码。

### XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#F1EDED"
    tools:context=".ProfileFragment">

<ScrollView
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

<RelativeLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content">

<ImageView
                android:id="@+id/cavertv"
                android:layout_width="match_parent"
                android:layout_height="180dp"
                android:background="@color/colorPrimaryDark"
                android:scaleType="fitXY">
            </ImageView>

<LinearLayout
                android:id="@+id/linearLayout"
                android:layout_width="match_parent"
                android:layout_height="120dp"
                android:layout_marginTop="100dp"
                android:orientation="horizontal">

<ImageView
                    android:id="@+id/avatartv"
                    android:layout_width="120dp"
                    android:layout_height="120dp"
                    android:layout_gravity="center_horizontal"
                    android:layout_marginStart="20dp"
                    android:background="@color/colorPrimary"
                    android:padding="5dp"
                    android:src="@drawable/ic_images" />

<LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:background="#77000000"
                    android:orientation="vertical">

<TextView
                        android:id="@+id/nametv"
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_marginStart="5dp"
                        android:layout_marginLeft="5dp"
                        android:layout_marginTop="5dp"
                        android:textColor="@color/colorWhite"
                        android:textSize="25sp" />

<TextView
                        android:id="@+id/emailtv"
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_marginStart="5dp"
                        android:layout_marginLeft="5dp"
                        android:textColor="@color/colorWhite" />
                </LinearLayout>

</LinearLayout>

</RelativeLayout>

</ScrollView>

<com.google.android.material.floatingactionbutton.FloatingActionButton
        android:id="@+id/fab"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:layout_margin="10dp"
        android:src="@drawable/ic_edit_white" />

</RelativeLayout>
```