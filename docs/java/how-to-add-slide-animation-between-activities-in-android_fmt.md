# 如何在安卓中的活动之间添加Slide动画？

> 原文：[https://www.geeksforgeeks.org/how-to-add-slide-animation-between-activities-in-android/](https://www.geeksforgeeks.org/how-to-add-slide-animation-between-activities-in-android/)

在这篇文章中，我们将学习如何在不同的活动之间添加**滑动屏幕动画**，让UX变得更好。应用程序由许多活动组成，在活动之间导航幻灯片屏幕动画非常有用。动画在任何应用程序中都扮演着非常关键的角色，如果应用程序中有动画，那么它肯定会吸引用户。

## 进场：

1.  创建一个新的**安卓资源目录**，右键单击资源文件夹 -> 安卓资源目录，确保选择资源类型为**动漫**。
2.  创建`slide_in_left.xml`并添加以下代码。

### slide_in_left.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="@android:integer/config_mediumAnimTime"
        android:fromXDelta="-100%p"
        android:toXDelta="0" />
</set>
```

3.  创建`slide_in_right.xml`并添加以下代码。

### slide_in_right.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="@android:integer/config_mediumAnimTime"
        android:fromXDelta="100%p"
        android:toXDelta="0" />
</set>
```

4.  创建`slide_out_left.xml`并添加以下代码。

### slide_out_left.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="@android:integer/config_mediumAnimTime"
        android:fromXDelta="0"
        android:toXDelta="-100%p" />
</set>
```

5.  创建`slide_out_right.xml`并添加以下代码。

### slide_out_right.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="@android:integer/config_mediumAnimTime"
        android:fromXDelta="0"
        android:toXDelta="100%p" />
</set>
```

6.  现在创建`activity_main2.xml`文件。添加以下代码。在这个文件中，我们给我们的按钮添加了`onClick`属性，当点击该属性时将调用`Open3rdActivity`函数。

### activity_main2.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity2">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Learn Algorithm"
        android:textColor="#219806"
        android:textSize="30sp" />

    <Button
        android:textAllCaps="false"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:onClick="Open3rdActivity"
        android:text="Open Third Activity" />

</LinearLayout>
```

7.  现在创建`activity_main3.xml`文件。添加以下代码，它将在布局中添加一个`TextView`。

### activity_main3.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity3">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Buy Course"
        android:textColor="#219806"
        android:textSize="30sp" />

</LinearLayout>
```

8.  现在创建`MainActivity2.java`文件。添加以下代码。这里我们添加了一个函数`Open3rdActivity`，点击按钮时调用。它使用`Intent`打开`MainActivity3`。此外，我们覆盖`onBackPressed`功能，添加从当前活动返回的动画。

### MainActivity2.java

```java
package org.geeksforgeeks.gfgslidescreen;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;

public class MainActivity2 extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);
    }

    // This function gets invoked automatically when the
    // user clicks on the button.
    public void Open3rdActivity(View view)
    {
        Intent intent = new Intent(this, MainActivity3.class);
        startActivity(intent);
    }

    // when the user pressed back button this function
    // get invoked automatically.
    @Override
    public void onBackPressed()
    {
        super.onBackPressed();
        overridePendingTransition(R.anim.slide_in_left,
                                  R.anim.slide_out_right);
    }
}
```

9.  现在创建`MainActivity3.java`文件。添加以下代码。

### MainActivity3.java

```java
package org.geeksforgeeks.gfgslidescreen;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity3 extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main3);
    }
}
```

10. 现在在`activity_main.xml`文件中添加以下代码。在这个文件中，我们为按钮添加了`onClick`属性。

### activity_main.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="GeeksForGeeks"
        android:textColor="#219806"
        android:textSize="30sp" />

    <Button
        android:textAllCaps="false"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:onClick="OpenSecondActivity"
        android:text="Open Second Activity " />

</LinearLayout>
```

11. 现在在`MainActivity.java`文件中添加以下代码。这里我们添加函数`OpenSecondActivity`，当按钮被点击时调用。它使用`Intent`打开`MainActivity2`。同时在函数中，我们添加了过渡到`MainActivity2`的动画。

### MainActivity.java

```java
package org.geeksforgeeks.gfgslidescreen;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    // when the user pressed back button this function
    // get invoked automatically.
    public void OpenSecondActivity(View view)
    {
        Intent intent = new Intent(this, MainActivity2.class);
        startActivity(intent);
        overridePendingTransition(R.anim.slide_in_right,
                                  R.anim.slide_out_left);
    }
}
```

*不要忘记在[`Manifest`](https://www.geeksforgeeks.org/application-manifest-file-android/)文件中添加活动。*

**输出：**
*   您可以观察到，当用户点击`打开秒活动`按钮和`打开秒活动`按钮时，这两个按钮在不同的动画中打开活动。
*   当用户处于`第三活动`并按下后退按钮时，默认动画被调用，而当用户处于`第二活动`并按下后退按钮时，我们定义的动画被调用。
<video class="wp-video-shortcode" id="video-436381-1" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200612162819/Record_2020-06-12-16-26-51_362beaafa7b641b43e176a1856bf3d4f1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200612162819/Record_2020-06-12-16-26-51_362beaafa7b641b43e176a1856bf3d4f1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200612162819/Record_2020-06-12-16-26-51_362beaafa7b641b43e176a1856bf3d4f1.mp4)</video>

## 在整个应用程序中设置动画

*   如果你想在整个应用程序中设置动画，你可以按照这个简单的步骤来完成。在`style.xml`文件中添加以下代码。

```java
<resources>
    <!-- Base application theme. -->
    <style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/colorPrimary</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorAccent</item>
        <item name="android:windowAnimationStyle">@style/MyCustomActivityAnimation</item>
    </style>

    <style name="MyCustomActivityAnimation" parent="@android:style/Animation.Activity">
        <item name="android:activityOpenEnterAnimation">@anim/slide_in_right</item>
        <item name="android:activityOpenExitAnimation">@anim/slide_out_left</item>
        <item name="android:activityCloseEnterAnimation">@anim/slide_in_left</item>
        <item name="android:activityCloseExitAnimation">@anim/slide_out_right</item>
    </style>
</resources>
```

*   完成并运行应用程序。
<video class="wp-video-shortcode" id="video-436381-2" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200612164225/Record_2020-06-12-16-41-06_362beaafa7b641b43e176a1856bf3d4f1.mp4?_=2">[https://media . geekesforgeks . org/WP-content/uploads/20200612164225/Record _ 2020-06-12-16-41-06 _ 362 beaafa 7a 641 b 43 e 176 a 1856 BF 3d 4 f 1 . MP4](https://media.geeksforgeeks.org/wp-content/uploads/20200612164225/Record_2020-06-12-16-41-06_362beaafa7b641b43e176a1856bf3d4f1.mp4)</video>