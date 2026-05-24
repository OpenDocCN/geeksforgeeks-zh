# 生物节律–序列输入/输出

> 原文: [https://www.geeksforgeeks.org/biopython-sequence-input-output/](https://www.geeksforgeeks.org/biopython-sequence-input-output/)

Biopython 有一个内置的 `Bio.SeqIO` 模块，提供分别从文件读取序列和向文件写入序列的功能。`Bio.SeqIO` 支持生物信息学中使用的几乎所有文件处理格式。Biopython 严格遵循单一方法，用 `SeqRecord` 对象向用户表示解析后的数据序列。

## 记录

`SeqRecord` 对象由 `Bio.SeqRecord` 模块提供，保存序列的元数据以及关于序列的信息。下面列出了一些主要数据信息:

| **记录** | **描述** |
| --- | --- |
| `seq` | 要解析的实际序列。 |
| `id` | 序列的主要标识，默认情况下是字符串类型 |
| `name` | 序列的名称，默认情况下是字符串类型。 |
| `description` | 以人类可读的格式显示有关序列的信息。 |
| `annotations` | 包含与序列相关的附加信息的字典。 |

## 读取顺序

`Bio.SeqIO` 模块有一个内置的 `read()` 方法，该方法获取一个序列文件，并根据文件格式将其转换为单个 `SeqRecord`。它能够解析只有一条记录的序列文件，如果文件没有记录或者有多条记录，那么就会引发异常。`read()` 方法的语法和参数如下:

```py
Bio.SeqIO.read(handle, format, alphabet=None)
```

| **参数** | **描述** |
| --- | --- |
| `handle` | 文件句柄或将文件名作为字符串(旧版本只接受句柄) |
| `format` | 文件格式为字符串 |
| `alphabet` | 可选参数，当序列类型不是从文件自动推断时使用(例如 `format = "fasta"`)。 |

### Python 3

```py
# Import libraries
from Bio import SeqIO

# Reading file
record = SeqIO.read("sequence.gb", "genbank")

# Showing records
print("ID: %s" % record.id)
print("Sequence length: %i" % len(record))
print("Sequence description: %s" % record.description)
```

**输出:**

![](img/b669b9d74647b79b9ac776061d5123a7.png)

## 解析顺序

`Bio.SeqIO` 模块提供的 `parse()` 方法在我们必须从句柄中读取多条记录时使用。它基本上将序列文件转换成迭代器，迭代器返回 `SeqRecords`。如果文件包含字符串数据，那么它必须被转换为句柄来解析它。无法确定字母表的文件格式，明确指定字母表(例如 FASTA)。`parse()` 方法的语法和参数如下:

```py
Bio.SeqIO.parse(handle, format, alphabet=None)
```

| **参数** | **描述** |
| --- | --- |
| `handle` | 文件句柄或将文件名作为字符串(旧版本只接受句柄) |
| `format` | 字符串形式的文件格式 |
| `alphabet` | 可选参数，当序列类型不是从文件自动推断时使用(例如 `format = "fasta"`)。 |

### Python 3

```py
# Import libraries
from Bio import SeqIO

# Parsing file
filename = "sequence.fasta"
for record in SeqIO.parse(filename, "fasta"):

    # Showing records
    print("ID: %s" % record.id)
    print("Sequence length: %i" % len(record))
    print("Sequence description: %s" % record.description)
```

**输出:**

![](img/23ae24f9202c9558f60e6c74743a821e.png)

## 写入序列

`Bio.SeqIO` 模块有一个 `write()` 方法用于写入文件，该方法将序列集写入文件，并返回一个代表写入记录数的整数。请确保在调用句柄后关闭该句柄，否则数据将被刷新到磁盘。`write()` 方法的语法和参数如下:

```py
Bio.SeqIO.write(sequences, handle, format)
```

| **参数** | **描述** |
| --- | --- |
| `sequences` | `SeqRecord` 对象的列表或迭代器(或 Biopython 1.54 版或更高版本中的单个 `SeqRecord`) |
| `handle` | 文件句柄或将文件名作为字符串(旧版本只接受句柄) |
| `format` | 以小写字符串形式写入的文件格式 |

**注意:** 下载文件点击[这里](https://www.ncbi.nlm.nih.gov/nuccore/L42023)

### Python 3

```py
# Import libraries
from Bio import SeqIO
from Bio.Seq import Seq
from Bio.SeqRecord import SeqRecord

rec1 = SeqRecord(Seq("MMYQQGCFAGGTVLRLAKDLAENNRGARVLVVCSEITAVTFRGPSETHLDSMVGQALFGD"
                     + "GAGAVIVGSDPDLSVERPLYELVWTGATLLPDSEGAIDGHLREVGLTFHLLKDVPGLISK"
                     + "NIEKSLKEAFTPLGISDWNSTFWIAHPGGPAILDQVEAKLGLKEEKMRATREVLSEYGNM"),
                 id="gi|14150838|gb|AAK54648.1|AF376133_1",
                 description="chalcone synthase [Cucumis sativus]")

rec2 = SeqRecord(Seq("MVTVEEFRRAQCAEGPATVMAIGTATPSNCVDQSTYPDYYFRITNSEHKVELKEKFKRMC"
                     + "EKSMIKKRYMHLTEEILKENPNICAYMAPSLDARQDIVVVEVPKLGKEAAQKAIKEWGQP"
                     + "KSKITHLVFCTTSGVDMPGCDYQLTKLLGLRPSVKRFMMYQQGCFAGGTVLRMAKDLAEN"
                     + "NKGARVLVVCSEITAVTFRGPNDTHLDSLVGQALFGDGAAAVIIGSDPIPEVERPLFELV"
                     + "SAAQTLLPDSEGAIDGHLREVGLTFHLLKDVPGLISKNIEKSLVEAFQPLGISDWNSLFW"
                     + "IAHPGGPAILDQVELKLGLKQEKLKATRKVLSNYGNMSSACVLFILDEMRKASAKEGLGT"
                     + "TGEGLEWGVLFGFGPGLTVETVVLHSVAT"),
                 id="gi|13925890|gb|AAK49457.1|",
                 description="chalcone synthase [Nicotiana tabacum]")
sequences = [rec1, rec2]

# Writing to file
with open("example.fasta", "w") as output_handle:
    SeqIO.write(sequences, output_handle, "fasta")

for record in SeqIO.parse("example.fasta", "fasta"):
    print("ID %s" % record.id)
    print("Sequence length %i" % len(record))
```

**输出:**

![](img/04ad196a5dd990735e72300ceef4b7d1.png)