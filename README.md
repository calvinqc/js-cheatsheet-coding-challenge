# Javascript Cheatsheet for Coding Challenge

# Table of content
- [String](#string)
- [Array](#array)
- [Set](#set)
- [HashMap](#hashmap)
- [Object](#object)
- [Bitwise](#bitwise)
- [Math](#math)
- [Source](#source)


## String

```js
const abc = "abcdefghijklmnopqrstuvwxyz";
abc.indexOf("l");               // find substring, -1 if doesn't contain 
abc.lastIndexOf("l");           // last occurance
abc.replace("abc","123");       // find and replace, takes regular expressions

abc.toUpperCase();              // convert to upper case
abc.toLowerCase();              // convert to lower case

abc.concat(" ", str2);          // abc + " " + str2
abc.charAt(2);                  // character at index: "c"
abc[2];                         // unsafe, abc[2] = "C" doesn't work
abc.charCodeAt(2);              // character code at index: "c" -> 99
abc.split(",");                 // splitting a string on commas gives an array
abc.split("");                  // splitting on characters
128.toString(16);               // number to hex(16), octal (8) or binary (2)
```

## Array
```js
const arr = [1];
arr.concat([4,5,6]);                      // Merge 2 arrays:                      [1,4,5,6]
arr.push(7);                              // Add element to LAST:                 [1,4,5,6,7]
arr.unshift(0);                           // Add element to FIRST:                [0,1,4,5,6,7]

arr.splice(2, 0, 2);                      // Add element BEFORE index 2:          [0,1,2,4,5,6,7]
arr.splice(2 + 1, 0, 3);                  // Add element AFTER index 2:           [0,1,2,3,4,5,6,7]

arr.shift();                              // Remove FIRST Element                 [1,2,3,4,5,6,7]
arr.pop();                                // Remove LAST Element                  [1,2,3,4,5,6]
arr.reverse();                            // Reverse                              [6,5,4,3,2,1]
arr.sort();                               // Sort                                 [1,2,3,4,5,6]  

arr.splice(arr.indexOf(REF), 0, NEW)      // Add element BEFORE a specific index  [_,_,REF,NEW,_,_]
arr.splice(arr.indexOf(REF) + 1, 0, NEW)  // Add element AFTER a specific index   [_,_,REF,NEW,_,_]
arr.splice(2, 1, '_');                    // Replace element at index 2:          [1,_,3,4,5,6]

// get the Sub Set
const arr = [0,1,2,3,4,5]
arr.slice(0);               // [0,1,2,3,4,5]
arr.slice(0,1);             // [0          ]
arr.slice(1);               // [  1,2,3,4,5]
arr.slice(1,2);             // [  1        ] 
arr.slice(2,4);             // [    2,3    ]
arr.slice(4);               // [        4,5]
arr.slice(5);               // [          5]

const newArr = arr.slice(); // clone the array
```

## Set
```js
const set = new Set([2,2,1]);       // Array  -> Set
const arr = [...set];               // Set    -> array

set.add(4).add(3)                   // Add element to LAST  [2,1,4,3]
set.delete(3)                       // Delete element       [2,1,4]

const entriesArr = set.entries();   // Create an iterator for loop [value, value]
entriesArr.next().value;            // [2,2]

set.has(1);                         // Check if set has 1 => TRUE
set.values();                       // return iterator object from the insert order
set.keys();                         // return iterator object from the insert order (same as values())
set.clear()                         // Clear all elements

const set = new Set([2,1,4])
const set2 = new Set([4,2,1,5])

const unionSet      = set.union(set2)          // Union 2 sets:         [2,1,4,5]
const intersectSet  = set.intersection(set2)   // Intersect 2 sets:     [2,1,4]
const diffSet       = set.difference(set2)     // Difference of 2 sets: [5]
```

## HashMap
```js
const map = new Map([[1 , 2], [2 , 3] ,[4, 5]]);

map.set(6,7);         // Add new key-value      => { 1 => 2, 2 => 3, 4 => 5, 6 => 7 }
map.has(3);           // Check if key 3 exist   => FALSE
map.get(1);           // get value of key 1     => 2
map.delete(1);        // delete key-value of 1  => { 2 => 3, 4 => 5, 6 => 7 }
map.size();           // get the size of a map  => 3
[...map.keys()];      // get the list of keys   => [2,4,6]
map.forEach((val, key) => console.log({key, val}));
// {key: 2, val: 3}
// {key: 4, val: 5}
// {key: 6, val: 7}
```

## Object
```js
const obj = {
    "firstName": "Calvin",
    "age": 23,
    "numList": [1,2,3]
};

// access the value
const { firstName, age, numList } = obj;  // Get the key-value: firstName = "Calvin", age = 23, numList = [1,2,3]
obj.newNumList = [...numList, 4];         // Add new key - value: [1,2,3,4]
delete obj.numList                        // Remove the key-value: { "firstName": "Calvin", "age": 23, "newNumList": [1,2,3,4] };
```

## Bitwise
```js
&	    AND 	                  5 & 1 (0101 & 0001)	1 (1)
|	    OR 	                    5 | 1 (0101 | 0001)	5 (101)
~	    NOT 	                  ~ 5 (~0101)	10 (1010)
^	    XOR 	                  5 ^ 1 (0101 ^ 0001)	4 (100)
<<	  left shift 	            5 << 1 (0101 << 1)	10 (1010)
>>	  right shift 	          5 >> 1 (0101 >> 1)	2 (10)
>>>	  zero fill right shift 	5 >>> 1 (0101 >>> 1)	2 (10)
```

## Math
```js
var pi = 3.141;
pi.toFixed(0);            // returns 3
pi.toFixed(2);            // returns 3.14 - for working with money
pi.toPrecision(2)         // returns 3.1
pi.valueOf();             // returns number

Number(true);             // converts to number
Number(new Date())        // number of milliseconds since 1970
parseInt("3 months");     // returns the first number: 3
parseFloat("3.5 days");   // returns 3.5

Number.MAX_VALUE          // largest possible JS number
Number.MIN_VALUE          // smallest possible JS number
Number.NEGATIVE_INFINITY  // -Infinity
Number.POSITIVE_INFINITY  // Infinity
```

## Source
- [Mozilla](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
- [htmlcheatsheet](https://htmlcheatsheet.com/js/)
