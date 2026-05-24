# Java 中 BitSet toLongArray()方法示例

> 原文: [https://www.geeksforgeeks.org/bitset-tolongarray-method-in-java-with-examples/](https://www.geeksforgeeks.org/bitset-tolongarray-method-in-java-with-examples/)

`java.util.BitSet.toLongArray()`是`BitSet`类的内置方法，用于生成包含现有`BitSet`所有位的新长数组。根据官方文件，该过程以下列方式工作:

> `long[] longs = bit_set.toLongArray();`
> 然后，`longs.length == (bit_set.length() + 63) / 64`,
> `bit_set.get(n) == ((longs[n / 64] & (1L << (n % 64))) != 0)`