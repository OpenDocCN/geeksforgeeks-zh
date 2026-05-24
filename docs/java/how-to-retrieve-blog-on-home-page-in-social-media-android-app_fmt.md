# 如何在社交媒体安卓 App 中检索首页博客？

> 原文：[https://www.geeksforgeeks.org/how-to-retrieve-blog-on-home-page-in-social-media-android-app/](https://www.geeksforgeeks.org/how-to-retrieve-blog-on-home-page-in-social-media-android-app/)

这是“在安卓工作室搭建社交媒体 App”教程的第 6 部分，我们将在本文中介绍以下功能：

*   我们将检索用户在`homefragment`上撰写的博客。
*   这里我们只显示用户数据以及博客的标题、描述和图片，但我们也会在后续博客中实现点赞和评论功能。
*   然后我们将显示帖子详情活动，用户可以在其中发表评论。
*   我们还实现了`like a blog function`。

## 分步实施

**第一步：新建布局资源文件**

转到`app > res >布局>新建>布局资源文件`并将文件命名为`row _ post`。下面是`row _ post . XML`文件的代码。

### XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    app:cardBackgroundColor="@color/colorWhite"
    app:cardCornerRadius="3dp"
    app:cardElevation="3dp"
    app:cardUseCompatPadding="true"
    app:contentPadding="5dp">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <LinearLayout
            android:id="@+id/profilelayout"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center_vertical"
            android:orientation="horizontal">

            <de.hdodenhof.circleimageview.CircleImageView
                android:id="@+id/picturetv"
                android:layout_width="50dp"
                android:layout_height="50dp"
                android:scaleType="centerCrop"
                android:src="@drawable/profile_image" />

            <LinearLayout
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:orientation="vertical">

                <TextView
                    android:id="@+id/unametv"
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:text="Name"
                    android:textColor="@color/colorBlack"
                    android:textSize="20sp" />

                <TextView
                    android:id="@+id/utimetv"
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:text="33 min" />

            </LinearLayout>

            <ImageButton
                android:id="@+id/morebtn"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="@null"
                android:src="@drawable/ic_more" />

        </LinearLayout>

        <TextView
            android:id="@+id/ptitletv"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Title"
            android:textSize="16sp"
            android:textStyle="bold" />

        <TextView
            android:id="@+id/descript"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Description"
            android:textColor="@color/colorBlack" />

        <ImageView
            android:id="@+id/pimagetv"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:background="@color/colorWhite" />

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal">

            <TextView
                android:id="@+id/plikeb"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:text="1.2K Likes"
                android:textColor="@color/colorPrimary" />

            <TextView
                android:id="@+id/pcommentco"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:text="1.2K Comment"
                android:textAlignment="textEnd"
                android:textColor="@color/colorPrimary" />
        </LinearLayout>

        <View
            android:layout_width="match_parent"
            android:layout_height="1dp"
            android:background="#F5F0F0" />

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:orientation="horizontal">

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

            <Button
                android:id="@+id/comment"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:autoLink="all"
                android:background="@color/colorWhite"
                android:drawableStart="@drawable/ic_comment"
                android:drawableLeft="@drawable/ic_comment"
                android:padding="5dp"
                android:text="COMMENT" />
        </LinearLayout>

    </LinearLayout>

</androidx.cardview.widget.CardView>
```