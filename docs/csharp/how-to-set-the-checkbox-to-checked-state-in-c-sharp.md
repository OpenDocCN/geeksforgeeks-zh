# 如何在 C# 中将 CheckBox 设置为 CheckBox 状态？

> 原文:[https://www . geeksforgeeks . org/如何将复选框设置为 c-sharp 中的选中状态/](https://www.geeksforgeeks.org/how-to-set-the-checkbox-to-checked-state-in-c-sharp/)

CheckBox 控件是 windows 窗体的一部分，用于接受用户的输入。或者换句话说，CheckBox 控件允许我们从给定的列表中选择单个或多个元素。在复选框中，您可以使用复选框的**选中属性**将复选框的状态设置为选中。
如果该属性的值为真，表示复选框处于选中状态，否则为假。“选中属性”的默认值为假。当“选中属性”的值设置为真时，对于正常外观，复选框显示勾号，对于按钮外观，控件看起来凹陷。在 Windows 窗体中，可以通过两种不同的方式设置此属性:

**1。设计时:**使用以下步骤设置复选框的选中属性是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单:
    T3】Visual Studio->File->New->Project->windows formapp

![](img/9889dfd1d09174ca813cf58170ab9cc8.png)

*   **步骤 2:** 从工具箱中拖动 CheckBox 控件，并将其放到窗口窗体上。您可以根据需要将 CheckBox 放在 windows 窗体上的任何位置。

![](img/b2eefad9eaf627dfc013a2924a1a41f0.png)

*   **步骤 3:** 拖放后，您将转到 CheckBox 控件的属性，使用 CheckBox 属性将 CheckBox 设置为选中状态。

![](img/53b0013fed3a26a1d2cc04002b00e00f.png)

**输出:**

![](img/fdf28254746600f1e79cb703af96f878.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以使用以下语法以编程方式设置 CheckBox 的 Checked 属性:

```cs
public bool Checked { get; set; }
```

这里，该属性的值类型为*系统。布尔*。如果三个状态的值设置为真，那么 Checked 属性将从 Checked 或 unlimited check state 返回 true。以下步骤用于设置复选框的“选中”属性:

*   **步骤 1:** 使用 checkbox 类提供的 CheckBox()构造函数创建一个 CheckBox。

```cs
// Creating checkbox
CheckBox Mycheckbox = new CheckBox();
```

*   **步骤 2:** 创建 CheckBox 后，设置 CheckBox 类提供的 CheckBox 的 CheckBox 属性。

```cs
// Set the Checked property of the CheckBox
Mycheckbox.Checked = true;
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
        l.Text = "Select Gender:";
        l.Location = new Point(233, 111);

        // Adding label to form
        this.Controls.Add(l);

        // Creating and setting the properties of CheckBox
        CheckBox Mycheckbox = new CheckBox();
        Mycheckbox.Height = 50;
        Mycheckbox.Width = 100;
        Mycheckbox.Location = new Point(229, 136);
        Mycheckbox.Text = "Male";
        Mycheckbox.Checked = true;

        // Adding checkbox to form
        this.Controls.Add(Mycheckbox);

        // Creating and setting the properties of CheckBox
        CheckBox Mycheckbox1 = new CheckBox();
        Mycheckbox1.Height = 50;
        Mycheckbox1.Width = 100;
        Mycheckbox1.Location = new Point(230, 174);
        Mycheckbox1.Text = "Female";
        Mycheckbox1.Checked = false;

        // Adding checkbox to form
        this.Controls.Add(Mycheckbox1);
    }
}
}
```

**输出:**

![](img/3d5a0be263110a7479096c7a8e081793.png)