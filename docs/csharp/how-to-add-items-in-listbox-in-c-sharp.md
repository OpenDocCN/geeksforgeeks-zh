# 如何用 C# 在 ListBox 中添加项目？

> 原文:[https://www . geesforgeks . org/如何在 c-sharp 列表框中添加项目/](https://www.geeksforgeeks.org/how-to-add-items-in-listbox-in-c-sharp/)

在 Windows 窗体中，ListBox 控件用于显示列表中的多个元素，用户可以从中选择一个或多个元素，这些元素通常显示在多个列中。在列表框中，可以使用**项属性**在列表框中添加项。此属性允许您获取对当前存储在列表框中的元素列表的引用。在此引用的帮助下，您可以添加、移除和获取集合中元素的计数。您可以通过两种不同的方式设置此属性:

**1。设计时:**在列表框中添加元素最简单的方法如下所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/52a0adebea6c33bdc662683df034f77e.png)
*   **步骤 2:** 从工具箱中拖动 ListBox 控件，并将其放到 windows 窗体上。根据您的需要，您可以将列表框控件放在窗口窗体的任何位置。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the ListBox control to add elements in the ListBox.
    ![](img/a45cb13a0e0a4c71ab4d2f731db0f811.png)

    **输出:**
    ![](img/2e9e93d695c7d0ced399ecef3606a9df.png)

**2。RunTime:** 比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式添加 ListBox 控件中的元素:

```cs
public System.Windows.Forms.ListBox.ObjectCollection Items { get; }
```

这里， *ListBox。对象集合*表示列表框中的元素。以下步骤显示了如何在列表框中动态添加元素:

*   **步骤 1:** 使用 list box 类提供的 ListBox()构造函数创建列表框。

    ```cs
    // Creating ListBox using ListBox class constructor
    ListBox mylist = new ListBox();

    ```

*   **步骤 2:** 创建 ListBox 后，设置 ListBox 类提供的 ListBox 的 Items 属性。

    ```cs
    // Adding the elements in the ListBox
    mylist.Items.Add("GeeksForGeeks");

    ```

*   **Step 3:** And last add this ListBox control to the form using Add() method.

    ```cs
    // Add this ListBox to the form
    this.Controls.Add(mylist);

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

    namespace WindowsFormsApp26 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting the 
            // properties of ListBox
            ListBox mylist = new ListBox();
            mylist.Location = new Point(287, 109);
            mylist.Size = new Size(120, 95);
            mylist.BorderStyle = BorderStyle.Fixed3D;
            mylist.Items.Add("Geeks");
            mylist.Items.Add("GFG");
            mylist.Items.Add("GeeksForGeeks");
            mylist.Items.Add("gfg");

            // Adding ListBox control to the form
            this.Controls.Add(mylist);
        }
    }
    }
    ```

    **输出:**

    ![](img/ab9c8963ef51411d67c9b2149c735cdd.png)