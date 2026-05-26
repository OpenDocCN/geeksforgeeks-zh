# Android 中的 ProgressBar 使用 Jetpack Compose

> 原文：[ProgressBar in Android using Jetpack Compose](https://www.geeksforgeeks.org/progressbar-in-android-using-jetpack-compose/)

[ProgressBar](https://www.geeksforgeeks.org/progressbar-in-kotlin/) 是 Android 中的一个 Material UI 组件，用来指示任何进程的进度，比如显示任何下载程序，作为占位屏幕等等。在本文中，我们将了解一下使用 [Jetpack Compose](https://www.geeksforgeeks.org/basics-of-jetpack-compose-in-android/) 在安卓系统中实现 ProgressBar。

| 属性 | 使用 |
| --- | --- |
| `modifier` | 给进度条添加填充。 |
| `color` | 为进度条添加颜色。 |
| `strokeWidth` | 该属性用于给出进度条的圆形线条的宽度。 |
| `progress` | 以指示循环进度条的进度。 |

## 分步实施

### 第一步：创建新项目

要在安卓工作室金丝雀版本中创建新项目，请参考[如何使用 Jetpack Compose 在安卓工作室金丝雀版本中创建新项目。](https://www.geeksforgeeks.org/how-to-create-a-new-project-in-android-studio-canary-version-with-jetpack-compose/)

### 步骤 2：使用 MainActivity.kt 文件

导航到 `应用程序 > java > 你的应用程序的包名`，打开 `MainActivity.kt` 文件。在该文件中添加下面的代码。代码中添加了注释，以更详细地理解代码。

```kt
import android.graphics.drawable.shapes.Shape
import android.media.Image
import android.os.Bundle
import android.widget.Toast
import androidx.appcompat.app.AppCompatActivity
import androidx.compose.foundation.*
import androidx.compose.foundation.Text
import androidx.compose.foundation.layout.*
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.foundation.text.KeyboardOptions
import androidx.compose.material.*
import androidx.compose.material.Icon
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.AccountCircle
import androidx.compose.material.icons.filled.Info
import androidx.compose.material.icons.filled.Menu
import androidx.compose.material.icons.filled.Phone
import androidx.compose.runtime.*
import androidx.compose.runtime.savedinstancestate.savedInstanceState
import androidx.compose.ui.Alignment
import androidx.compose.ui.layout.ContentScale
import androidx.compose.ui.platform.setContent
import androidx.compose.ui.res.imageResource
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import com.example.gfgapp.ui.GFGAppTheme
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.graphics.SolidColor
import androidx.compose.ui.platform.ContextAmbient
import androidx.compose.ui.platform.testTag
import androidx.compose.ui.res.colorResource
import androidx.compose.ui.semantics.SemanticsProperties.ToggleableState
import androidx.compose.ui.text.TextStyle
import androidx.compose.ui.text.font.FontFamily
import androidx.compose.ui.text.input.*
import androidx.compose.ui.unit.Dp
import androidx.compose.ui.unit.TextUnit

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            Column {
                // in below line we are calling
                // a progress bar  method.
                SimpleCircularProgressComponent()
            }
        }
    }
}

@Preview(showBackground = true)
@Composable
fun DefaultPreview() {
    GFGAppTheme {
        SimpleCircularProgressComponent();
    }
}

@Composable
fun SimpleCircularProgressComponent() {
    // CircularProgressIndicator is generally used
    // at the loading screen and it indicates that
    // some progress is going on so please wait.
    Column(
        // we are using column to align our
        // imageview to center of the screen.
        modifier = Modifier.fillMaxWidth().fillMaxHeight(),

        // below line is used for specifying
        // vertical arrangement.
        verticalArrangement = Arrangement.Center,

        // below line is used for specifying
        // horizontal arrangement.
        horizontalAlignment = Alignment.CenterHorizontally,

    ) {
        // below line is use to display
        // a circular progress bar.
        CircularProgressIndicator(
            // below line is use to add padding
            // to our progress bar.
            modifier = Modifier.padding(16.dp),

            // below line is use to add color
            // to our progress bar.
            color = colorResource(id = R.color.purple_200),

            // below line is use to add stroke
            // width to our progress bar.
            strokeWidth = Dp(value = 4F)
        )
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

### 输出

[视频演示](https://media.geeksforgeeks.org/wp-content/uploads/20210118220656/Screenrecorder-2021-01-18-22-05-28-34.mp4)