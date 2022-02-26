# LibFile: strings.scad

String manipulation and formatting functions.

To use, add the following lines to the beginning of your file:

    include <BOSL2/std.scad>

## Table of Contents

1. [Section: Extracting substrings](#section-extracting-substrings)
    - [`substr()`](#function-substr)
    - [`suffix()`](#function-suffix)

2. [Section: String Searching](#section-string-searching)
    - [`str_find()`](#function-str_find)
    - [`starts_with()`](#function-starts_with)
    - [`ends_with()`](#function-ends_with)
    - [`str_split()`](#function-str_split)

3. [Section: String modification](#section-string-modification)
    - [`str_join()`](#function-str_join)
    - [`str_strip()`](#function-str_strip)
    - [`str_pad()`](#function-str_pad)
    - [`str_replace_char()`](#function-str_replace_char)
    - [`downcase()`](#function-downcase)
    - [`upcase()`](#function-upcase)

4. [Section: Parsing strings into numbers](#section-parsing-strings-into-numbers)
    - [`parse_int()`](#function-parse_int)
    - [`parse_float()`](#function-parse_float)
    - [`parse_frac()`](#function-parse_frac)
    - [`parse_num()`](#function-parse_num)

5. [Section: Formatting numbers into strings](#section-formatting-numbers-into-strings)
    - [`format_int()`](#function-format_int)
    - [`format_fixed()`](#function-format_fixed)
    - [`format_float()`](#function-format_float)
    - [`format()`](#function-format)

6. [Section: Checking character class](#section-checking-character-class)
    - [`is_lower()`](#function-is_lower)
    - [`is_upper()`](#function-is_upper)
    - [`is_digit()`](#function-is_digit)
    - [`is_hexdigit()`](#function-is_hexdigit)
    - [`is_letter()`](#function-is_letter)


## Section: Extracting substrings


### Function: substr()

**Usage:** 

- substr(str, [pos], [len])

**Description:** 

Returns a substring from a string start at position `pos` with length `len`, or
if `len` isn't given, the rest of the string.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | string to operate on
`pos`                | starting index of substring, or vector of first and last position.  Default: 0
`len`                | length of substring, or omit it to get the rest of the string.  If len is zero or less then the emptry string is returned.

**Example 1:** 

    include <BOSL2/std.scad>
    substr("abcdefg",3,3);     // Returns "def"
    substr("abcdefg",2);       // Returns "cdefg"
    substr("abcdefg",len=3);   // Returns "abc"
    substr("abcdefg",[2,4]);   // Returns "cde"
    substr("abcdefg",len=-2);  // Returns ""

<br clear="all" /><br/>

---

### Function: suffix()

**Usage:** 

- suffix(str,len)

**Description:** 

Returns the last `len` characters from the input string `str`.
If `len` is longer than the length of `str`, then the entirety of `str` is returned.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | The string to get the suffix of.
`len`                | The number of characters of suffix to get.

---

## Section: String Searching


### Function: str\_find()

**Usage:** 

- str\_find(str,pattern,[last],[all],[start])

**Description:** 

Searches input string `str` for the string `pattern` and returns the index or indices of the matches in `str`.
By default `str_find()` returns the index of the first match in `str`.  If `last` is true then it returns the index of the last match.
If the pattern is the empty string the first match is at zero and the last match is the last character of the `str`.
If `start` is set then the search begins at index start, working either forward and backward from that position.  If you set `start`
and `last` is true then the search will find the pattern if it begins at index `start`.  If no match exists, returns `undef`.
If you set `all` to true then `str_find()` returns all of the matches in a list, or an empty list if there are no matches.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | String to search.
`pattern`            | string pattern to search for
`last`               | set to true to return the last match. Default: false
`all`                | set to true to return all matches as a list.  Overrides last.  Default: false
`start`              | index where the search starts

**Example 1:** 

    include <BOSL2/std.scad>
    str_find("abc123def123abc","123");   // Returns 3
    str_find("abc123def123abc","b");     // Returns 1
    str_find("abc123def123abc","1234");  // Returns undef
    str_find("abc","");                  // Returns 0
    str_find("abc123def123", "123", start=4);     // Returns 9
    str_find("abc123def123abc","123",last=true);  // Returns 9
    str_find("abc123def123abc","b",last=true);    // Returns 13
    str_find("abc123def123abc","1234",last=true); // Returns undef
    str_find("abc","",last=true);                 // Returns 3
    str_find("abc123def123", "123", start=8, last=true));  // Returns 3
    str_find("abc123def123abc","123",all=true);   // Returns [3,9]
    str_find("abc123def123abc","b",all=true);     // Returns [1,13]
    str_find("abc123def123abc","1234",all=true);  // Returns []
    str_find("abc","",all=true);                  // Returns [0,1,2]

<br clear="all" /><br/>

---

### Function: starts\_with()

**Usage:** 

- starts\_with(str,pattern)

**Description:** 

Returns true if the input string `str` starts with the specified string pattern, `pattern`.
Otherwise returns false.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | String to search.
`pattern`            | String pattern to search for.

**Example 1:** 

    include <BOSL2/std.scad>
    starts_with("abcdef","abc");  // Returns true
    starts_with("abcdef","def");  // Returns false
    starts_with("abcdef","");     // Returns true

<br clear="all" /><br/>

---

### Function: ends\_with()

**Usage:** 

- ends\_with(str,pattern)

**Description:** 

Returns true if the input string `str` ends with the specified string pattern, `pattern`.
Otherwise returns false.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | String to search.
`pattern`            | String pattern to search for.

**Example 1:** 

    include <BOSL2/std.scad>
    ends_with("abcdef","def");  // Returns true
    ends_with("abcdef","de");   // Returns false
    ends_with("abcdef","");     // Returns true

<br clear="all" /><br/>

---

### Function: str\_split()

**Usage:** 

- str\_split(str, sep, [keep\_nulls])

**Description:** 

Breaks an input string into substrings using a separator or list of separators.  If keep_nulls is true
then two sequential separator characters produce an empty string in the output list.  If keep_nulls is false
then no empty strings are included in the output list.

If sep is a single string then each character in sep is treated as a delimiting character and the input string is
split at every delimiting character.  Empty strings can occur whenever two delimiting characters are sequential.
If sep is a list of strings then the input string is split sequentially using each string from the list in order.
If keep_nulls is true then the output will have length equal to `len(sep)+1`, possibly with trailing null strings
if the string runs out before the separator list.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | String to split.
`sep`                | a string or list of strings to use for the separator
`keep_nulls`         | boolean value indicating whether to keep null strings in the output list.  Default: true

**Example 1:** 

    include <BOSL2/std.scad>
    str_split("abc+def-qrs*iop","*-+");     // Returns ["abc", "def", "qrs", "iop"]
    str_split("abc+*def---qrs**iop+","*-+");// Returns ["abc", "", "def", "", "", "qrs", "", "iop", ""]
    str_split("abc      def"," ");          // Returns ["abc", "", "", "", "", "", "def"]
    str_split("abc      def"," ",keep_nulls=false);  // Returns ["abc", "def"]
    str_split("abc+def-qrs*iop",["+","-","*"]);     // Returns ["abc", "def", "qrs", "iop"]
    str_split("abc+def-qrs*iop",["-","+","*"]);     // Returns ["abc+def", "qrs*iop", "", ""]

<br clear="all" /><br/>

---

## Section: String modification


### Function: str\_join()

**Usage:** 

- str\_join(list, [sep])

**Description:** 

Returns the concatenation of a list of strings, optionally with a
separator string inserted between each string on the list.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`list`               | list of strings to concatenate
`sep`                | separator string to insert.  Default: ""

**Example 1:** 

    include <BOSL2/std.scad>
    str_join(["abc","def","ghi"]);        // Returns "abcdefghi"
    str_join(["abc","def","ghi"], " + ");  // Returns "abc + def + ghi"

<br clear="all" /><br/>

---

### Function: str\_strip()

**Usage:** 

- str\_strip(s,c,[start],[end]);

**Description:** 

Takes a string `s` and strips off all leading and/or trailing characters that exist in string `c`.
By default strips both leading and trailing characters.  If you set start or end to true then
it will strip only the leading or trailing characters respectively.  If you set start
or end to false then it will strip only lthe trailing or leading characters.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`s`                  | The string to strip leading or trailing characters from.
`c`                  | The string of characters to strip.
`start`              | if true then strip leading characters
`end`                | if true then strip trailing characters

**Example 1:** 

    include <BOSL2/std.scad>
    str_strip("--##--123--##--","#-");  // Returns: "123"
    str_strip("--##--123--##--","-");   // Returns: "##--123--##"
    str_strip("--##--123--##--","#");   // Returns: "--##--123--##--"
    str_strip("--##--123--##--","#-",end=true);  // Returns: "--##--123"
    str_strip("--##--123--##--","-",end=true);   // Returns: "--##--123--##"
    str_strip("--##--123--##--","#",end=true);   // Returns: "--##--123--##--"
    str_strip("--##--123--##--","#-",start=true); // Returns: "123--##--"
    str_strip("--##--123--##--","-",start=true);  // Returns: "##--123--##--"
    str_strip("--##--123--##--","#",start=true);  // Returns: "--##--123--##--"

<br clear="all" /><br/>

---

### Function: str\_pad()

**Usage:** 

- padded = str\_pad(str, length, char, [left]);

**Description:** 

Pad the given string `str` with to length `length` with the specified character,
which must be a length 1 string.  If left is true then pad on the left, otherwise
pad on the right.  If the string is longer than the specified length the full string
is returned unchanged.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | string to pad
`length`             | length to pad to
`char`               | character to pad with.  Default: " " (space)
`left`               | if true, pad on the left side.  Default: false

---

### Function: str\_replace\_char()

**Usage:** 

- newstr = str\_replace\_char(str, char, replace)

**Description:** 

Replace every occurence of `char` in the input string with the string `replace` which
can be any string.

---

### Function: downcase()

**Usage:** 

- downcase(str)

**Description:** 

Returns the string with the standard ASCII upper case letters A-Z replaced
by their lower case versions.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | String to convert.

**Example 1:** 

    include <BOSL2/std.scad>
    downcase("ABCdef");   // Returns "abcdef"

<br clear="all" /><br/>

---

### Function: upcase()

**Usage:** 

- upcase(str)

**Description:** 

Returns the string with the standard ASCII lower case letters a-z replaced
by their upper case versions.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | String to convert.

**Example 1:** 

    include <BOSL2/std.scad>
    upcase("ABCdef");   // Returns "ABCDEF"

<br clear="all" /><br/>

---

## Section: Parsing strings into numbers


### Function: parse\_int()

**Usage:** 

- parse\_int(str, [base])

**Description:** 

Converts a string into an integer with any base up to 16.  Returns NaN if
conversion fails.  Digits above 9 are represented using letters A-F in either
upper case or lower case.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | String to convert.
`base`               | Base for conversion, from 2-16.  Default: 10

**Example 1:** 

    include <BOSL2/std.scad>
    parse_int("349");        // Returns 349
    parse_int("-37");        // Returns -37
    parse_int("+97");        // Returns 97
    parse_int("43.9");       // Returns nan
    parse_int("1011010",2);  // Returns 90
    parse_int("13",2);       // Returns nan
    parse_int("dead",16);    // Returns 57005
    parse_int("CEDE", 16);   // Returns 52958
    parse_int("");           // Returns 0

<br clear="all" /><br/>

---

### Function: parse\_float()

**Usage:** 

- parse\_float(str)

**Description:** 

Converts a string to a floating point number.  Returns NaN if the
conversion fails.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | String to convert.

**Example 1:** 

    include <BOSL2/std.scad>
    parse_float("44");       // Returns 44
    parse_float("3.4");      // Returns 3.4
    parse_float("-99.3332"); // Returns -99.3332
    parse_float("3.483e2");  // Returns 348.3
    parse_float("-44.9E2");  // Returns -4490
    parse_float("7.342e-4"); // Returns 0.0007342
    parse_float("");         // Returns 0

<br clear="all" /><br/>

---

### Function: parse\_frac()

**Usage:** 

- parse\_frac(str,[mixed],[improper],[signed])

**Description:** 

Converts a string fraction to a floating point number.  A string fraction has the form `[-][# ][#/#]` where each `#` is one or more of the
digits 0-9, and there is an optional sign character at the beginning.
The full form is a sign character and an integer, followed by exactly one space, followed by two more
integers separated by a "/" character.  The leading integer and
space can be omitted or the trailing fractional part can be omitted.  If you set `mixed` to false then the leading integer part is not
accepted and the input must include a slash.  If you set `improper` to false then the fractional part must be a proper fraction, where
the numerator is smaller than the denominator.  If you set `signed` to false then the leading sign character is not permitted.
The empty string evaluates to zero.  Any invalid string evaluates to NaN.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`str`                | String to convert.
`mixed`              | set to true to accept mixed fractions, false to reject them.  Default: true
`improper`           | set to true to accept improper fractions, false to reject them.  Default: true
`signed`             | set to true to accept a leading sign character, false to reject.  Default: true

**Example 1:** 

    include <BOSL2/std.scad>
    parse_frac("3/4");     // Returns 0.75
    parse_frac("-77/9");   // Returns -8.55556
    parse_frac("+1/3");    // Returns 0.33333
    parse_frac("19");      // Returns 19
    parse_frac("2 3/4");   // Returns 2.75
    parse_frac("-2 12/4"); // Returns -5
    parse_frac("");        // Returns 0
    parse_frac("3/0");     // Returns inf
    parse_frac("0/0");     // Returns nan
    parse_frac("-77/9",improper=false);   // Returns nan
    parse_frac("-2 12/4",improper=false); // Returns nan
    parse_frac("-2 12/4",signed=false);   // Returns nan
    parse_frac("-2 12/4",mixed=false);    // Returns nan
    parse_frac("2 1/4",mixed=false);      // Returns nan

<br clear="all" /><br/>

---

### Function: parse\_num()

**Usage:** 

- parse\_num(str)

**Description:** 

Converts a string to a number.  The string can be either a fraction (two integers separated by a "/") or a floating point number.
Returns NaN if the conversion fails.

**Example 1:** 

    include <BOSL2/std.scad>
    parse_num("3/4");    // Returns 0.75
    parse_num("3.4e-2"); // Returns 0.034

<br clear="all" /><br/>

---

## Section: Formatting numbers into strings


### Function: format\_int()

**Usage:** 

- format\_int(i, [mindigits]);

**Description:** 

Formats an integer number into a string.  This can handle larger numbers than `str()`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`i`                  | The integer to make a string of.
`mindigits`          | If the number has fewer than this many digits, pad the front with zeros until it does.  Default: 1.

**Example 1:** 

    include <BOSL2/std.scad>
    str(123456789012345);  // Returns "1.23457e+14"
    format_int(123456789012345);  // Returns "123456789012345"
    format_int(-123456789012345);  // Returns "-123456789012345"

<br clear="all" /><br/>

---

### Function: format\_fixed()

**Usage:** 

- s = format\_fixed(f, [digits]);

**Description:** 

Given a floating point number, formats it into a string with the given number of digits after the decimal point.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`f`                  | The floating point number to format.
`digits`             | The number of digits after the decimal to show.  Default: 6

---

### Function: format\_float()

**Usage:** 

- format\_float(f,[sig]);

**Description:** 

Formats the given floating point number `f` into a string with `sig` significant digits.
Strips trailing `0`s after the decimal point.  Strips trailing decimal point.
If the number can be represented in `sig` significant digits without a mantissa, it will be.
If given a list of numbers, recursively prints each item in the list, returning a string like `[3,4,5]`

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`f`                  | The floating point number to format.
`sig`                | The number of significant digits to display.  Default: 12

**Example 1:** 

    include <BOSL2/std.scad>
    format_float(PI,12);  // Returns: "3.14159265359"
    format_float([PI,-16.75],12);  // Returns: "[3.14159265359, -16.75]"

<br clear="all" /><br/>

---

### Function: format()

**Usage:** 

- s = format(fmt, vals);

**Description:** 

Given a format string and a list of values, inserts the values into the placeholders in the format string and returns it.
Formatting placeholders have the following syntax:
- A leading `{` character to show the start of the placeholder.
- An integer index into the `vals` list to specify which value should be formatted at that place. If not given, the first placeholder will use index `0`, the second will use index `1`, etc.
- An optional `:` separator to indicate that what follows if a formatting specifier.  If not given, no formatting info follows.
- An optional `-` character to indicate that the value should be left justified if the value needs field width padding.  If not given, right justification is used.
- An optional `0` character to indicate that the field should be padded with `0`s.  If not given, spaces will be used for padding.
- An optional integer field width, which the value should be padded to.  If not given, no padding will be performed.
- An optional `.` followed by an integer precision length, for specifying how many digits to display in numeric formats.  If not give, 6 digits is assumed.
- An optional letter to indicate the formatting style to use.  If not given, `s` is assumed, which will do it's generic best to format any data type.
- A trailing `}` character to show the end of the placeholder.

Formatting styles, and their effects are as follows:
- `s`: Converts the value to a string with `str()` to display.  This is very generic.
- `i` or `d`: Formats numeric values as integers.
- `f`: Formats numeric values with the precision number of digits after the decimal point.  NaN and Inf are shown as `nan` and `inf`.
- `F`: Formats numeric values with the precision number of digits after the decimal point.  NaN and Inf are shown as `NAN` and `INF`.
- `g`: Formats numeric values with the precision number of total significant digits.  NaN and Inf are shown as `nan` and `inf`.  Mantissas are demarked by `e`.
- `G`: Formats numeric values with the precision number of total significant digits.  NaN and Inf are shown as `NAN` and `INF`.  Mantissas are demarked by `E`.
- `b`: If the value logically evaluates as true, it shows as `true`, otherwise `false`.
- `B`: If the value logically evaluates as true, it shows as `TRUE`, otherwise `FALSE`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`fmt`                | The formatting string, with placeholders to format the values into.
`vals`               | The list of values to format.

**Example 1:** 

    include <BOSL2/std.scad>
    format("The value of {} is {:.14f}.", ["pi", PI]);  // Returns: "The value of pi is 3.14159265358979."
    format("The value {1:f} is known as {0}.", ["pi", PI]);  // Returns: "The value 3.141593 is known as pi."
    format("We use a very small value {1:.6g} as {0}.", ["EPSILON", EPSILON]);  // Returns: "We use a very small value 1e-9 as EPSILON."
    format("{:-5s}{:i}{:b}", ["foo", 12e3, 5]);  // Returns: "foo  12000true"
    format("{:-10s}{:.3f}", ["plecostamus",27.43982]);  // Returns: "plecostamus27.440"
    format("{:-10.9s}{:.3f}", ["plecostamus",27.43982]);  // Returns: "plecostam 27.440"

<br clear="all" /><br/>

---

## Section: Checking character class


### Function: is\_lower()

**Usage:** 

- x = is\_lower(s);

**Description:** 

Returns true if all the characters in the given string are lowercase letters. (a-z)

---

### Function: is\_upper()

**Usage:** 

- x = is\_upper(s);

**Description:** 

Returns true if all the characters in the given string are uppercase letters. (A-Z)

---

### Function: is\_digit()

**Usage:** 

- x = is\_digit(s);

**Description:** 

Returns true if all the characters in the given string are digits. (0-9)

---

### Function: is\_hexdigit()

**Usage:** 

- x = is\_hexdigit(s);

**Description:** 

Returns true if all the characters in the given string are valid hexadecimal digits. (0-9 or a-f or A-F))

---

### Function: is\_letter()

**Usage:** 

- x = is\_letter(s);

**Description:** 

Returns true if all the characters in the given string are standard ASCII letters. (A-Z or a-z)

---

