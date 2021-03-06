# Paths, Polygons and Regions Tutorial

<!-- TOC -->

## Paths
A number of advanced features in BOSL2 rely on paths, which are just ordered lists of points.

First-off, some terminology:
- A 2D point is a vector of X and Y axis position values.  ie: `[3,4]` or `[7,-3]`.
- A 3D point is a vector of X, Y and Z axis position values.  ie: `[3,4,2]` or `[-7,5,3]`.
- A 2D path is simply a list of two or more 2D points.  ie: `[[5,7], [1,-5], [-5,6]]`
- A 3D path is simply a list of two or more 3D points.  ie: `[[5,7,-1], [1,-5,3], [-5,6,1]]`
- A polygon is a 2D (or planar 3D) path where the last point is assumed to connect to the first point.
- A region is a list of 2D polygons, where each polygon is XORed against all the others.  ie: if one polygon is inside another, it makes a hole in the first polygon.

### Stroke
A path can be hard to visualize, since it's just a bunch of numbers in the source code.
One way to see the path is to pass it to `polygon()`:

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
polygon(path);
```
![Figure 1](images/tutorials/Paths_1.png)

Sometimes, however, it's easier to see just the path itself.  For this, you can use the `stroke()` module.
At its most basic, `stroke()` just shows the path's line segments:

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path);
```
![Figure 2](images/tutorials/Paths_2.png)

You can vary the width of the drawn path with the `width=` argument:

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path, width=3);
```
![Figure 3](images/tutorials/Paths_3.png)

You can vary the line length along the path by giving a list of widths, one per point:

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path, width=[3,2,1,2,3]);
```
![Figure 4](images/tutorials/Paths_4.png)

If a path is meant to represent a closed polygon, you can use `closed=true` to show it that way:

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path, closed=true);
```
![Figure 5](images/tutorials/Paths_5.png)

The ends of the drawn path are normally capped with a "round" endcap, but there are other options:

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path, endcaps="round");
```
![Figure 6](images/tutorials/Paths_6.png)

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path, endcaps="butt");
```
![Figure 7](images/tutorials/Paths_7.png)

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path, endcaps="line");
```
![Figure 8](images/tutorials/Paths_8.png)

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path, endcaps="tail");
```
![Figure 9](images/tutorials/Paths_9.png)

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path, endcaps="arrow2");
```
![Figure 10](images/tutorials/Paths_10.png)

For more standard supported endcap options, see the docs for [`stroke()`](shapes2d.scad#stroke).

The start and ending endcaps can be specified individually or separately, using `endcap1=` and `endcap2=`:

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path, endcap2="arrow2");
```
![Figure 11](images/tutorials/Paths_11.png)

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path, endcap1="butt", endcap2="arrow2");
```
![Figure 12](images/tutorials/Paths_12.png)

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
stroke(path, endcap1="tail", endcap2="arrow");
```
![Figure 13](images/tutorials/Paths_13.png)

The size of the endcaps will be relative to the width of the line where the endcap is to be placed:

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
widths = [1, 1.25, 1.5, 1.75, 2];
stroke(path, width=widths, endcaps="arrow2");
```
![Figure 14](images/tutorials/Paths_14.png)

If none of the standard endcaps are useful to you, it is possible to design your own, simply by
passing a path to the `endcaps=`, `endcap1=`, or `endcap2=` arguments.  You may also need to give
`trim=` to tell it how far back to trim the main line, so it renders nicely.  The values in the
endcap polygon, and in the `trim=` argument are relative to the line width.  A value of 1 is one
line width size.

Untrimmed:

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
dblarrow = [[0,0], [2,-3], [0.5,-2.3], [2,-4], [0.5,-3.5], [-0.5,-3.5], [-2,-4], [-0.5,-2.3], [-2,-3]];
stroke(path, endcaps=dblarrow);
```
![Figure 15](images/tutorials/Paths_15.png)

Trimmed:

```openscad
include <BOSL2/std.scad>
path = [[0,0], [-10,10], [0,20], [10,20], [10,10]];
dblarrow = [[0,0], [2,-3], [0.5,-2.3], [2,-4], [0.5,-3.5], [-0.5,-3.5], [-2,-4], [-0.5,-2.3], [-2,-3]];
stroke(path, trim=3.5, endcaps=dblarrow);
```
![Figure 16](images/tutorials/Paths_16.png)

### Standard 2D Shape Polygons
BOSL2 will let you get the perimeter polygon for almost all of the standard 2D shapes simply by calling them like a function:

```openscad
include <BOSL2/std.scad>
path = square(40, center=true);
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 17](images/tutorials/Paths_17.png)

