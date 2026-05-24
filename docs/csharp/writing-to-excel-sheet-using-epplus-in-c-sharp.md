# 用 C# 中的 EPPlus 写入 Excel 工作表

> 原文:[https://www . geeksforgeeks . org/writing-to-excel-sheet-using-epplus-in-c-sharp/](https://www.geeksforgeeks.org/writing-to-excel-sheet-using-epplus-in-c-sharp/)

EPPlus 是一个非常有帮助的开源[第三方 DLL](https://stackoverflow.com/questions/17364730/what-is-third-party-dll) 用于将数据写入 excel。EPPlus 支持电子表格的多种属性，如单元格区域、单元格样式、图表、图片、形状、注释、表格、保护、加密、透视表、数据验证、条件格式、公式计算等。

首先，通过编写以下命令，使用数据包管理器控制台安装 EPPlus:

```cs
Install-Package EPPlus 

```

让我们看看如何使用 C# 创建和写入 excel 工作表。

```cs
using System;
using System.IO;
// The following to two namespace contains
// the functions for manipulating the
// Excel file 
using OfficeOpenXml;
using OfficeOpenXml.Style;

class Program
{
    static void Main(string[] args)
    {
        var Articles = new[]
        {
                new {
                    Id = "101", Name = "C++"
                },
                new {
                    Id = "102", Name = "Python"
                },
                new {
                    Id = "103", Name = "Java Script"
                },
                new {
                    Id = "104", Name = "GO"
                },
                new {
                    Id = "105", Name = "Java"
                },
                new {
                    Id = "106", Name = "C#"
                }
            };

        // Creating an instance
        // of ExcelPackage
        ExcelPackage excel = new ExcelPackage();

        // name of the sheet
        var workSheet = excel.Workbook.Worksheets.Add("Sheet1");

        // setting the properties
        // of the work sheet 
        workSheet.TabColor = System.Drawing.Color.Black;
        workSheet.DefaultRowHeight = 12;

        // Setting the properties
        // of the first row
        workSheet.Row(1).Height = 20;
        workSheet.Row(1).Style.HorizontalAlignment = ExcelHorizontalAlignment.Center;
        workSheet.Row(1).Style.Font.Bold = true;

        // Header of the Excel sheet
        workSheet.Cells[1, 1].Value = "S.No";
        workSheet.Cells[1, 2].Value = "Id";
        workSheet.Cells[1, 3].Value = "Name";

        // Inserting the article data into excel
        // sheet by using the for each loop
        // As we have values to the first row 
        // we will start with second row
        int recordIndex = 2;

        foreach (var article in Articles)
        {
            workSheet.Cells[recordIndex, 1].Value = (recordIndex - 1).ToString();
            workSheet.Cells[recordIndex, 2].Value = article.Id;
            workSheet.Cells[recordIndex, 3].Value = article.Name;
            recordIndex++;
        }

        // By default, the column width is not 
        // set to auto fit for the content
        // of the range, so we are using
        // AutoFit() method here. 
        workSheet.Column(1).AutoFit();
        workSheet.Column(2).AutoFit();
        workSheet.Column(3).AutoFit();

        // file name with .xlsx extension 
        string p_strPath = "H:\\geeksforgeeks.xlsx";

        if (File.Exists(p_strPath))
            File.Delete(p_strPath);

        // Create excel file on physical disk 
        FileStream objFileStrm = File.Create(p_strPath);
        objFileStrm.Close();

        // Write content to excel file 
        File.WriteAllBytes(p_strPath, excel.GetAsByteArray());
        //Close Excel package
        excel.Dispose();
        Console.ReadKey();

    }
}
```

**输出:**

![Writing in Excel File](img/263e45ae24f675b60a434b091041bba0.png)

在这个程序中，我们获取了文章数据的静态值，但是实时地，我们可以使用数据库调用和 foreach 循环来迭代每个记录。