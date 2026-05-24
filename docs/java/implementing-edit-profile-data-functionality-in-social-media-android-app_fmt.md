# 在社交媒体安卓应用中实现编辑个人资料数据功能

> 原文：[https://www.geeksforgeeks.org/implementing-edit-profile-data-functionality-in-social-media-android-app/](https://www.geeksforgeeks.org/implementing-edit-profile-data-functionality-in-social-media-android-app/)

这是`【在 Android Studio 上构建社交媒体 App】`教程的`第三部分`，我们将在本文中介绍以下功能：

*   我们将编辑个人资料数据，例如更改姓名、更改用户密码和更改个人资料图片。
*   更改密码是一个非常重要的功能，因为有时可能会发生有人知道我们密码的情况。在这种情况下，我们需要更改密码。
*   我们通过从图库中选择图像或在相机中拍摄图像来更改个人资料图片。

## 分步实施

### 第一步：在 `build.gradle`（模块：app）中添加依赖项

导航至`Gradle Scripts > build.gradle (Module: app)`并在依赖项部分添加下面的依赖项。

```gradle
implementation "androidx.recyclerview:recyclerview:1.1.0"
implementation 'de.hdodenhof:circleimageview:3.1.0'
implementation 'com.github.bumptech.glide:glide:4.11.0'
annotationProcessor 'com.github.bumptech.glide:compiler:4.11.0'
annotationProcessor 'com.github.bumptech.glide:compiler:4.11.0'
```

现在从右上角的“Sync Now”选项同步项目。

### 第二步：在 `AndroidManifest.xml` 文件中添加互联网权限

导航到`AndroidManifest.xml`文件，并添加以下权限，以便在应用程序中获得互联网权限。

```xml
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.CAMERA" />
```

### 步骤 3：创建一个新的空活动，并将该活动命名为 `EditProfilePage`

使用`activity_edit_profile.xml`文件。在此页面上将更改用户的电子邮件、姓名和个人资料图片。导航到`app > res > layout > activity_edit_profile_page.xml`并将下面的代码添加到该文件中。下面是`activity_edit_profile_page.xml`文件的代码。

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".EditProfilePage">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="50dp"
        android:text="Edit Profile Data"
        android:textAlignment="center"
        android:textColor="@android:color/black"
        android:textSize="26sp" />

    <de.hdodenhof.circleimageview.CircleImageView
        android:id="@+id/setting_profile_image"
        android:layout_width="130dp"
        android:layout_height="130dp"
        android:layout_marginStart="140dp"
        android:layout_marginTop="40dp"
        android:src="@drawable/ic_users" />

    <TextView
        android:id="@+id/profilepic"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="20dp"
        android:text="Update Profile Pic"
        android:textAlignment="center"
        android:textColor="@android:color/black"
        android:textSize="20sp" />

    <TextView
        android:id="@+id/editname"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="20dp"
        android:text="Update Name"
        android:textAlignment="center"
        android:textColor="@android:color/black"
        android:textSize="20sp" />

    <TextView
        android:id="@+id/changepassword"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="20dp"
        android:text="Change Password "
        android:textAlignment="center"
        android:textColor="@android:color/black"
        android:textSize="20sp" />

</LinearLayout>
```

### 第四步：新建布局资源文件

转到`app > res > layout > New > Layout Resource File`并将文件命名为`dialog_update_password.xml`。导航到`app > res > layout > dialog_update_password.xml`并将下面的代码添加到该文件中。下面是`dialog_update_password.xml`文件的代码。

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    android:padding="20dp">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Update Password"
        android:textAlignment="center"
        android:textColor="@color/colorBlack"
        android:textSize="16sp"
        android:textStyle="bold" />

    <com.google.android.material.textfield.TextInputLayout
        android:id="@+id/oldpass"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:layout_centerVertical="true"
        app:passwordToggleEnabled="true">

        <EditText
            android:id="@+id/oldpasslog"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Old Password"
            android:inputType="textPassword" />

    </com.google.android.material.textfield.TextInputLayout>

    <com.google.android.material.textfield.TextInputLayout
        android:id="@+id/newpass"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/oldpasslog"
        android:layout_centerHorizontal="true"
        android:layout_centerVertical="true"
        app:passwordToggleEnabled="true">

        <EditText
            android:id="@+id/newpasslog"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="New Password"
            android:inputType="textPassword" />
    </com.google.android.material.textfield.TextInputLayout>

    <Button
        android:id="@+id/updatepass"
        style="@style/Widget.AppCompat.Button.Colored"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:text="Update Password" />

</LinearLayout>
```