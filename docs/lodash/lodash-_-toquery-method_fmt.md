# Lodash _.toQuery() Method

> Original: [https://www.geeksforgeeks.org/lodash-_-toquery-method/](https://www.geeksforgeeks.org/lodash-_-toquery-method/)

The **Lodash `_.toQuery()` method** takes an object and converts it into an equivalent URL query string.

## Syntax

```
_.toQuery( Object);
```

## Parameters

This method takes a single parameter as described above:

*   `Object`: The method takes an object for conversion.

## Return Value

This method returns the equivalent URL query string.

## Note

This will not work in normal JavaScript as it requires the installation of the `lodash.js contrib` library. You can install the Lodash.js contrib library using `npm install lodash-contrib`.

## Example 1

### JavaScript

```
// Defining lodash contrib variable 
var _ = require('lodash-contrib');

var s  = _.toQuery({ 
    name: 'GeeksforGeeks', 
    address: 'Noida',
    contact: '9876543210'
});

console.log("The generated URL Query String is : ", s);
```

**Output:**

```
The generated URL Query String is : 
name=GeeksforGeeks&address=Noida&contact=9876543210
```

## Example 2

### JavaScript

```
// Defining lodash contrib variable 
var _ = require('lodash-contrib');

var s  = _.toQuery(
    { 'https://practice.geeksforgeeks.org/courses/?ref': 
    'gfg_header' });

console.log("The generated URL Query String is : ", s);
```

**Output:**

```
The generated URL Query String is : 
https%3A%2F%2Fpractice.geeksforgeeks.org%2Fcourses%2F%3Fref=gfg_header
```