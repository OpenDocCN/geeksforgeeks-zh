# 不透明指针

> 原文:[https://www.geeksforgeeks.org/opaque-pointer/](https://www.geeksforgeeks.org/opaque-pointer/)

**什么是不透明指针？**
不透明顾名思义就是我们看不透的东西。例如木材是不透明的。不透明指针是一种指向数据结构的指针，该数据结构的内容在其定义时没有被公开。

跟随指针不透明。人们不能通过查看定义来知道 STest 结构中包含的数据。

```cpp
struct STest* pSTest;
```

将空值赋给不透明指针是安全的。

```cpp
pSTest = NULL; 
```

**为什么指针不透明？**
有些地方我们就是想提示编译器“嘿！这是我们的客户将使用的一些数据结构。不用担心，客户端会在准备编译单元的时候提供它的实现”。当我们处理共享代码时，这种类型的设计是健壮的。请看下面的例子:

假设我们正在开发一个处理图像的应用程序。由于我们生活在一个一切都在向云发展、设备非常便宜的世界，我们希望为 windows、安卓和苹果平台开发应用程序。因此，如果有一个根据我们的要求健壮、可扩展和灵活的好设计就好了。我们可以拥有所有平台都可以使用的共享代码，然后不同的端点可以拥有特定于平台的代码。
为了处理图像，我们有一个 CImage 类公开 API 来处理各种图像操作(缩放、旋转、移动、保存等)。
由于所有平台将提供相同的操作，我们将在头文件中定义这个类。但是不同平台处理图像的方式可能不同。像苹果可以有不同的机制来访问图像的像素，而不是视窗系统。这意味着 API 可能需要不同的信息集来执行操作。因此，为了开发共享代码，我们希望这样做:

**Image.h :** 存储类声明的头文件。

```cpp
// This class provides API to deal with various
// image operations. Different platforms can 
// implement these operations in different ways.
class CImage
{
public:
    CImage();
    ~CImage();
    struct SImageInfo* pImageInfo;
    void Rotate(double angle);
    void Scale(double scaleFactorX, 
               double scaleFactorY);
    void Move(int toX, int toY);    
private:
    void InitImageInfo();
};
```

**Image.cpp :** 将在不同端点间共享的代码

```cpp
// Constructor and destructor for CImage
CImage::CImage()
{
    InitImageInfo();
}

CImage::~CImage()
{
    // Destroy stuffs here
}
```

**Image_windows.cpp :** 特定于 windows 的代码将驻留在这里

```cpp
struct SImageInfo
{
   // Windows specific DataSet
};

void CImage::InitImageInfo()
{
    pImageInfo = new SImageInfo;
    // Initialize windows specific info here
}

void CImage::Rotate()
{
    // Make use of windows specific SImageInfo
}
```

**Image_apple.cpp :** 苹果特有的代码将驻留在这里

```cpp
struct SImageInfo
{
    // Apple specific DataSet
};
void CImage::InitImageInfo()
{
    pImageInfo = new SImageInfo;

    // Initialize apple specific info here
}
void CImage::Rotate()
{
    // Make use of apple specific SImageInfo
}
```

从上面的例子可以看出，**在定义 CImage 类的蓝图时，我们只提到有一个 SImageInfo 数据结构。
司马根福的含量不详。现在，客户(windows、苹果、安卓)有责任定义这种数据结构，并按照他们的要求使用它**。如果将来我们想为一个新的端点‘X’开发应用程序，设计已经在那里了。我们只需要为端点‘X’定义 SImageInfo 并相应地使用它。

请注意，上面解释的例子是这样做的一种方式。设计就是讨论和需求。一个好的设计是在考虑了许多因素后决定的。我们还可以有特定于平台的类，如 CImageWindows、CImageApple，并将所有特定于平台的代码放在那里。

有问题吗？让他们继续来。我们很乐意回答。

本文由 [**阿施·巴恩瓦尔**](https://about.me/aashishbarnwal?promo=email_sig&utm_source=email_sig&utm_medium=external_link&utm_campaign=chrome_ext) 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论