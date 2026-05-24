# Java 中的 PrintStateReason API

> 原文: [https://www.geeksforgeeks.org/java-program-to-implement-printerstatereasons-api/](https://www.geeksforgeeks.org/java-program-to-implement-printerstatereasons-api/)

`PrintStateReason` API 用于访问打印机设备的当前状态数据，比如打印机是否连接或现在，是否已经用完墨粉等。

## 类 `PrinterStateReasons`

```java
java.lang.Object
java.util.AbstractMap<K,V>
java.util.HashMap<PrinterStateReason,Severity>
javax.print.attribute.standard.PrinterStateReasons
```

### 所有实现的接口:

1.  `Serializable`
2.  `Cloneable`
3.  `Map<PrinterStateReason, Severity>`
4.  `Attribute`
5.  `PrintServiceAttribute`

### 构造函数:

**1. `public PrinterStateReasons()`**
它是默认的构造函数。

**2. `public PrinterStateReasons(int initialCapacity)`**
它是一个参数化的构造函数。
*   **参数:** `initialCapacity` – 初始容量。
*   **异常:** `IllegalArgumentException` – 如果初始容量小于零。

**3. `public PrinterStateReasons(int initialCapacity, float loadFactor)`**
*   **参数:**
    *   `initialCapacity` – 初始容量。
    *   `loadFactor` – 负载系数。
*   **异常:** `IllegalArgumentException` – 如果初始容量小于零。

所有这些构造函数都构造了一个新的空打印状态原因属性和具有默认初始容量和加载因子的底层哈希映射。

**4. `public PrinterStateReasons(Map<PrinterStateReason, Severity> map)`**
*   **参数:** `map` – 要复制的地图。
*   **例外:**
    *   `NullPointerException` – (未检查的异常)如果映射为空或者映射中的任何键或值为空，则抛出。
    *   `ClassCastException` – (未选中的异常)如果映射中的任何键不是类 `PrinterStateReason` 的实例，或者如果映射中的任何值不是类 `Severity` 的实例，则抛出。

它构造了一个新的打印机状态原因属性，该属性包含与给定映射相同的打印机状态原因到严重性的映射。底层哈希映射的初始容量和加载因子在超类构造函数 `HashMap(map)` 中指定。

下面是问题陈述的实现:

## Java 实现代码

```java
// Java Program to Implement PrinterStateReasons API

import java.util.Collection;
import java.util.Iterator;
import java.util.Map;
import java.util.Map.Entry;
import java.util.Set;
import javax.print.attribute.Attribute;
import javax.print.attribute.standard.PrinterStateReason;
import javax.print.attribute.standard.PrinterStateReasons;
import javax.print.attribute.standard.Severity;

public class PrinterStateReasonsImpl {
    private PrinterStateReasons printerStateReasons;

    // Construct a new, empty printer state reasons
    // attribute; the underlying hash map has the default
    // initial capacity and load factor.
    public PrinterStateReasonsImpl()
    {
        printerStateReasons = new PrinterStateReasons();
    }

    // super a new, empty printer state reasons attribute;
    // the underlying hash map has the given initial
    // capacity and the default load factor.
    public PrinterStateReasonsImpl(int initialCapacity)
    {
        printerStateReasons
            = new PrinterStateReasons(initialCapacity);
    }

    // Construct a new, empty printer state reasons
    // attribute; the underlying hash map has the given
    // initial capacity and load factor.
    public PrinterStateReasonsImpl(int initialCapacity,
                                   float loadFactor)
    {
        printerStateReasons = new PrinterStateReasons(
            initialCapacity, loadFactor);
    }

    // Construct a new printer state reasons attribute that
    // contains the same PrinterStateReason-to-Severity
    // mappings as the given map.
    public PrinterStateReasonsImpl(
        Map<PrinterStateReason, Severity> map)
    {
        printerStateReasons = new PrinterStateReasons(map);
    }

    // Removes all of the mappings from this map.
    public void clear() { printerStateReasons.clear(); }

    // Returns a shallow copy of this HashMap instance: the
    // keys and values themselves are not cloned.
    public Object clone()
    {
        return printerStateReasons.clone();
    }

    // Returns true if this map contains
    // a mapping for the specified key.
    public boolean containsKey(Object key)
    {
        return printerStateReasons.containsKey(key);
    }

    // Returns true if this map maps one
    // or more keys to the specified value.
    public boolean containsValue(Object value)
    {
        return printerStateReasons.containsValue(value);
    }

    // Returns a Set view of the mappings
    // contained in this map.
    public Set<Entry<PrinterStateReason, Severity> >
    entrySet()
    {
        return printerStateReasons.entrySet();
    }

    // Returns the value to which the specified
    // key is mapped, or null if this map contains
    // no mapping for the key.
    public Severity get(Object key)
    {
        return printerStateReasons.get(key);
    }

    // Returns true if this map contains
    // no key-value mappings.
    public boolean isEmpty()
    {
        return printerStateReasons.isEmpty();
    }

    // Returns a Set view of the
    // keys contained in this map.
    public Set<PrinterStateReason> keySet()
    {
        return printerStateReasons.keySet();
    }

    // Associates the specified value with
    // the specified key in this map.
    public Severity put(PrinterStateReason reason,
                        Severity severity)
    {
        return printerStateReasons.put(reason, severity);
    }

    // Copies all of the mappings from the
    // specified map to this map.
    public void putAll(Map<? extends PrinterStateReason, ?
                             extends Severity> m)
    {
        printerStateReasons.putAll(m);
    }

    // Removes the mapping for the specified
    // key from this map if present.
    public Severity remove(Object key)
    {
        return printerStateReasons.remove(key);
    }

    // Returns the number of key-value
    // mappings in this map.
    public int size() { return printerStateReasons.size(); }

    // Returns a Collection view of the
    // values contained in this map.
    public Collection<Severity> values()
    {
        return printerStateReasons.values();
    }

    // Get the printing attribute class which is to be used
    // as the "category" for this printing attribute value.
    public Class<? extends Attribute> getCategory()
    {
        return printerStateReasons.getCategory();
    }

    // Get the name of the category of which
    // this attribute value is an instance.
    public String getName()
    {
        return printerStateReasons.getName();
    }

    // Obtain an unmodifiable set view of the individual
    // printer state reason attributes at the given severity
    // level in this PrinterStateReasons attribute.
    public Set<PrinterStateReason>
    printerStateReasonSet(Severity severity)
    {
        return printerStateReasons.printerStateReasonSet(
            severity);
    }

    public static void main(String[] arg)
    {
        PrinterStateReasonsImpl printerStateReasons
            = new PrinterStateReasonsImpl();
        printerStateReasons.put(
            PrinterStateReason.CONNECTING_TO_DEVICE,
            Severity.ERROR);
        printerStateReasons.put(
            PrinterStateReason.COVER_OPEN, Severity.REPORT);
        printerStateReasons.put(
            PrinterStateReason.INPUT_TRAY_MISSING,
            Severity.WARNING);

        System.out.println(
            "the key set of the printerStateReasons is ");
        Set<PrinterStateReason> keySet
            = printerStateReasons.keySet();
        Iterator<PrinterStateReason> itr
            = keySet.iterator();
        while (itr.hasNext()) {
            System.out.print(itr.next() + "\t");
        }
        System.out.println();
    }
}
```

## 代码示例

```java
System.out.println(
            "the values of the printerStateReasons is ");
        Collection<Severity> collectionValues
            = printerStateReasons.values();
        Iterator<Severity> citr
            = collectionValues.iterator();
        while (citr.hasNext()) {
            System.out.print(citr.next() + "\t");
        }
        System.out.println();
        System.out.println(
            "the entry set of the printerStateReasons is ");
        Iterator<Entry<PrinterStateReason, Severity> > eitr;
        Set<Entry<PrinterStateReason, Severity> > entrySet
            = printerStateReasons.entrySet();
        eitr = entrySet.iterator();
        while (eitr.hasNext()) {
            System.out.println(eitr.next() + "\t");
        }
        System.out.println(
            "the printerStateReasons contains Key CONNECTING_TO_DEVICE :"
            + printerStateReasons.containsKey(
                PrinterStateReason.CONNECTING_TO_DEVICE));
        System.out.println(
            "the printerStateReasons contains Value ERROR :"
            + printerStateReasons.containsValue(
                Severity.ERROR));
        System.out.println(
            "the size of the printerStateReasons is "
            + printerStateReasons.size());
        printerStateReasons.clear();
        if (printerStateReasons.isEmpty())
            System.out.println(
                "the printerStateReasons is empty");
        else
            System.out.println(
                "the printerStateReasons is not empty");
    }
}
```

### 输出

```text
the key set of the printerStateReasons is 
input-tray-missing    connecting-to-device    cover-open    
the values of the printerStateReasons is 
warning    error    report    
the entry set of the printerStateReasons is 
input-tray-missing=warning    
connecting-to-device=error    
cover-open=report    
the printerStateReasons contains Key CONNECTING_TO_DEVICE :true
the printerStateReasons contains Value ERROR :true
the size of the printerStateReasons is 3
the printerStateReasons is empty
```