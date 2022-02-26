# LibFile: vectors.scad

This file provides some mathematical operations that apply to each
entry in a vector.  It provides normalizatoin and angle computation, and
it provides functions for searching lists of vectors for matches to
a given vector.

To use, add the following lines to the beginning of your file:

    include <BOSL2/std.scad>

## Table of Contents

1. [Section: Vector Testing](#section-vector-testing)
    - [`is_vector()`](#function-is_vector)

2. [Section: Scalar operations on vectors](#section-scalar-operations-on-vectors)
    - [`add_scalar()`](#function-add_scalar)
    - [`v_mul()`](#function-v_mul)
    - [`v_div()`](#function-v_div)
    - [`v_abs()`](#function-v_abs)
    - [`v_floor()`](#function-v_floor)
    - [`v_ceil()`](#function-v_ceil)
    - [`v_lookup()`](#function-v_lookup)

3. [Section: Vector Properties](#section-vector-properties)
    - [`unit()`](#function-unit)
    - [`v_theta()`](#function-v_theta)
    - [`vector_angle()`](#function-vector_angle)
    - [`vector_axis()`](#function-vector_axis)

4. [Section: Vector Searching](#section-vector-searching)
    - [`pointlist_bounds()`](#function-pointlist_bounds)
    - [`closest_point()`](#function-closest_point)
    - [`furthest_point()`](#function-furthest_point)
    - [`vector_search()`](#function-vector_search)
    - [`vector_search_tree()`](#function-vector_search_tree)
    - [`vector_nearest()`](#function-vector_nearest)


## Section: Vector Testing


### Function: is\_vector()

**Usage:** 

- is\_vector(v, [length], ...);

**Description:** 

Returns true if v is a list of finite numbers.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`v`                  | The value to test to see if it is a vector.
`length`             | If given, make sure the vector is `length` items long.
`zero`               | If false, require that the length/`norm()` of the vector is not approximately zero.  If true, require the length/`norm()` of the vector to be approximately zero-length.  Default: `undef` (don't check vector length/`norm()`.)
`all_nonzero`        | If true, requires all elements of the vector to be more than `eps` different from zero.  Default: `false`
`eps`                | The minimum vector length that is considered non-zero.  Default: `EPSILON` (`1e-9`)

**Example 1:** 

    include <BOSL2/std.scad>
    is_vector(4);                          // Returns false
    is_vector([4,true,false]);             // Returns false
    is_vector([3,4,INF,5]);                // Returns false
    is_vector([3,4,5,6]);                  // Returns true
    is_vector([3,4,undef,5]);              // Returns false
    is_vector([3,4,5],3);                  // Returns true
    is_vector([3,4,5],4);                  // Returns true
    is_vector([]);                         // Returns false
    is_vector([0,4,0],3,zero=false);       // Returns true
    is_vector([0,0,0],zero=false);         // Returns false
    is_vector([0,0,1e-12],zero=false);     // Returns false
    is_vector([0,1,0],all_nonzero=false);  // Returns false
    is_vector([1,1,1],all_nonzero=false);  // Returns true
    is_vector([],zero=false);              // Returns false

<br clear="all" /><br/>

---

## Section: Scalar operations on vectors


### Function: add\_scalar()

**Usage:** 

- v\_new = add\_scalar(v, s);

**Topics:** [List Handling](Topics#list-handling)

**Description:** 

Given a vector and a scalar, returns the vector with the scalar added to each item in it.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`v`                  | The initial array.
`s`                  | A scalar value to add to every item in the array.

**Example 1:** 

    include <BOSL2/std.scad>
    a = add_scalar([1,2,3],3);            // Returns: [4,5,6]

<br clear="all" /><br/>

---

### Function: v\_mul()

**Usage:** 

- v3 = v\_mul(v1, v2);

**Description:** 

Element-wise multiplication.  Multiplies each element of `v1` by the corresponding element of `v2`.
Both `v1` and `v2` must be the same length.  Returns a vector of the products.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`v1`                 | The first vector.
`v2`                 | The second vector.

**Example 1:** 

    include <BOSL2/std.scad>
    v_mul([3,4,5], [8,7,6]);  // Returns [24, 28, 30]

<br clear="all" /><br/>

---

### Function: v\_div()

**Usage:** 

- v3 = v\_div(v1, v2);

**Description:** 

Element-wise vector division.  Divides each element of vector `v1` by
the corresponding element of vector `v2`.  Returns a vector of the quotients.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`v1`                 | The first vector.
`v2`                 | The second vector.

**Example 1:** 

    include <BOSL2/std.scad>
    v_div([24,28,30], [8,7,6]);  // Returns [3, 4, 5]

<br clear="all" /><br/>

---

### Function: v\_abs()

**Usage:** 

- v2 = v\_abs(v);

**Description:** 

Returns a vector of the absolute value of each element of vector `v`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`v`                  | The vector to get the absolute values of.

**Example 1:** 

    include <BOSL2/std.scad>
    v_abs([-1,3,-9]);  // Returns: [1,3,9]

<br clear="all" /><br/>

---

### Function: v\_floor()

**Usage:** 

- v2 = v\_floor(v);

**Description:** 

Returns the given vector after performing a `floor()` on all items.

---

### Function: v\_ceil()

**Usage:** 

- v2 = v\_ceil(v);

**Description:** 

Returns the given vector after performing a `ceil()` on all items.

---

### Function: v\_lookup()

**Usage:** 

- v2 = v\_ceil(x, v);

**Description:** 

Works just like the built-in function [`lookup()`](https://en.wikibooks.org/wiki/OpenSCAD_User_Manual/Mathematical_Functions#lookup), except that it can also interpolate between vector result values of the same length.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`x`                  | The scalar value to look up.
`v`                  | A list of [KEY,VAL] pairs. KEYs are scalars.  VALs should either all be scalar, or all be vectors of the same length.

**Example 1:** 

    include <BOSL2/std.scad>
    x = v_lookup(4.5, [[4, [3,4,5]], [5, [5,6,7]]]);  // Returns: [4,5,6]

<br clear="all" /><br/>

---

## Section: Vector Properties


### Function: unit()

**Usage:** 

- v = unit(v, [error]);

**Description:** 

Returns the unit length normalized version of vector v.  If passed a zero-length vector,
asserts an error unless `error` is given, in which case the value of `error` is returned.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`v`                  | The vector to normalize.
`error`              | If given, and input is a zero-length vector, this value is returned.  Default: Assert error on zero-length vector.

**Example 1:** 

    include <BOSL2/std.scad>
    v1 = unit([10,0,0]);   // Returns: [1,0,0]
    v2 = unit([0,10,0]);   // Returns: [0,1,0]
    v3 = unit([0,0,10]);   // Returns: [0,0,1]
    v4 = unit([0,-10,0]);  // Returns: [0,-1,0]
    v5 = unit([0,0,0],[1,2,3]);    // Returns: [1,2,3]
    v6 = unit([0,0,0]);    // Asserts an error.

<br clear="all" /><br/>

---

### Function: v\_theta()

**Usage:** 

- theta = v\_theta([X,Y]);

**Description:** 

Given a vector, returns the angle in degrees counter-clockwise from X+ on the XY plane.

---

### Function: vector\_angle()

**Usage:** 

- ang = vector\_angle(v1,v2);
- ang = vector\_angle([v1,v2]);
- ang = vector\_angle(PT1,PT2,PT3);
- ang = vector\_angle([PT1,PT2,PT3]);

**Description:** 

If given a single list of two vectors, like `vector_angle([V1,V2])`, returns the angle between the two vectors V1 and V2.
If given a single list of three points, like `vector_angle([A,B,C])`, returns the angle between the line segments AB and BC.
If given two vectors, like `vector_angle(V1,V2)`, returns the angle between the two vectors V1 and V2.
If given three points, like `vector_angle(A,B,C)`, returns the angle between the line segments AB and BC.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`v1`                 | First vector or point.
`v2`                 | Second vector or point.
`v3`                 | Third point in three point mode.

**Example 1:** 

    include <BOSL2/std.scad>
    ang1 = vector_angle(UP,LEFT);     // Returns: 90
    ang2 = vector_angle(RIGHT,LEFT);  // Returns: 180
    ang3 = vector_angle(UP+RIGHT,RIGHT);  // Returns: 45
    ang4 = vector_angle([10,10], [0,0], [10,-10]);  // Returns: 90
    ang5 = vector_angle([10,0,10], [0,0,0], [-10,10,0]);  // Returns: 120
    ang6 = vector_angle([[10,0,10], [0,0,0], [-10,10,0]]);  // Returns: 120

<br clear="all" /><br/>

---

### Function: vector\_axis()

**Usage:** 

- axis = vector\_axis(v1,v2);
- axis = vector\_axis([v1,v2]);
- axis = vector\_axis(PT1,PT2,PT3);
- axis = vector\_axis([PT1,PT2,PT3]);

**Description:** 

If given a single list of two vectors, like `vector_axis([V1,V2])`, returns the vector perpendicular the two vectors V1 and V2.
If given a single list of three points, like `vector_axis([A,B,C])`, returns the vector perpendicular to the plane through a, B and C.
If given two vectors, like `vector_axis(V1,V2)`, returns the vector perpendicular to the two vectors V1 and V2.
If given three points, like `vector_axis(A,B,C)`, returns the vector perpendicular to the plane through a, B and C.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`v1`                 | First vector or point.
`v2`                 | Second vector or point.
`v3`                 | Third point in three point mode.

**Example 1:** 

    include <BOSL2/std.scad>
    axis1 = vector_axis(UP,LEFT);     // Returns: [0,-1,0] (FWD)
    axis2 = vector_axis(RIGHT,LEFT);  // Returns: [0,-1,0] (FWD)
    axis3 = vector_axis(UP+RIGHT,RIGHT);  // Returns: [0,1,0] (BACK)
    axis4 = vector_axis([10,10], [0,0], [10,-10]);  // Returns: [0,0,-1] (DOWN)
    axis5 = vector_axis([10,0,10], [0,0,0], [-10,10,0]);  // Returns: [-0.57735, -0.57735, 0.57735]
    axis6 = vector_axis([[10,0,10], [0,0,0], [-10,10,0]]);  // Returns: [-0.57735, -0.57735, 0.57735]

<br clear="all" /><br/>

---

## Section: Vector Searching


### Function: pointlist\_bounds()

**Usage:** 

- pt\_pair = pointlist\_bounds(pts);

**Topics:** [Geometry](Topics#geometry), [Bounding Boxes](Topics#bounding-boxes), [Bounds](Topics#bounds)

**Description:** 

Finds the bounds containing all the points in `pts` which can be a list of points in any dimension.
Returns a list of two items: a list of the minimums and a list of the maximums.  For example, with
3d points `[[MINX, MINY, MINZ], [MAXX, MAXY, MAXZ]]`

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`pts`                | List of points.

---

### Function: closest\_point()

**Usage:** 

- index = closest\_point(pt, points);

**Topics:** [Geometry](Topics#geometry), [Points](Topics#points), [Distance](Topics#distance)

**Description:** 

Given a list of `points`, finds the index of the closest point to `pt`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`pt`                 | The point to find the closest point to.
`points`             | The list of points to search.

---

### Function: furthest\_point()

**Usage:** 

- index = furthest\_point(pt, points);

**Topics:** [Geometry](Topics#geometry), [Points](Topics#points), [Distance](Topics#distance)

**Description:** 

Given a list of `points`, finds the index of the furthest point from `pt`.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`pt`                 | The point to find the farthest point from.
`points`             | The list of points to search.

---

### Function: vector\_search()

**Usage:** 

- indices = vector\_search(query, r, target);

**Topics:** [Search](Topics#search), [Points](Topics#points), [Closest](Topics#closest)

**Description:** 

Given a list of query points `query` and a `target` to search,
finds the points in `target` that match each query point. A match holds when the
distance between a point in `target` and a query point is less than or equal to `r`.
The returned list will have a list for each query point containing, in arbitrary
order, the indices of all points that match that query point.
The `target` may be a simple list of points or a search tree.
When `target` is a large list of points, a search tree is constructed to
speed up the search with an order around O(log n) per query point.
For small point lists, a direct search is done dispensing a tree construction.
Alternatively, `target` may be a search tree built with `vector_search_tree()`.
In that case, that tree is parsed looking for matches.
An empty list of query points will return a empty output list.
An empty list of target points will return a output list with an empty list for each query point.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`query`              | list of points to find matches for.
`r`                  | the search radius.
`target`             | list of the points to search for matches or a search tree.

**See Also:** [vector\_search\_tree()](#function-vector_search_tree), [vector\_nearest()](#function-vector_nearest)

**Example 1:** A set of four queries to find points within 1 unit of the query.  The circles show the search region and all have radius 1.

    include <BOSL2/std.scad>
    $fn=32;
    k = 2000;
    points = list_to_matrix(rands(0,10,k*2,seed=13333),2);
    queries = [for(i=[3,7],j=[3,7]) [i,j]];
    search_ind = vector_search(queries, points, 1);
    move_copies(points) circle(r=.08);
    for(i=idx(queries)){
        color("blue")stroke(move(queries[i],circle(r=1)), closed=true, width=.08);
        color("red") move_copies(select(points, search_ind[i])) circle(r=.08);
    }

<br clear="all" /><br/>

**Example 2:** when a series of search with different radius are needed, its is faster to pre-compute the tree

    include <BOSL2/std.scad>
    $fn=32;
    k = 2000;
    points = list_to_matrix(rands(0,10,k*2),2,seed=13333);
    queries1 = [for(i=[3,7]) [i,i]];
    queries2 = [for(i=[3,7]) [10-i,i]];
    r1 = 1;
    r2 = .7;
    search_tree = vector_search_tree(points);
    search_1 = vector_search(queries1, r1, search_tree);
    search_2 = vector_search(queries2, r2, search_tree);
    move_copies(points) circle(r=.08);
    for(i=idx(queries1)){
        color("blue")stroke(move(queries1[i],circle(r=r1)), closed=true, width=.08);
        color("red") move_copies(select(points, search_1[i])) circle(r=.08);
    }
    for(i=idx(queries2)){
        color("green")stroke(move(queries2[i],circle(r=r2)), closed=true, width=.08);
        color("red") move_copies(select(points, search_2[i])) circle(r=.08);
    }

<br clear="all" /><br/>

---

### Function: vector\_search\_tree()

**Usage:** 

- tree = vector\_search\_tree(points,leafsize);

**Topics:** [Search](Topics#search), [Points](Topics#points), [Closest](Topics#closest)

**Description:** 

Construct a search tree for the given list of points to be used as input
to the function `vector_search()`. The use of a tree speeds up the
search process. The tree construction stops branching when
a tree node represents a number of points less or equal to `leafsize`.
Search trees are ball trees. Constructing the
tree should be O(n log n) and searches should be O(log n), though real life
performance depends on how the data is distributed, and it will deteriorate
for high data dimensions.  This data structure is useful when you will be
performing many searches of the same data, so that the cost of constructing
the tree is justified. (See https://en.wikipedia.org/wiki/Ball_tree)
For a small lists of points, the search with a tree may be more expensive
than direct comparisons. The argument `treemin` sets the minimum length of
point set for which a tree search will be done by `vector_search`.
For an empty list of points it returns an empty list.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`points`             | list of points to store in the search tree.
`leafsize`           | the size of the tree leaves. Default: 25
`treemin`            | the minimum size of the point list for which a tree search is done. Default: 400

**See Also:** [vector\_nearest()](#function-vector_nearest), [vector\_search()](#function-vector_search)

**Example 1:** A set of four queries to find points within 1 unit of the query.  The circles show the search region and all have radius 1.

    include <BOSL2/std.scad>
    $fn=32;
    k = 2000;
    points = random_points(k, scale=10, dim=2,seed=13333);
    queries = [for(i=[3,7],j=[3,7]) [i,j]];
    search_tree = vector_search_tree(points);
    search_ind = vector_search(queries,1,search_tree);
    move_copies(points) circle(r=.08);
    for(i=idx(queries)){
        color("blue") stroke(move(queries[i],circle(r=1)), closed=true, width=.08);
        color("red")  move_copies(select(points, search_ind[i])) circle(r=.08);
    }

<br clear="all" /><br/>

---

### Function: vector\_nearest()

**Usage:** 

- indices = vector\_nearest(query, k, target);

**Description:** 

Search `target` for the `k` points closest to point `query`.
The input `target` is either a list of points to search or a search tree
pre-computed by `vector_search_tree(). A list is returned containing the indices
of the points found in sorted order, closest point first.

**Arguments:** 

<abbr title="These args can be used by position or by name.">By&nbsp;Position</abbr> | What it does
-------------------- | ------------
`query`              | point to search for
`k`                  | number of neighbors to return
`target`             | a list of points or a search tree to search in

**See Also:** [vector\_search()](#function-vector_search), [vector\_search\_tree()](#function-vector_search_tree)

**Example 1:** Four queries to find the 15 nearest points.  The circles show the radius defined by the most distant query result.  Note they are different for each query.

    include <BOSL2/std.scad>
    $fn=32;
    k = 1000;
    points = list_to_matrix(rands(0,10,k*2,seed=13333),2);
    tree = vector_search_tree(points);
    queries = [for(i=[3,7],j=[3,7]) [i,j]];
    search_ind = [for(q=queries) vector_nearest(q, 15, tree)];
    move_copies(points) circle(r=.08);
    for(i=idx(queries)){
        circle = circle(r=norm(points[last(search_ind[i])]-queries[i]));
        color("red")  move_copies(select(points, search_ind[i])) circle(r=.08);
        color("blue") stroke(move(queries[i], circle), closed=true, width=.08);
    }

<br clear="all" /><br/>

---

