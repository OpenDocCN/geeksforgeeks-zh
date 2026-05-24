# 如何在 C# 中设置 CheckBox 的可见性？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中复选框的可见性/](https://www.geeksforgeeks.org/how-to-set-the-visibility-of-the-checkbox-in-c-sharp/)

CheckBox 控件是 windows 窗体中用于接收用户输入的部分。或者换句话说，CheckBox 控件允许我们从给定的列表中选择单个或多个元素。在 CheckBox 中，您可以设置一个代表 CheckBox 的值，并使用 CheckBox 的**可见属性**显示其 CheckBox 控件。

如果要显示给定的 CheckBox 及其子控件，则将“可见”属性的值设置为真，否则设置为假。此属性的默认值为真。在 Windows 窗体中，可以通过两种不同的方式设置此属性:

**1。设计时:**使用以下步骤设置复选框的可见属性是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单:
    T3】Visual Studio->File->New->Project->windows formapp

![](img/9889dfd1d09174ca813cf58170ab9cc8.png)

*   **步骤 2:** 从工具箱中拖动 CheckBox 控件，并将其放到窗口窗体上。您可以根据需要将 CheckBox 放在 windows 窗体上的任何位置。

![](img/b2eefad9eaf627dfc013a2924a1a41f0.png)

*   **步骤 3:** 拖放后，您将转到 CheckBox 控件的属性，通过使用可见属性来设置 CheckBox 的可见性。

![](img/6544dbe44a28408f22e7f2689acc5c51.png)

**输出:**

![](img/80ec2da7f7089d4cff39007dba12b2fb.png)

**注意:**如果 Visible 属性的值为 true，有时控件可能不可见，因为它们隐藏在其他控件后面。

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以使用以下语法设置 CheckBox 的 Visible 属性:

```cs
public bool Visible { get; set; }
```

这里，该属性的值类型为*系统。布尔*。以下步骤用于设置复选框的可见属性:

*   **步骤 1:** 使用 checkbox 类提供的 CheckBox()构造函数创建一个 CheckBox。

```cs
// Creating checkbox
CheckBox Mycheckbox = new CheckBox();
```

*   **步骤 2:** 创建 CheckBox 后，设置 CheckBox 类提供的 CheckBox 的可见属性。

```cs
// Set the Visible property of the CheckBox
Mycheckbox.Visible = true;
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
        Mycheckbox.Visible = true;

        // Adding checkbox to form
        this.Controls.Add(Mycheckbox);

        // Creating and setting the properties of CheckBox
        // This CheckBox is not displayed in the output because
        // the visibility of this CheckBox is set to be false

        CheckBox Mycheckbox1 = new CheckBox();
        Mycheckbox1.Height = 50;
        Mycheckbox1.Width = 100;
        Mycheckbox1.Location = new Point(230, 174);
        Mycheckbox1.Text = "Female";
        Mycheckbox1.Visible = false;

        // Adding checkbox to form
        this.Controls.Add(Mycheckbox1);
    }
}
}
```

**输出:**

![](img/e7c43a6c3171922f8231658f066fd507.png)