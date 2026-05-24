# 如何在 C# 中使用 CheckBox 的 AutoCheck 属性？

> 原文:[https://www . geeksforgeeks . org/如何使用-自动检查-c-sharp 中复选框的属性/](https://www.geeksforgeeks.org/how-to-use-autocheck-property-of-checkbox-in-c-sharp/)

CheckBox 控件是 windows 窗体中用于接收用户输入的部分。或者换句话说，CheckBox 控件允许我们从给定的列表中选择单个或多个元素。您可以设置一个值来确定已检查或已检查的状态值，并且当您使用**自动检查属性**单击复选框时，复选框的外观会自动设置。该房产的价值属于*系统。布尔*类型。
如果“自动检查”属性值为真，则单击复选框时，“已检查”或“检查状态”的值以及复选框的外观会自动更改。否则，假的。此属性的默认值为真。在 Windows 窗体中，可以通过两种不同的方式设置此属性:

**1。设计时:**使用以下步骤设置复选框的自动检查属性是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单
    T3】Visual Studio->File->New->Project->windows formpp

![](img/2ddebe34e4657619941285899ab3c91f.png)

*   **步骤 2:** 从工具箱中拖动 CheckBox 控件，并将其放到窗口窗体上。您可以根据需要将 CheckBox 放在 windows 窗体上的任何位置。

![](img/e7225de327187dbfa4127c7ddbf8a761.png)

*   **第 3 步:**拖放后，您将转到 CheckBox 控件的属性来设置自动检查属性的值。

![](img/c80f2acef46431ff0460a255e9c0f2dd.png)

*   **输出:**

![](img/12a181a5ac756404e796402925dad46c.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，可以使用以下语法以编程方式设置 CheckBox 的自动检查属性:

```cs
public bool AutoCheck { get; set; }
```

以下步骤用于设置复选框的自动检查属性:

*   **步骤 1:** 使用 checkbox 类提供的 CheckBox()构造函数创建一个 CheckBox。

```cs
// Creating checkbox
CheckBox Mycheckbox = new CheckBox();
```

*   **步骤 2:** 创建 CheckBox 后，设置 CheckBox 类提供的 CheckBox 的自动检查属性。

```cs
// Set the AutoCheck property of the CheckBox
Mycheckbox.AutoCheck = false;
```

*   **第 3 步:**最后使用 add()方法将该复选框控件添加到表单中。

```cs
// Add this checkbox to form
this.Controls.Add(Mycheckbox);
```

*   **示例:**

## C#

```cs
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace WindowsFormsApp5 {

public partial class Form1 : Form {

    public Form1()
    {
        InitializeComponent();
    }

    private void Form1_Load(object sender, EventArgs e)
    {
        // Creating and setting the properties of label
        Label l = new Label();
        l.Text = "Select language:";
        l.AutoSize = true;
        l.Location = new Point(233, 111);
        l.Font = new Font("Bradley Hand ITC", 12);
        // Adding label to form
        this.Controls.Add(l);

        // Creating and setting the properties of CheckBox
        CheckBox Mycheckbox = new CheckBox();
        Mycheckbox.Height = 50;
        Mycheckbox.Width = 100;
        Mycheckbox.Location = new Point(229, 136);
        Mycheckbox.Text = "C#";
        Mycheckbox.AutoCheck = false;
        Mycheckbox.Font = new Font("Bradley Hand ITC", 12);

        // Adding checkbox to form
        this.Controls.Add(Mycheckbox);

        // Creating and setting the properties of CheckBox
        CheckBox Mycheckbox1 = new CheckBox();
        Mycheckbox1.Height = 50;
        Mycheckbox1.Width = 100;
        Mycheckbox1.Location = new Point(230, 198);
        Mycheckbox1.Text = "Ruby";
        Mycheckbox1.AutoCheck = true;
        Mycheckbox1.Font = new Font("Bradley Hand ITC", 12);

        // Adding checkbox to form
        this.Controls.Add(Mycheckbox1);
    }
}
}
```

*   **输出:**

![](img/a1abd3d6bfe8409372e15309472a06d0.png)