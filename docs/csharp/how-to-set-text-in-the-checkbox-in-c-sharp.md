# 如何在 C# 中设置 CheckBox 中的文本？

> 原文:[https://www . geesforgeks . org/如何设置 c-sharp 中的复选框文本/](https://www.geeksforgeeks.org/how-to-set-text-in-the-checkbox-in-c-sharp/)

CheckBox 控件是 windows 窗体的一部分，用于接受用户的输入。或者换句话说，CheckBox 控件允许我们从给定的列表中选择单个或多个元素。在复选框中，您可以使用复选框的**文本属性**设置复选框中的文本。这会让你的 CheckBox 更有吸引力。在 Windows 窗体中，可以通过两种不同的方式设置此属性:

**1。设计时:**使用以下步骤设置复选框的文本属性是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单
    T3】Visual Studio->File->New->Project->windows formpp

![](img/2ddebe34e4657619941285899ab3c91f.png)

*   **步骤 2:** 从工具箱中拖动 CheckBox 控件，并将其放到窗口窗体上。您可以根据需要将 CheckBox 放在 windows 窗体上的任何位置。

![](img/e7225de327187dbfa4127c7ddbf8a761.png)

*   **步骤 3:** 拖放后，您将转到 CheckBox 控件的属性，使用 text 属性设置与 CheckBox 关联的文本。

![](img/71672b3aceb2018a2eef6891c591e548.png)

**输出:**

![](img/042c8142a9a0eabc3d9e4e176bfc21cd.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以使用以下语法以编程方式设置复选框的文本属性:

```cs
public override string Text { get; set; }
```

这里，CheckBox 的文本是字符串类型的。以下步骤用于设置复选框的文本属性:

*   **步骤 1:** 使用 checkbox 类提供的 *CheckBox()构造函数*创建一个复选框。

```cs
// Creating checkbox
CheckBox Mycheckbox = new CheckBox();
```

*   **步骤 2:** 创建 CheckBox 后，设置 CheckBox 类提供的 CheckBox 的 Text 属性。

```cs
// Set the Text property of the CheckBox
Mycheckbox.Text = "C#";
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
        Mycheckbox.ForeColor = Color.DarkGreen;
        Mycheckbox.Name = "First_Check_Box";

        // Adding checkbox to form
        this.Controls.Add(Mycheckbox);

        // Creating and setting the properties of CheckBox
        CheckBox Mycheckbox1 = new CheckBox();
        Mycheckbox1.Height = 50;
        Mycheckbox1.Width = 100;
        Mycheckbox1.Location = new Point(250, 198);
        Mycheckbox1.Text = "Ruby";
        Mycheckbox1.BackColor = Color.LightGreen;
        Mycheckbox1.ForeColor = Color.DeepPink;
        Mycheckbox1.Name = "Second_Check_Box";
        // Adding checkbox to form
        this.Controls.Add(Mycheckbox1);
    }
}
}
```

**输出:**

![](img/73be838807f1f9536d0b1cf6f391c979.png)