# 如何在 C# 的 DateTimePicker 中设置最大日期？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中的最大日期时间选择器/](https://www.geeksforgeeks.org/how-to-set-maximum-date-in-the-datetimepicker-in-c-sharp/)

在 Windows 窗体中，DateTimePicker 控件用于在窗体中选择和显示具有特定格式的日期/时间。在日期选择器控件中，您可以使用**最大日期属性**设置日期选择器中可以选择的最大日期和时间。这个属性的默认值是 9998 年 12 月 31 日上午 12 点。您可以通过两种不同的方式设置此属性:

**1。设计时间:**最简单的方法是在日期时间选择器中设置最大日期和时间，如以下步骤所示:

*   **Step 1:** Create a windows form as shown in the below image:

    **Visual Studio - >文件- >新建- >项目->window formapp**

    ![](img/de9202f1f4646167e60ea580d67273d9.png)

*   **Step 2:** Next, drag and drop the DateTimePicker control from the toolbox to the form as shown in the below image:

    ![](img/1e722a2fb337b7d3bb23498b9f24712d.png)

*   **Step 3:** After drag and drop you will go to the properties of the DateTimePicker and set the maximum date and time in the DateTimePicker as shown in the below image:

    ![](img/9a7ff99ad6405b34bfe2906684e999bf.png)

    **输出:**

    ![](img/f43dc1f7e2a99b49df63621f9d826fdb.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下，以编程方式设置 DateTimePicker 控件中的最大日期和时间:

```cs
public DateTime MaxDate { get; set; }
```

如果该属性的值不小于 MaxDate 值，它将引发 ArgumentException 如果该属性的值小于 MinDateTime 值，它还将引发 *SystemException* 。以下步骤显示了如何在 DateTimePicker 中动态设置最大日期和时间:

*   **步骤 1:** 使用 DateTimePicker 类提供的 DateTimePicker()构造函数创建一个 DateTimePicker。

    ```cs
    // Creating a DateTimePicker
    DateTimePicker dt = new DateTimePicker();

    ```

*   **步骤 2:** 创建日期时间选择器后，设置由日期时间选择器类提供的日期时间选择器的最大日期属性。

    ```cs
    // Setting the maximum date and time 
    dt.MaxDate = new DateTime(2500, 12, 20);

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

namespace WindowsFormsApp48 {

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
        lab.Text = "Select Date and Time";
        lab.Font = new Font("Comic Sans MS", 12);

        // Adding this control
        // to the form
        this.Controls.Add(lab);

        // Creating and setting the
        // properties of the DateTimePicker
        DateTimePicker dt = new DateTimePicker();
        dt.Location = new Point(360, 162);
        dt.Size = new Size(292, 26);
        dt.MaxDate = new DateTime(2500, 12, 20);
        dt.MinDate = new DateTime(1753, 1, 1);
        dt.Format = DateTimePickerFormat.Long;
        dt.Name = "MyPicker";
        dt.Font = new Font("Comic Sans MS", 12);
        dt.Visible = true;
        dt.Value = DateTime.Today;

        // Adding this control 
        // to the form
        this.Controls.Add(dt);
    }
}
}
```

**输出:**

![](img/e2a739f46e56377525df58a21c86ec7d.png)