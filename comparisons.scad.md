# LibFile: comparisons.scad

Functions for comparisons with lists, ordering and sorting

To use, add the following lines to the beginning of your file:

    include <BOSL2/std.scad>

## Table of Contents

1. [Section: List comparison operations](#section-list-comparison-operations)
    - [`approx()`](#function-approx)
    - [`all_zero()`](#function-all_zero)
    - [`all_nonzero()`](#function-all_nonzero)
    - [`all_positive()`](#function-all_positive)
    - [`all_negative()`](#function-all_negative)
    - [`all_nonpositive()`](#function-all_nonpositive)
    - [`all_nonnegative()`](#function-all_nonnegative)
    - [`all_equal()`](#function-all_equal)
    - [`is_increasing()`](#function-is_increasing)
    - [`is_decreasing()`](#function-is_decreasing)
    - [`compare_vals()`](#function-compare_vals)
    - [`compare_lists()`](#function-compare_lists)

2. [Section: Finding the index of the minimum or maximum of a list](#section-finding-the-index-of-the-minimum-or-maximum-of-a-list)
    - [`min_index()`](#function-min_index)
    - [`max_index()`](#function-max_index)

3. [Section: Dealing with duplicate list entries](#section-dealing-with-duplicate-list-entries)
    - [`find_approx()`](#function-find_approx)
    - [`deduplicate()`](#function-deduplicate)
    - [`deduplicate_indexed()`](#function-deduplicate_indexed)
    - [`unique()`](#function-unique)
    - [`unique_count()`](#function-unique_count)

4. [Section: Sorting](#section-sorting)
    - [`sort()`](#function-sort)
    - [`sortidx()`](#function-sortidx)
    - [`group_sort()`](#function-group_sort)
    - [`group_data()`](#function-group_data)
    - [`list_smallest()`](#function-list_smallest)


## Section: List comparison operations


### Function: approx()

**Usage:** 

- test = approx(a, b, [eps])

**Description:** 

Compares two numbers, vectors, or matrices.  Returns true if they are closer than `eps` to each other.
Results are undefined if `a` and `b` are of different types, or if vectors or matrices contain non-numbers.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | First value.
`b`                  | Second value.
`eps`                | The maximum allowed difference between `a` and `b` that will return true.

**Example 1:** 

    include <BOSL2/std.scad>
    test1 = approx(-0.3333333333,-1/3);  // Returns: true
    test2 = approx(0.3333333333,1/3);    // Returns: true
    test3 = approx(0.3333,1/3);          // Returns: false
    test4 = approx(0.3333,1/3,eps=1e-3); // Returns: true
    test5 = approx(PI,3.1415926536);     // Returns: true
    test6 = approx([0,0,sin(45)],[0,0,sqrt(2)/2]);  // Returns: true

<br clear="all" /><br/>

---

### Function: all\_zero()

**Usage:** 

- x = all\_zero(x, [eps]);

**Description:** 

Returns true if the finite number passed to it is approximately zero, to within `eps`.
If passed a list returns true if all its entries are approximately zero.
Otherwise, returns false.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`x`                  | The value to check.
`eps`                | The maximum allowed variance.  Default: `EPSILON` (1e-9)

**Example 1:** 

    include <BOSL2/std.scad>
    a = all_zero(0);  // Returns: true.
    b = all_zero(1e-3);  // Returns: false.
    c = all_zero([0,0,0]);  // Returns: true.
    d = all_zero([0,0,1e-3]);  // Returns: false.

<br clear="all" /><br/>

---

### Function: all\_nonzero()

**Usage:** 

- test = all\_nonzero(x, [eps]);

**Description:** 

Returns true if the finite number passed to it is different from zero by `eps`.
If passed a list returns true if all the entries of the list are different from zero by `eps`.
Otherwise, returns false.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`x`                  | The value to check.
`eps`                | The maximum allowed variance.  Default: `EPSILON` (1e-9)

**Example 1:** 

    include <BOSL2/std.scad>
    a = all_nonzero(0);  // Returns: false.
    b = all_nonzero(1e-3);  // Returns: true.
    c = all_nonzero([0,0,0]);  // Returns: false.
    d = all_nonzero([0,0,1e-3]);  // Returns: false.
    e = all_nonzero([1e-3,1e-3,1e-3]);  // Returns: true.

<br clear="all" /><br/>

---

### Function: all\_positive()

**Usage:** 

- test = all\_positive(x,[eps]);

**Description:** 

Returns true if the finite number passed to it is greater than zero.
If passed a list returns true if all the entries are positive.
Otherwise, returns false.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`x`                  | The value to check.
`eps`                | Tolerance. Default: 0

**Example 1:** 

    include <BOSL2/std.scad>
    a = all_positive(-2);  // Returns: false.
    b = all_positive(0);  // Returns: false.
    c = all_positive(2);  // Returns: true.
    d = all_positive([0,0,0]);  // Returns: false.
    e = all_positive([0,1,2]);  // Returns: false.
    f = all_positive([3,1,2]);  // Returns: true.
    g = all_positive([3,-1,2]);  // Returns: false.

<br clear="all" /><br/>

---

### Function: all\_negative()

**Usage:** 

- test = all\_negative(x, [eps]);

**Description:** 

Returns true if the finite number passed to it is less than zero.
If passed a list, recursively checks if all items in the list are negative.
Otherwise, returns false.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`x`                  | The value to check.
`eps`                | tolerance.  Default: 0

**Example 1:** 

    include <BOSL2/std.scad>
    a = all_negative(-2);  // Returns: true.
    b = all_negative(0);  // Returns: false.
    c = all_negative(2);  // Returns: false.
    d = all_negative([0,0,0]);  // Returns: false.
    e = all_negative([0,1,2]);  // Returns: false.
    f = all_negative([3,1,2]);  // Returns: false.
    g = all_negative([3,-1,2]);  // Returns: false.
    h = all_negative([-3,-1,-2]);  // Returns: true.

<br clear="all" /><br/>

---

### Function: all\_nonpositive()

**Usage:** 

- all\_nonpositive(x, [eps]);

**Description:** 

Returns true if the finite number passed to it is less than or equal to zero.
If passed a list, recursively checks if all items in the list are nonpositive.
Otherwise, returns false.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`x`                  | The value to check.
`eps`                | tolerance.  Default: 0

**Example 1:** 

    include <BOSL2/std.scad>
    a = all_nonpositive(-2);  // Returns: true.
    b = all_nonpositive(0);  // Returns: true.
    c = all_nonpositive(2);  // Returns: false.
    d = all_nonpositive([0,0,0]);  // Returns: true.
    e = all_nonpositive([0,1,2]);  // Returns: false.
    f = all_nonpositive([3,1,2]);  // Returns: false.
    g = all_nonpositive([3,-1,2]);  // Returns: false.
    h = all_nonpositive([-3,-1,-2]);  // Returns: true.

<br clear="all" /><br/>

---

### Function: all\_nonnegative()

**Usage:** 

- all\_nonnegative(x, [eps]);

**Description:** 

Returns true if the finite number passed to it is greater than or equal to zero.
If passed a list, recursively checks if all items in the list are nonnegative.
Otherwise, returns false.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`x`                  | The value to check.
`eps`                | tolerance.  Default: 0

**Example 1:** 

    include <BOSL2/std.scad>
    a = all_nonnegative(-2);  // Returns: false.
    b = all_nonnegative(0);  // Returns: true.
    c = all_nonnegative(2);  // Returns: true.
    d = all_nonnegative([0,0,0]);  // Returns: true.
    e = all_nonnegative([0,1,2]);  // Returns: true.
    f = all_nonnegative([0,-1,-2]);  // Returns: false.
    g = all_nonnegative([3,1,2]);  // Returns: true.
    h = all_nonnegative([3,-1,2]);  // Returns: false.
    i = all_nonnegative([-3,-1,-2]);  // Returns: false.

<br clear="all" /><br/>

---

### Function: all\_equal()

**Usage:** 

- b = all\_equal(vec, [eps]);

**Description:** 

Returns true if all of the entries in vec are equal to each other, or approximately equal to each other if eps is set.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`vec`                | vector to check
`eps`                | Set to tolerance for approximate equality.  Default: 0

---

### Function: is\_increasing()

**Usage:** 

- bool = is\_increasing(list);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Returns true if the list is (non-strictly) increasing, or strictly increasing if strict is set to true.
The list can be a list of any items that OpenSCAD can compare, or it can be a string which will be
evaluated character by character.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`list`               | list (or string) to check
`strict`             | set to true to test that list is strictly increasing

**See Also:** [max\_index()](#function-max_index), [min\_index()](#function-min_index), [is\_decreasing()](#function-is_decreasing)

**Example 1:** 

    include <BOSL2/std.scad>
    a = is_increasing([1,2,3,4]);  // Returns: true
    b = is_increasing([1,3,2,4]);  // Returns: false
    c = is_increasing([1,3,3,4]);  // Returns: true
    d = is_increasing([1,3,3,4],strict=true);  // Returns: false
    e = is_increasing([4,3,2,1]);  // Returns: false

<br clear="all" /><br/>

---

### Function: is\_decreasing()

**Usage:** 

- bool = is\_decreasing(list);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Returns true if the list is (non-strictly) decreasing, or strictly decreasing if strict is set to true.
The list can be a list of any items that OpenSCAD can compare, or it can be a string which will be
evaluated character by character.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`list`               | list (or string) to check
`strict`             | set to true to test that list is strictly decreasing

**See Also:** [max\_index()](#function-max_index), [min\_index()](#function-min_index), [is\_increasing()](#function-is_increasing)

**Example 1:** 

    include <BOSL2/std.scad>
    a = is_decreasing([1,2,3,4]);  // Returns: false
    b = is_decreasing([4,2,3,1]);  // Returns: false
    c = is_decreasing([4,3,2,1]);  // Returns: true

<br clear="all" /><br/>

---

### Function: compare\_vals()

**Usage:** 

- test = compare\_vals(a, b);

**Description:** 

Compares two values.  Lists are compared recursively.
Returns <0 if a<b.  Returns >0 if a>b.  Returns 0 if a==b.
If types are not the same, then undef < bool < nan < num < str < list < range.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | First value to compare.
`b`                  | Second value to compare.

---

### Function: compare\_lists()

**Usage:** 

- test = compare\_lists(a, b)

**Description:** 

Compare contents of two lists using `compare_vals()`.
Returns <0 if `a`<`b`.
Returns 0 if `a`==`b`.
Returns >0 if `a`>`b`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`a`                  | First list to compare.
`b`                  | Second list to compare.

---

## Section: Finding the index of the minimum or maximum of a list


### Function: min\_index()

**Usage:** 

- idx = min\_index(vals);
- idxlist = min\_index(vals, all=true);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Returns the index of the first occurrence of the minimum value in the given list.
If `all` is true then returns a list of all indices where the minimum value occurs.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`vals`               | vector of values
`all`                | set to true to return indices of all occurences of the minimum.  Default: false

**See Also:** [max\_index()](#function-max_index), [is\_increasing()](#function-is_increasing), [is\_decreasing()](#function-is_decreasing)

**Example 1:** 

    include <BOSL2/std.scad>
    a = min_index([5,3,9,6,2,7,8,2,1]); // Returns: 8
    b = min_index([5,3,9,6,2,7,8,2,7],all=true); // Returns: [4,7]

<br clear="all" /><br/>

---

### Function: max\_index()

**Usage:** 

- idx = max\_index(vals);
- idxlist = max\_index(vals, all=true);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Returns the index of the first occurrence of the maximum value in the given list.
If `all` is true then returns a list of all indices where the maximum value occurs.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`vals`               | vector of values
`all`                | set to true to return indices of all occurences of the maximum.  Default: false

**See Also:** [min\_index()](#function-min_index), [is\_increasing()](#function-is_increasing), [is\_decreasing()](#function-is_decreasing)

**Example 1:** 

    include <BOSL2/std.scad>
    max_index([5,3,9,6,2,7,8,9,1]); // Returns: 2
    max_index([5,3,9,6,2,7,8,9,1],all=true); // Returns: [2,7]

<br clear="all" /><br/>

---

## Section: Dealing with duplicate list entries


### Function: find\_approx()

**Topics:** [List Handling](Topics#list-handling)

**Usage:** 

- idx = find\_approx(val, list, [start=], [eps=]);
- indices = find\_approx(val, list, all=true, [start=], [eps=]);

**Description:** 

Finds the first item in `list` that matches `val`, returning the index.  Returns `undef` if there is no match.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`val`                | The value to search for.
`list`               | The list to search through.

<abbr title="These args must be used by name, ie: name=value">By&nbsp;Name</abbr> | What it does
-------------------- | ------------
`start`              | The index to start searching from.  Default: 0
`all`                | If true, returns a list of all matching item indices.
`eps`                | The maximum allowed floating point rounding error for numeric comparisons.

**See Also:** [in\_list()](lists.scad#function-in_list)

---

### Function: deduplicate()

**Usage:** 

- list = deduplicate(list, [close], [eps]);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Removes consecutive duplicate items in a list.
When `eps` is zero, the comparison between consecutive items is exact.
Otherwise, when all list items and subitems are numbers, the comparison is within the tolerance `eps`.
Unlike `unique()` only consecutive duplicates are removed and the list is *not* sorted.
If `closed` is set to true then the first and last entries in `list` are treated as adjacent,
so all trailing items that match `list[0]` are dropped.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`list`               | The list to deduplicate.
`closed`             | If true, treats first and last list entry as adjacent.  Default: false
`eps`                | The maximum tolerance between items.  Default: EPSILON

**See Also:** [deduplicate\_indexed()](#function-deduplicate_indexed)

**Example 1:** 

    include <BOSL2/std.scad>
    a = deduplicate([8,3,4,4,4,8,2,3,3,8,8]);  // Returns: [8,3,4,8,2,3,8]
    b = deduplicate(closed=true, [8,3,4,4,4,8,2,3,3,8,8]);  // Returns: [8,3,4,8,2,3]
    c = deduplicate("Hello");  // Returns: "Helo"
    d = deduplicate([[3,4],[7,2],[7,1.99],[1,4]],eps=0.1);  // Returns: [[3,4],[7,2],[1,4]]
    e = deduplicate([[7,undef],[7,undef],[1,4],[1,4+1e-12]],eps=0);    // Returns: [[7,undef],[1,4],[1,4+1e-12]]

<br clear="all" /><br/>

---

### Function: deduplicate\_indexed()

**Usage:** 

- new\_idxs = deduplicate\_indexed(list, indices, [closed], [eps]);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Given a list, and a list of indices, removes consecutive indices corresponding to list values that are equal
or approximately equal.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`list`               | The list that the indices index into.
`indices`            | The list of indices to deduplicate.
`closed`             | If true, drops trailing indices if their list value matches the list value corresponding to the first index.
`eps`                | The maximum difference to allow between numbers or vectors.

**See Also:** [deduplicate()](#function-deduplicate)

**Example 1:** 

    include <BOSL2/std.scad>
    a = deduplicate_indexed([8,6,4,6,3], [1,4,3,1,2,2,0,1]);  // Returns: [1,4,3,2,0,1]
    b = deduplicate_indexed([8,6,4,6,3], [1,4,3,1,2,2,0,1], closed=true);  // Returns: [1,4,3,2,0]
    c = deduplicate_indexed([[7,undef],[7,undef],[1,4],[1,4],[1,4+1e-12]],eps=0);    // Returns: [0,2,4]

<br clear="all" /><br/>

---

### Function: unique()

**Usage:** 

- ulist = unique(list);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Given a string or a list returns the sorted string or the sorted list with all repeated items removed.
The sorting order of non homogeneous lists is the function `sort` order.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`list`               | The list to uniquify.

**See Also:** [shuffle()](lists.scad#function-shuffle), [sort()](#function-sort), [sortidx()](#function-sortidx), [unique\_count()](#function-unique_count)

**Example 1:** 

    include <BOSL2/std.scad>
    sorted = unique([5,2,8,3,1,3,8,7,5]);  // Returns: [1,2,3,5,7,8]
    sorted = unique("axdbxxc");  // Returns: "abcdx"
    sorted = unique([true,2,"xba",[1,0],true,[0,0],3,"a",[0,0],2]); // Returns: [true,2,3,"a","xba",[0,0],[1,0]]

<br clear="all" /><br/>

---

### Function: unique\_count()

**Usage:** 

- counts = unique\_count(list);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Returns `[sorted,counts]` where `sorted` is a sorted list of the unique items in `list` and `counts` is a list such
that `count[i]` gives the number of times that `sorted[i]` appears in `list`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`list`               | The list to analyze.

**See Also:** [shuffle()](lists.scad#function-shuffle), [sort()](#function-sort), [sortidx()](#function-sortidx), [unique()](#function-unique)

**Example 1:** 

    include <BOSL2/std.scad>
    sorted = unique([5,2,8,3,1,3,8,3,5]);  // Returns: [ [1,2,3,5,8], [1,1,3,2,2] ]

<br clear="all" /><br/>

---

## Section: Sorting


### Function: sort()

**Usage:** 

- slist = sort(list, [idx]);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Sorts the given list in lexicographic order. If the input is a homogeneous simple list or a homogeneous
list of vectors (see function is_homogeneous), the sorting method uses the native comparison operator and is faster.
When sorting non homogeneous list the elements are compared with `compare_vals`, with types ordered according to
`undef < boolean < number < string < list`.  Comparison of lists is recursive.
When comparing vectors, homogeneous or not, the parameter `idx` may be used to select the components to compare.
Note that homogeneous lists of vectors may contain mixed types provided that for any two list elements
list[i] and list[j] satisfies  type(list[i][k])==type(list[j][k]) for all k.
Strings are allowed as any list element and are compared with the native operators although no substring
comparison is possible.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`list`               | The list to sort.
`idx`                | If given, do the comparison based just on the specified index, range or list of indices.

**See Also:** [shuffle()](lists.scad#function-shuffle), [sortidx()](#function-sortidx), [unique()](#function-unique), [unique\_count()](#function-unique_count), [group\_sort()](#function-group_sort)

**Example 1:** 

    include <BOSL2/std.scad>
    // Homogeneous lists
    l1 = [45,2,16,37,8,3,9,23,89,12,34];
    sorted1 = sort(l1);  // Returns [2,3,8,9,12,16,23,34,37,45,89]
    l2 = [["oat",0], ["cat",1], ["bat",3], ["bat",2], ["fat",3]];
    sorted2 = sort(l2); // Returns: [["bat",2],["bat",3],["cat",1],["fat",3],["oat",0]]
    // Non-homegenous list
    l3 = [[4,0],[7],[3,9],20,[4],[3,1],[8]];
    sorted3 = sort(l3); // Returns: [20,[3,1],[3,9],[4],[4,0],[7],[8]]

<br clear="all" /><br/>

---

### Function: sortidx()

**Usage:** 

- idxlist = sortidx(list, [idx]);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Given a list, sort it as function `sort()`, and returns
a list of indexes into the original list in that sorted order.
If you iterate the returned list in order, and use the list items
to index into the original list, you will be iterating the original
values in sorted order.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`list`               | The list to sort.
`idx`                | If given, do the comparison based just on the specified index, range or list of indices.

**See Also:** [shuffle()](lists.scad#function-shuffle), [sort()](#function-sort), [group\_sort()](#function-group_sort), [unique()](#function-unique), [unique\_count()](#function-unique_count)

**Example 1:** 

    include <BOSL2/std.scad>
    lst = ["d","b","e","c"];
    idxs = sortidx(lst);  // Returns: [1,3,0,2]
    ordered = select(lst, idxs);   // Returns: ["b", "c", "d", "e"]

<br clear="all" /><br/>

**Example 2:** 

    include <BOSL2/std.scad>
    lst = [
        ["foo", 88, [0,0,1], false],
        ["bar", 90, [0,1,0], true],
        ["baz", 89, [1,0,0], false],
        ["qux", 23, [1,1,1], true]
    ];
    idxs1 = sortidx(lst, idx=1); // Returns: [3,0,2,1]
    idxs2 = sortidx(lst, idx=0); // Returns: [1,2,0,3]
    idxs3 = sortidx(lst, idx=[1,3]); // Returns: [3,0,2,1]

<br clear="all" /><br/>

---

### Function: group\_sort()

**Usage:** 

- ulist = group\_sort(list);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Given a list of values, returns the sorted list with all repeated items grouped in a list.
When the list entries are themselves lists, the sorting may be done based on the `idx` entry
of those entries, that should be numbers.
The result is always a list of lists.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`list`               | The list to sort.
`idx`                | If given, do the comparison based just on the specified index. Default: zero.

**See Also:** [shuffle()](lists.scad#function-shuffle), [sort()](#function-sort), [sortidx()](#function-sortidx), [unique()](#function-unique), [unique\_count()](#function-unique_count)

**Example 1:** 

    include <BOSL2/std.scad>
    sorted = group_sort([5,2,8,3,1,3,8,7,5]);  // Returns: [[1],[2],[3,3],[5,5],[7],[8,8]]
    sorted2 = group_sort([[5,"a"],[2,"b"], [5,"c"], [3,"d"], [2,"e"] ], idx=0);  // Returns: [[[2,"b"],[2,"e"]], [[5,"a"],[5,"c"]], [[3,"d"]] ]

<br clear="all" /><br/>

---

### Function: group\_data()

**Usage:** 

- groupings = group\_data(groups, values);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Given a list of integer group numbers, and an equal-length list of values,
returns a list of groups with the values sorted into the corresponding groups.
Ie: if you have a groups index list of [2,3,2] and values of ["A","B","C"], then
the values "A" and "C" will be put in group 2, and "B" will be in group 3.
Groups that have no values grouped into them will be an empty list.  So the
above would return [[], [], ["A","C"], ["B"]]

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`groups`             | A list of integer group index numbers.
`values`             | A list of values to sort into groups.

**Example 1:** 

    include <BOSL2/std.scad>
    groups = group_data([1,2,0], ["A","B","C"]);  // Returns [["B"],["C"],["A"]]

<br clear="all" /><br/>

**Example 2:** 

    include <BOSL2/std.scad>
    groups = group_data([1,3,1], ["A","B","C"]);  // Returns [[],["A","C"],[],["B"]]

<br clear="all" /><br/>

---

### Function: list\_smallest()

**Usage:** 

- small = list\_smallest(list, k)

**Description:** 

Returns a set of the k smallest items in list in arbitrary order.  The items must be
mutually comparable with native OpenSCAD comparison operations.  You will get "undefined operation"
errors if you provide invalid input.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`list`               | list to process
`k`                  | number of items to return

---

