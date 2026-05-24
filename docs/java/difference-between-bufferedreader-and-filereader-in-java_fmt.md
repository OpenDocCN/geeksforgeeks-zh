# Java 中 BufferedReader 和 FileReader 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-bufferedreader-and-filereader-in-java/](https://www.geeksforgeeks.org/difference-between-bufferedreader-and-filereader-in-java/)

`BufferedReader` 和 `FileReader` 这两个类都用于从给定的字符流中读取数据。两者各有利弊。在本文中，我们将讨论它们之间的差异。虽然最重要的区别在于它们的工作方式，但我们也会讨论其他细节。

## 什么是缓冲区？

缓冲区是设备内存存储的一小部分，用于临时存储一定数量的数据。通常，缓冲区使用设备的内存来存储临时数据，因此，从缓冲区访问数据比从硬盘访问相同数量的数据要快得多。

`BufferedReader` 和 `FileReader` 之间的差异通过考虑以下主要参数进行了说明和讨论：

1.  用法
2.  效率
3.  速度
4.  阅读行

### 1. 用法

`FileReader` 用于从磁盘驱动器读取文件，而 `BufferedReader` 不仅限于读取文件。它可以用来从任何字符流中读取数据。`FileReader` 类提供了两个构造函数：

*   `FileReader(File file)`: 它接受一个代表磁盘中文件的 `File` 对象，并创建一个新的 `FileReader` 实例。
*   `FileReader(FileDescriptor fd)`: 给定要读取的文件描述符，创建一个新的 `FileReader`。
*   `FileReader(String fileName)`: 将文件名作为唯一参数，并创建一个新的 `FileReader` 实例来读取文件。

`BufferedReader` 类提供了两种构造函数：

*   `BufferedReader(Reader rd)`: 它使用 `Reader` 从字符输入流中读取数据，并创建一个默认大小的输入缓冲区。
*   `BufferedReader(Reader rd, int size)`: 采用两个参数：
    *   第一: 用于读取输入流数据的 `Reader`
    *   第二: 输入缓冲区的大小。它用给定大小的输入缓冲区创建一个新的 `BufferedReader`。

如图所示，`BufferedReader` 接受任何类型的 `Reader`（`StringReader`、`FileReader` 等）并因此能够从任何字符输入流中读取。而 `FileReader` 只能从文件中读取字符。通常，我们用 `BufferedReader` 包装 `FileReader`，以便从文件中读取字符。

### 2. 效率

就性能而言，`BufferedReader` 比 `FileReader` 高效得多。`FileReader` 直接从来自文件的字符流中读取数据。每次，它读取一个字符，它直接访问磁盘驱动器，每次磁盘驱动器需要一些时间来正确定位读取头，这使得它非常低效。

而 `BufferedReader` 创建了一个输入缓冲区，允许以大块数据而不是一次一个字节的形式从硬盘中读取输入，从而大大提高了性能。默认的缓冲区大小是 8Kb（在大多数情况下这已经足够了），尽管它可以自定义。缓冲存储器一次读取大量数据，并将其存储在创建的缓冲存储器中。当调用 `BufferedReader.read()` 时，它从内存缓冲区读取数据。当数据在缓冲区中不可用时，它会对底层字符流发出相应的读取请求，并将大量数据加载到创建的缓冲区中。因此，当读取每个字符时，我们不必直接访问硬盘，我们可以从缓冲存储器中读取，这更快、更有效。

### 3. 速度

由于 `BufferedReader` 在内部使用缓冲区，这个类比 `FileReader` 快得多。`BufferedReader` 不需要像 `FileReader` 那样每次都访问硬盘，因此速度更快。

### 4. 阅读行

在大多数情况下，您希望一次读取一行，而不是一次读取一个字符，只有 `BufferedReader` 提供了一种一次读取整行的 `readLine()` 方法。简单地说，给定的读取器（在这种情况下是 `FileReader`）读取字符并将其存储在缓冲区中。当调用 `BufferedReader.readLine()` 方法时，存储在缓冲区中的一行字符将作为字符串返回。它节省了大量时间，因此比 `FileReader#read()` 方法更快。请注意，`BufferedReader` 一次只能读取一整行，因为它使用缓冲存储器，它可以将一行的字符存储在缓冲区中，并直接从缓冲区中一起读取所有字符。

## 结论：BufferedReader 和 FileReader 的区别

| 基础 | BufferedReader | FileReader |
| :--- | :--- | :--- |
| 用法 | 用于从任何类型的字符输入流（`String`、文件等）中读取字符。 | 它只能用于读取文件 |
| 缓冲区 | 在内部使用缓冲区读取字符 | 不使用缓冲区。通过访问硬盘直接读取文件。 |
| 速度 | 更快的 | 慢的 |
| 效率 | 更有效地读取文件 | 效率较低 |
| 阅读行 | `BufferedReader` 可以用来一次读取一个字符，也可以一次读取一行。 | 它一次只能读取一个字符，不能读取行 |

## 实施

### 示例 1：使用 BufferedReader 读取行

```java
// Java Program to differenciate between
// BufferedReader and FileReader in Java

// Reading lines using BufferedReader

// Import necessary classes
import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        FileReader reader;

        // Try block to check exceptions
        try {

            // A Reader that reads creates an input
            // character stream
            // and reads characters from it
            reader = new FileReader("geeks.txt");

            // Creating a BufferedReader object (instance)
            //  that 16Kb in buffer in the memory
            BufferedReader buffer
                = new BufferedReader(reader, 16384);

            // Custom input
            // A string to store the lines
            String line = "";

            // Maintaining real time count using
            // currentTimeMillis() method to get time taken
            // to read the data
            long initialTime = System.currentTimeMillis();
            while (true) {

                // Try block to check exceptions
                try {

                    // readLine() method of BufferedReader
                    // returns
                    //  a whole line at a time
                    line = buffer.readLine();
                }
```

