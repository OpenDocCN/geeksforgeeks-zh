# C 语言中 FILE 的数据类型是什么？

> 原文:[https://www.geeksforgeeks.org/data-type-file-c/](https://www.geeksforgeeks.org/data-type-file-c/)

**先决条件:** [文件处理基础知识](https://www.geeksforgeeks.org/basics-file-handling-c/)
在 C 语言中，当文件处理完成时，使用一个词 File。什么是文件？
**示例**

```cpp
FILE *fp1, *fp2;

```

在进行文件处理时，我们经常使用 file 来声明指针，以便指向我们想要读取或写入的文件。因为我们声明了 FILE 类型的指针，所以我们可以说它是数据类型，但是什么类型的数据类型呢？文件是一种被定义为文件的结构类型。由于其实现是隐藏的，因此被认为是**不透明数据类型**。我们不知道类型是由什么组成的，我们只使用指向类型的指针，库知道类型的内部，可以使用数据。

文件的定义在 stdio 中，尽管它是系统特定的。

**以下是 ubuntu** 中 FILE 的定义

```cpp
struct _IO_FILE {
  int _flags;       /* High-order word is _IO_MAGIC; rest is flags. */
#define _IO_file_flags _flags

  /* The following pointers correspond to the C++ streambuf protocol. */
  /* Note:  Tk uses the _IO_read_ptr and _IO_read_end fields directly. */
  char* _IO_read_ptr;   /* Current read pointer */
  char* _IO_read_end;   /* End of get area. */
  char* _IO_read_base;  /* Start of putback+get area. */
  char* _IO_write_base; /* Start of put area. */
  char* _IO_write_ptr;  /* Current put pointer. */
  char* _IO_write_end;  /* End of put area. */
  char* _IO_buf_base;   /* Start of reserve area. */
  char* _IO_buf_end;    /* End of reserve area. */
  /* The following fields are used to support backing up and undo. */
  char *_IO_save_base; /* Pointer to start of non-current get area. */
  char *_IO_backup_base;  /* Pointer to first valid character of backup area */
  char *_IO_save_end; /* Pointer to end of non-current get area. */

  struct _IO_marker *_markers;

  struct _IO_FILE *_chain;

  int _fileno;
#if 0
  int _blksize;
#else
  int _flags2;
#endif
  _IO_off_t _old_offset; /* This used to be _offset but it's too small.  */

#define __HAVE_COLUMN /* temporary */
  /* 1+column number of pbase(); 0 is unknown. */
  unsigned short _cur_column;
  signed char _vtable_offset;
  char _shortbuf[1];

  /*  char* _save_gptr;  char* _save_egptr; */

  _IO_lock_t *_lock;
#ifdef _IO_USE_OLD_IO_FILE
};

struct _IO_FILE_complete
{
  struct _IO_FILE _file;
#endif
#if defined _G_IO_IO_FILE_VERSION && _G_IO_IO_FILE_VERSION == 0x20001
  _IO_off64_t _offset;
# if defined _LIBC || defined _GLIBCPP_USE_WCHAR_T
  /* Wide character stream stuff.  */
  struct _IO_codecvt *_codecvt;
  struct _IO_wide_data *_wide_data;
  struct _IO_FILE *_freeres_list;
  void *_freeres_buf;
  size_t _freeres_size;
# else
  void *__pad1;
  void *__pad2;
  void *__pad3;
  void *__pad4;
  size_t __pad5;
# endif
  int _mode;
  /* Make sure we don't get into trouble again.  */
  char _unused2[15 * sizeof (int) - 4 * sizeof (void *) - sizeof (size_t)];
#endif
};

```

演示文件使用的 C 程序示例

```cpp
// Program beased on FILE handling.
#include<stdio.h>
int main()
{

    // declaring pointer of FILE type
    FILE *fp1, *fp2;
    char c;

    // pointing fp1 to a file geeky.txt
    // to read from it.
    fp1 = fopen("geeky.txt", "r");

    // pointing fp2 to a file outgeeky.txt
    // to write to it. 
    fp2 = fopen("outgeeky.txt", "w");

    // reading a character from file.
    fscanf(fp1, "%c", &c);

    // writing a character to file.
    fprintf(fp2, "%c", c);

    return 0;
}
```

**注意:**文件应该在程序存在的同一个目录下或者指定文件的路径。