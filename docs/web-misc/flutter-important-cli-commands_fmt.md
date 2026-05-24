# Flutter – 重要的命令行界面命令

> 原文: [https://www.geeksforgeeks.org/flutter-important-cli-commands/](https://www.geeksforgeeks.org/flutter-important-cli-commands/)

[Flutter](https://www.geeksforgeeks.org/what-is-flutter/) 是谷歌管理的移动开发 UI 套件。它由 [Dart](https://www.geeksforgeeks.org/introduction-to-dart-programming-language/) 语言提供动力，该语言用于 Flutter 框架，使移动、网络和桌面应用程序具有单一代码库。Flutter 命令行工具使用户能够与 Flutter SDK 交互。

在本文中，我们将讨论 Flutter 使用的所有命令。我们将看到几乎所有 Flutter 项目中使用的最重要的命令及其解释。

### 1. 创建应用程序

```
Syntax: flutter create APP_NAME
```

该命令在当前目录中创建新的 Flutter app 项目。如果您想在特定的文件夹中创建项目，那么首先使用命令 `cd FILE ADDRESS` 移动到该目录。

### 2. 分析 Dart 代码

```
Syntax: flutter analyze -d <DEVICE_ID>
```

该命令对项目的 Dart 源代码进行静态分析。基本上它所做的就是搜索任何丢失的代码或错误。它可以针对特定文件或整个 Flutter 项目执行。

### 3. 测试 Flutter 应用

```
Syntax: flutter test [<DIRECTORY|DART_FILE>]
```

该命令对 Flutter 项目或特定的 Dart 文件进行测试。它检查应用程序或代码是否有缺陷。如果我们的应用程序很大，并且手动测试是不可能的，这是非常有用的。

### 4. 运行 Dart 文件

```
Syntax: flutter run <DART_FILE>
```

这个命令将运行 Dart 文件（如果提到的话），否则它将在用户选择的设备中运行整个项目。

### 5. 下载依赖项/包

```
Syntax: flutter pub get
```

该命令下载当前或活动项目文件的 `pubspeck.yaml` 文件中列出的所有包或依赖项。

### 6. 更新 Flutter 包

```
Syntax: flutter pub update
```

该命令将更新当前项目中使用的 Flutter 包。

### 7. 获取帮助

```
Syntax: flutter --help --verbose
```

这是一个非常有用的命令，尤其是对于初学者。它显示了 Flutter 使用的所有命令的列表。

### 8. 检查项目运行状况

```
Syntax: flutter doctor
```

该命令将检查 Flutter 信息的当前状态。如果某些软件丢失或不工作，它将显示一个警告。

### 9. 检查版本

```
Syntax: flutter version
```

它显示了 Flutter 和 Dart SDK 的版本相关信息。

### 10. 检查频道

```
Syntax: flutter channel <CHANNEL_NAME>
```

该命令将列出所有可用的 Flutter 通道。您可以看到您使用的是哪一个，或者切换到另一个来访问新功能。一般 `稳定` 是大多数人用的。

### 11. 构建项目

```
Syntax: flutter build <DIRECTORY>
```

这个命令是在我们想要的目录中构建 Flutter 应用程序。如果我们不分配目录，那么它将在构建文件夹中构建。我们可以用 `flutter build web` 命令构建 Web 应用，用 `flutter build apk` 或 `flutter build appbundel` 命令构建安卓应用（更好），用 `flutter build ios` 命令构建 iOS 应用。

### 12. 列出连接的设备

```
Syntax: flutter devices -d <DEVICE_ID>
```

这是列出所有连接设备的命令，我们可以在这些设备上运行我们的 Flutter 应用程序。然后我们可以连接到我们选择的设备来运行 Flutter 应用程序。

### 13. 升级 Flutter 版本

```
Syntax: flutter upgrade
```

该命令应该在系统中全局运行。它在我们的机器上升级了 Flutter SDK 和 Dart SDK 的副本。在每个新版本发布后运行这个命令通常是个好主意。

### 14.获取项目所需的包:

```
Syntax:  flutter assemble -o <DIRECTORY>
```

该命令获取应用程序中使用的所有必要的包(如果尚未出现)，然后构建应用程序。

### 15.添加预先存在的颤振应用程序:

```
Syntax: flutter attach -d <DEVICE_ID>
```

该命令类似于 `flutter run` 命令，但是当我们向使用另一个框架制作的应用程序添加 flutter 时，它提供了除 `flutter run` 命令之外的某些其他终端功能。这个命令应该在我们向一个预先存在的应用程序添加 flutter 时使用，如果我们简单地给出 `flutter run` 命令，那么我们将不会得到热重载、开发工具和其他功能。

### 16.使用堆栈跟踪文件:

```
Syntax: flutter symbolize --input=<STACK_TRACK_FILE>
```

该命令用于使堆栈跟踪可读。堆栈跟踪可能是应用程序崩溃时生成的文件。

### 17.配置功能:

```
Syntax: flutter config --build-dir=<DIRECTORY>
```

该命令用于配置项目中所需的 flutter 功能。例如您可以启用或禁用 flutter web。

### 18.降级颤振/飞镖 SDK:

```
Syntax: flutter downgrade
```

该命令应该在系统中全局运行。它将我们机器中的 flutter SDK 和 dart SKD 的副本降级为以前可用的活动版本。如果在当前版本的 flutter 中有些东西对你不起作用，这是可以做到的。

### 19.使用连接的设备硬件:

```
Syntax: flutter drive
```

如果我们的 flutter 项目从用户的设备访问一些硬件，这需要应用一些驱动程序，那么这就是我们喊运行的命令，以测试我们的驱动程序是否运行良好，没有错误。

### 20.列出可用的仿真器:

```
Syntax: flutter emulators
```

这个命令列出了当前安装在我们机器上的所有仿真器，如果我们愿意，可以选择启动仿真器并创建一个新的仿真器。

### 21.设置 Dart 文件格式:

```
Syntax: flutter format <DART_FILE | DIRECTORY>
```

该 flutter 命令根据 flutter SDK 中预先指定的设置格式化 dart 文件。但是如果您使用的是安装了 flutter 和 dart 扩展的 VS-Code 或 Android Studio，那么 dart 会自动格式化。

### 22.本地获取依赖项:

```
Syntax: flutter gen-l10n <DIRECTORY>
```

该命令用于生成颤振相关性的本地文件。例如，如果我们通过一个应用编程接口使用某些字体的法师，这个命令将使他们在本地可用。对于所有选项，使用此命令 `flutter gen-l10n -h` 。

### 23.在设备上安装颤振应用程序:

```
Syntax: flutter install -d <DEVICE_ID>
```

这是在构建应用程序后在连接的设备上安装 flutter 应用程序的命令。连接的设备可以是安卓或 iOS 手机等物理设备，也可以是模拟器或浏览器等内置应用程序。

### 24.查看终端日志:

```
Syntax: flutter logs
```

这个命令向我们显示了终端中运行 flutter 应用程序的日志输出。它通常用于判断应用程序中的某些代码是否被破坏或给出异常。

### 25.列出项目资产:

```
Syntax: flutter precache <ARGUMENTS> 
```

该命令用于获取 flutter 应用程序在本地或全球使用的所有资产。