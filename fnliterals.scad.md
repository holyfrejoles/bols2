# LibFile: fnliterals.scad

Handlers for function literals, and Function literal generators.

To use, add the following lines to the beginning of your file:

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>

## Table of Contents

1. [Section: Function Literal Algorithms](#section-function-literal-algorithms)
    - [`map()`](#function-map)
    - [`filter()`](#function-filter)
    - [`reduce()`](#function-reduce)
    - [`accumulate()`](#function-accumulate)
    - [`while()`](#function-while)
    - [`for_n()`](#function-for_n)
    - [`find_all()`](#function-find_all)
    - [`find_first()`](#function-find_first)
    - [`binsearch()`](#function-binsearch)
    - [`simple_hash()`](#function-simple_hash)
    - [`hashmap()`](#function-hashmap)

2. [Section: Function Meta-Generators](#section-function-meta-generators)
    - [`f_1arg()`](#function-f_1arg)
    - [`f_2arg()`](#function-f_2arg)
    - [`f_2arg_simple()`](#function-f_2arg_simple)
    - [`f_3arg()`](#function-f_3arg)
    - [`ival()`](#function-ival)
    - [`xval()`](#function-xval)

3. [Section: Comparator Generators](#section-comparator-generators)
    - [`f_cmp()`](#function-f_cmp)
    - [`f_gt()`](#function-f_gt)
    - [`f_lt()`](#function-f_lt)
    - [`f_gte()`](#function-f_gte)
    - [`f_lte()`](#function-f_lte)
    - [`f_eq()`](#function-f_eq)
    - [`f_neq()`](#function-f_neq)
    - [`f_approx()`](#function-f_approx)
    - [`f_napprox()`](#function-f_napprox)

4. [Section: Logic Operators](#section-logic-operators)
    - [`f_or()`](#function-f_or)
    - [`f_and()`](#function-f_and)
    - [`f_nor()`](#function-f_nor)
    - [`f_nand()`](#function-f_nand)
    - [`f_xor()`](#function-f_xor)
    - [`f_not()`](#function-f_not)
    - [`f_even()`](#function-f_even)
    - [`f_odd()`](#function-f_odd)

5. [Section: Math Operators](#section-math-operators)
    - [`f_add()`](#function-f_add)
    - [`f_sub()`](#function-f_sub)
    - [`f_mul()`](#function-f_mul)
    - [`f_div()`](#function-f_div)
    - [`f_mod()`](#function-f_mod)
    - [`f_pow()`](#function-f_pow)
    - [`f_neg()`](#function-f_neg)

6. [Section: Min/Max Operators](#section-minmax-operators)
    - [`f_min()`](#function-f_min)
    - [`f_max()`](#function-f_max)
    - [`f_min2()`](#function-f_min2)
    - [`f_max2()`](#function-f_max2)
    - [`f_min3()`](#function-f_min3)
    - [`f_max3()`](#function-f_max3)

7. [Section: Trigonometry Operators](#section-trigonometry-operators)
    - [`f_sin()`](#function-f_sin)
    - [`f_cos()`](#function-f_cos)
    - [`f_tan()`](#function-f_tan)
    - [`f_asin()`](#function-f_asin)
    - [`f_acos()`](#function-f_acos)
    - [`f_atan()`](#function-f_atan)
    - [`f_atan2()`](#function-f_atan2)

8. [Section: String Operators](#section-string-operators)
    - [`f_len()`](#function-f_len)
    - [`f_chr()`](#function-f_chr)
    - [`f_ord()`](#function-f_ord)
    - [`f_str()`](#function-f_str)
    - [`f_str2()`](#function-f_str2)
    - [`f_str3()`](#function-f_str3)

9. [Section: Miscellaneous Operators](#section-miscellaneous-operators)
    - [`f_floor()`](#function-f_floor)
    - [`f_round()`](#function-f_round)
    - [`f_ceil()`](#function-f_ceil)
    - [`f_abs()`](#function-f_abs)
    - [`f_sign()`](#function-f_sign)
    - [`f_ln()`](#function-f_ln)
    - [`f_log()`](#function-f_log)
    - [`f_exp()`](#function-f_exp)
    - [`f_sqr()`](#function-f_sqr)
    - [`f_sqrt()`](#function-f_sqrt)
    - [`f_norm()`](#function-f_norm)
    - [`f_cross()`](#function-f_cross)

10. [Section: Type Queries](#section-type-queries)
    - [`f_is_def()`](#function-f_is_def)
    - [`f_is_undef()`](#function-f_is_undef)
    - [`f_is_bool()`](#function-f_is_bool)
    - [`f_is_num()`](#function-f_is_num)
    - [`f_is_int()`](#function-f_is_int)
    - [`f_is_nan()`](#function-f_is_nan)
    - [`f_is_finite()`](#function-f_is_finite)
    - [`f_is_string()`](#function-f_is_string)
    - [`f_is_list()`](#function-f_is_list)
    - [`f_is_range()`](#function-f_is_range)
    - [`f_is_function()`](#function-f_is_function)
    - [`f_is_vector()`](#function-f_is_vector)
    - [`f_is_path()`](#function-f_is_path)
    - [`f_is_region()`](#function-f_is_region)
    - [`f_is_vnf()`](#function-f_is_vnf)
    - [`f_is_patch()`](#function-f_is_patch)


## Section: Function Literal Algorithms


### Function: map()

**Topics:** [Function Literals](Topics#function-literals), [Looping](Topics#looping)

**Usage:** 

- lst = map(func, list);
- lst = map(function (x) x+1, list);

**Description:** 

Applies the function `func` to all items in `list`, returning the list of results.
In pseudo-code, this is effectively:
```
function map(func,list):
    out = [];
    foreach item in list:
        append func(item) to out;
    return out;
```

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`func`               | The function of signature (x) to evaluate for each item in `list`.
`list`               | The input list.

**See Also:** [filter()](#function-filter), [reduce()](#function-reduce), [accumulate()](#function-accumulate), [while()](#function-while), [for\_n()](#function-for_n)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    func = function(x) x*x;
    echo(map(func, [1,2,3,4]));
    // ECHO: [1,4,9,16]

<br clear="all" /><br/>

**Example 2:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    path = star(n=5,step=2,d=100);
    seglens = map(function (p) norm(p[1]-p[0]), pair(path,wrap=true));

<br clear="all" /><br/>

---

### Function: filter()

**Topics:** [Function Literals](Topics#function-literals), [Looping](Topics#looping), [Filters](Topics#filters)

**Usage:** 

- lst = filter(func, list);
- lst = filter(function (x) x&gt;1, list);

**Description:** 

Returns all items in `list` that the function `func` returns true for.
In pseudo-code, this is effectively:
```
function filter(func,list):
    out = [];
    foreach item in list:
        if func(item) is true:
            append item to out;
    return out;
```

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`func`               | The function of signature `function (x)` to evaluate for each item in `list`.
`list`               | The input list.

**See Also:** [map()](#function-map), [reduce()](#function-reduce), [accumulate()](#function-accumulate), [while()](#function-while), [for\_n()](#function-for_n)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    func = function(x) x>5;
    echo(filter(func, [3,4,5,6,7]));
    // ECHO: [6,7]

<br clear="all" /><br/>

---

### Function: reduce()

**Topics:** [Function Literals](Topics#function-literals), [Looping](Topics#looping)

**Usage:** 

- res = reduce(func, list, [init]);
- res = reduce(function (a,b) a+b, list, &lt;init=);

**Description:** 

First the accumulator is set to the value in `init`.  Then, for each item in `list`, the function
in `func` is called with the accumulator and that list item, and the result is stored in the
acumulator for the next iteration.  Once all list items have been processed, the value in the
accumulator is returned.  Ie: `reduce(function (a,b) a+b, list)` is the equivalent of `sum(list)`.
In pseduo-code, this is effectively:
```
function reduce(func, list, init=0):
    x = init;
    foreach item in list:
        x = func(x, item);
    return x;
```

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`func`               | The function of signature `function (x)` to evaluate for each item in `list`.
`list`               | The input list.
`init`               | The starting value for the accumulator.  Default: 0

**See Also:** [map()](#function-map), [filter()](#function-filter), [accumulate()](#function-accumulate), [while()](#function-while), [for\_n()](#function-for_n)

**Example 1:** Re-Implement sum()

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    x = reduce(f_add(),[3,4,5]);  // Returns: 12

<br clear="all" /><br/>

**Example 2:** Re-Implement product()

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    x = reduce(f_mul(),[3,4,5]);  // Returns: 60

<br clear="all" /><br/>

**Example 3:** Re-Implement all()

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    x = reduce(f_and(),[true,true,true]);   // Returns: true
    y = reduce(f_and(),[true,false,true]);  // Returns: false

<br clear="all" /><br/>

**Example 4:** Re-Implement any()

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    x = reduce(f_or(),[false,false,false]); // Returns: false
    y = reduce(f_or(),[true,false,true]);   // Returns: true

<br clear="all" /><br/>

---

### Function: accumulate()

**Topics:** [Function Literals](Topics#function-literals), [Looping](Topics#looping)

**Usage:** 

- res = accumulate(func, list, [init]);
- res = accumulate(function (a,b) a+b, list, [init=]);

**Description:** 

First the accumulator is set to the value in `init`.  Then, for each item in `list`, the function
in `func` is called with the accumulator and that list item, and the result is stored in the
acumulator for the next iteration.  That value is also appended to the output list.  Once all
list items have been processed, the list of accumulator values is returned.
In pseduo-code, this is effectively:
```
function accumulate(func, list, init=0):
    out = []
    x = init;
    foreach item in list:
        x = func(x, item);
        append x to out;
    return out;
```

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`func`               | The function of signature `function (a,b)` to evaluate for each item in `list`.  Default: `f_add()`
`list`               | The input list.
`init`               | The starting value for the accumulator.  Default: 0

**See Also:** [map()](#function-map), [filter()](#function-filter), [reduce()](#function-reduce), [while()](#function-while), [for\_n()](#function-for_n)

**Example 1:** Reimplement cumsum()

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    echo(accumulate(function (a,b) a+b, [3,4,5],0));  // ECHO: [3,7,12]

<br clear="all" /><br/>

**Example 2:** Reimplement cumprod()

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    echo(accumulate(f_mul(),[3,4,5],1)); // ECHO: [3,12,60,360]

<br clear="all" /><br/>

---

### Function: while()

**Topics:** [Function Literals](Topics#function-literals), [Looping](Topics#looping), [Iteration](Topics#iteration)

**Usage:** 

- x = while(init, cond, func);

**Description:** 

Repeatedly calls the function literals in `cond` and `func` until the `cond` call returns false.
Both `cond` and `func` have the signature `function (i,x)`. The variable `i` is passed the iteration
number, starting with 0.  On the first iteration, the variable `x` is given by `init`.  On subsequent
iterations, `x` is given by the results of the previous call to `func`.  Returns the resulting `x` of
the final iteration.  In pseudo-code, this is effectively:
```
function while(init, cond, func):
    x = init;
    i = 0;
    while cond(i, x):
        x = func(i, x);
        i = i + 1;
    return x;
```

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`init`               | The initial value for `x`.
`cond`               | A function literal with signature `function (i,x)`, called to determine if the loop should continue.  Returns true if the loop should continue.
`func`               | A function literal with signature `function (i,x)`, called on each iteration.  The returned value is passed as `x` on the next iteration.

**See Also:** [map()](#function-map), [filter()](#function-filter), [reduce()](#function-reduce), [accumulate()](#function-accumulate), [for\_n()](#function-for_n)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    fibs = while(
        init = [1,1],
        cond = function (i,x) select(x,-1)<25,
        func = function (i,x) concat(x, [sum(select(x,-2,-1))])
    );  // Returns: [1,1,2,3,5,8,13,21]

<br clear="all" /><br/>

---

### Function: for\_n()

**Topics:** [Function Literals](Topics#function-literals), [Looping](Topics#looping), [Iteration](Topics#iteration)

**Usage:** 

- x = for\_n(n, init, func);

**Description:** 

Given the function literal `func`, with the signature `function (i,x)`, repeatedly calls it `n` times.
If `n` is given as a scalar, the `i` value will traverse the range `[0:1:n-1]`, one value per call.
If `n` is given as a range, the `i` value will traverse the given range, one value per call.
The `x` value for the first  iteration is given in `init`, and in all subsequent iterations `x` will be the result of the previous call.
In pseudo-code, this is effectively:
```
function for_n(n, init, func):
    x = init;
    if is_range(n):
        iterate i over range n:
            x = func(i,x);
    else:
        iterate i from 0 to n-1 by 1:
            x = func(i,x);
    return x;
```

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`n`                  | The number of iterations to perform, or, if given as a range, the range to traverse.
`init`               | The initial value to pass as `x` to the function in `func`.
`func`               | The function literal to call, with signature `function (i,x)`.

**See Also:** [map()](#function-map), [filter()](#function-filter), [reduce()](#function-reduce), [accumulate()](#function-accumulate), [while()](#function-while)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    fib = function(n) for_n(
        n, [],
        function(i,x) x? [x[1], x[0]+x[1]] : [0,1]
    )[1];

<br clear="all" /><br/>

---

### Function: find\_all()

**Topics:** [Function Literals](Topics#function-literals), [Looping](Topics#looping), [Filters](Topics#filters)

**Usage:** 

- indices = find\_all(func, list);
- indices = find\_all(function (x) x&gt;1, list);

**Description:** 

Returns the indices of all items in `list` that the function `func` returns true for.
In pseudo-code, this is effectively:
```
function find_all(func,list):
    out = [];
    foreach item in list:
        if func(item) is true:
            append item index to out;
    return out;
```

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`func`               | The function of signature `function (x)` to evaluate for each item in `list`.
`list`               | The input list.

**See Also:** [map()](#function-map), [reduce()](#function-reduce), [accumulate()](#function-accumulate), [while()](#function-while), [for\_n()](#function-for_n)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    func = function(x) x>5;
    echo(find_all(func, [3,4,5,6,7]));
    // ECHO: [3,4]

<br clear="all" /><br/>

---

### Function: find\_first()

**Topics:** [Function Literals](Topics#function-literals), [Searching](Topics#searching)

**Usage:** 

- idx = find\_first(func, list, [start=]);

**Description:** 

Finds the first item in `list`, after index `start`,  which the function literal in `func` will return true for.
The signature of the function literal in `func` is `function (x)`, and it is expected to return true when the
value compares as matching.  It should return false otherwise.  If you need to find *all* matching items in the
list, you should use [`find_all()`](#function-find_all) instead.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`func`               | The function literal to use to check each item in `list`.  Expects the signature `function (x)`, and a boolean return value.
`list`               | The list to search.

<abbr title="These args must be used by name, ie: name=value">By&nbsp;Name</abbr> | What it does
-------------------- | ------------
`start`              | The first item to check.

**See Also:** [find\_all()](#function-find_all), [map()](#function-map), [filter()](#function-filter), [reduce()](#function-reduce), [accumulate()](#function-accumulate), [while()](#function-while), [for\_n()](#function-for_n), [binsearch()](#function-binsearch)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    data = [8,5,3,7,4,2,9];
    echo(find_first(f_lte(4), data));
    // ECHO: 2

<br clear="all" /><br/>

**Example 2:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    data = [8,5,3,7,4,2,9];
    echo(find_first(f_lte(4), data, start=3));
    // ECHO: 4

<br clear="all" /><br/>

---

### Function: binsearch()

**Topics:** [Function Literals](Topics#function-literals), [Data Structures](Topics#data-structures), [Searching](Topics#searching)

**Usage:** 

- idx = binsearch(key,list, [cmp]);

**Description:** 

Searches a sorted list for an entry with the given key, using a binary search strategy.
Returns the index of the matching item found.  If none found, returns undef.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`key`                | The key to look for.
`list`               | The list of items to search through.
`idx`                | If given, the index of the item sublists to use as the item key.
`cmp`                | The comparator function literal to use.  Default: `f_cmp()`

**See Also:** [map()](#function-map), [filter()](#function-filter), [reduce()](#function-reduce), [accumulate()](#function-accumulate), [hashmap()](#function-hashmap)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    items = unique(rands(0,100,10000));
    idx = binsearch(44, items);

<br clear="all" /><br/>

**Example 2:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    items = unique(rands(0,100,10000));
    idx = binsearch(44, items, cmp=function(a,b) a-b);

<br clear="all" /><br/>

**Example 3:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    items = [for (i=[32:126]) [chr(i), i]];
    idx = binsearch("G", items, idx=0);

<br clear="all" /><br/>

---

### Function: simple\_hash()

**Topics:** [Function Literals](Topics#function-literals), [Hashing](Topics#hashing), [Data Structures](Topics#data-structures)

**Usage:** 

- hx = simple\_hash(x);

**Description:** 

Given an arbitrary value, returns the integer hash value for it.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`x`                  | The value to get the simple hash value  of.

**See Also:** [hashmap()](#function-hashmap)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    x = simple_hash("Foobar");
    x = simple_hash([[10,20],[-5,3]]);

<br clear="all" /><br/>

---

### Function: hashmap()

**Topics:** [Function Literals](Topics#function-literals), [Data Structures](Topics#data-structures), [Hashing](Topics#hashing)

**Usage:** Creating an Empty HashMap.

- hm = hashmap([hashsize=]);

**Usage:** Creating a Populated HashMap.

- hm = hashmap(items=KEYVAL\_LIST, [hashsize=]);

**Usage:** Adding an Entry

- hm2 = hm(key, val);

**Usage:** Adding Multiple Entries

- hm2 = hm(additems=KEYVAL\_LIST);

**Usage:** Removing an Entry

- hm2 = hm(del=KEY);

**Usage:** Fetching a Value

- x = hm(key);

**Usage:** Iterating a HashMap

- for (kv=hm()) let(k=kv[0], v=kv[1]) ...

**Description:** 

This is a factory function for creating hashmap data structure functions.  You can use a hashmap
to store large amounts of [key,value] data.  At around 4000 items, this becomes faster than using
`search()` through the list.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`hashsize`           | The number of hashtable buckets to form.
`items`              | A list of [key,value] pairs to initialize the hashmap with.

**FunctionLiteral Args:** 

Positional | Definition
---------- | ----------
k | The key name.
v | The value to store with the key.

Named | Definition
----- | ----------
del | If given the key of an item to delete, makes a new hashmap with that item removed.
additems | If given a list of [key,val] pairs, makes a new hashmap with the items added.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    hm = hashmap(items=[for (i=[0:9999]) [str("foo",i),i]]);
    a = hm("foo37");  // Returns: 37
    hm2 = hm("Blah", 39);  // Adds entry "Blah" with val 39.
    b = hm2("Blah");  // Returns: 39
    hm3 = hm2(additems=[["bar",39],["qux",21]]);  // Adds "bar" and "qux"
    hm4 = hm3(del="Blah");  // Deletes entry "Blah".
    for (kv = hm4()) {  // Iterates over all key/value pairs.
       echo(key=kv[0], val=kv[1]);
    }

<br clear="all" /><br/>

---

## Section: Function Meta-Generators


### Function: f\_1arg()

**Topics:** [Function Literals](Topics#function-literals), [Function Literal Factories](Topics#function-literal-factories)

**Usage:** 

- fn = f\_1arg(func);

**Description:** 

Takes a function literal that accepts one argument, and returns a function
literal factory that can be used to pre-fill out that argument with a constant.

**See Also:** [f\_2arg()](#function-f_2arg), [f\_3arg()](#function-f_3arg)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    f_str = f_1arg(function(a) str(a));
    fn_str = f_str();   // = function(a) str(a);
    fn_str3 = f_str(3); // = function() str(3);

<br clear="all" /><br/>

---

### Function: f\_2arg()

**Topics:** [Function Literals](Topics#function-literals), [Function Literal Factories](Topics#function-literal-factories)

**Usage:** 

- fn = f\_2arg(target\_func);

**Description:** 

Takes a function literal that accepts two arguments, and returns a function
literal factory that can be used to pre-fill out one or both of those arguments
with a constant.

**See Also:** [f\_1arg()](#function-f_1arg), [f\_3arg()](#function-f_3arg)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    f_lt = f_2arg(function(a,b) a<b);
    fn_lt = f_lt();      // = function(a,b) a<b;
    fn_3lt = f_lt(3);    // = function(b) 3<b;
    fn_3lt = f_lt(a=3);  // = function(b) 3<b;
    fn_lt3 = f_lt(b=3);  // = function(a) a<3;
    fn_3lt4 = f_lt(3,4); // = function() 3<4;

<br clear="all" /><br/>

---

### Function: f\_2arg\_simple()

**Topics:** [Function Literals](Topics#function-literals), [Function Literal Factories](Topics#function-literal-factories)

**Usage:** 

- fn = f\_2arg\_simple(target\_func);

**Description:** 

Takes a function literal that accepts two arguments, and returns a function
literal factory that can be used to pre-fill out one or both of those arguments
with a constant.  When given a single argument, fills out the segond function
argument with a constant.

**See Also:** [f\_1arg()](#function-f_1arg), [f\_3arg()](#function-f_3arg)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    f_lt = f_2arg_simple(function(a,b) a<b);
    fn_lt = f_lt();       // = function(a,b) a<b;
    fn_lt3 = f_lt(3);     // = function(a) a<3;
    fn_3lt4 = f_lt(3,4);  // = function() 3<4;

<br clear="all" /><br/>

---

### Function: f\_3arg()

**Topics:** [Function Literals](Topics#function-literals), [Function Literal Factories](Topics#function-literal-factories)

**Usage:** 

- fn = f\_3arg(target\_func);

**Description:** 

Takes a function literal that accepts three arguments, and returns a function
literal factory that can be used to pre-fill out some or all of those arguments
with a constant.

**See Also:** [f\_1arg()](#function-f_1arg), [f\_2arg()](#function-f_2arg)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    p1 = [10,4]; p2 = [3,7];
    f_va = f_3arg(function(a,b,c) vector_angle(a,b,c));
    fn_va = f_va();       // = function(a,b,c) vector_angle(a,b,c);
    fn_va2 = f_lt(c=p1);  // = function(a,b) vector_angle(a,b,p1);
    fn_va3 = f_lt(a=p2);  // = function(a,c) vector_angle(a,p2,c);
    fn_va4 = f_lt(a=p1,c=p2); // = function() vector_angle(p1,b,p2);

<br clear="all" /><br/>

---

### Function: ival()

**Usage:** 

- newfunc = ival(func);

**Description:** 

Wraps a single-argument function literal so that it can take two arguments,
passing the first argument along to the wrapped function.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`target_func`        | The function of signature (x) to wrap.

**FunctionLiteral Args:** 

Positional | Definition
---------- | ----------
a | The argument that will be passed through.
b | The argumen that will be discarded.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    x = while(0, ival(f_lt(5)), xval(fngen_add(1)));

<br clear="all" /><br/>

---

### Function: xval()

**Usage:** 

- newfunc = xval(func);

**Description:** 

Wraps a single-argument function literal so that it can take two arguments,
passing the first argument along to the wrapped function.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`target_func`        | The function of signature (x) to wrap.

**FunctionLiteral Args:** 

Positional | Definition
---------- | ----------
a | The argument that will be passed through.
b | The argumen that will be discarded.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    x = while(0, ival(f_lt(5)), xval(fngen_add(1)));

<br clear="all" /><br/>

---

## Section: Comparator Generators


### Function: f\_cmp()

**Usage:** 

- fn = f\_cmp();
- fn = f\_cmp(b);
- fn = f\_cmp(a,b);

**Description:** 

A factory that generates function literals that compare `a` and `b`, where one or
both arguments can be replaced with constants.  If `a` and `b` are equal, the function
literal will return 0.  If a<b then -1 is returned.  If a>b then 1 is returned.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    fn_cmp = f_cmp();       // = function(a,b) a==b?0: a>b?1: -1;
    fn_cmp3 = f_cmp(3);     // = function(a) a==3?0: a>3?1: -1;
    fn_3cmp4 = f_cmp(3,4);  // = function() 3==4?0: 3>4?1: -1;

<br clear="all" /><br/>

---

### Function: f\_gt()

**Usage:** 

- fn = f\_gt();
- fn = f\_gt(b);
- fn = f\_gt(a,b);

**Description:** 

A factory that generates function literals based on `a > b`, where one
or both of the arguments can be replaced with constants.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    fn_gt = f_gt();       // = function(a,b) a>b;
    fn_gt3 = f_gt(3);     // = function(a) a>3;
    fn_3gt4 = f_gt(3,4);  // = function() 3>4;

<br clear="all" /><br/>

---

### Function: f\_lt()

**Usage:** 

- fn = f\_lt();
- fn = f\_lt(b);
- fn = f\_lt(a,b);

**Description:** 

A factory that generates function literals based on `a < b`, where one
or both of the arguments can be replaced with constants.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    fn_lt = f_lt();       // = function(a,b) a<b;
    fn_lt3 = f_lt(3);     // = function(a) a<3;
    fn_3lt4 = f_lt(3,4);  // = function() 3<4;

<br clear="all" /><br/>

---

### Function: f\_gte()

**Usage:** 

- fn = f\_gte();
- fn = f\_gte(b);
- fn = f\_gte(a,b);

**Description:** 

A factory that generates function literals based on `a >= b`, where one
or both of the arguments can be replaced with constants.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    fn_gte = f_gte();       // = function(a,b) a>=b;
    fn_gte3 = f_gte(3);     // = function(a) a>=3;
    fn_3gte4 = f_gte(3,4);  // = function() 3>=4;

<br clear="all" /><br/>

---

### Function: f\_lte()

**Usage:** 

- fn = f\_lte();
- fn = f\_lte(b);
- fn = f\_lte(a,b);

**Description:** 

A factory that generates function literals based on `a <= b`, where
one or both arguments can be replaced with constants.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    fn_lte = f_lte();       // = function(a,b) a<=b;
    fn_lte3 = f_lte(3);     // = function(a) a<=3;
    fn_3lte4 = f_lte(3,4);  // = function() 3<=4;

<br clear="all" /><br/>

---

### Function: f\_eq()

**Usage:** 

- fn = f\_eq();
- fn = f\_eq(b);
- fn = f\_eq(a,b);

**Description:** 

A factory that generates function literals based on `a == b`, where
one or both arguments can be replaced with constants.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    fn_eq = f_eq();       // = function(a,b) a==b;
    fn_eq3 = f_eq(3);     // = function(a) a==3;
    fn_3eq4 = f_eq(3,4);  // = function() 3==4;

<br clear="all" /><br/>

---

### Function: f\_neq()

**Usage:** 

- fn = f\_neq();
- fn = f\_neq(b);
- fn = f\_neq(a,b);

**Description:** 

A factory that generates function literals based on `a != b`, where
one or both arguments can be replaced with constants.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    fn_neq = f_neq();       // = function(a,b) a!=b;
    fn_neq3 = f_neq(3);     // = function(a) a!=3;
    fn_3neq4 = f_neq(3,4);  // = function() 3!=4;

<br clear="all" /><br/>

---

### Function: f\_approx()

**Usage:** 

- fn = f\_approx();
- fn = f\_approx(b);
- fn = f\_approx(a,b);

**Description:** 

A factory that generates function literals based on `approx(a,b)`, where
one or both arguments can be replaced with constants.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    fn_approx = f_approx();       // = function(a,b) approx(a,b);
    fn_approx3 = f_approx(3);     // = function(a) approx(a,3);
    fn_3approx4 = f_approx(3,4);  // = function() approx(3,4);

<br clear="all" /><br/>

---

### Function: f\_napprox()

**Usage:** 

- fn = f\_napprox();
- fn = f\_napprox(b);
- fn = f\_napprox(a,b);

**Description:** 

A factory that generates function literals based on `!approx(a,b)`, where
one or both arguments can be replaced with constants.

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    fn_napprox = f_napprox();       // = function(a,b) napprox(a,b);
    fn_napprox3 = f_napprox(3);     // = function(a) napprox(a,3);
    fn_3napprox4 = f_napprox(3,4);  // = function() napprox(3,4);

<br clear="all" /><br/>

---

## Section: Logic Operators


### Function: f\_or()

**Topics:** [Function Literals](Topics#function-literals), [Logic](Topics#logic), [Boolean Operations](Topics#boolean-operations)

**Usage:** 

- fn = f\_or();
- fn = f\_or(a=);
- fn = f\_or(b=);
- fn = f\_or(a=,b=);

**Description:** 

A factory that generates function literals based on `a || b`, where
either or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_and()](#function-f_and), [f\_nor()](#function-f_nor), [f\_nand()](#function-f_nand), [f\_xor()](#function-f_xor), [f\_not()](#function-f_not)

---

### Function: f\_and()

**Topics:** [Function Literals](Topics#function-literals), [Logic](Topics#logic), [Boolean Operations](Topics#boolean-operations)

**Usage:** 

- fn = f\_and();
- fn = f\_and(a=);
- fn = f\_and(b=);
- fn = f\_and(a=,b=);

**Description:** 

A factory that generates function literals based on `a && b`, where
either or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_or()](#function-f_or), [f\_nor()](#function-f_nor), [f\_nand()](#function-f_nand), [f\_xor()](#function-f_xor), [f\_not()](#function-f_not)

---

### Function: f\_nor()

**Topics:** [Function Literals](Topics#function-literals), [Logic](Topics#logic), [Boolean Operations](Topics#boolean-operations)

**Usage:** 

- fn = f\_nor();
- fn = f\_nor(a=);
- fn = f\_nor(b=);
- fn = f\_nor(a=,b=);

**Description:** 

A factory that generates function literals based on `!(a || b)`, where
either or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_or()](#function-f_or), [f\_and()](#function-f_and), [f\_nand()](#function-f_nand), [f\_xor()](#function-f_xor), [f\_not()](#function-f_not)

---

### Function: f\_nand()

**Topics:** [Function Literals](Topics#function-literals), [Logic](Topics#logic), [Boolean Operations](Topics#boolean-operations)

**Usage:** 

- fn = f\_nand();
- fn = f\_nand(a=);
- fn = f\_nand(b=);
- fn = f\_nand(a=,b=);

**Description:** 

A factory that generates function literals based on `!(a && b)`, where
either or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_or()](#function-f_or), [f\_and()](#function-f_and), [f\_nor()](#function-f_nor), [f\_xor()](#function-f_xor), [f\_not()](#function-f_not)

---

### Function: f\_xor()

**Topics:** [Function Literals](Topics#function-literals), [Logic](Topics#logic), [Boolean Operations](Topics#boolean-operations)

**Usage:** 

- fn = f\_xor();
- fn = f\_xor(a=);
- fn = f\_xor(b);
- fn = f\_xor(a=,b=);

**Description:** 

A factory that generates function literals based on `(!a && b) || (a && !b)`, where
either or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_or()](#function-f_or), [f\_and()](#function-f_and), [f\_nor()](#function-f_nor), [f\_nand()](#function-f_nand), [f\_not()](#function-f_not)

---

### Function: f\_not()

**Topics:** [Function Literals](Topics#function-literals), [Logic](Topics#logic), [Boolean Operations](Topics#boolean-operations)

**Usage:** 

- fn = f\_not();
- fn = f\_not(a);

**Description:** 

A factory that generates function literals based on `!a`, where the `a`
argument can be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_or()](#function-f_or), [f\_and()](#function-f_and), [f\_nor()](#function-f_nor), [f\_nand()](#function-f_nand), [f\_xor()](#function-f_xor)

---

### Function: f\_even()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_even();
- fn = f\_even(a);

**Description:** 

A factory that generates function literals based on `a % 2 == 0`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_or()](#function-f_or), [f\_and()](#function-f_and), [f\_nor()](#function-f_nor), [f\_nand()](#function-f_nand), [f\_xor()](#function-f_xor), [f\_not()](#function-f_not), [f\_odd()](#function-f_odd)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    l2 = filter(f_even(), [3,4,5,6,7,8]);  // Returns: [4,6,8]

<br clear="all" /><br/>

---

### Function: f\_odd()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_odd();
- fn = f\_odd(a);

**Description:** 

A factory that generates function literals based on `a % 2 != 0`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_or()](#function-f_or), [f\_and()](#function-f_and), [f\_nor()](#function-f_nor), [f\_nand()](#function-f_nand), [f\_xor()](#function-f_xor), [f\_not()](#function-f_not), [f\_even()](#function-f_even)

**Example 1:** 

    include <BOSL2/std.scad>
    include <BOSL2/fnliterals.scad>
    l2 = filter(f_odd(), [3,4,5,6,7,8]);  // Returns: [3,5,7]

<br clear="all" /><br/>

---

## Section: Math Operators


### Function: f\_add()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_add();
- fn = f\_add(a=);
- fn = f\_add(b);
- fn = f\_add(a=,b=);

**Description:** 

A factory that generates function literals based on `a + b`, where either
or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_sub()](#function-f_sub), [f\_mul()](#function-f_mul), [f\_div()](#function-f_div), [f\_mod()](#function-f_mod), [f\_pow()](#function-f_pow), [f\_neg()](#function-f_neg)

---

### Function: f\_sub()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_sub();
- fn = f\_sub(a=);
- fn = f\_sub(b);
- fn = f\_sub(a=,b=);

**Description:** 

A factory that generates function literals based on `a - b`, where either
or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_add()](#function-f_add), [f\_mul()](#function-f_mul), [f\_div()](#function-f_div), [f\_mod()](#function-f_mod), [f\_pow()](#function-f_pow), [f\_neg()](#function-f_neg)

---

### Function: f\_mul()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_mul();
- fn = f\_mul(a=);
- fn = f\_mul(b);
- fn = f\_mul(a=,b=);

**Description:** 

A factory that generates function literals based on `a * b`, where either
or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_add()](#function-f_add), [f\_sub()](#function-f_sub), [f\_div()](#function-f_div), [f\_mod()](#function-f_mod), [f\_pow()](#function-f_pow), [f\_neg()](#function-f_neg)

---

### Function: f\_div()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_div();
- fn = f\_div(a=);
- fn = f\_div(b);
- fn = f\_div(a=,b=);

**Description:** 

A factory that generates function literals based on `a / b`, where either
or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_add()](#function-f_add), [f\_sub()](#function-f_sub), [f\_mul()](#function-f_mul), [f\_mod()](#function-f_mod), [f\_pow()](#function-f_pow), [f\_neg()](#function-f_neg)

---

### Function: f\_mod()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_mod();
- fn = f\_mod(a=);
- fn = f\_mod(b);
- fn = f\_mod(a=,b=);

**Description:** 

A factory that generates function literals based on `a % b`, where either
or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_add()](#function-f_add), [f\_sub()](#function-f_sub), [f\_mul()](#function-f_mul), [f\_div()](#function-f_div), [f\_pow()](#function-f_pow), [f\_neg()](#function-f_neg)

---

### Function: f\_pow()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_pow();
- fn = f\_pow(a=);
- fn = f\_pow(b);
- fn = f\_pow(a=,b=);

**Description:** 

A factory that generates function literals based on `pow(a,b)`, where either
or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_add()](#function-f_add), [f\_sub()](#function-f_sub), [f\_mul()](#function-f_mul), [f\_div()](#function-f_div), [f\_mod()](#function-f_mod), [f\_neg()](#function-f_neg)

---

### Function: f\_neg()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_neg();
- fn = f\_neg(a);

**Description:** 

A factory that generates function literals based on `-a`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_add()](#function-f_add), [f\_sub()](#function-f_sub), [f\_mul()](#function-f_mul), [f\_div()](#function-f_div), [f\_mod()](#function-f_mod), [f\_pow()](#function-f_pow)

---

## Section: Min/Max Operators


### Function: f\_min()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_min();
- fn = f\_min(a);

**Description:** 

A factory that generates function literals based on `min(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_max()](#function-f_max), [f\_min2()](#function-f_min2), [f\_max2()](#function-f_max2), [f\_min3()](#function-f_min3), [f\_max3()](#function-f_max3)

---

### Function: f\_max()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_max();
- fn = f\_max(a);

**Description:** 

A factory that generates function literals based on `max(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_min()](#function-f_min), [f\_min2()](#function-f_min2), [f\_max2()](#function-f_max2), [f\_min3()](#function-f_min3), [f\_max3()](#function-f_max3)

---

### Function: f\_min2()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_min2();
- fn = f\_min2(a=);
- fn = f\_min2(b);
- fn = f\_min2(a=,b=);

**Description:** 

A factory that generates function literals based on `min(a,b)`, where either
or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_min()](#function-f_min), [f\_max()](#function-f_max), [f\_max2()](#function-f_max2), [f\_min3()](#function-f_min3), [f\_max3()](#function-f_max3)

---

### Function: f\_max2()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_max2();
- fn = f\_max2(a=);
- fn = f\_max2(b);
- fn = f\_max2(a=,b=);

**Description:** 

A factory that generates function literals based on `max(a,b)`, where either
or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_min()](#function-f_min), [f\_max()](#function-f_max), [f\_min2()](#function-f_min2), [f\_min3()](#function-f_min3), [f\_max3()](#function-f_max3)

---

### Function: f\_min3()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_min3();
- fn = f\_min3(a=);
- fn = f\_min3(b=);
- fn = f\_min3(c=);
- fn = f\_min3(a=,b=);
- fn = f\_min3(b=,c=);
- fn = f\_min3(a=,c=);
- fn = f\_min3(a=,b=,c=);

**Description:** 

A factory that generates function literals based on `min(a,b,c)`, where any
or all of the `a`, `b`, or`c` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.
`c`                  | If given, replaces the third argument.

**See Also:** [f\_min()](#function-f_min), [f\_max()](#function-f_max), [f\_min2()](#function-f_min2), [f\_max2()](#function-f_max2), [f\_max3()](#function-f_max3)

---

### Function: f\_max3()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_max3();
- fn = f\_max3(a=);
- fn = f\_max3(b=);
- fn = f\_max3(c=);
- fn = f\_max3(a=,b=);
- fn = f\_max3(b=,c=);
- fn = f\_max3(a=,c=);
- fn = f\_max3(a=,b=,c=);

**Description:** 

A factory that generates function literals based on `min(a,b,c)`, where any
or all of the `a`, `b`, or`c` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.
`c`                  | If given, replaces the third argument.

**See Also:** [f\_min()](#function-f_min), [f\_max()](#function-f_max), [f\_min2()](#function-f_min2), [f\_max2()](#function-f_max2), [f\_min3()](#function-f_min3)

---

## Section: Trigonometry Operators


### Function: f\_sin()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_sin();
- fn = f\_sin(a);

**Description:** 

A factory that generates function literals based on `sin(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_cos()](#function-f_cos), [f\_tan()](#function-f_tan), [f\_asin()](#function-f_asin), [f\_acos()](#function-f_acos), [f\_atan()](#function-f_atan), [f\_atan2()](#function-f_atan2)

---

### Function: f\_cos()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_cos();
- fn = f\_cos(a);

**Description:** 

A factory that generates function literals based on `cos(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_sin()](#function-f_sin), [f\_tan()](#function-f_tan), [f\_asin()](#function-f_asin), [f\_acos()](#function-f_acos), [f\_atan()](#function-f_atan), [f\_atan2()](#function-f_atan2)

---

### Function: f\_tan()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_tan();
- fn = f\_tan(a);

**Description:** 

A factory that generates function literals based on `tan(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_sin()](#function-f_sin), [f\_cos()](#function-f_cos), [f\_asin()](#function-f_asin), [f\_acos()](#function-f_acos), [f\_atan()](#function-f_atan), [f\_atan2()](#function-f_atan2)

---

### Function: f\_asin()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_asin();
- fn = f\_asin(a);

**Description:** 

A factory that generates function literals based on `asin(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_sin()](#function-f_sin), [f\_cos()](#function-f_cos), [f\_tan()](#function-f_tan), [f\_acos()](#function-f_acos), [f\_atan()](#function-f_atan), [f\_atan2()](#function-f_atan2)

---

### Function: f\_acos()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_acos();
- fn = f\_acos(a);

**Description:** 

A factory that generates function literals based on `acos(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_sin()](#function-f_sin), [f\_cos()](#function-f_cos), [f\_tan()](#function-f_tan), [f\_asin()](#function-f_asin), [f\_atan()](#function-f_atan), [f\_atan2()](#function-f_atan2)

---

### Function: f\_atan()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_atan();
- fn = f\_atan(a);

**Description:** 

A factory that generates function literals based on `atan(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_sin()](#function-f_sin), [f\_cos()](#function-f_cos), [f\_tan()](#function-f_tan), [f\_asin()](#function-f_asin), [f\_acos()](#function-f_acos), [f\_atan2()](#function-f_atan2)

---

### Function: f\_atan2()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_atan2();
- fn = f\_atan2(a=);
- fn = f\_atan2(b);
- fn = f\_atan2(a=,b=);

**Description:** 

A factory that generates function literals based on `atan2(a,b)`, where either
or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_sin()](#function-f_sin), [f\_cos()](#function-f_cos), [f\_tan()](#function-f_tan), [f\_asin()](#function-f_asin), [f\_acos()](#function-f_acos), [f\_atan()](#function-f_atan)

---

## Section: String Operators


### Function: f\_len()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_len();
- fn = f\_len(a);

**Description:** 

A factory that generates function literals based on `len(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_chr()](#function-f_chr), [f\_ord()](#function-f_ord), [f\_str()](#function-f_str), [f\_str2()](#function-f_str2), [f\_str3()](#function-f_str3)

---

### Function: f\_chr()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_chr();
- fn = f\_chr(a);

**Description:** 

A factory that generates function literals based on `chr(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_len()](#function-f_len), [f\_ord()](#function-f_ord), [f\_str()](#function-f_str), [f\_str2()](#function-f_str2), [f\_str3()](#function-f_str3)

---

### Function: f\_ord()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_ord();
- fn = f\_ord(a);

**Description:** 

A factory that generates function literals based on `ord(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_len()](#function-f_len), [f\_chr()](#function-f_chr), [f\_str()](#function-f_str), [f\_str2()](#function-f_str2), [f\_str3()](#function-f_str3)

---

### Function: f\_str()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_str();
- fn = f\_str(a);

**Description:** 

A factory that generates function literals based on `str(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_len()](#function-f_len), [f\_chr()](#function-f_chr), [f\_ord()](#function-f_ord), [f\_str2()](#function-f_str2), [f\_str3()](#function-f_str3)

---

### Function: f\_str2()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_str2();
- fn = f\_str2(a=);
- fn = f\_str2(b);
- fn = f\_str2(a=,b=);

**Description:** 

A factory that generates function literals based on `str(a,b)`, where either
or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_len()](#function-f_len), [f\_chr()](#function-f_chr), [f\_ord()](#function-f_ord), [f\_str()](#function-f_str), [f\_str3()](#function-f_str3)

---

### Function: f\_str3()

**Topics:** [Function Literals](Topics#function-literals), [Math Operators](Topics#math-operators)

**Usage:** 

- fn = f\_str3();
- fn = f\_str3(a=);
- fn = f\_str3(b=);
- fn = f\_str3(c=);
- fn = f\_str3(a=,b=);
- fn = f\_str3(b=,c=);
- fn = f\_str3(a=,c=);
- fn = f\_str3(a=,b=,c=);

**Description:** 

A factory that generates function literals based on `str(a,b,c)`, where any
or all of the `a`, `b`, or`c` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.
`c`                  | If given, replaces the third argument.

**See Also:** [f\_len()](#function-f_len), [f\_chr()](#function-f_chr), [f\_ord()](#function-f_ord), [f\_str()](#function-f_str), [f\_str2()](#function-f_str2)

---

## Section: Miscellaneous Operators


### Function: f\_floor()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_floor();
- fn = f\_floor(a);

**Description:** 

A factory that generates function literals based on `floor(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_ceil()](#function-f_ceil), [f\_round()](#function-f_round)

---

### Function: f\_round()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_round();
- fn = f\_round(a);

**Description:** 

A factory that generates function literals based on `round(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_floor()](#function-f_floor), [f\_ceil()](#function-f_ceil)

---

### Function: f\_ceil()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_ceil();
- fn = f\_ceil(a);

**Description:** 

A factory that generates function literals based on `ceil(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_floor()](#function-f_floor), [f\_round()](#function-f_round)

---

### Function: f\_abs()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_abs();
- fn = f\_abs(a);

**Description:** 

A factory that generates function literals based on `abs(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_sign()](#function-f_sign), [f\_ln()](#function-f_ln), [f\_log()](#function-f_log), [f\_exp()](#function-f_exp), [f\_sqr()](#function-f_sqr), [f\_sqrt()](#function-f_sqrt)

---

### Function: f\_sign()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_sign();
- fn = f\_sign(a);

**Description:** 

A factory that generates function literals based on `sign(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_abs()](#function-f_abs), [f\_ln()](#function-f_ln), [f\_log()](#function-f_log), [f\_exp()](#function-f_exp), [f\_sqr()](#function-f_sqr), [f\_sqrt()](#function-f_sqrt)

---

### Function: f\_ln()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_ln();
- fn = f\_ln(a);

**Description:** 

A factory that generates function literals based on `ln(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_abs()](#function-f_abs), [f\_sign()](#function-f_sign), [f\_log()](#function-f_log), [f\_exp()](#function-f_exp), [f\_sqr()](#function-f_sqr), [f\_sqrt()](#function-f_sqrt)

---

### Function: f\_log()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_log();
- fn = f\_log(a);

**Description:** 

A factory that generates function literals based on `log(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_abs()](#function-f_abs), [f\_sign()](#function-f_sign), [f\_ln()](#function-f_ln), [f\_exp()](#function-f_exp), [f\_sqr()](#function-f_sqr), [f\_sqrt()](#function-f_sqrt)

---

### Function: f\_exp()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_exp();
- fn = f\_exp(a);

**Description:** 

A factory that generates function literals based on `exp(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_abs()](#function-f_abs), [f\_sign()](#function-f_sign), [f\_ln()](#function-f_ln), [f\_log()](#function-f_log), [f\_sqr()](#function-f_sqr), [f\_sqrt()](#function-f_sqrt)

---

### Function: f\_sqr()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_sqr();
- fn = f\_sqr(a);

**Description:** 

A factory that generates function literals based on `a*a`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_abs()](#function-f_abs), [f\_sign()](#function-f_sign), [f\_ln()](#function-f_ln), [f\_log()](#function-f_log), [f\_exp()](#function-f_exp), [f\_sqrt()](#function-f_sqrt)

---

### Function: f\_sqrt()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_sqrt();
- fn = f\_sqrt(a);

**Description:** 

A factory that generates function literals based on `sqrt(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_abs()](#function-f_abs), [f\_sign()](#function-f_sign), [f\_ln()](#function-f_ln), [f\_log()](#function-f_log), [f\_exp()](#function-f_exp), [f\_sqr()](#function-f_sqr)

---

### Function: f\_norm()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_norm();
- fn = f\_norm(a);

**Description:** 

A factory that generates function literals based on `norm(a)`, where the `a`
argument can optionally be replaced with a constant.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_abs()](#function-f_abs), [f\_sign()](#function-f_sign), [f\_ln()](#function-f_ln), [f\_log()](#function-f_log), [f\_exp()](#function-f_exp), [f\_sqr()](#function-f_sqr), [f\_sqrt()](#function-f_sqrt)

---

### Function: f\_cross()

**Topics:** [Function Literals](Topics#function-literals), [String Operators](Topics#string-operators)

**Usage:** 

- fn = f\_cross();
- fn = f\_cross(a=);
- fn = f\_cross(b);
- fn = f\_cross(a=,b=);

**Description:** 

A factory that generates function literals based on `str(a,b)`, where either
or both of the `a` or `b` arguments can be replaced with constants.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the first argument.
`b`                  | If given, replaces the second argument.

**See Also:** [f\_norm()](#function-f_norm), [f\_abs()](#function-f_abs), [f\_sign()](#function-f_sign)

---

## Section: Type Queries


### Function: f\_is\_def()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_def();

**Description:** 

A factory that returns function literals equivalent to `is_def(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_undef()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_undef();

**Description:** 

A factory that returns function literals equivalent to `is_undef(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_bool()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_bool();

**Description:** 

A factory that returns function literals equivalent to `is_bool(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_num()](#function-f_is_num), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_num()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_num();

**Description:** 

A factory that returns function literals equivalent to `is_num(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_int()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_int();

**Description:** 

A factory that returns function literals equivalent to `is_int(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_nan()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_nan();

**Description:** 

A factory that returns function literals equivalent to `is_nan(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_int()](#function-f_is_int), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_finite()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_finite();

**Description:** 

A factory that returns function literals equivalent to `is_finite(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_int()](#function-f_is_int), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_string()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_string();

**Description:** 

A factory that returns function literals equivalent to `is_string(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_int()](#function-f_is_int), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_list()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_list();

**Description:** 

A factory that returns function literals equivalent to `is_list(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_int()](#function-f_is_int), [f\_is\_string()](#function-f_is_string)

---

### Function: f\_is\_range()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_range();

**Description:** 

A factory that returns function literals equivalent to `is_range(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_int()](#function-f_is_int), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_function()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_function();

**Description:** 

A factory that returns function literals equivalent to `is_function(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_int()](#function-f_is_int), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_vector()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_vector();

**Description:** 

A factory that returns function literals equivalent to `is_vector(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_int()](#function-f_is_int), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_path()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_path();

**Description:** 

A factory that returns function literals equivalent to `is_path(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_int()](#function-f_is_int), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_region()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_region();

**Description:** 

A factory that returns function literals equivalent to `is_region(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_int()](#function-f_is_int), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_vnf()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_vnf();

**Description:** 

A factory that returns function literals equivalent to `is_vnf(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_int()](#function-f_is_int), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

### Function: f\_is\_patch()

**Topics:** [Function Literals](Topics#function-literals), [Type Queries](Topics#type-queries)

**Usage:** 

- fn = f\_is\_patch();

**Description:** 

A factory that returns function literals equivalent to `is_patch(a)`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | If given, replaces the argument.

**See Also:** [f\_is\_undef()](#function-f_is_undef), [f\_is\_bool()](#function-f_is_bool), [f\_is\_num()](#function-f_is_num), [f\_is\_int()](#function-f_is_int), [f\_is\_string()](#function-f_is_string), [f\_is\_list()](#function-f_is_list)

---