## BufferedReader 与 FileReader 的比较

### 示例 1: 使用 BufferedReader 读取行

```java
// Java Program to differenciate between
// BufferedReader and FileReader in Java

// Reading lines using BufferedReader

// Import necessary classes
import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

// Class
public class GFG {

// Main driver method
    public static void main(String[] args)
    {
        BufferedReader reader;

// Try block to check if exception occured
        try {

// A BufferedReader to read data from "geeks.txt"
            // File present in local directory
            reader = new BufferedReader(new FileReader("geeks.txt"));

String line;

// Stores the initial current time
            long initialTime = System.currentTimeMillis();
            while (true) {
                try {
                    // The readLine() method of BufferedReader
                    // reads a line of text
                    line = reader.readLine();
                }
                // Catch block to handle exceptions
                catch (IOException e) {
                    // Print the line where exception occurred
                    e.printStackTrace();
                }

// When the read head reaches the "End Of File" the readLine method returns null
                if (line == null)
                    break;

// Prints the line
                System.out.println(line);
            }

// New line
            System.out.println();

// Display the time taken to read the data
            System.out.println("Time taken : "
                               + (System.currentTimeMillis()
                                  - initialTime));

// Try block to check exceptions
            try {
                // Close all the streams
                reader.close();
            }
            // Catching only exceptions those occurred only during closing streams
            catch (IOException e) {
                // Prints the line number where exception occurred
                e.printStackTrace();
            }
        }
        // Catch block
        catch (FileNotFoundException e) {
            // print the exception only if the file not found
            e.printStackTrace();
        }
    }
}
```

`输出:`来自上面程序中使用的本地目录中的文件`geeks.txt`

> 你好极客们！
>
> BufferedReader 使用文件读取器从该文件中读取数据。
>
> 缓冲区缓存器创建一个给定大小的输入缓冲区(如果没有给定大小，默认大小为 8Kb)。
>
> 如果我们只使用文件阅读器，那么它通过直接访问磁盘驱动器一次读取一个字符。
>
> 每次读取数据时，磁盘驱动器都需要一些时间来正确定位读取头，这使得读取效率非常低。
>
> 每次访问磁盘驱动器读取一个字符都会影响性能。
>
> 而 BufferedReader 创建一个缓冲区，使用给定的文件读取器读取大量数据，并将其加载到内存中的输入缓冲区。
>
> 每次您想要读取文件数据时，您可以从缓冲区中读取它(您不必每次都直接访问磁盘驱动器)，因此比文件阅读器更快。
>
> `时间:3`

### 示例 2: 仅使用 FileReader 读取行

```java
// Java Program to differenciate between
// BufferedReader and FileReader in Java

// Reading lines using FileReader

// Import necessary classes
import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

// Class
public class GFG {

// Main driver method
    public static void main(String[] args)
    {
        FileReader reader;

// Try block to check if exception occured
        try {

// A FileReader to read data from "geeks.txt"
            // File present in local directory
            reader = new FileReader("geeks.txt");

char ch;

// An integer to store the integer returned by FileReader#read() method
            int i = -1;

// Stores the initial current time
            long initialTime = System.currentTimeMillis();
            while (true) {
                try {
                    // The read() method of FileReader reads one character at a time and returns it as an integer
                    i = reader.read();
                }
                catch (IOException e) {
                    e.printStackTrace();
                }

// When the "End Of File" is reached the read() method returns -1
                if (i == -1)
                    break;

ch = (char)i;
                System.out.print(ch);
            }

// New line
            System.out.println();

// Display and print the time taken
            System.out.println("Time taken : "
                               + (System.currentTimeMillis()
                                  - initialTime));

try {
                reader.close();
            }
            catch (IOException e) {
                e.printStackTrace();
            }
        }
        catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

`输出:`来自上面程序中使用的本地目录中的文件`geeks.txt`

> 你好极客们！
>
> BufferedReader 使用文件读取器从该文件中读取数据。
>
> 缓冲区缓存器创建一个给定大小的输入缓冲区(如果没有给定大小，默认大小为 8Kb)。
>
> 如果我们只使用文件阅读器，那么它通过直接访问磁盘驱动器一次读取一个字符。
>
> 每次读取数据时，磁盘驱动器都需要一些时间来正确定位读取头，这使得读取效率非常低。
>
> 每次访问磁盘驱动器读取一个字符都会影响性能。
>
> 而 BufferedReader 创建一个缓冲区，使用给定的文件读取器读取大量数据，并将其加载到内存中的输入缓冲区。
>
> 每次您想要读取文件数据时，您可以从缓冲区中读取它(您不必每次都直接访问磁盘驱动器)，因此比文件读取器更高效。
>
> `时间:32`

**注:**

1.  在您的系统中，读取过程所花费的时间可能会有所不同，但事实是 `BufferedReader` 比 `FileReader` 工作得更快、更高效。
2.  如果你想要一个好的表现，那么你会把两者结合使用。`BufferedReader` 本身并不从输入流中读取数据，它使用一个与本机系统 API 交互的读取器(通常是文件读取器)来从给定的输入源中读取字符(文件读取器情况下的文件)。`BufferedReader` 类只是向字符流中添加一个缓冲区，并从缓冲区中读取字符，而不是直接从输入源中读取。因此，您可以只使用文件阅读器来读取文件，因为它可以访问硬盘来读取数据。但是您不能使用“仅 `BufferedReader`”来读取文件，因为它没有访问硬盘的权限，您必须提供一个具有访问权限的读取器(文件读取器)。