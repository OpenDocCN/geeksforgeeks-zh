# 科特林的文本切换器

> 原文：[https://www.geeksforgeeks.org/textswitcher-in-kotlin/](https://www.geeksforgeeks.org/textswitcher-in-kotlin/)

安卓`TextSwitcher`是一个用户界面小部件，包含多个文本视图，一次显示一个。`TextSwitcher`是`ViewSwitcher`的子类，用于动画显示一个文本并显示下一个文本。

通常，我们在XML布局中以两种方式手动使用`TextSwitcher`，在Kotlin文件中以编程方式使用`TextSwitcher`。

我们应该定义一个XML组件，在我们的安卓应用程序中使用`TextSwitcher`。

## 代码示例

```kt
<TextSwitcher android:id="@+id/imgSw"
    android:layout_width="match_parent"
    android:layout_height="250dp">
</TextSwitcher>
```

首先，我们按照以下步骤创建一个新项目：

1.  点击**文件**，然后**新建** => **新建项目**。
2.  之后加入Kotlin支持，点击下一步。
3.  根据方便选择最小SDK，点击下一步按钮。
4.  然后选择**清空**活动 => **下一个** => **完成**。

## 文本切换器小部件的不同属性

| XML属性 | 描述 |
| --- | --- |
| `android:id` | 用于指定视图的id。 |
| `android:onClick` | 用于指定单击此视图时的操作。 |
| `android:background` | 用于设置视图的背景。 |
| `android:padding` | 用于设置视图的填充。 |
| `android:visibility` | 用于设置视图的可见性。 |
| `android:inAnimation` | 用于定义显示视图时使用的动画。 |
| `android:outAnimation` | 用于定义视图隐藏时使用的动画。 |
| `android:animateFirstView` | 用于定义第一次显示视图动画时是否动画显示当前视图。 |

## 修改 activity_main.xml 文件

在这个文件中，我们使用了`TextSwitcher`、`Button`，并设置了它们的属性。

```kt
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <TextSwitcher
        android:id="@+id/textSwitcher"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginLeft="32dp"
        android:layout_marginTop="32dp"
        android:layout_marginRight="32dp"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/prev"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="32dp"
        android:layout_marginTop="128dp"
        android:text="@string/prev"
        app:layout_constraintRight_toLeftOf="@id/next"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textSwitcher" />

    <Button
        android:id="@+id/next"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:text="@string/next"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toEndOf="@+id/prev"
        app:layout_constraintTop_toBottomOf="@id/textSwitcher"
        app:layout_constraintTop_toTopOf="@+id/prev" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

## 更新 strings.xml 文件

这里，我们使用字符串标签更新应用程序的名称。

```kt
<resources>
    <string name="app_name">TextSwitcherInKotlin</string>
    <string name="next">Next</string>
    <string name="prev">Prev</string>
</resources>
```

## 在 MainActivity.kt 文件中访问 TextSwitcher

首先，我们声明一个数组`textList`，它包含用于文本视图的语言列表。

```kt
private val textList = arrayOf("Java","Python","Kotlin","Scala","C++")
```

然后，我们从XML布局中访问`TextSwitcher`，并设置文本颜色、文本大小等属性。

```kt
val textSwitcher = findViewById<TextSwitcher>(R.id.textSwitcher)
```

## 完整代码

```kt
package com.geeksforgeeks.myfirstkotlinapp

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.view.Gravity
import android.view.animation.AnimationUtils
import android.widget.Button
import android.widget.TextSwitcher
import android.widget.TextView
import android.graphics.Color

class MainActivity : AppCompatActivity() {

    private val languages = arrayOf("Java","Python","Kotlin","Scala","C++")
    private var index = 0

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // accessing the TextSwitcher from XML layout
        val textSwitcher = findViewById<TextSwitcher>(R.id.textSwitcher)
        textSwitcher.setFactory {
            val textView = TextView(this@MainActivity)
            textView.gravity = Gravity.TOP or Gravity.CENTER_HORIZONTAL
            textView.textSize = 32f
            textView.setTextColor(Color.BLUE)
            textView
        }
        textSwitcher.setText(languages[index])

        val textIn = AnimationUtils.loadAnimation(
            this, android.R.anim.slide_in_left)
        textSwitcher.inAnimation = textIn

        val textOut = AnimationUtils.loadAnimation(
            this, android.R.anim.slide_out_right)
        textSwitcher.outAnimation = textOut

        // previous button functionality
        val prev = findViewById<Button>(R.id.prev)
        prev.setOnClickListener {
            index = if (index - 1 >= 0) index - 1 else 4
            textSwitcher.setText(languages[index])
        }
        // next button functionality
        val button = findViewById<Button>(R.id.next)
        button.setOnClickListener {
            index = if (index + 1 < languages.size) index + 1 else 0
            textSwitcher.setText(languages[index])
        }
    }
}
```

## AndroidManifest.xml 文件

```kt
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
package="com.geeksforgeeks.myfirstkotlinapp">

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

## 作为模拟器运行

单击**下一步**按钮，然后我们在文本视图中获得其他文本。