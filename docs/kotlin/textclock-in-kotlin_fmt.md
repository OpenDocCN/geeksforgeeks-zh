# 科特林的文字时钟

> 原文:[https://www.geeksforgeeks.org/textclock-in-kotlin/](https://www.geeksforgeeks.org/textclock-in-kotlin/)

安卓`文本时钟`是一个用户界面控件，用于以字符串格式显示日期/时间。

它提供两种模式的时间，第一种是以 24 小时格式显示时间，另一种是以 12 小时格式显示时间。我们可以很容易地使用`is24HourModeEnabled()`方法，以 24 小时或 12 小时格式显示系统使用的文本时钟。

首先，我们按照以下步骤创建一个`新项目`:
1. 点击`文件`，然后`新建` => `新建项目`。
2. 之后加入 Kotlin 支持，点击下一步。
3. 根据方便选择最小 SDK，点击下一步按钮。
4. 然后选择`清空活动` => `下一个` => `完成`。

## 文本时钟小部件的不同属性

| XML 属性 | 描述 |
| --- | --- |
| `android:id` | 用于指定视图的 id。 |
| `android:timeZone` | 用于指定时间的区域。 |
| `android:format12Hour` | 用于 12 小时格式。 |
| `android:format24Hour` | 用于 24 小时格式。 |
| `android:text` | 用于指定文本。 |
| `android:textStyle` | 用于指定文本的样式。 |
| `android:textSize` | 用于指定文本的大小。 |
| `android:background` | 用于设置视图的背景。 |
| `android:padding` | 用于设置视图的填充。 |
| `android:visibility` | 用于设置视图的可见性。 |
| `android:gravity` | 用于指定视图的重心，如中心、顶部、底部等 |

## 修改 activity_main.xml 文件

在这个文件中，我们使用文本时钟、文本视图和按钮来设置所有小部件的属性。

```kt
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextClock
        android:id="@+id/txtClok"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="100dp"
        android:layout_marginLeft="70dp"
        android:format12Hour="hh:mm:ss a"
        android:textColor="#F1912F"
        android:textSize="30dp"
        android:textStyle="italic"/>

    <Button
        android:id="@+id/btn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignLeft="@+id/txtClok"
        android:layout_below="@+id/txtClok"
        android:layout_marginLeft="40dp"
        android:text="Show Time"/>

    <TextView
        android:id="@+id/textview"
        android:layout_width="wrap_content"
        android:layout_height="match_parent"
        android:layout_alignLeft="@+id/btn"
        android:layout_below="@+id/btn"
        android:layout_marginTop="20dp"
        android:layout_marginLeft="-50dp"
        android:textSize="25dp"
        android:textStyle="normal"/>
</RelativeLayout>
```

## 更新 strings.xml 文件

这里，我们使用字符串标签更新应用程序的名称。

```kt
<resources>
    <string name="app_name">TextClockInKotlin</string>
</resources>
```

## 在 MainActivity.kt 文件中访问 TextClock

首先，我们声明两个变量`txtClock`和`txtView`来使用 id 从 XML 布局中访问小部件。

```kt
val txtClock = findViewById<TextClock>(R.id.txtClok)
val txtView = findViewById<TextView>(R.id.textview)
```

然后，我们访问按钮，设置`OnClickListener`在点击按钮的同时显示时间。

```kt
val btn = findViewById<Button>(R.id.btn)
btn?.setOnClickListener {
    txtView?.text = "Time: " + txtClock?.text
}
```

```kt
package com.geeksforgeeks.myfirstKotlinapp

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button
import android.widget.TextClock
import android.widget.TextView

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val txtClock = findViewById<TextClock>(R.id.txtClok)
        val txtView = findViewById<TextView>(R.id.textview)

        val btn = findViewById<Button>(R.id.btn)
        btn?.setOnClickListener {
            txtView?.text = "Time: " + txtClock?.text
        }
    }
}
```

## AndroidManifest.xml 文件

```kt
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.geeksforgeeks.myfirstKotlinapp">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

## 作为模拟器运行: