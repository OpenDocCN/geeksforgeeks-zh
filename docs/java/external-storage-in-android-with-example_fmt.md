# 安卓外部存储示例

> 原文：[https://www.geeksforgeeks.org/external-storage-in-android-with-example/](https://www.geeksforgeeks.org/external-storage-in-android-with-example/)

安卓为存储应用数据提供了多种选择，它使用类似于计算机平台上基于磁盘的系统的文件系统。

*   **Application-specific storage:** 在内部卷目录或外部存储数据文件。这些数据文件仅供应用程序使用。它使用内部存储目录来存储敏感信息，例如用户名和密码，其他应用程序不应访问。
*   **Shared storage:** 存储图像、音频、视频、文档和其他数据文件。这些数据可能需要与其他应用程序共享。
*   **Sharing preferences:** 以键值对的形式存储原始数据类型，如整数、浮点数、布尔值、字符串和长整型。
*   **Database:** 存储结构化数据，例如用户信息（姓名、年龄、电话号码、电子邮件、地址等）到私有数据库。

建议开发者根据**所需空间**、**可靠数据访问**和**数据隐私**来使用可用选项存储数据。通过外部存储设备保存的数据文件可以使用通用串行总线大容量存储传输在共享的外部存储设备上公开访问。使用**文件输出流**对象存储在外部存储器上的数据文件，可以使用**文件输入流**对象**读取。**

## 外部存储可用性

为了避免应用崩溃，我们需要检查存储SD卡是否可用于读写操作。方法`getExternalStorageState()`用于确定SD卡等已挂载存储介质的状态是缺失、只读还是可读、可写。下面是我们将用来检查外部存储可用性的代码片段。

### Java

```java
boolean isAvailable= false;
boolean isWritable= false;
boolean isReadable= false;
String state = Environment.getExternalStorageState();

if(Environment.MEDIA_MOUNTED.equals(state)) {
  // Operation possible - Read and Write
  isAvailable= true;
  isWritable= true;
  isReadable= true;
} else if (Environment.MEDIA_MOUNTED_READ_ONLY.equals(state)) {
      // Operation possible - Read Only
      isAvailable= true;
      isWritable= false;
      isReadable= true;
} else {
      // SD card not available
      isAvailable = false;
      isWritable= false;
      isReadable= false; 
}
```