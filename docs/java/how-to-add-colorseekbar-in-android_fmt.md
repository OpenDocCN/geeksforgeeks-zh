# 如何在安卓中添加 ColorSeekBar

> 原文: [https://www.geeksforgeeks.org/how-to-add-colorseekbar-in-android/](https://www.geeksforgeeks.org/how-to-add-colorseekbar-in-android/)

`Seekbar` 是进度条的一种类型。我们可以将 seekbar 从左向右拖动，反之亦然，从而改变当前进度。`ColorSeekbar` 与 `Seekbar` 类似，但是我们使用它从多种颜色中选择一种颜色，并且可以选择任何自定义颜色。在这个小部件的帮助下，我们可以给用户更多的控制权来根据他的需要定制它的应用程序。

## 进场:

1.  将支持库添加到您的根 `build.gradle` 文件中(不是您的模块 `build.gradle` 文件)。这个库 jitpack 是一个新颖的包存储库。它是为 JVM 而做的，这样任何存在于 `github` 和 `bigbucket` 中的库都可以直接在应用中使用。

```java
allprojects {
    repositories {
        maven { url "https://jitpack.io" }
    }
}
```

2.  在 `build.gradle` 文件中添加支持库，并在依赖项部分添加依赖项。这个库提供了各种内置的功能，我们可以使用这些功能给用户最大的独立性来定制。

```java
dependencies {
    implementation 'com.github.rtugeek:colorseekbar:1.7.7'
}
```

3.  现在在 `/values` 目录的 `strings.xml` 文件中添加一组颜色， `custom_colors` 。

## 字符串

```java
<array name="custom_colors">
    <item>#219806</item>
    <item>#F44336</item>
    <item>#FFEB3B</item>
</array>
```

4.  现在在 `activity_main.xml` 文件中添加以下代码。这将在 activity_main 中添加一个 `TextView` 和一个 `ColorSeekbar` 。在这个文件中，我们将我们的数组 `custom_colors` 添加到 Seekbar 中。

## activity_main.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="16dp"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/text_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="GeeksForGeeks"
        android:textSize="30sp"
        android:textStyle="bold" />

    <com.rtugeek.android.colorseekbar.ColorSeekBar
        android:id="@+id/color_seek_bar"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:colorSeeds="@array/custom_colors"
        app:showAlphaBar="true" />

</LinearLayout>
```

5.  现在在 `MainActivity.java` 文件中添加以下代码。 `onClickListener` 被添加到 seekbar。当通过 seekbar 改变值时， `onClickListener` 被调用，textview 中文本的颜色随之改变。

## MainActivity.java

```java
package org.geeksforgeeks.colorseekbar;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.TextView;
import com.rtugeek.android.colorseekbar.ColorSeekBar;

public class MainActivity extends AppCompatActivity {

    TextView textView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        textView = findViewById(R.id.text_view);
        ColorSeekBar colorSeekBar = findViewById(R.id.color_seek_bar);

        colorSeekBar.setOnColorChangeListener(
            new ColorSeekBar.OnColorChangeListener() {
                @Override
                public void onColorChangeListener(int i, int i1, int i2) {
                    textView.setTextColor(i2);
                }
            });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-416921-1" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200515132427/Record_2020-05-15-13-23-04_1a4811e1943b5c025442b43456dabc2c.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200515132427/Record_2020-05-15-13-23-04_1a4811e1943b5c025442b43456dabc2c.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200515132427/Record_2020-05-15-13-23-04_1a4811e1943b5c025442b43456dabc2c.mp4)</video>