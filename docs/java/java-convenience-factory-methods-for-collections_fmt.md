# Java 便利工厂收集方法

> 原文: [https://www.geeksforgeeks.org/java-convenience-factory-methods-for-collections/](https://www.geeksforgeeks.org/java-convenience-factory-methods-for-collections/)

JDK 9 在基本的收集接口上增加了静态工厂方法，如 `List.of()`，以创建不可修改的收集对象。这些与我们在 JDK 6、7、8 中创建的不可修改(不可变)集合相同。它允许您在一行中创建值的列表、集合和映射。Java 9 没有像它的前身那样给我们的编码方式带来太多戏剧性的变化，但是我们肯定会有一些奇特的特性。

下面提到的方式导致了创造不必要的物体。为了克服这个问题，Java 9 引入了静态工厂方法来创建一个不可变的列表、集合和映射，这将在后面讨论。在此之前，让我们在 JDK 9 (JDK 7，8)之前修改不可修改的集合的创建。

## JDK 8 列表

```java
List<String> listOfString = new ArrayList<>();
listOfString.add("Geeks");
listOfString.add("Java");
listOfString.add("Kotlin");
listOfString.add("Groovy");
listOfString.add("Scala");
listOfString = Collections.unmodifiableList(listOfString);
```

### 方式 1: 使用双括号初始化

```java
List<String> listOfString = Collections.unmodifiableList(new ArrayList<>() {{
    add("Geeks");
    add("Java");
    add("Kotlin");
    add("Groovy");
    add("Scala");
}});
```

### 方式 2: 使用数组 API 将数组转换为数组列表

```java
List<String> listOfString = Collections.unmodifiableList(Arrays.asList("Geeks", "Java", "Kotlin", "Groovy", "Scala"));
```

### 方式 3: 使用流应用编程接口

```java
List<String> listOfString = Collections.unmodifiableList(Stream.of("Bruce", "Steve", "Adrian", "Dave", "Janick", "Nicko").collect(Collectors.toList()));
```

## 为什么是 Java 9？

现在让我们先看看好处，为什么在使用 Java 9 静态工厂方法之前要先使用它们

*   允许在一行中创建值的列表、集合和映射。
*   使用静态工厂方法创建[不可变对象](https://www.geeksforgeeks.org/create-immutable-class-java/)可以防止我们插入空值或重复值(在集合或映射中)。
*   在遍历集合元素时，我们不会得到[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)。

现在让我们讨论在 JDK 创建一个不可修改的收藏。下面讨论列表、集合和映射。

## 1. Java 9 中的列表

```java
List<String> listOfString = List.of("Geeks", "Java", "Kotlin", "Groovy", "Scala");
```

仅仅一行代码就足以创建一个不可修改的列表，因此不需要创建不必要的对象。

*   `List.of()` 允许你创建一个空的不可变列表。
*   任何修改都将导致 `UnsupportedOperationException`。
*   从性能角度来看，`List.of()` 有多个重载版本。

一个不可变的列表有一个抽象基类 `AbstractImmutableList<E>` 和四个实现:

*   `List0`
*   `List1`
*   `List2`
*   `ListN`

这些类型中的每一种都对应于用于创建它们的元素的数量。在 `java.util.List` 接口中，我们有 12 个静态工厂方法，它们使用上面的实现来创建不可变的对象:

```java
// creates empty immutable list
static <E> List<E> of()

// creates one-element immutable list
static <E> List<E> of(E e1)

// creates two-element immutable list
static <E> List<E> of(E e1, E e2)

// creates ten-element immutable list
static <E> List<E> of(E e1, E e2, E e3, E e4, E e5, E e6, E e7, E e8, E e9, E e10)

// creates N-element immutable list
static <E> List<E> of(E... elements)
```

同样，也要偷偷找出抛出 `UnsupportedOperationException` 的方法，具体如下

*   `add(E e)`, `addAll(Collection<? extends E> c)`, `addAll(int index, Collection<? extends E> c)`
*   `remove(Object o)`, `removeAll(Collection<?> c)`, `removeIf(Predicate<? super E> filter)`
*   `replaceAll(UnaryOperator<E> operator)`
*   `retainAll(Collection<?> c)`
*   `sort(Comparator<? super E> c)`
*   `clear()`

插入空值将导致 `NullPointerException`，如下所示

```java
List<String> listOfString = List.of("Geeks","Java","Kotlin", "Scala", "Groovy", null);
// throws NullPointerException
```

因此，不可变列表的有效创建如下:

```java
List<String> listOfString = List.of("Geeks","Java","Kotlin", "Scala", "Groovy","Pearl");
```

## 2. Java 9 中的集合

*   `Set.of()` 允许您创建一个空的不可变集。
*   任何修改都将导致 `UnsupportedOperationException`。
*   从性能的角度来看，`Set.of()` 有几个重载版本。

插图:

不可变集的实现方式类似于我们在 `List` 接口上看到的方式。它有一个抽象基类 `AbstractImmutableSet<E>` 和四个实现:

*   `Set0`
*   `Set1`
*   `Set2`
*   `SetN`

这也对应于在它们的创建中使用的元素的数量。在 [`java.util.Set` 界面](https://www.geeksforgeeks.org/set-in-java/) 中，我们有 12 个静态工厂方法:

```java
// creates empty immutable set
static <E> Set<E> of()

// creates one-element immutable set
static <E> Set<E> of(E e1)

// creates two-element immutable set
static <E> Set<E> of(E e1, E e2)

// creates ten-element immutable set
static <E> Set<E> of(E e1, E e2, E e3, E e4, E e5, E e6, E e7, E e8, E e9, E e10)

// creates N-element immutable set
static <E> Set<E> of(E... elements)
```

引发 `UnsupportedOperationException` 的方法如下:

1.  `add(E e)`, `addAll(Collection<? extends E> c)`
2.  `remove(Object o)`, `removeAll(Collection<?> c)`, `removeIf(Predicate<? super E> filter)`
3.  `retainAll(Collection<?> c)`
4.  `clear()`

插图:

像不可变列表一样，我们不能用空值实例化一个集合，因为它会抛出 `NullPointerException`，其中添加重复将导致如下所示的 `IllegalArgumentException`:

```java
Set<String> setOfString = Set.of("Geeks", "Java", "Kotlin", "Scala", "Groovy", null);
// throws NullPointerException

Set<String> setOfString = Set.of("Geeks", "Java", "Kotlin", "Java");
// throws IllegalArgumentException
```

因此，不可变集合的有效创建如下:

```java
Set<String> setOfString = Set.of("Geeks", "Java", "Kotlin", "Scala", "Groovy", "Pearl");
```

## 3. Java 9 中的地图

*   `Map.of()` 和 `Map.ofEntries()` 允许你创建一个不可变的地图。
*   任何修改都将导致 `UnsupportedOperationException`。
*   `Map.of()` 被重载以创建最多 10 个键值对的映射。
*   `Map.ofEntries()` 将用于创建 10 个以上键值对的映射。

一个不可变的映射有一个抽象的基类，抽象的可替换的映射 `<K,V>`，有三个实现:

*   `Map0`
*   `Map1`
*   `MapN`

在 [`java.util.map` 界面](https://www.geeksforgeeks.org/map-interface-java-examples/) 中，我们又有了下面一组工厂方法。

```java
// creates an empty map
static <K, V> Map<K, V> of()

// creates one-element map
static <K, V> Map<K, V> of(K k1, V v1)

// creates two-element map
static <K, V> Map<K, V> of(K k1, V v1, K k2, V v2)

// creates ten-element map
static <K, V> Map<K, V> of(K k1, V v1, K k2, V v2, K k3, V v3, K k4, V v4,
                           K k5, V v5, K k6, V v6, K k7, V v7, K k8, V v8, 
                           K k9, V v9, K k10, V v10)

// creates N-element map
static <K, V> Map<K, V> ofEntries(Entry<? extends K, ? extends V>... entries)
```

同样，引发 `UnsupportedOperationException` 的方法如下:

*   `clear()`
*   `compute(K key, BiFunction<? super K, ? super V, ? extends V> rf)`
*   `computeIfAbsent(K key, Function<? super K, ? extends V> mf)`
*   `computeIfPresent(K key, BiFunction<? super K, ? super V, ? extends V> rf)`
*   `merge(K key, V value, BiFunction<? super V, ? super V, ? extends V> rf)`
*   `put(K key, V value)`, `putAll(Map<? extends K, ? extends V> m)`, `putIfAbsent(K key, V value)`
*   `remove(Object key)`, `remove(Object key, Object value)`
*   `replace(K key, V value)`, `replace(K key, V oldValue, V newValue)`, `replaceAll(BiFunction<? super K, ? super V, ? extends V> f)`

插图:

插入空键或空值将导致 `NullPointerException`:

```java
Map<String, Integer> weightInKg = Map.of(null, 59, "John", 61);
// throws NullPointerException because of null key
```

```java
Map<String, Integer> weightInKg = Map.of("Ron", null, "John", 61);
// throws NullPointerException because of null value
```

```java
Map<String, Integer> weightInKg = Map.ofEntries(Map.entry("Ron", 59), null);
// throws NullPointerException because of null entry
```

添加重复的键元素将引发 `IllegalArgumentException`:

```java
Map<String, Integer> weightInKg = Map.of("Ron", 59, "Ron", 59);
```

```java
Map<String, Long> weightInKg = Map.ofEntries(Map.entry("Ron", 59), Map.entry("Ron", 59));
```

不可变映射的有效创建如下:

```java
Map<String, Long> weightInKg = Map.of("Ron", 59, "John", 61, "Ed", 60, "Nick", 60, "Jack", 60L, "Ben", 65);
```

```java
Map<String, Long> age = Map.ofEntries(Map.entry("Ron", 59),
                                      Map.entry("John", 61),
                                      Map.entry("Ed", 60),
                                      Map.entry("Nick", 60),
                                      Map.entry("Jack", 60),
                                      Map.entry("Ben", 65));
```