```openscad
include <BOSL2/std.scad>
path = rect([40,30], rounding=5);
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 18](images/tutorials/Paths_18.png)

```openscad
include <BOSL2/std.scad>
path = trapezoid(w1=40, w2=20, h=30);
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 19](images/tutorials/Paths_19.png)

```openscad
include <BOSL2/std.scad>
path = circle(d=50);
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 20](images/tutorials/Paths_20.png)

```openscad
include <BOSL2/std.scad>
path = ellipse(d=[50,30]);
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 21](images/tutorials/Paths_21.png)

```openscad
include <BOSL2/std.scad>
path = pentagon(d=50);
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 22](images/tutorials/Paths_22.png)

```openscad
include <BOSL2/std.scad>
path = star(n=5, step=2, d=50);
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 23](images/tutorials/Paths_23.png)

### Arcs
Often, when you are constructing a path, you will want to add an arc.  The `arc()` command lets you do that:

```openscad
include <BOSL2/std.scad>
path = arc(r=30, angle=120);
stroke(path, endcap2="arrow2");
```
![Figure 24](images/tutorials/Paths_24.png)

```openscad
include <BOSL2/std.scad>
path = arc(d=60, angle=120);
stroke(path, endcap2="arrow2");
```
![Figure 25](images/tutorials/Paths_25.png)

If you give the `N=` argument, you can control exactly how many points the arc is divided into:

```openscad
include <BOSL2/std.scad>
path = arc(N=5, r=30, angle=120);
stroke(path, endcap2="arrow2");
```
![Figure 26](images/tutorials/Paths_26.png)

With the `start=` argument, you can start the arc somewhere other than the X+ axis:

```openscad
include <BOSL2/std.scad>
path = arc(start=45, r=30, angle=120);
stroke(path, endcap2="arrow2");
```
![Figure 27](images/tutorials/Paths_27.png)

Alternatively, you can give starting and ending angles in a list in the `angle=` argument:

```openscad
include <BOSL2/std.scad>
path = arc(angle=[120,45], r=30);
stroke(path, endcap2="arrow2");
```
![Figure 28](images/tutorials/Paths_28.png)

The `cp=` argument lets you center the arc somewhere other than the origin:

```openscad
include <BOSL2/std.scad>
path = arc(cp=[10,0], r=30, angle=120);
stroke(path, endcap2="arrow2");
```
![Figure 29](images/tutorials/Paths_29.png)

The arc can also be given by three points on the arc:

```openscad
include <BOSL2/std.scad>
pts = [[-15,10],[0,20],[35,-5]];
path = arc(points=pts);
stroke(path, endcap2="arrow2");
```
![Figure 30](images/tutorials/Paths_30.png)


### Turtle Graphics
Another way you can create a path is using the `turtle()` command.  It implements a simple path
description language that is similar to LOGO Turtle Graphics. The concept is that you have a virtial
turtle or cursor walking a path.  It can "move" forward or backward, or turn "left" or "right" in
place:

```openscad
include <BOSL2/std.scad>
path = turtle([
    "move", 10,
    "left", 90,
    "move", 20,
    "left", 135,
    "move", 10*sqrt(2),
    "right", 90,
    "move", 10*sqrt(2),
    "left", 135,
    "move", 20
]);
stroke(path, endcap2="arrow2");
```
![Figure 31](images/tutorials/Paths_31.png)

The position and the facing of the turtle/cursor updates after each command.  The motion and turning
commands can also have default distances or angles given:

```openscad
include <BOSL2/std.scad>
path = turtle([
    "angle",360/6,
    "length",10,
    "move","turn",
    "move","turn",
    "move","turn",
    "move","turn",
    "move"
]);
stroke(path, endcap2="arrow2");
```
![Figure 32](images/tutorials/Paths_32.png)

You can use "scale" to relatively scale up the default motion length:

```openscad
include <BOSL2/std.scad>
path = turtle([
    "angle",360/6,
    "length",10,
    "move","turn",
    "move","turn",
    "scale",2,
    "move","turn",
    "move","turn",
    "scale",0.5,
    "move"
]);
stroke(path, endcap2="arrow2");
```
![Figure 33](images/tutorials/Paths_33.png)

