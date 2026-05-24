# 如何解压缩 Golang 中的文件？

> 原文:[https://www . geesforgeks . org/如何解压缩 golang 中的文件/](https://www.geeksforgeeks.org/how-to-uncompress-a-file-in-golang/)

根据维基百科，**数据压缩**或文件压缩可以理解为在保留原始数据的同时减小特定文件/文件夹/任何数据大小的过程。较小的文件大小有很多好处，因为它将占用较少的存储区域，为您提供更多的空间来容纳其他数据，随着文件大小的减小，传输文件的速度会更快，并且在文件压缩时会解锁各种其他额外功能。压缩文件以压缩文件扩展名文件夹的形式存储，如“*”。拉链*、*。rar* ”、“ *.tar.gz* ”、“*。arj* ”和“*”。tgz* ”。压缩会将文件大小减小到最大压缩大小。如果不能进一步压缩，则尺寸应保持不变，且不能变小。

在数据被压缩后，我们经常感到需要撤销它们，以便使它们易于访问。这个撤销过程被称为**解压缩**。从压缩文件中提取普通文件/文件夹的过程称为解压缩。

#### 但是如何解压缩文件呢？

有各种软件为我们执行这样的任务；我知道的一个最好的例子是 WinRAR/WinZip。它们能够压缩和解压缩数据文件。但是我们单独依赖软件有多久呢？他们的大部分功能都是付费的，除了财务方面，我们程序员是否必须永远依赖外包应用程序来满足我们的需求？还是可以挖掘出自己的方式来满足自己的要求？嗯，数据解压缩也可以手动完成。下面将使用 GoLang 讨论一种这样的手动方法。

**示例:**

**案例场景:**归档文件夹中的文件。程序将所有文件提取到目标位置。

## 去

```go
package main

import (
    "archive/zip"
    "fmt"
    "io"
    "log"
    "os"
    "path/filepath"
    "strings"
)

func main() {

    // Unzip accepts two arguments:
    // First argument represents
    // the source directory
    // path where archived files are present.
    // Second argument represents the
    // destination directory path where unzipped
    // files will be stored after uncompression.
    // Note that destination folder will be created
    // inside pwd and then files will be 
    // extracted into the destination folder.
    // Unzip returns 2 values:
    // names of files in archived directory & error (if any)

    files, err := Unzip("compression-test.zip", "uncompressed files")

    // If any error is present then that
    // error value will be assigned to err
    // In case of no error, err will be equal to nill
    // condition check to ensure if any error
    // is present we'd print the error message
    // and log the error using log.Fatal

    if err != nil {        
        log.Fatal(err)
    }

    fmt.Println("Unzipped the following files:\n" + strings.Join(files, "\n"))

    //end of main function
}

// Unzip will decompress a zip archived file,
// copying all files and folders
// within the zip file (parameter 1)
// to an output directory (parameter 2).

func Unzip(src string, destination string) ([]string, error) {

    // a variable that will store any
    //file names available in a array of strings
    var filenames []string

    // OpenReader will open the Zip file
    // specified by name and return a ReadCloser
    // Readcloser closes the Zip file,
    // rendering it unusable for I/O
    // It returns two values:
    // 1\. a pointer value to ReadCloser
    // 2\. an error message (if any)
    r, err := zip.OpenReader(src)

    // if there is any error then
    // (err!=nill) becomes true 
    if err != nil {
        // and this block will break the loop
        // and return filenames gathered so far
        // with an err message, and move
        // back to the main function

        return filenames, err
    }

    defer r.Close()
    // defer makes sure the file is closed
    // at the end of the program no matter what.

    for _, f := range r.File {

    // this loop will run until there are
    // files in the source directory & will
    // keep storing the filenames and then 
    // extracts into destination folder until an err arises

        // Store "path/filename" for returning and using later on
        fpath := filepath.Join(destination, f.Name)

        // Checking for any invalid file paths
        if !strings.HasPrefix(fpath, filepath.Clean(destination)+string(os.PathSeparator)){
            return filenames, fmt.Errorf("%s is an illegal filepath", fpath)
        }

        // the filename that is accessed is now appended
        // into the filenames string array with its path
        filenames = append(filenames, fpath)

        if f.FileInfo().IsDir() {

            // Creating a new Folder
            os.MkdirAll(fpath, os.ModePerm)
            continue
        }

        // Creating the files in the target directory
        if err = os.MkdirAll(filepath.Dir(fpath), os.ModePerm); err != nil {
            return filenames, err
        }

        // The created file will be stored in
        // outFile with permissions to write &/or truncate
        outFile, err := os.OpenFile(fpath, 
                                    os.O_WRONLY|os.O_CREATE|os.O_TRUNC,
                                    f.Mode())

        // again if there is any error this block
        // will be executed and process
        // will return to main function
        if err != nil {
            // with filenames gathered so far
            // and err message
            return filenames, err
        }

        rc, err := f.Open()

        // again if there is any error this block
        // will be executed and process
        // will return to main function        
        if err != nil {
            // with filenames gathered so far
            // and err message back to main function
            return filenames, err
        }

        _, err = io.Copy(outFile, rc)

        // Close the file without defer so that
        // it closes the outfile before the loop
        // moves to the next iteration. this kinda
        // saves an iteration of memory & time in
        // the worst case scenario.
        outFile.Close()
        rc.Close()

        // again if there is any error this block
        // will be executed and process
        // will return to main function
        if err != nil {
            // with filenames gathered so far
            // and err message back to main function
            return filenames, err
        }
    }

    // Finally after every file has been appended
    // into the filenames string[] and all the
    // files have been extracted into the
    // target directory, we return filenames
    // and nil as error value as the process executed
    // successfully without any errors*
    // *only if it reaches until here.
    return filenames, nil
}
```

```go
My pwd path                   : ../src/myprograms/unzip and zip
Source zip folder             : ../src/myprograms/unzip and zip/compression-test.zip
Compression-test.zip contains : *Hello world.txt                     main.go*
Destination path              : ../src/myprograms/unzip and zip/uncompressed files
Output on my screen:
Unzipped the following files:
uncompressed files\compression-test\Hello world.txt
uncompressed files\compression-test\main.go

```

**Visual Studio 代码上的可视化演示:**

<video class="wp-video-shortcode" id="video-460383-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200727181139/unzipafileinGO.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200727181139/unzipafileinGO.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200727181139/unzipafileinGO.mp4)</video>