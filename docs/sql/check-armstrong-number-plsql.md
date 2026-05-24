# 检查 PL/SQL 中的阿姆斯特朗号

> 原文:[https://www.geeksforgeeks.org/check-armstrong-number-plsql/](https://www.geeksforgeeks.org/check-armstrong-number-plsql/)

给定一个数 x，确定给定的数是否是阿姆斯特朗数。一个 n 位数的正整数被称为 n 阶阿姆斯特朗数(阶是位数)。

```sql
**abcd... = pow(a, n) + pow(b, n) + pow(c, n) + pow(d, n) + ....** 
```

例:

```sql
Input : 153
Output : Yes
153 is an Armstrong number.
1*1*1 + 5*5*5 + 3*3*3 = 153

Input : 120
Output : No
120 is not a Armstrong number.
1*1*1 + 2*2*2 + 0*0*0 = 9

Input : 1253
Output : No
1253 is not a Armstrong Number
1*1*1*1 + 2*2*2*2 + 5*5*5*5 + 3*3*3*3 = 723

Input : 1634
Output : Yes
1*1*1*1 + 6*6*6*6 + 3*3*3*3 + 4*4*4*4 = 1634
```

```sql
declare
-- declare variable n, s,r, len
-- and m of datatype number
    n number:=1634;
    s number:=0;
    r number;
    len number;
    m number;

begin
    m := n;

    len := length(to_char(n));

    -- while loop till n>0
    while n>0
    loop
        r := mod(n , 10);
        s := s + power(r , len);
        n := trunc(n / 10);
    end loop;

    if m = s
    then
        dbms_output.put_line('yes');
    else
        dbms_output.put_line('no');
    end if;

end;

-- End program
```

输出:

```sql
Yes
```