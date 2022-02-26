# LibFile: structs.scad

Struct/Dictionary manipulation functions.

To use, add the following lines to the beginning of your file:

    include <BOSL2/std.scad>
    include <BOSL2/structs.scad>

## Table of Contents

1. [Section: struct operations](#section-struct-operations)
    - [`struct_set()`](#function-struct_set)
    - [`struct_remove()`](#function-struct_remove)
    - [`struct_val()`](#function-struct_val)
    - [`struct_keys()`](#function-struct_keys)
    - [`struct_echo()`](#functionmodule-struct_echo)
    - [`is_struct()`](#function-is_struct)


## Section: struct operations


### Function: struct\_set()

**Usage:** 

- struct\_set(struct, keyword, value, [grow])
- struct\_set(struct, [keyword1, value1, keyword2, value2, ...], [grow])

**Description:** 

Sets the keyword(s) in the structure to the specified value(s), returning a new updated structure.  If a keyword
exists its value is changed, otherwise the keyword is added to the structure.  If grow is set to false then
it is an error to set a keyword not already defined in the structure.  If you specify the same keyword twice
that is also an error.  If speed matters, use the first form with scalars rather than the list form: this is
about thirty times faster.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`struct`             | Input structure.
`keyword`            | Keyword to set.
`value`              | Value to set the keyword to.
`grow`               | Set to true to allow structure to grow, or false for new keywords to generate an error.  Default: true

---

### Function: struct\_remove()

**Usage:** 

- struct\_remove(struct, keyword)

**Description:** 

Remove keyword or keyword list from a structure

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`struct`             | input structure
`keyword`            | a single string (keyword) or list of strings (keywords) to remove

---

### Function: struct\_val()

**Usage:** 

- struct\_val(struct, keyword, default)

**Description:** 

Returns the value for the specified keyword in the structure, or default value if the keyword is not present

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`struct`             | input structure
`keyword`            | keyword whose value to return
`default`            | default value to return if keyword is not present, defaults to undef

---

### Function: struct\_keys()

**Usage:** 

- keys = struct\_keys(struct)

**Description:** 

Returns a list of the keys in a structure

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`struct`             | input structure

---

### Function/Module: struct\_echo()

**Usage:** 

- struct\_echo(struct, [name])

**Description:** 

Displays a list of structure keywords and values, one pair per line, for easier reading.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`struct`             | input structure
`name`               | optional structure name to list at the top of the output.  Default: ""

---

### Function: is\_struct()

**Usage:** 

- is\_struct(struct)

**Description:** 

Returns true if the input has the form of a structure, false otherwise.

---

