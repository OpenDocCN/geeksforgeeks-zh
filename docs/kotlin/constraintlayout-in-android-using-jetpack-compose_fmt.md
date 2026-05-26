# 使用 Jetpack Compose 在安卓系统中约束布局

> 原文：[https://www.geeksforgeeks.org/constraintlayout-in-android-using-jetpack-compose/](https://www.geeksforgeeks.org/constraintlayout-in-android-using-jetpack-compose/)

**约束布局**是[视图组](https://www.geeksforgeeks.org/difference-between-view-and-viewgroup-in-android/)中的视图系统，用于相对于屏幕上其他小部件的位置放置小部件。在 Jetpack Compose 中，几乎每个布局都可以使用`行`和`列`来创建，但是如果您想要创建更大的复杂布局，您也可以使用约束布局作为行和列的替代。在本文中，我们将创建一个简单的布局，演示如何在 Jetpack Compose 中使用`约束布局`。首先，从[这里](https://github.com/sunny52525/GFG-articles/blob/master/BounceAnimation/app/src/main/res/drawable-v24/gfg.jpg)抓取图像，或者使用您选择的任何图像。我们将创建这个布局。让我们看一下分步指南。

**先决条件：**

*   了解 [Kotlin](https://www.geeksforgeeks.org/kotlin-programming-language/)。
*   精通在 [XML Android](https://www.geeksforgeeks.org/android-ui-layouts/) 中创建布局。
*   了解 [Jetpack Compose](https://www.geeksforgeeks.org/basics-of-jetpack-compose-in-android/)。

### 分步实施

#### 步骤 1：创建一个新项目（或在现有的 Compose 项目中使用它）

要在 Android Studio Canary 版本中创建新项目，请参考文章[如何使用 Jetpack Compose 在 Android Studio Canary 版本中创建新项目。](https://www.geeksforgeeks.org/how-to-create-a-new-project-in-android-studio-canary-version-with-jetpack-compose/)

#### 步骤 2：添加依赖关系

打开 `build.gradle` (app) 并添加以下依赖项。

> 实现 “androidx.constraintlayout:constraintlayout-compose:1.0.0-alpha08”

#### 步骤 3：使用可组合

创建一个名为 `ConstraintLayoutExample` 的可组合函数。在 Jetpack Compose 中，我们有一个名为 `ConstraintLayout` 的可组合体，我们可以在其中放置其他可组合体，使其相对于其他组合体进行定位。在 Compose 中，我们使用 `createRefs()` 函数来创建引用，类似于视图系统中的 `Id`。在 `ConstraintLayoutExample` 函数中，放置一个 `ConstraintLayout` composable，并为顶部栏、徽标和底部文本创建三个我们需要的引用。

```kt
ConstraintLayout(
        modifier = Modifier
            .fillMaxSize()
            .background(Color.White)
    ) {

// Creating references
val (logo, topBar, companyName) = createRefs()

}
```

然后在 `ConstraintLayout` 内部创建一个`顶栏`，参考下面代码中的注释可以更好的理解如何放置约束。

```kt
// TopAppBar Composable
TopAppBar(
          modifier = Modifier
                .constrainAs(topBar) {

// top of TopAppBar constraints
                    // to top of parent
                    top.linkTo(parent.top)

// start of TopAppBar constraints
                    // to start of parent
                    start.linkTo(parent.start)

// end of TopAppBar constraints 
                    // to end of parent
                    end.linkTo(parent.end)
                },

backgroundColor = Green
  ) {

// Contents for topAppBar
Text(
     text = "Geeks for Geeks | Constraint Layout", color = Color.White
    )
}
```