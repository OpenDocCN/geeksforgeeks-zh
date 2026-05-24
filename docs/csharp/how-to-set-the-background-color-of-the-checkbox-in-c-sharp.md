# 如何在 C# 中设置 CheckBox 的背景色？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中复选框的背景颜色/](https://www.geeksforgeeks.org/how-to-set-the-background-color-of-the-checkbox-in-c-sharp/)

CheckBox 控件是 windows 窗体的一部分，用于接受用户的输入。或者换句话说，CheckBox 控件允许我们从给定的列表中选择单个或多个元素。在 CheckBox 中，您可以使用 CheckBox 的**背景颜色属性**来设置 CheckBox 的背景颜色。这会让你的 CheckBox 更有吸引力。在 Windows 窗体中，可以通过两种不同的方式设置该属性:
**1。设计时:**使用以下步骤设置 CheckBox 的 BackColor 属性是最简单的方法:

*   **第一步:**创建如下图所示的 windows 窗体:
    **Visual Studio->File->New->Project->windows formpp**

![](img/2ddebe34e4657619941285899ab3c91f.png)

*   **步骤 2:** 从工具箱中拖动 CheckBox 控件，并将其放到窗口窗体上。您可以根据需要将 CheckBox 放在 windows 窗体上的任何位置。

![](img/e7225de327187dbfa4127c7ddbf8a761.png)

*   **第 3 步:**拖放后，您将转到 CheckBox 控件的属性来设置 BackColor 属性的值。

![](img/180ce62355548abc9682e2e34cd18512.png)

*   **输出:**

![](img/40d77c8909e8572512904b2d59c1504f.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以使用以下语法以编程方式设置 CheckBox 的 BackColor 属性:

```cs
public override System.Drawing.Color BackColor { get; set; }
```

这里，颜色用于表示复选框的背景颜色。以下步骤用于设置复选框的背景颜色属性:

*   **步骤 1:** 使用 checkbox 类提供的 CheckBox()构造函数创建一个 CheckBox。

```cs
// Creating checkbox
CheckBox Mycheckbox = new CheckBox();
```

*   **步骤 2:** 创建 CheckBox 后，设置 CheckBox 类提供的 CheckBox 的 BackColor 属性。

```cs
// Set the BackColor property of the CheckBox
Mycheckbox.BackColor = Color.LightPink;
```

*   **第 3 步:**最后使用 add()方法将该复选框控件添加到表单中。

```cs
// Add this checkbox to form
this.Controls.Add(Mycheckbox);
```

*   **例:**

## c sharp . c sharp . c sharp . c sharp

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
        l.Location = new Point(233, 111);

        // Adding label to form
        this.Controls.Add(l);

        // Creating and setting the properties of CheckBox
        CheckBox Mycheckbox = new CheckBox();
        Mycheckbox.Height = 50;
        Mycheckbox.Width = 100;
        Mycheckbox.Location = new Point(229, 136);
        Mycheckbox.Text = "C#";
        Mycheckbox.BackColor = Color.LightPink;

        // Adding checkbox to form
        this.Controls.Add(Mycheckbox);

        // Creating and setting the properties of CheckBox
        CheckBox Mycheckbox1 = new CheckBox();
        Mycheckbox1.Height = 50;
        Mycheckbox1.Width = 100;
        Mycheckbox1.Location = new Point(250, 198);
        Mycheckbox1.Text = "Ruby";
        Mycheckbox1.BackColor = Color.LightGreen;

        // Adding checkbox to form
        this.Controls.Add(Mycheckbox1);
    }
}
}
```

*   **输出:**

![](img/ac01ea5cada9b8a37395d1e058c2ae56.png)