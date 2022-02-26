# LibFile: linalg.scad

This file provides linear algebra, with support for matrix construction,
solutions to linear systems of equations, QR and Cholesky factorizations, and
matrix inverse.

To use, add the following lines to the beginning of your file:

    include <BOSL2/std.scad>

## Table of Contents

1. [Section: Matrices](#section-matrices)

2. [Section: Matrix testing and display](#section-matrix-testing-and-display)
    - [`is_matrix()`](#function-is_matrix)
    - [`is_matrix_symmetric()`](#function-is_matrix_symmetric)
    - [`echo_matrix()`](#functionmodule-echo_matrix)

3. [Section: Matrix indexing](#section-matrix-indexing)
    - [`column()`](#function-column)
    - [`submatrix()`](#function-submatrix)

4. [Section: Matrix construction and modification](#section-matrix-construction-and-modification)
    - [`ident()`](#function-ident)
    - [`diagonal_matrix()`](#function-diagonal_matrix)
    - [`transpose()`](#function-transpose)
    - [`outer_product()`](#function-outer_product)
    - [`submatrix_set()`](#function-submatrix_set)
    - [`hstack()`](#function-hstack)
    - [`block_matrix()`](#function-block_matrix)

5. [Section: Solving Linear Equations and Matrix Factorizations](#section-solving-linear-equations-and-matrix-factorizations)
    - [`linear_solve()`](#function-linear_solve)
    - [`linear_solve3()`](#function-linear_solve3)
    - [`matrix_inverse()`](#function-matrix_inverse)
    - [`rot_inverse()`](#function-rot_inverse)
    - [`null_space()`](#function-null_space)
    - [`qr_factor()`](#function-qr_factor)
    - [`back_substitute()`](#function-back_substitute)
    - [`cholesky()`](#function-cholesky)

6. [Section: Matrix Properties: Determinants, Norm, Trace](#section-matrix-properties-determinants-norm-trace)
    - [`det2()`](#function-det2)
    - [`det3()`](#function-det3)
    - [`det4()`](#function-det4)
    - [`determinant()`](#function-determinant)
    - [`norm_fro()`](#function-norm_fro)
    - [`matrix_trace()`](#function-matrix_trace)


## Section: Matrices

The matrix, a rectangular array of numbers which represents a linear transformation,
is the fundamental object in linear algebra.  In OpenSCAD a matrix is a list of lists of numbers
with a rectangular structure.  Because OpenSCAD treats all data the same, most of the functions that
index matrices or construct them will work on matrices (lists of lists) whose elements are not numbers but may be
arbitrary data: strings, booleans, or even other lists.  It may even be acceptable in some cases if the structure is non-rectangular.
Of course, linear algebra computations and solutions require true matrices with rectangular structure, where all the entries are
finite numbers.

Matrices in OpenSCAD are lists of row vectors.  However, a potential source of confusion is that OpenSCAD
treats vectors as either column vectors or row vectors as demanded by
context.  Thus both `v*M` and `M*v` are valid if `M` is square and `v` has the right length.  If you want to multiply
`M` on the left by `v` and `w` you can do this with `[v,w]*M` but if you want to multiply on the right side with `v` and `w` as
column vectors, you now need to use [`transpose()`](#function-transpose) because OpenSCAD doesn't adjust matrices
contextually:  `A=M*transpose([v,w])`.  The solutions are now columns of A and you must extract
them with [`column()`](#function-column) or take the transpose of `A`.

## Section: Matrix testing and display


### Function: is\_matrix()

**Usage:** 

- test = is\_matrix(A, [m], [n], [square])

**Description:** 

Returns true if A is a numeric matrix of height m and width n with finite entries.  If m or n
are omitted or set to undef then true is returned for any positive dimension.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`A`                  | The matrix to test.
`m`                  | If given, requires the matrix to have this height.
`n`                  | Is given, requires the matrix to have this width.
`square`             | If true, matrix must have height equal to width. Default: false

---

### Function: is\_matrix\_symmetric()

**Usage:** 

- b = is\_matrix\_symmetric(A, [eps])

**Description:** 

Returns true if the input matrix is symmetric, meaning it approximately equals its transpose.
The matrix can have arbitrary entries.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`A`                  | matrix to test
`eps`                | epsilon for comparing equality.  Default: 1e-12

---

### Function/Module: echo\_matrix()

**Usage:** 

- echo\_matrix(M, [description], [sig], [sep], [eps]);
- dummy = echo\_matrix(M, [description], [sig], [sep], [eps]),

**Description:** 

Display a numerical matrix in a readable columnar format with `sig` significant
digits.  Values smaller than eps display as zero.  If you give a description
it is displayed at the top.  You can change the space between columns by
setting `sep` to a number of spaces, which will use wide figure spaces the same
width as digits, or you can set it to any string to separate the columns.
Values that are NaN or INF will display as "nan" and "inf".  Values which are
otherwise non-numerica display as two dashes.  Note that this includes lists, so
a 3D array will display as a list of dashes.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`M`                  | matrix to display, which should be numerical
`description`        | optional text to print before the matrix
`sig`                | number of digits to display.  Default: 4
`sep`                | number of spaces between columns or a text string to separate columns.  Default: 1
`eps`                | numbers smaller than this display as zero.  Default: 1e-9

---

## Section: Matrix indexing


### Function: column()

**Usage:** 

- list = column(M, i);

**Topics:** [Matrices](Topics#matrices), [List Handling](Topics#list-handling)

**Description:** 

Extracts entry `i` from each list in M, or equivalently column i from the matrix M, and returns it as a vector.
This function will return `undef` at all entry positions indexed by i not found in M.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`M`                  | The given list of lists.
`i`                  | The index to fetch

**See Also:** [select()](lists.scad#function-select), [slice()](lists.scad#function-slice)

**Example 1:** 

    include <BOSL2/std.scad>
    M = [[1,2,3,4],[5,6,7,8],[9,10,11,12],[13,14,15,16]];
    a = column(M,2);      // Returns [3, 7, 11, 15]
    b = column(M,0);      // Returns [1, 5, 9, 13]
    N = [ [1,2], [3], [4,5], [6,7,8] ];
    c = column(N,1);      // Returns [1,undef,5,7]
    data = [[1,[3,4]], [3, [9,3]], [4, [3,1]]];   // Matrix with non-numeric entries
    d = column(data,0);   // Returns [1,3,4]
    e = column(data,1);   // Returns [[3,4],[9,3],[3,1]]

<br clear="all" /><br/>

---

### Function: submatrix()

**Usage:** 

- mat = submatrix(M, idx1, idx2);

**Topics:** [Matrices](Topics#matrices)

**Description:** 

The input must be a list of lists (a matrix or 2d array).  Returns a submatrix by selecting the rows listed in idx1 and columns listed in idx2.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`M`                  | Given list of lists
`idx1`               | rows index list or range
`idx2`               | column index list or range

**See Also:** [column()](#function-column), [block\_matrix()](#function-block_matrix), [submatrix\_set()](#function-submatrix_set)

**Example 1:** 

    include <BOSL2/std.scad>
    M = [[ 1, 2, 3, 4, 5],
         [ 6, 7, 8, 9,10],
         [11,12,13,14,15],
         [16,17,18,19,20],
         [21,22,23,24,25]];
    submatrix(M,[1:2],[3:4]);  // Returns [[9, 10], [14, 15]]
    submatrix(M,[1], [3,4]));  // Returns [[9,10]]
    submatrix(M,1, [3,4]));  // Returns [[9,10]]
    submatrix(M,1,3));  // Returns [[9]]
    submatrix(M, [3,4],1); // Returns  [[17],[22]]);
    submatrix(M, [1,3],[2,4]); // Returns [[8,10],[18,20]]);
    A = [[true,    17, "test"],
         [[4,2],   91, false],
         [6,    [3,4], undef]];
    submatrix(A,[0,2],[1,2]);   // Returns [[17, "test"], [[3, 4], undef]]

<br clear="all" /><br/>

---

## Section: Matrix construction and modification


### Function: ident()

**Usage:** 

- mat = ident(n);

**Topics:** [Affine](Topics#affine), [Matrices](Topics#matrices)

**Description:** 

Create an `n` by `n` square identity matrix.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`n`                  | The size of the identity matrix square, `n` by `n`.

**Example 1:** 

    include <BOSL2/std.scad>
    mat = ident(3);
    // Returns:
    //   [
    //     [1, 0, 0],
    //     [0, 1, 0],
    //     [0, 0, 1]
    //   ]

<br clear="all" /><br/>

**Example 2:** 

    include <BOSL2/std.scad>
    mat = ident(4);
    // Returns:
    //   [
    //     [1, 0, 0, 0],
    //     [0, 1, 0, 0],
    //     [0, 0, 1, 0],
    //     [0, 0, 0, 1]
    //   ]

<br clear="all" /><br/>

---

### Function: diagonal\_matrix()

**Usage:** 

- mat = diagonal\_matrix(diag, [offdiag]);

**Topics:** [Matrices](Topics#matrices)

**Description:** 

Creates a square matrix with the items in the list `diag` on
its diagonal.  The off diagonal entries are set to offdiag,
which is zero by default.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`diag`               | A list of items to put in the diagnal cells of the matrix.
`offdiag`            | Value to put in non-diagonal matrix cells.

**See Also:** [column()](#function-column), [submatrix()](#function-submatrix)

---

### Function: transpose()

**Usage:** 

- M = transpose(M, [reverse]);

**Topics:** [Matrices](Topics#matrices)

**Description:** 

Returns the transpose of the given input matrix.  The input can be a matrix with arbitrary entries or
a numerical vector.  If you give a vector then transpose returns it unchanged.
When reverse=true, the transpose is done across to the secondary diagonal.  (See example below.)
By default, reverse=false.

**See Also:** [submatrix()](#function-submatrix), [block\_matrix()](#function-block_matrix), [hstack()](#function-hstack), [flatten()](lists.scad#function-flatten)

**Example 1:** 

    include <BOSL2/std.scad>
    M = [
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
    ];
    t = transpose(M);
    // Returns:
    // [
    //     [1, 4, 7],
    //     [2, 5, 8],
    //     [3, 6, 9]
    // ]

<br clear="all" /><br/>

**Example 2:** 

    include <BOSL2/std.scad>
    M = [
        [1, 2, 3],
        [4, 5, 6]
    ];
    t = transpose(M);
    // Returns:
    // [
    //     [1, 4],
    //     [2, 5],
    //     [3, 6],
    // ]

<br clear="all" /><br/>

**Example 3:** 

    include <BOSL2/std.scad>
    M = [
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
    ];
    t = transpose(M, reverse=true);
    // Returns:
    // [
    //  [9, 6, 3],
    //  [8, 5, 2],
    //  [7, 4, 1]
    // ]

<br clear="all" /><br/>

**Example 4:** Transpose on a list of numbers returns the list unchanged

    include <BOSL2/std.scad>
    transpose([3,4,5]);  // Returns: [3,4,5]

<br clear="all" /><br/>

**Example 5:** Transpose on non-numeric input

    include <BOSL2/std.scad>
    arr = [
        [  "a",  "b", "c"],
        [  "d",  "e", "f"],
        [[1,2],[3,4],[5,6]]
    ];
    t = transpose(arr);
    // Returns:
    // [
    //     ["a", "d", [1,2]],
    //     ["b", "e", [3,4]],
    //     ["c", "f", [5,6]],
    // ]

<br clear="all" /><br/>

---

### Function: outer\_product()

**Usage:** 

- x = outer\_product(u,v);

**Usage:** 

- M = outer\_product(u,v);

**Description:** 

Compute the outer product of two vectors, a matrix.

---

### Function: submatrix\_set()

**Usage:** 

- mat = submatrix\_set(M, A, [m], [n]);

**Topics:** [Matrices](Topics#matrices)

**Description:** 

Sets a submatrix of M equal to the matrix A.  By default the top left corner of M is set to A, but
you can specify offset coordinates m and n.  If A (as adjusted by m and n) extends beyond the bounds
of M then the extra entries are ignored.  You can pass in A=[[]], a null matrix, and M will be
returned unchanged.  This function works on arbitrary lists of lists and the input M need not be rectangular in shape.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`M`                  | Original matrix.
`A`                  | Submatrix of new values to write into M
`m`                  | Row number of upper-left corner to place A at.  Default: 0
`n`                  | Column number of upper-left corner to place A at.  Default: 0

**See Also:** [column()](#function-column), [submatrix()](#function-submatrix)

---

### Function: hstack()

**Usage:** 

- A = hstack(M1, M2)
- A = hstack(M1, M2, M3)
- A = hstack([M1, M2, M3, ...])

**Topics:** [Matrices](Topics#matrices)

**Description:** 

Constructs a matrix by horizontally "stacking" together compatible matrices or vectors.  Vectors are treated as columsn in the stack.
This command is the inverse of `column`.  Note: strings given in vectors are broken apart into lists of characters.  Strings given
in matrices are preserved as strings.  If you need to combine vectors of strings use [`list_to_matrix()`](lists.scad#function-list_to_matrix) as shown below to convert the
vector into a column matrix.  Also note that vertical stacking can be done directly with concat.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`M1`                 | If given with other arguments, the first matrix (or vector) to stack.  If given alone, a list of matrices/vectors to stack.
`M2`                 | Second matrix/vector to stack
`M3`                 | Third matrix/vector to stack.

**See Also:** [column()](#function-column), [submatrix()](#function-submatrix), [block\_matrix()](#function-block_matrix)

**Example 1:** 

    include <BOSL2/std.scad>
    M = ident(3);
    v1 = [2,3,4];
    v2 = [5,6,7];
    v3 = [8,9,10];
    a = hstack(v1,v2);     // Returns [[2, 5], [3, 6], [4, 7]]
    b = hstack(v1,v2,v3);  // Returns [[2, 5,  8],
                           //          [3, 6,  9],
                           //          [4, 7, 10]]
    c = hstack([M,v1,M]);  // Returns [[1, 0, 0, 2, 1, 0, 0],
                           //          [0, 1, 0, 3, 0, 1, 0],
                           //          [0, 0, 1, 4, 0, 0, 1]]
    d = hstack(column(M,0), submatrix(M,idx(M),[1 2]));  // Returns M
    strvec = ["one","two"];
    strmat = [["three","four"], ["five","six"]];
    e = hstack(strvec,strvec); // Returns [["o", "n", "e", "o", "n", "e"],
                               //          ["t", "w", "o", "t", "w", "o"]]
    f = hstack(list_to_matrix(strvec,1), list_to_matrix(strvec,1));
                               // Returns [["one", "one"],
                               //          ["two", "two"]]
    g = hstack(strmat,strmat); //  Returns: [["three", "four", "three", "four"],
                               //            [ "five",  "six",  "five",  "six"]]

<br clear="all" /><br/>

---

### Function: block\_matrix()

**Usage:** 

- bmat = block\_matrix([[M11, M12,...],[M21, M22,...], ... ]);

**Topics:** [Matrices](Topics#matrices)

**Description:** 

Create a block matrix by supplying a matrix of matrices, which will
be combined into one unified matrix.  Every matrix in one row
must have the same height, and the combined width of the matrices
in each row must be equal. Strings will stay strings.

**See Also:** [column()](#function-column), [submatrix()](#function-submatrix)

**Example 1:** 

    include <BOSL2/std.scad>
    A = [[1,2],
         [3,4]];
    B = ident(2);
    C = block_matrix([[A,B],[B,A],[A,B]]);
        // Returns:
        //        [[1, 2, 1, 0],
        //         [3, 4, 0, 1],
        //         [1, 0, 1, 2],
        //         [0, 1, 3, 4],
        //         [1, 2, 1, 0],
        //         [3, 4, 0, 1]]);
    D = block_matrix([[A,B], ident(4)]);
        // Returns:
        //        [[1, 2, 1, 0],
        //         [3, 4, 0, 1],
        //         [1, 0, 0, 0],
        //         [0, 1, 0, 0],
        //         [0, 0, 1, 0],
        //         [0, 0, 0, 1]]);
    E = [["one", "two"], [3,4]];
    F = block_matrix([[E,E]]);
        // Returns:
        //        [["one", "two", "one", "two"],
        //         [    3,     4,     3,     4]]

<br clear="all" /><br/>

---

## Section: Solving Linear Equations and Matrix Factorizations


### Function: linear\_solve()

**Usage:** 

- solv = linear\_solve(A,b,[pivot])

**Usage:** 

- A = Matrix describing the linear system, which need not be square
- b = right hand side for linear system, which can be a matrix to solve several cases simultaneously.  Must be consistent with A.
- pivot = if true use pivoting when computing the QR factorization.  Default: true

**Description:** 

Solves the linear system Ax=b.  If `A` is square and non-singular the unique solution is returned.  If `A` is overdetermined
the least squares solution is returned. If `A` is underdetermined, the minimal norm solution is returned.
If `A` is rank deficient or singular then linear_solve returns `[]`.  If `b` is a matrix that is compatible with `A`
then the problem is solved for the matrix valued right hand side and a matrix is returned.  Note that if you
want to solve Ax=b1 and Ax=b2 that you need to form the matrix `transpose([b1,b2])` for the right hand side and then
transpose the returned value.  The solution is computed using QR factorization.  If `pivot` is set to true (the default) then
pivoting is used in the QR factorization, which is slower but expected to be more accurate.

---

### Function: linear\_solve3()

**Usage:** 

- x = linear\_solve3(A,b)

**Description:** 

Fast solution to a 3x3 linear system using Cramer's rule (which appears to be the fastest
method in OpenSCAD).  The input `A` must be a 3x3 matrix.  Returns undef if `A` is singular.
The input `b` must be a 3-vector.  Note that Cramer's rule is not a stable algorithm, so for
the highest accuracy on ill-conditioned problems you may want to use the general solver, which is about ten times slower.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`A`                  | 3x3 matrix for linear system
`b`                  | length 3 vector, right hand side of linear system

---

### Function: matrix\_inverse()

**Usage:** 

- mat = matrix\_inverse(A)

**Description:** 

Compute the matrix inverse of the square matrix `A`.  If `A` is singular, returns `undef`.
Note that if you just want to solve a linear system of equations you should NOT use this function.
Instead use {{linear_solve()}}, or use [`qr_factor()`](#function-qr_factor).  The computation
will be faster and more accurate.

---

### Function: rot\_inverse()

**Usage:** 

- B = rot\_inverse(A)

**Description:** 

Inverts a 2d (3x3) or 3d (4x4) rotation matrix.  The matrix can be a rotation around any center,
so it may include a translation.  This is faster and likely to be more accurate than using `matrix_inverse()`.

---

### Function: null\_space()

**Usage:** 

- x = null\_space(A)

**Description:** 

Returns an orthonormal basis for the null space of `A`, namely the vectors {x} such that Ax=0.
If the null space is just the origin then returns an empty list.

---

### Function: qr\_factor()

**Usage:** 

- qr = qr\_factor(A,[pivot]);

**Description:** 

Calculates the QR factorization of the input matrix A and returns it as the list [Q,R,P].  This factorization can be
used to solve linear systems of equations.  The factorization is `A = Q*R*transpose(P)`.  If pivot is false (the default)
then P is the identity matrix and A = Q*R.  If pivot is true then column pivoting results in an R matrix where the diagonal
is non-decreasing.  The use of pivoting is supposed to increase accuracy for poorly conditioned problems, and is necessary
for rank estimation or computation of the null space, but it may be slower.

---

### Function: back\_substitute()

**Usage:** 

- x = back\_substitute(R, b, [transpose]);

**Description:** 

Solves the problem Rx=b where R is an upper triangular square matrix.  The lower triangular entries of R are
ignored.  If transpose==true then instead solve transpose(R)*x=b.
You can supply a compatible matrix b and it will produce the solution for every column of b.  Note that if you want to
solve Rx=b1 and Rx=b2 you must set b to transpose([b1,b2]) and then take the transpose of the result.  If the matrix
is singular (e.g. has a zero on the diagonal) then it returns [].

---

### Function: cholesky()

**Usage:** 

- L = cholesky(A);

**Description:** 

Compute the cholesky factor, L, of the symmetric positive definite matrix A.
The matrix L is lower triangular and `L * transpose(L) = A`.  If the A is
not symmetric then an error is displayed.  If the matrix is symmetric but
not positive definite then undef is returned.

---

## Section: Matrix Properties: Determinants, Norm, Trace


### Function: det2()

**Usage:** 

- d = det2(M);

**Description:** 

Rturns the determinant for the given 2x2 matrix.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`M`                  | The 2x2 matrix to get the determinant of.

**Example 1:** 

    include <BOSL2/std.scad>
    M = [ [6,-2], [1,8] ];
    det = det2(M);  // Returns: 50

<br clear="all" /><br/>

---

### Function: det3()

**Usage:** 

- d = det3(M);

**Description:** 

Returns the determinant for the given 3x3 matrix.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`M`                  | The 3x3 square matrix to get the determinant of.

**Example 1:** 

    include <BOSL2/std.scad>
    M = [ [6,4,-2], [1,-2,8], [1,5,7] ];
    det = det3(M);  // Returns: -334

<br clear="all" /><br/>

---

### Function: det4()

**Usage:** 

- d = det4(M);

**Description:** 

Returns the determinant for the given 4x4 matrix.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`M`                  | The 4x4 square matrix to get the determinant of.

**Example 1:** 

    include <BOSL2/std.scad>
    M = [ [6,4,-2,1], [1,-2,8,-3], [1,5,7,4], [2,3,4,7] ];
    det = det4(M);  // Returns: -1773

<br clear="all" /><br/>

---

### Function: determinant()

**Usage:** 

- d = determinant(M);

**Description:** 

Returns the determinant for the given square matrix.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`M`                  | The NxN square matrix to get the determinant of.

**Example 1:** 

    include <BOSL2/std.scad>
    M = [ [6,4,-2,9], [1,-2,8,3], [1,5,7,6], [4,2,5,1] ];
    det = determinant(M);  // Returns: 2267

<br clear="all" /><br/>

---

### Function: norm\_fro()

**Usage:** 

- norm\_fro(A)

**Description:** 

Computes frobenius norm of input matrix.  The frobenius norm is the square root of the sum of the
squares of all of the entries of the matrix.  On vectors it is the same as the usual 2-norm.
This is an easily computed norm that is convenient for comparing two matrices.

---

### Function: matrix\_trace()

**Usage:** 

- matrix\_trace(M)

**Description:** 

Computes the trace of a square matrix, the sum of the entries on the diagonal.

---

