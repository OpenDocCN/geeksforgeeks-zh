# 如何在 C# 的 DateTimePicker 中设置上下按钮？

> 原文:[https://www . geeksforgeeks . org/如何设置和按下按钮-in-datetime picker-in-c-sharp/](https://www.geeksforgeeks.org/how-to-set-up-and-down-button-in-datetimepicker-in-c-sharp/)

在 Windows 窗体中，DateTimePicker 控件用于在窗体中选择和显示具有特定格式的日期/时间。在日期选择器控件中，您可以使用**显示向下属性**在日期选择器中设置旋转按钮控件或上下控件来调整日期/时间。如果此属性的值设置为 true，则在 DateTimePicker 控件中显示上下控件，否则为 false。您可以通过两种不同的方式设置此属性:

**1。设计时:**在 DateTimePicker 中设置上下控件是最简单的方法，如以下步骤所示:

*   **Step 1:** Create a windows form as shown in the below image:

    **Visual Studio->File->New->Project->window formapp**
    ![](img/de9202f1f4646167e60ea580d67273d9.png)

*   **Step 2:** Next, drag and drop the DateTimePicker control from the toolbox to the form as shown in the below image:

    ![](img/1e722a2fb337b7d3bb23498b9f24712d.png)

*   **Step 3:** After drag and drop you will go to the properties of the DateTimePicker and set an up-down control in the DateTimePicker as shown in the below image:

    ![](img/db6ce33d3383e8e249de7ba7bd136656.png)

    **输出:**

    ![](img/adf5ba303752f435313a75788fbe1b27.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下，以编程方式在 DateTimePicker 控件中设置上下控件:

```cs
public bool ShowUpDown { get; set; }
```

该属性的值为**系统。布尔**类型，非真即假。此属性的默认值为 false。以下步骤显示了如何在 DateTimePicker 中动态设置上下控件:

*   **步骤 1:** 使用 DateTimePicker 类提供的 DateTimePicker()构造函数创建一个 DateTimePicker。

    ```cs
    // Creating a DateTimePicker
    DateTimePicker dt = new DateTimePicker();

    ```

*   **步骤 2:** 创建日期选择器后，设置由日期选择器类提供的日期选择器的 ShowUpDown 属性。

    ```cs
    // Setting the ShowUpDown property
    dt.ShowUpDown = true;

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
        lab.Text = "Select Time";
        lab.Font = new Font("Comic Sans MS", 12);

        // Adding this control to the form
        this.Controls.Add(lab);

        // Creating and setting the 
        // properties of the DateTimePicker
        DateTimePicker dt = new DateTimePicker();
        dt.Location = new Point(360, 162);
        dt.Size = new Size(292, 26);
        dt.MaxDate = new DateTime(2500, 12, 20);
        dt.MinDate = new DateTime(1753, 1, 1);
        dt.Format = DateTimePickerFormat.Time;
        dt.Name = "MyPicker";
        dt.Font = new Font("Comic Sans MS", 12);
        dt.ShowUpDown = true;

        // Adding this control
        // to the form
        this.Controls.Add(dt);
    }
}
}
```

**输出:**

![](img/3e2198075214ab1d09d2f62b79fe3e9e.png)