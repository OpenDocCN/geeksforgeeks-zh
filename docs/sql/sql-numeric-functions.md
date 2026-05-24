# SQL |数值函数

> 原文:[https://www.geeksforgeeks.org/sql-numeric-functions/](https://www.geeksforgeeks.org/sql-numeric-functions/)

**数字功能**用于对数字进行运算并返回数字。
以下是 SQL 中定义的数值函数:

1.  **ABS():** It returns the absolute value of a number.

    ```sql
    Syntax: SELECT ABS(-243.5);
    ```

    **输出:** 243.5

    ```sql
    SQL> SELECT ABS(-10);
    +--------------------------------------+
    | ABS(10)                                                  
    +--------------------------------------+
    | 10                                                       
    +--------------------------------------+

    ```

2.  **ACOS():** It returns the cosine of a number.

    ```sql
    Syntax:  SELECT ACOS(0.25);
    ```

    **输出:** 1.318116071652818

3.  **ASIN():** It returns the arc sine of a number.

    ```sql
    Syntax: SELECT ASIN(0.25);
    ```

    **输出:** 0.25268025514207865

4.  **ATAN():** It returns the arc tangent of a number.

    ```sql
    Syntax: SELECT ATAN(2.5);
    ```

    **输出:** 1.1902899496825317

5.  **CEIL():** It returns the smallest integer value that is greater than or equal to a number.

    ```sql
    Syntax: SELECT CEIL(25.75);
    ```

    **输出:** 26

6.  **CEILING():** It returns the smallest integer value that is greater than or equal to a number.

    ```sql
    Syntax: SELECT CEILING(25.75);
    ```

    **输出:** 26

7.  **COS():** It returns the cosine of a number.

    ```sql
    Syntax: SELECT COS(30);
    ```

    **输出:** 0.154251449887584

8.  **COT():** It returns the cotangent of a number.

    ```sql
    Syntax: SELECT COT(6);
    ```

    **输出:** -3.436353004180128

9.  **DEGREES():** It converts a radian value into degrees.

    ```sql
    Syntax: SELECT DEGREES(1.5);
    ```

    **输出:**8560 . 888888888686

    ```sql
    SQL>SELECT DEGREES(PI());
    +------------------------------------------+
    | DEGREES(PI())                                           
    +------------------------------------------+
    | 180.000000                                              
    +------------------------------------------+
    ```

10.  **DIV():** It is used for integer division.

    ```sql
    Syntax: SELECT 10 DIV 5;
    ```

    **输出:** 2

11.  **EXP():** It returns e raised to the power of number.

    ```sql
    Syntax: SELECT EXP(1);
    ```

    **输出:** 2.718281828459045

12.  **FLOOR():** It returns the largest integer value that is less than or equal to a number.

    ```sql
    Syntax: SELECT FLOOR(25.75);
    ```

    **输出:** 25

13.  **GREATEST():** It returns the greatest value in a list of expressions.

    ```sql
    Syntax: SELECT GREATEST(30, 2, 36, 81, 125);
    ```

    **输出:** 125

14.  **LEAST():** It returns the smallest value in a list of expressions.

    ```sql
    Syntax: SELECT LEAST(30, 2, 36, 81, 125);
    ```

    **输出:** 2

15.  **LN():** It returns the natural logarithm of a number.

    ```sql
    Syntax: SELECT LN(2);
    ```

    **输出:** 0.6931471805599453

16.  **LOG10():** It returns the base-10 logarithm of a number.

    ```sql
    Syntax: SELECT LOG(2);
    ```

    **输出:** 0.6931471805599453

17.  **LOG2():** It returns the base-2 logarithm of a number.

    ```sql
    Syntax: SELECT LOG2(6);
    ```

    **输出:** 2.584962500721156

18.  **MOD():** It returns the remainder of n divided by m.

    ```sql
    Syntax: SELECT MOD(18, 4);
    ```

    **输出:** 2

19.  **PI():** It returns the value of PI displayed with 6 decimal places.

    ```sql
    Syntax: SELECT PI();
    ```

    **输出:** 3.141593

20.  **POW():** It returns m raised to the nth power.

    ```sql
    Syntax: SELECT POW(4, 2);
    ```

    **输出:** 16

21.  **RADIANS():** It converts a value in degrees to radians.

    ```sql
    Syntax: SELECT RADIANS(180);
    ```

    **输出:** 3.141592653589793

22.  **RAND():** It returns a random number.

    ```sql
    Syntax: SELECT RAND();
    ```

    **输出:** 0.33623238684258

23.  **ROUND():** It returns a number rounded to a certain number of decimal places.

    ```sql
    Syntax: SELECT ROUND(5.553);
    ```

    **输出:** 6

24.  **SIGN():** It returns a value indicating the sign of a number.

    ```sql
    Syntax: SELECT SIGN(255.5);
    ```

    **输出:** 1

25.  **SIN():** It returns the sine of a number.

    ```sql
    Syntax: SELECT SIN(2);
    ```

    **输出:** 0.9092974268256817

26.  **SQRT():** It returns the square root of a number.

    ```sql
    Syntax: SELECT SQRT(25);
    ```

    **输出:** 5

27.  **TAN():** It returns the tangent of a number.

    ```sql
    Syntax: SELECT TAN(1.75);
    ```

    **输出:** -5.52037992250933

28.  **ATAN2():** It returns the arctangent of the x and y coordinates, as an angle and expressed in radians.

    ```sql
    Syntax: SELECT ATAN2(7);
    ```

    **输出:** 1.42889927219073

29.  **TRUNCATE():** This doesn’t work for SQL Server. It returns 7.53635 truncated to 2 places right of the decimal point.

    ```sql
    Syntax: SELECT TRUNCATE(7.53635, 2);
    ```

    **输出:** 7.53