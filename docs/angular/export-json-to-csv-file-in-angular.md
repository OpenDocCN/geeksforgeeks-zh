# 在 Angular

中将 JSON 导出到 CSV 文件

> 原文:[https://www . geesforgeks . org/export-JSON-to-CSV-file-in-angular/](https://www.geeksforgeeks.org/export-json-to-csv-file-in-angular/)

在本文中，我们将学习如何使用 **angular 8** 中的 **Blob** 将 **JSON 数组**转换为 **CSV** 以及如何**将 CSV** 导出为可下载文件。

**演示:**[https://stackblitz.com/edit/angular8-json-to-csv](https://stackblitz.com/edit/angular8-json-to-csv)

**步骤 1:** 将 JSON 转换为 CSV
要将 JSON 数据转换为 CSV 格式，请使用以下方法。

```ts
ConvertToCSV(objArray, headerList) {
    let array = typeof objArray != 'object' ? JSON.parse(objArray) : objArray;
    let str = '';
    let row = 'S.No, ';
    for (let index in headerList) {
        row += headerList[index] + ', ';
    }
    row = row.slice(0, -1);
    str += row + '\r\n';
    for (let i = 0; i & lt; array.length; i++) {
        let line = (i + 1) + & #039;;&# 039;;
        for (let index in headerList) {
            let head = headerList[index];
            line += & #039;,  &# 039; + array[i][head];
        }
        str += line + & #039;\r\nn&# 039;;
    }
    return str;
}
```

**第一个**参数是对象数组，**第二个**参数是标题列表一般是 Json 的键。

**步骤 2:** 将 CSV 导出为可下载文件。
用于将 CSV 数据导出为*。csv* 文件使用以下方法。

```ts
downloadFile(data, filename = 'data') {
    let csvData = this.ConvertToCSV(data, [
      'name', 'age', 'average', 'approved', 'description']);
    console.log(csvData)
    let blob = new Blob(['\ufeff' + csvData], {
        type: 'text/csv;charset=utf-8;'
    });
    let dwldLink = document.createElement("a");
    let url = URL.createObjectURL(blob);
    let isSafariBrowser = navigator.userAgent.indexOf(
      'Safari') != -1 & amp; & amp;
    navigator.userAgent.indexOf('Chrome') == -1;

    //if Safari open in new window to save file with random filename.
    if (isSafariBrowser) { 
        dwldLink.setAttribute("target", "_blank");
    }
    dwldLink.setAttribute("href", url);
    dwldLink.setAttribute("download", filename + ".csv");
    dwldLink.style.visibility = "hidden";
    document.body.appendChild(dwldLink);
    dwldLink.click();
    document.body.removeChild(dwldLink);
}
```

下载方法接受两个参数，JSONdata 中的**第一个**参数和**第二个**参数是文件名。这里的默认文件名是**数据**。在下载文件方法中，我们调用 ***ConvertToCSV*** 方法将 JSON 转换为 CSV。

一个 **[Blob](https://developer.mozilla.org/en-US/docs/Web/API/Blob)** 对象代表一个不可变的原始数据的类似文件的对象。Blobs 代表不一定是 JavaScript 原生格式的数据。**文件**界面基于 blob，继承 Blob 功能并扩展它以支持用户系统上的文件。

**app.service.ts:** 创建一个名为 *app.component.ts* 的新服务文件

```ts
import {
    Injectable
}
from '@angular/core';
@Injectable()
export class AppService {
    downloadFile(data, filename = 'data') {
        let csvData = this.ConvertToCSV(data, [
            'name', 'age', 'average', 'approved', 'description'
        ]);
        console.log(csvData)
        let blob = new Blob(['\ufeff' + csvData], {
            type: 'text/csv;charset=utf-8;'
        });
        let dwldLink = document.createElement("a");
        let url = URL.createObjectURL(blob);
        let isSafariBrowser = navigator.userAgent.indexOf(
            'Safari') != -1 & amp; & amp;
        navigator.userAgent.indexOf('Chrome') == -1;
        /if Safari open in new window to save file with random filename.
        if (isSafariBrowser) {
            /
            dwldLink.setAttribute("target", "_blank");
        }
        dwldLink.setAttribute("href", url);
        dwldLink.setAttribute("download", filename + ".csv");
        dwldLink.style.visibility = "hidden";
        document.body.appendChild(dwldLink);
        dwldLink.click();
        document.body.removeChild(dwldLink);
    }
    ConvertToCSV(objArray, headerList) {
        let array =
            typeof objArray != 'object' ? JSON.parse(objArray) : objArray;
        let str = '';
        let row = 'S.No, ';
        for (let index in headerList) {
            row += headerList[index] + ', ';
        }
        row = row.slice(0, -1);
        str += row + '\r\n';
        for (let i = 0; i & lt; array.length; i++) {
            let line = (i + 1) + & #039;;&# 039;;
            for (let index in headerList) {
                let head = headerList[index];
                line += & #039;,  &# 039; + array[i][head];
            }
            str += line + & #039;\r\nn&# 039;;
        }
        return str;
    }
}
```

现在我们有了我们的服务文件，在我们的组件中使用这个服务文件来发送数据，并检查我们的 downloadFile 方法是否正常工作。在创建组件之前，首先在 **app.module.ts** 中导入我们的服务

**app.module.ts:**

```ts
import { AppService } from './app.service';
@NgModule({
  providers: [AppService],
})</pre>

<h5>app.component.ts:-</h5>
<pre>
import { Component } from '@angular/core';
import { AppService } from './app.service';
@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: [ './app.component.css' ]
})
export class AppComponent  {
constructor(private appService:AppService) {  }
  jsonData =  [
      {
        name: "Anil Singh",
        age: 33,
        average: 98,
        approved: true,
        description: "I am active blogger and Author."
      },
      {
        name: 'Reena Singh',
        age: 28,
        average: 99,
        approved: true,
        description: "I am active HR."
      },
      {
        name: 'Aradhya',
        age: 4,
        average: 99,
        approved: true,
        description: "I am engle."
      },
    ];
  download(){
    this.appService.downloadFile(this.jsonData, 'jsontocsv');
  }
}
```

**输出:**app.component.html 文件
T3】