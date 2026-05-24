# C |动态内存分配|问题 6

> 原文:[https://www . geesforgeks . org/c-dynamic-memory-allocation-question-6/](https://www.geeksforgeeks.org/c-dynamic-memory-allocation-question-6/)

以下哪一项是正确的？
**(A)**“ptr = calloc(m，n)”相当于跟随
ptr = malloc(m * n)；

**(B)**“ptr = calloc(m，n)”相当于跟随
ptr = malloc(m * n)；
memset(ptr，0，m * n)；

**(C)**“ptr = calloc(m，n)”相当于跟随
ptr = malloc(m)；
memset(ptr，0，m)；

**(D)**“ptr =胼胝体(m，n)”相当于跟随
ptr = malloc(n)；
记忆集(ptr，0，n)；

**回答:****(B)**

**解释:**详见[卡洛克()vs 马洛克()](https://www.geeksforgeeks.org/calloc-versus-malloc/)。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)