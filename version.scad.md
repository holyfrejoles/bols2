# LibFile: version.scad

File that provides functions to manage versioning.

To use, add the following lines to the beginning of your file:

    include <BOSL2/std.scad>

## Table of Contents

1. [Section: BOSL Library Version Functions](#section-bosl-library-version-functions)
    - [`bosl_version()`](#function-bosl_version)
    - [`bosl_version_num()`](#function-bosl_version_num)
    - [`bosl_version_str()`](#function-bosl_version_str)
    - [`bosl_required()`](#module-bosl_required)

2. [Section: Generic Version Functions](#section-generic-version-functions)
    - [`version_to_list()`](#function-version_to_list)
    - [`version_to_str()`](#function-version_to_str)
    - [`version_to_num()`](#function-version_to_num)
    - [`version_cmp()`](#function-version_cmp)


## Section: BOSL Library Version Functions


### Function: bosl\_version()

**Usage:** 

- ver = bosl\_version();

**Description:** 

Returns a list with three integer elements, [MAJOR,MINOR,REV],
representing the Major, Minor, and Build Revision numbers.
For example, version 2.1.43 will be returned as `[2,1,43]`.

---

### Function: bosl\_version\_num()

**Usage:** 

- ver = bosl\_version\_num();

**Description:** 

Returns a floating point number of the version, formatted like M.mmrrrr where M is the major version number,
each m is a zero-padded digit of the minor version number, and each r is a zero-padded digit of the build
revision number.  For example, version 2.1.43 will be returned as `2.010043`.

---

### Function: bosl\_version\_str()

**Usage:** 

- ver = bosl\_version\_str();

**Description:** 

Returns a string of the version, formatted like "MAJOR.MINOR.REV".
For example, version 2.1.43 will be returned as `"2.1.43"`.

---

### Module: bosl\_required()

**Usage:** 

- bosl\_required(x);

**Description:** 

Given a version as a list, number, or string, asserts that the currently installed BOSL library is at least the given version.

---

## Section: Generic Version Functions


### Function: version\_to\_list()

**Usage:** 

- ver = version\_to\_list(x);

**Description:** 

Given a version string, number, or list, returns the list of version integers [MAJOR,MINOR,REVISION].

**Example 1:** 

    include <BOSL2/std.scad>
    v1 = version_to_list("2.1.43");  // Returns: [2,1,43]
    v2 = version_to_list(2.120234);  // Returns: [2,12,234]
    v3 = version_to_list([2,3,4]);   // Returns: [2,3,4]
    v4 = version_to_list([2,3,4,5]); // Returns: [2,3,4]

<br clear="all" /><br/>

---

### Function: version\_to\_str()

**Usage:** 

- str = version\_to\_str(x);

**Description:** 

Takes a version string, number, or list, and returns the properly formatter version string for it.

**Example 1:** 

    include <BOSL2/std.scad>
    v1 = version_to_str([2,1,43]);  // Returns: "2.1.43"
    v2 = version_to_str(2.010043);  // Returns: "2.1.43"
    v3 = version_to_str(2.340789);  // Returns: "2.34.789"
    v4 = version_to_str("2.3.89");  // Returns: "2.3.89"

<br clear="all" /><br/>

---

### Function: version\_to\_num()

**Usage:** 

- str = version\_to\_num(x);

**Description:** 

Takes a version string, number, or list, and returns the properly formatter version number for it.

**Example 1:** 

    include <BOSL2/std.scad>
    v1 = version_to_num([2,1,43]);   // Returns: 2.010043
    v2 = version_to_num([2,34,567]); // Returns: 2.340567
    v3 = version_to_num(2.120567);   // Returns: 2.120567
    v4 = version_to_num("2.6.79");   // Returns: 2.060079

<br clear="all" /><br/>

---

### Function: version\_cmp()

**Usage:** 

- cmp = version\_cmp(a,b);

**Description:** 

Given a pair of versions, in any combination of string, integer, or list, compares them, and returns the relative value of them.
Returns an integer <0 if a<b.  Returns 0 if a==b.  Returns an integer >0 if a>b.

**Example 1:** 

    include <BOSL2/std.scad>
    cmp1 = version_cmp(2.010034, "2.1.33");  // Returns: >0
    cmp2 = version_cmp(2.010034, "2.1.34");  // Returns: 0
    cmp3 = version_cmp(2.010034, "2.1.35");  // Returns: <0

<br clear="all" /><br/>

---