Sequences of commands can be repeated using the "repeat" command:

```openscad
include <BOSL2/std.scad>
path=turtle([
    "angle",360/5,
    "length",10,
    "repeat",5,["move","turn"]
]);
stroke(path, endcap2="arrow2");
```
![Figure 34](images/tutorials/Paths_34.png)

More complicated commands also exist, including those that form arcs:

```openscad
include <BOSL2/std.scad>
path = turtle([
    "move", 10,
    "left", 90,
    "move", 20,
    "arcleft", 10, 180,
    "move", 20
]);
stroke(path, endcap2="arrow2");
```
![Figure 35](images/tutorials/Paths_35.png)

A comprehensive list of supported turtle commands can be found in the docs for [`turtle()`](shapes2d.scad#turtle).

### Transforming Paths and Polygons
To translate a path, you can just pass it to the `move()` (or up/down/left/right/fwd/back) function in the `p=` argument:

```openscad
include <BOSL2/std.scad>
path = move([-15,-30], p=square(50,center=true));
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 36](images/tutorials/Paths_36.png)

```openscad
include <BOSL2/std.scad>
path = fwd(30, p=square(50,center=true));
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 37](images/tutorials/Paths_37.png)

```openscad
include <BOSL2/std.scad>
path = left(30, p=square(50,center=true));
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 38](images/tutorials/Paths_38.png)

To scale a path, you can just pass it to the `scale()` (or [xyz]scale) function in the `p=` argument:

```openscad
include <BOSL2/std.scad>
path = scale([1.5,0.75], p=square(50,center=true));
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 39](images/tutorials/Paths_39.png)

```openscad
include <BOSL2/std.scad>
path = xscale(1.5, p=square(50,center=true));
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 40](images/tutorials/Paths_40.png)

```openscad
include <BOSL2/std.scad>
path = yscale(1.5, p=square(50,center=true));
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 41](images/tutorials/Paths_41.png)

To rotate a path, just can pass it to the `rot()` (or [xyz]rot) function in the `p=` argument:

```openscad
include <BOSL2/std.scad>
path = rot(30, p=square(50,center=true));
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 42](images/tutorials/Paths_42.png)

```openscad
include <BOSL2/std.scad>
path = zrot(30, p=square(50,center=true));
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 43](images/tutorials/Paths_43.png)

To mirror a path, just can pass it to the `mirror()` (or [xyz]flip) function in the `p=` argument:

```openscad
include <BOSL2/std.scad>
path = mirror([1,1], p=trapezoid(w1=40, w2=10, h=25));
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 44](images/tutorials/Paths_44.png)

```openscad
include <BOSL2/std.scad>
path = xflip(p=trapezoid(w1=40, w2=10, h=25));
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 45](images/tutorials/Paths_45.png)

```openscad
include <BOSL2/std.scad>
path = yflip(p=trapezoid(w1=40, w2=10, h=25));
stroke(path, closed=true, endcap2="arrow2");
```
![Figure 46](images/tutorials/Paths_46.png)

You can get raw transformation matrices for various transformations by calling them like a function without a `p=` argument:

```openscad
include <BOSL2/std.scad>
mat = move([5,10,0]);
multmatrix(mat) square(50,center=true);
```
![Figure 47](images/tutorials/Paths_47.png)

```openscad
include <BOSL2/std.scad>
mat = scale([1.5,0.75,1]);
multmatrix(mat) square(50,center=true);
```
![Figure 48](images/tutorials/Paths_48.png)

```openscad
include <BOSL2/std.scad>
mat = rot(30);
multmatrix(mat) square(50,center=true);
```
![Figure 49](images/tutorials/Paths_49.png)

Raw transformation matrices can be multiplied together to precalculate a compound transformation.  For example, to scale a shape, then rotate it, then translate the result, you can do something like:

```openscad
include <BOSL2/std.scad>
mat = move([5,10,0]) * rot(30) * scale([1.5,0.75,1]);
multmatrix(mat) square(50,center=true);
```
![Figure 50](images/tutorials/Paths_50.png)

To apply a compound transformation matrix to a path, you can use the `apply()` function:

```openscad
include <BOSL2/std.scad>
mat = move([5,10]) * rot(30) * scale([1.5,0.75]);
path = square(50,center=true);
tpath = apply(mat, path);
stroke(tpath, endcap2="arrow2");
```
![Figure 51](images/tutorials/Paths_51.png)


