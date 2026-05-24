# 在 SQL 中查找相似类型的名称|模糊搜索

> 原文:[https://www . geesforgeks . org/find-相似类型名称-模糊-SQL-search/](https://www.geeksforgeeks.org/finding-similar-type-of-names-fuzzy-search-in-sql/)

**模糊搜索:**
一种寻找近似(而非精确)匹配模式的字符串的技术。用户/审阅者经常不准确地获取姓名。键入错误是审阅者在捕获名称时经常犯的错误，这会导致数据不一致。但有时，我们无论如何都需要搜索或匹配这些不准确的数据。例如，用户应该匹配现有的客户记录，而不是创建不需要的重复记录。

**问题陈述:**
查找下表中描述的所有类型的错误，例如拼写错误、名称不完整、格式问题、后缀缺失。

<figure class="table">T21】本杰明 T32T61】杰夫 T63】沃伊特 T65】拼写错误 T67T69】玛丽 T71】普伦德加斯特 T73】玛丽 T75】普伦德加斯特 T77】拼写错误 T79T81】迈克尔 T83】 瓦莱 T129】J丹尼尔

| name | surname | name | surname | type of error |
| --- | --- | --- | --- | --- |
| Magistrate | Benjamin | Serif | spelling mistake |
| chocolate | Ferchler | jens voigt |
| Incomplete name |
| Yolanda | Balcazar | Yolanda | Balcazar Rodriguez | Incomplete name |
| Garcia Martinez | J | Garcia |
| Connie | mark | Connie | Mark Iv | Suffix missing |
| Daniel | rad | Daniel | Jr Ladd | Missing suffix [T186 |

</figure>

**解决方法:**
SOUNDEX()函数可以发现名称中的不一致。SOUNDEX()可以评估两个名称的相似性。SOUNDEX()只有当我们有 1 或 2 个令牌时才能很好地工作。名称通常包含 1-2 个标记，因此它对名称很有效。但是如果我们想为公司找到相似的名字，那么它就没那么有用了，因为它包含多个标记。

**数据:**
本杰明·警长和本杰明·谢里夫，其中名字相同，但姓氏中的任何一个都有拼写错误。同样，这些数据中有许多错误，如格式问题、名称不完整。

<figure class="table">

| 西方人名的第一个字 | 姓 |
| --- | --- |
| 本杰明 | 州长 |
| 本杰明 | 州长 |
| 弗吉尼亚 | 滑轮阿尔伯特 |
| 弗吉尼亚 | 滑轮-阿尔伯特 |
| 杰弗里 | 向下 |
| 杰弗里（男子名） | 向下 |
| -花序 | 卡斯迪 |
| 安东尼 | 卡斯迪 |
| 罗德里戈 | 德尔加多 |
| 罗德里戈 | 小德尔加多 |
| 【男性名字】利奥纳多 | 情歌 |
| 【男性名字】利奥纳多 | 马德拉戈德尔瓦莱 |
| 迈克尔 | 迈尔斯 |
| 米切尔 | 迈尔斯 |

</figure>

**代码:**
案例-1:名字完全相同，但姓氏是类似的类型。
案例 2:姓氏完全相同，但名字是相似的类型。

下面我们一个一个来讨论。

**病例-1 :**
**名字与** **完全相同，但姓氏相似类型:**

```sql
select distinct ss.firstname,ss.lastname,sd.firstname,sd.lastname
from load as ss, load as sd
where ss.firstName=sd.firstName and SOUNDEX(ss.lastName)=SOUNDEX(sd.lastname)
      and
      left(ss.lastname,2)=left(sd.lastname,2)
      and
      ss.lastName<>sd.lastName
```

**输出:**

<figure class="table">**名****名****名****名****名****名****名****名****名****名****名****名****名****T68】小德尔加多 T70****T72】罗德里戈 T74】小德尔加多 T76】罗德里戈 T78】德尔加多 T88**

| Name | surname | name | surname |
| --- | --- | --- | --- |
| Benjamin | sergeant | Benjamin | Sharif |
| Benjamin | Sharif Leonardo | pastoral |
| Rodrigo | cesar delgado | Rodrigo |

</figure>

****病例-2 :**
**姓氏完全相同，但名字相似类型:****

```sql
select distinct ss.lastname,ss.firstname,sd.lastname,sd.firstname
from load as ss, load as sd
where ss.lastname=sd.lastname and SOUNDEX(ss.firstname)=SOUNDEX(sd.firstname)
      and
      left(ss.firstname,2)=left(sd.firstname,2)
      and
      ss.firstname<>sd.firstname
```

****输出:****

<figure class="table">**s。没有。last name【安东尼】【castoldi】【安东尼】【castoldi】2。 [Anthony]【castoldi】【安东尼】【castoldi】3。【bown】【杰弗里】【bown】4。【杰弗里】【bown】【杰弗里】【bown】5。【米切尔】【迈尔斯】【米切尔】【迈尔斯】6。【迈尔斯】[Mitchell]【迈尔斯】**</figure>

****参考:**
Github Link–[https://Github . com/SuryaSD/find-相似-名称类型-模糊-搜索](https://github.com/SuryaSD/Finding-Similar-Types-of-Names-Fuzzy-Search)**