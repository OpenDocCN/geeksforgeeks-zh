# 如何在 C# 的 DateTimePicker 中设置复选框？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中的复选框/](https://www.geeksforgeeks.org/how-to-set-a-check-box-in-the-datetimepicker-in-c-sharp/)

在 Windows 窗体中，DateTimePicker 控件用于选择和显示窗体中特定格式的日期/时间。在日期选择器控件中，您可以使用**显示复选框属性**在日期选择器中设置复选框。
如果该属性的值设置为 true，则在 DateTimePicker 控件中显示一个复选框，否则为 false。当复选框被选中时，这意味着日期/时间被更新，如果复选框未被选中，则您不能更新日期/时间。您可以通过两种不同的方式设置此属性:

**1。设计时:**在日期选择器中设置复选框是最简单的方法，如以下步骤所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/de9202f1f4646167e60ea580d67273d9.png)
*   **Step 2:** Next, drag and drop the DateTimePicker control from the toolbox to the form as shown in the below image:

    ![](img/1e722a2fb337b7d3bb23498b9f24712d.png)

*   **Step 3:** After drag and drop you will go to the properties of the DateTimePicker and set a checkbox in the DateTimePicker as shown in the below image:

    ![](img/785c997d8ecfd77679c22d94b356046d.png)

    **输出:**
    ![](img/4f05ddcde72f8e84738b654504cf8716.png)

**运行时间:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下，以编程方式设置 DateTimePicker 控件中的复选框:

```cs
public bool ShowCheckBox { get; set; }
```

该属性的值为**系统。布尔**类型，非真即假。此属性的默认值为 false。以下步骤显示了如何在日期时间选择器中动态设置复选框:

*   **步骤 1:** 使用 DateTimePicker 类提供的 DateTimePicker()构造函数创建一个 DateTimePicker。

    ```cs
    // Creating a DateTimePicker
    DateTimePicker dt = new DateTimePicker();

    ```

*   **步骤 2:** 创建日期选择器后，设置由日期选择器类提供的日期选择器的 ShowCheckBox 属性。

    ```cs
    // Setting the ShowCheckBox property
    dt.ShowCheckBox = true;

    ```

*   **第 3 步:**最后使用下面的语句将这个 DateTimePicker 控件添加到表单中:

    ```cs
    // Adding this control to the form
    this.Controls.Add(dt);

    ```

**示例:**

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

namespace WindowsFormsApp49 {

public partial class Form1 : Form {

    public Form1()
    {
        InitializeComponent();
    }

    private void Form1_Load(object sender, EventArgs e)
    {
        // Creating and setting the 
        // properties of the Label
        Label lab = new Label();
        lab.Location = new Point(183, 162);
        lab.Size = new Size(172, 20);
        lab.Text = "Select Date of Birth";
        lab.Font = new Font("Comic Sans MS", 12);

        // Adding this control to the form
        this.Controls.Add(lab);

        // Creating and setting the 
        // properties of the DateTimePicker
        DateTimePicker dt = new DateTimePicker();
        dt.Location = new Point(360, 162);
        dt.Size = new Size(292, 26);
        dt.MaxDate = new DateTime(2500, 12, 20);
        ;
        dt.MinDate = new DateTime(1753, 1, 1);
        dt.Format = DateTimePickerFormat.Short;
        dt.Name = "MyPicker";
        dt.Font = new Font("Comic Sans MS", 12);
        dt.ShowCheckBox = true;

        // Adding this control to the form
        this.Controls.Add(dt);
    }
}
}
```

**输出:**

![](img/04285e48d2ab04769b3b7999dcbc8403.png)