### Regions
A polygon is good to denote a single closed 2D shape with no holes in it.  For more complex 2D
shapes, you will need to use regions.  A region is a list of 2D polygons, where each polygon is
XORed against all the others.  You can display a region using the `region()` module.

If you have a region with one polygon fully inside another, it makes a hole:

```openscad
include <BOSL2/std.scad>
rgn = [square(50,center=true), circle(d=30)];
region(rgn);
```
![Figure 52](images/tutorials/Paths_52.png)

If you have a region with multiple polygons that are not contained by any others, they make multiple discontiguous shapes:

```openscad
include <BOSL2/std.scad>
rgn = [
    move([-30, 20], p=square(20,center=true)),
    move([  0,-20], p=trapezoid(w1=20, w2=10, h=20)),
    move([ 30, 20], p=square(20,center=true)),
];
region(rgn);
```
![Figure 53](images/tutorials/Paths_53.png)

Region polygons can be nested abitrarily deep, in multiple discontiguous shapes:

```openscad
include <BOSL2/std.scad>
rgn = [
    for (d=[50:-10:10]) left(30, p=circle(d=d)),
    for (d=[50:-10:10]) right(30, p=circle(d=d))
];
region(rgn);
```
![Figure 54](images/tutorials/Paths_54.png)

A region with crossing polygons is somewhat poorly formed, but the intersection(s) of the polygons become holes:

```openscad
include <BOSL2/std.scad>
rgn = [
    left(15, p=circle(d=50)),
    right(15, p=circle(d=50))
];
region(rgn);
```
![Figure 55](images/tutorials/Paths_55.png)

### Boolean Region Geometry
Similarly to how OpenSCAD can perform operations like union/difference/intersection/offset on shape geometry,
the BOSL2 library lets you perform those same operations on regions:

```openscad
include <BOSL2/std.scad>
rgn1 = [for (d=[40:-10:10]) circle(d=d)];
rgn2 = [square([60,12], center=true)];
rgn = union(rgn1, rgn2);
region(rgn);
```
![Figure 56](images/tutorials/Paths_56.png)

```openscad
include <BOSL2/std.scad>
rgn1 = [for (d=[40:-10:10]) circle(d=d)];
rgn2 = [square([60,12], center=true)];
rgn = difference(rgn1, rgn2);
region(rgn);
```
![Figure 57](images/tutorials/Paths_57.png)

```openscad
include <BOSL2/std.scad>
rgn1 = [for (d=[40:-10:10]) circle(d=d)];
rgn2 = [square([60,12], center=true)];
rgn = intersection(rgn1, rgn2);
region(rgn);
```
![Figure 58](images/tutorials/Paths_58.png)

```openscad
include <BOSL2/std.scad>
rgn1 = [for (d=[40:-10:10]) circle(d=d)];
rgn2 = [square([60,12], center=true)];
rgn = exclusive_or(rgn1, rgn2);
region(rgn);
```
![Figure 59](images/tutorials/Paths_59.png)

```openscad
include <BOSL2/std.scad>
orig_rgn = [star(n=5, step=2, d=50)];
rgn = offset(orig_rgn, r=-3, closed=true);
color("blue") region(orig_rgn);
region(rgn);
```
![Figure 60](images/tutorials/Paths_60.png)

You can use regions for several useful things.  If you wanted a grid of holes in your object that
form the shape given by a region, you can do that with `grid2d()`:

```openscad
include <BOSL2/std.scad>
rgn = [
    circle(d=100),
    star(n=5,step=2,d=100,spin=90)
];
difference() {
    cyl(h=5, d=120);
    grid2d(size=[120,120], spacing=[4,4], inside=rgn) cyl(h=10,d=2);
}
```
![Figure 61](images/tutorials/Paths_61.png)

You can also sweep a region through 3-space to make a solid:

```openscad
include <BOSL2/std.scad>
$fa=1; $fs=1;
rgn = [ for (d=[50:-10:10]) circle(d=d) ];
tforms = [
    for (a=[90:-5:0]) xrot(a, cp=[0,-70]),
    for (a=[0:5:90]) xrot(a, cp=[0,70]),
    move([0,150,-70]) * xrot(90),
];
sweep(rgn, tforms, closed=false, caps=true);
```
![Figure 62](images/tutorials/Paths_62.png)



