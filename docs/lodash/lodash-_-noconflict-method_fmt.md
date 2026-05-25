# 洛达什 `_.noConflict()`方法

> 原文:[https://www.geeksforgeeks.org/lodash-_-noconflict-method/](https://www.geeksforgeeks.org/lodash-_-noconflict-method/)

`Lodash` 是一个工作在`下划线. js`之上的 JavaScript 库，`Lodash`有助于处理数组、字符串、对象、数字等。

`_.noConflict()`方法用于将变量恢复到其以前的值，并返回对 `lodash` 函数的引用。

**语法:**

```
_.noConflict()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回`lodash`函数。

**示例:**

## java 描述语言

```
// Requiring lodash library
const _ = require('lodash');

// Calling _.noConflict() method
var lod = _.noConflict();

// Displays output
console.log(lod);
```

**输出:**

# Lodash 库函数概览

以下是 Lodash 库（版本 `4.17.15`）导出的主要函数和属性列表。

## 核心配置与方法

### `templateSettings`
包含模板函数的正则配置。
```javascript
{
  escape: /<%-([\s\S]+?)%>/g,
  evaluate: /<%([\s\S]+?)%>/g,
  interpolate: /<%=([\s\S]+?)%>/g,
  variable: '',
  imports: { _: [Circular] }
}
```

### 常用工具函数
- `after()`
- `ary()`
- `assign()`
- `assignIn()`
- `assignInWith()`
- `assignWith()`
- `at()`
- `before()`
- `bind()`
- `bindAll()`
- `bindKey()`
- `castArray()`
- `chain()`
- `chunk()`
- `compact()`
- `concat()`
- `cond()`
- `conforms()`
- `constant()`
- `countBy()`
- `create()`
- `curry()`
- `curryRight()`
- `debounce()`
- `defaults()`
- `defaultsDeep()`
- `defer()`
- `delay()`
- `difference()`
- `differenceBy()`
- `differenceWith()`
- `drop()`
- `dropRight()`
- `dropRightWhile()`
- `dropWhile()`
- `fill()`
- `filter()`
- `flatMap()`
- `flatMapDeep()`
- `flatMapDepth()`
- `flatten()`
- `flattenDeep()`
- `flattenDepth()`
- `flip()`
- `flow()`
- `flowRight()`
- `fromPairs()`
- `functions()`
- `functionsIn()`
- `groupBy()`
- `initial()`
- `intersection()`
- `intersectionBy()`
- `intersectionWith()`
- `invert()`
- `invertBy()`
- `invokeMap()`
- `iteratee()`
- `keyBy()`
- `keys()`
- `keysIn()`
- `map()`
- `mapKeys()`
- `mapValues()`
- `matches()`
- `matchesProperty()`
- `memoize()`
- `merge()`
- `mergeWith()`
- `method()`
- `methodOf()`
- `mixin()`
- `negate()`
- `nthArg()`
- `omit()`
- `omitBy()`
- `once()`
- `orderBy()`
- `over()`
- `overArgs()`
- `overEvery()`
- `overSome()`
- `partial()`
- `partialRight()`
- `partition()`
- `pick()`
- `pickBy()`
- `property()`
- `propertyOf()`
- `pull()`
- `pullAll()`
- `pullAllBy()`
- `pullAllWith()`
- `pullAt()`
- `range()`
- `rangeRight()`
- `rearg()`
- `reject()`
- `remove()`
- `rest()`
- `reverse()`
- `sampleSize()`
- `set()`
- `setWith()`
- `shuffle()`
- `slice()`
- `sortBy()`
- `sortedUniq()`
- `sortedUniqBy()`
- `split()`
- `spread()`
- `tail()`
- `take()`
- `takeRight()`
- `takeRightWhile()`
- `takeWhile()`
- `tap()`
- `throttle()`
- `thru()`
- `toArray()`
- `toPairs()`
- `toPairsIn()`
- `toPath()`
- `toPlainObject()`
- `transform()`
- `unary()`
- `union()`
- `unionBy()`
- `unionWith()`
- `uniq()`
- `uniqBy()`
- `uniqWith()`
- `unset()`
- `unzip()`
- `unzipWith()`
- `update()`
- `updateWith()`
- `values()`
- `valuesIn()`
- `without()`
- `words()`
- `wrap()`
- `xor()`
- `xorBy()`
- `xorWith()`
- `zip()`
- `zipObject()`
- `zipObjectDeep()`
- `zipWith()`
- `entries()`
- `entriesIn()`
- `extend()`
- `extendWith()`

## 实用函数

### 数学运算
- `add()`
- `ceil()`
- `clamp()`
- `divide()`
- `floor()`
- `max()`
- `maxBy()`
- `mean()`
- `meanBy()`
- `min()`
- `minBy()`
- `multiply()`
- `nth()`
- `round()`
- `subtract()`
- `sum()`
- `sumBy()`

### 类型检查与转换
- `castArray()`
- `clone()`
- `cloneDeep()`
- `cloneDeepWith()`
- `cloneWith()`
- `conformsTo()`
- `eq()`
- `isArguments()`
- `isArray()`
- `isArrayBuffer()`
- `isArrayLike()`
- `isArrayLikeObject()`
- `isBoolean()`
- `isBuffer()`
- `isDate()`
- `isElement()`
- `isEmpty()`
- `isEqual()`
- `isEqualWith()`
- `isError()`
- `isFinite()`
- `isFunction()`
- `isInteger()`
- `isLength()`
- `isMap()`
- `isMatch()`
- `isMatchWith()`
- `isNaN()`
- `isNative()`
- `isNil()`
- `isNull()`
- `isNumber()`
- `isObject()`
- `isObjectLike()`
- `isPlainObject()`
- `isRegExp()`
- `isSafeInteger()`
- `isSet()`
- `isString()`
- `isSymbol()`
- `isTypedArray()`
- `isUndefined()`
- `isWeakMap()`
- `isWeakSet()`
- `toFinite()`
- `toInteger()`
- `toLength()`
- `toNumber()`
- `toSafeInteger()`
- `toString()`

### 字符串处理
- `camelCase()`
- `capitalize()`
- `deburr()`
- `endsWith()`
- `escape()`
- `escapeRegExp()`
- `kebabCase()`
- `lowerCase()`
- `lowerFirst()`
- `pad()`
- `padEnd()`
- `padStart()`
- `parseInt()`
- `repeat()`
- `replace()`
- `snakeCase()`
- `startsWith()`
- `template()`
- `toLower()`
- `toUpper()`
- `trim()`
- `trimEnd()`
- `trimStart()`
- `truncate()`
- `unescape()`
- `upperCase()`
- `upperFirst()`
- `words()`

### 集合操作
- `countBy()`
- `each()`
- `eachRight()`
- `every()`
- `filter()`
- `find()`
- `findIndex()`
- `findKey()`
- `findLast()`
- `findLastIndex()`
- `findLastKey()`
- `forEach()`
- `forEachRight()`
- `forIn()`
- `forInRight()`
- `forOwn()`
- `forOwnRight()`
- `groupBy()`
- `includes()`
- `invoke()`
- `invokeMap()`
- `keyBy()`
- `map()`
- `orderBy()`
- `partition()`
- `reduce()`
- `reduceRight()`
- `reject()`
- `sample()`
- `sampleSize()`
- `shuffle()`
- `size()`
- `some()`
- `sortBy()`
- `every()`
- `filter()`
- `find()`
- `findLast()`
- `flatMap()`
- `flatMapDeep()`
- `flatMapDepth()`
- `forEach()`
- `forEachRight()`
- `groupBy()`
- `includes()`
- `invokeMap()`
- `keyBy()`
- `map()`
- `orderBy()`
- `partition()`
- `reduce()`
- `reduceRight()`
- `reject()`
- `sample()`
- `sampleSize()`
- `shuffle()`
- `size()`
- `some()`
- `sortBy()`

### 对象操作
- `assign()`
- `assignIn()`
- `assignInWith()`
- `assignWith()`
- `at()`
- `create()`
- `defaults()`
- `defaultsDeep()`
- `entries()`
- `entriesIn()`
- `extend()`
- `extendWith()`
- `findKey()`
- `findLastKey()`
- `forIn()`
- `forInRight()`
- `forOwn()`
- `forOwnRight()`
- `get()`
- `has()`
- `hasIn()`
- `invert()`
- `invertBy()`
- `keys()`
- `keysIn()`
- `mapKeys()`
- `mapValues()`
- `merge()`
- `mergeWith()`
- `omit()`
- `omitBy()`
- `pick()`
- `pickBy()`
- `result()`
- `set()`
- `setWith()`
- `toPairs()`
- `toPairsIn()`
- `toPlainObject()`
- `transform()`
- `unset()`
- `update()`
- `updateWith()`
- `values()`
- `valuesIn()`

### 函数增强
- `after()`
- `ary()`
- `before()`
- `bind()`
- `bindAll()`
- `bindKey()`
- `curry()`
- `curryRight()`
- `debounce()`
- `defer()`
- `delay()`
- `flip()`
- `flow()`
- `flowRight()`
- `memoize()`
- `negate()`
- `once()`
- `overArgs()`
- `partial()`
- `partialRight()`
- `rearg()`
- `rest()`
- `spread()`
- `throttle()`
- `thru()`
- `unary()`
- `wrap()`

### 其他实用工具
- `attempt()`
- `defaultTo()`
- `identity()`
- `iteratee()`
- `matches()`
- `matchesProperty()`
- `method()`
- `methodOf()`
- `mixin()`
- `noConflict()`
- `noop()`
- `now()`
- `property()`
- `propertyOf()`
- `range()`
- `rangeRight()`
- `runInContext()`
- `stubArray()`
- `stubFalse()`
- `stubObject()`
- `stubString()`
- `stubTrue()`
- `times()`
- `uniqueId()`

## 版本信息
- `VERSION`: `'4.17.15'`
- `_`: `[Circular]` (指向 Lodash 自身的引用)

```
```