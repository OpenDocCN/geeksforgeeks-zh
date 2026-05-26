# Kotlin协程中的作用域

> 原文：[https://www.geeksforgeeks.org/scopes-in-kotlin-coroutines/](https://www.geeksforgeeks.org/scopes-in-kotlin-coroutines/)

**先决条件：**

*   [Android上的Kotlin协程](https://www.geeksforgeeks.org/kotlin-coroutines-on-android/)
*   [Kotlin协程的`suspend`函数](https://www.geeksforgeeks.org/suspend-function-in-kotlin-coroutines/)

Kotlin协程中的作用域可以定义为[Kotlin协程](https://www.geeksforgeeks.org/kotlin-coroutines-on-android/)被执行的限制。作用域有助于预测协程的生命周期。Kotlin协程基本上有**3个作用域**：

1.  全局作用域
2.  生命周期作用域
3.  ViewModel作用域

### 要在`build.gradle`（应用程序级文件）中导入的依赖项

将以下依赖项导入 [`build.gradle (app)`](https://www.geeksforgeeks.org/android-build-gradle/) 级文件。

```groovy
implementation 'org.jetbrains.kotlinx:kotlinx-coroutines-core:1.3.5'
implementation 'org.jetbrains.kotlinx:kotlinx-coroutines-android:1.3.5'
def arch_version = '2.2.0-alpha01'
implementation "androidx.lifecycle:lifecycle-viewmodel-ktx:$arch_version"
implementation "androidx.lifecycle:lifecycle-runtime-ktx:$arch_version"
```

### 1. 全局作用域

全局作用域是启动协程的方式之一。当协程在全局作用域内启动时，它们和应用程序一样长寿。如果协程完成了它的工作，它将被销毁，并且在应用程序死亡之前不会保持活动。但是让我们想象一种情况，当协程还有一些工作或指令要做，突然我们结束了应用程序，那么协程也将死亡，因为协程的最大生命周期等于应用程序的生命周期。在全局作用域内启动的协程将在单独的线程中启动。下面的例子显示了在全局作用域内的协程是在一个单独的线程中启动的。

**MainActivity.kt**

```kotlin
import android.os.Bundle
import android.util.Log
import androidx.appcompat.app.AppCompatActivity
import kotlinx.coroutines.GlobalScope
import kotlinx.coroutines.launch

class MainActivity : AppCompatActivity() {
    val TAG = "Main Activity"
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        GlobalScope.launch {
            Log.d(TAG, Thread.currentThread().name.toString())
        }
        Log.d("Outside Global Scope", Thread.currentThread().name.toString())
    }
}
```

以下是上述程序的日志输出：

![Log Output](img/aac09d622d9ed35cfde553236ffc5026.png)

众所周知，在全局作用域内启动的协程只要应用程序运行，就会一直运行。但是当开发人员需要协程只要应用程序运行就一直运行时，这种情况是非常罕见的。在全局作用域内启动的协程的主要问题是，当启动协程的Activity死亡时，协程不会随着Activity一起死亡，因为协程的生命周期是根据应用程序生命周期而不是Activity生命周期决定的。由于协程正在使用启动它的Activity的资源，现在由于该Activity已经死亡，资源将不会被垃圾回收，因为协程仍然引用该资源。这个问题会导致内存泄漏。所以一直使用全局作用域并不总是一个好主意。

让我们尝试启动一个协程，运行一个延迟为1秒的无限循环，并通过终止第一个Activity并`Intent`执行另一个Activity，在从开始延迟5秒后，在全局作用域内启动另一个协程。我们可以在输出中看到，即使在第一个Activity以编程方式终止之后，与第一个Activity相关联的协程也不会死亡。让我们试着通过编程来理解上一段写的内容。下面是 **activity_main.xml** 和 **MainActivity.kt** 文件的代码。

**activity_main.xml**

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/btnStartActivity"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="167dp"
        android:layout_marginTop="320dp"
        android:layout_marginEnd="156dp"
        android:layout_marginBottom="363dp"
        android:text="Start Activity"
        android:textSize="22sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

**MainActivity.kt**

```kotlin
// program for main activity which intent to another activity
// it uses global scope to launch the coroutine

import android.content.Intent
import android.os.Bundle
import android.util.Log
import androidx.appcompat.app.AppCompatActivity
import kotlinx.android.synthetic.main.activity_main.*
import kotlinx.coroutines.GlobalScope
import kotlinx.coroutines.delay
import kotlinx.coroutines.launch

const val TAG = "Main Activity"

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        btnStartActivity.setOnClickListener {
            // coroutine will launch when button got pressed
            GlobalScope.launch {
                // infinite loop
                while (true) {
                    delay(1000L)
                    Log.d(TAG, "Still Running..")
                }
            }

            GlobalScope.launch {
                delay(5000L)
                // new activity will get intended after 5 sec
                val intent = Intent(this@MainActivity, SecondActivity::class.java)
                startActivity(intent)
                // calling finish() method,so that first activity will not be alive
                // after being intended to second activity
                finish()
            }
        }
    }
}
```

转到 **app > java > 第一个包名 > 右键单击 > 新建 > 活动 > 空活动** 创建一个新活动，并将其命名为 **SecondActivity**。下面是 **activity_second.xml** 和 **SecondActivity.kt** 文件的代码。

**activity_second.xml**

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".SecondActivity">

    <!--Various attributes for button-->
    <Button
        android:id="@+id/btnSecondActivity"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="166dp"
        android:layout_marginTop="331dp"
        android:layout_marginEnd="130dp"
        android:layout_marginBottom="352dp"
        android:gravity="center"
        android:text="Second Activity"
        android:textSize="22sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

**SecondActivity.kt**

```kotlin
// program for second activity

import android.os.Bundle
import android.util.Log
import android.widget.Toast
import androidx.appcompat.app.AppCompatActivity

class SecondActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_second)
        Log.i("Second Activity", "Second Activity Running ....")
        Toast.makeText(this, "Second Activity", Toast.LENGTH_SHORT).show()
    }
}
```

**输出：**

<video class="wp-video-shortcode" id="video-501410-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201018110933/Coroutine_Scope.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201018110933/Coroutine_Scope.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201018110933/Coroutine_Scope.mp4)</video>

从下面的日志中可以看出，即使在第二个Activity启动后，主Activity的协程仍然在运行。椭圆形圆圈用于显示时间戳。

![Log Output](img/92bdfb1a4330b99be25875abc28b4c22.png)

### 2. 生命周期作用域

生命周期作用域与全局作用域相同，但唯一的区别是，当我们使用生命周期作用域时，在Activity中启动的所有协程也会随着Activity的结束而结束。这是有益的，因为即使在我们的Activity结束后，我们的协程也不会继续运行。为了在我们的项目中实现生命周期作用域，只需在生命周期作用域而不是全局作用域中启动协程，即只需在运行无限循环的主Activity中将`GlobalScope`更改为`lifecycleScope`。除了上面提到的主要Activity代码的一些变化之外，所有代码都将保持不变。

## 我的锅

```kt
// program to show how lifecycle scope works

import android.content.Intent
import android.os.Bundle
import android.util.Log
import androidx.appcompat.app.AppCompatActivity
import androidx.lifecycle.lifecycleScope
import kotlinx.android.synthetic.main.activity_main.*
import kotlinx.coroutines.GlobalScope
import kotlinx.coroutines.delay
import kotlinx.coroutines.launch

const val TAG = "Main Activity"

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        btnStartActivity.setOnClickListener {
            // launching the coroutine in the lifecycle scope
            lifecycleScope.launch {
                while (true) {
                    delay(1000L)
                    Log.d(TAG, "Still Running..")
                }
            }

            GlobalScope.launch {
                delay(5000L)
                val intent = Intent(this@MainActivity, SecondActivity::class.java)
                startActivity(intent)
                finish()
            }
        }
    }
}
```

**日志输出:**

椭圆形圆圈用于显示时间戳。

![Log Output ](img/f9fc6eb9fdd6dc4d50c068fe10244450.png)

在上面的日志输出中可以看到，主活动在第二个活动启动后停止 get 打印。

### 3.视图模型范围

它也与生命周期范围相同，唯一的区别是，只要视图模型还活着，这个范围中的协同程序就会存在。`ViewModel` 是一个通过遵循 android 中[生命周期系统的原理来管理和存储 UI 相关数据的类。](https://www.geeksforgeeks.org/activity-lifecycle-in-android-with-demo-app/)如果想深入了解基本视图模型类是什么，可以参考[这个安卓官方文档的链接](https://developer.android.com/topic/libraries/architecture/viewmodel)。