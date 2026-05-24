# 如何在 C# 中设置 CheckBox 的外观？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中复选框的外观/](https://www.geeksforgeeks.org/how-to-set-the-appearance-of-the-checkbox-in-c-sharp/)

CheckBox 控件是 windows 窗体的一部分，用于接受用户的输入。或者换句话说，CheckBox 控件允许我们从给定的列表中选择单个或多个元素。通过使用 CheckBox 类提供的**外观属性**，您可以将 CheckBox 用作普通的 CheckBox 或将 CheckBox 用作按钮。
外观属性设置为正常，那么它的行为就像正常的 CheckBox，如果外观属性设置为按钮，那么它将像切换按钮一样工作。默认情况下，此属性的值为“正常”。在 Windows 窗体中，可以通过两种不同的方式设置此属性:

**1。设计时:**使用以下步骤设置复选框的外观属性是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单
    T3】Visual Studio->File->New->Project->windows formpp

![](img/2ddebe34e4657619941285899ab3c91f.png)

*   **步骤 2:** 从工具箱中拖动 CheckBox 控件，并将其放到窗口窗体上。您可以根据需要将 CheckBox 放在 windows 窗体上的任何位置。

![](img/e7225de327187dbfa4127c7ddbf8a761.png)

*   **第 3 步:**拖放后，您将转到 CheckBox 控件的属性来设置外观属性的值。

![](img/6c66313619d72bc9d2aa80ed3bc0caa4.png)

**输出:**

![](img/c531aa6a4fe94501928025ebc931d0c8.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以使用以下语法以编程方式设置 CheckBox 的外观属性:

```cs
public System.Windows.Forms.Appearance Appearance { get; set; }
```

如果分配给该属性的值不是外观值，它还会引发*InvalidEnumArgumentException*。以下步骤用于设置复选框的外观属性:

*   **步骤 1:** 使用 checkbox 类提供的 CheckBox()构造函数创建一个 CheckBox。

```cs
// Creating checkbox
CheckBox Mycheckbox = new CheckBox();
```

*   **步骤 2:** 创建 CheckBox 后，设置 CheckBox 类提供的 CheckBox 的外观属性。

```cs
// Set the Appearance property of the CheckBox
Mycheckbox.Appearance = Appearance.Normal;
```

*   **第 3 步:**最后使用 add()方法将该复选框控件添加到表单中。

```cs
// Add this checkbox to form
this.Controls.Add(Mycheckbox);
```

**示例:**

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
        Mycheckbox.Appearance = Appearance.Normal;
        Mycheckbox.Font = new Font("Bradley Hand ITC", 12);

        // Adding checkbox to form
        this.Controls.Add(Mycheckbox);

        // Creating and setting the properties of CheckBox
        CheckBox Mycheckbox1 = new CheckBox();
        Mycheckbox1.Height = 50;
        Mycheckbox1.Width = 100;
        Mycheckbox1.Location = new Point(230, 198);
        Mycheckbox1.Text = "Ruby";
        Mycheckbox1.Appearance = Appearance.Button;
        Mycheckbox1.Font = new Font("Bradley Hand ITC", 12);

        // Adding checkbox to form
        this.Controls.Add(Mycheckbox1);
    }
}
}
```

**输出:**

![](img/f07304ee3231956fdc8b908937e4956e.png)