# Basic Shapes Tutorial

<!-- TOC -->

## Primitives
There are 3 built-in 3D primitive shapes that OpenSCAD provides: `cube()`, `cylinder()`,
and `sphere()`.  The BOSL2 library extends and provides alternative to these shapes so
that they support more features, and more ways to simply reorient them.


### 3D Cubes
BOSL2 overrides the built-in `cube()` module.  It still can be used as you expect from the built-in:

```openscad
include <BOSL2/std.scad>
cube(100);
```
![Figure 1](images/tutorials/Shapes3d_1.png)

```openscad
include <BOSL2/std.scad>
cube(100, center=true);
```
![Figure 2](images/tutorials/Shapes3d_2.png)

```openscad
include <BOSL2/std.scad>
cube([50,40,20], center=true);
```
![Figure 3](images/tutorials/Shapes3d_3.png)

It is also enhanced to allow you to anchor, spin, orient, and attach it.

You can use `anchor=` similarly to how you use it with `rect()` or `oval()`,
except you can also anchor vertically in 3D, allowing anchoring to faces, edges,
and corners:

```openscad
include <BOSL2/std.scad>
cube([50,40,20], anchor=BOTTOM);
```
![Figure 4](images/tutorials/Shapes3d_4.png)

```openscad
include <BOSL2/std.scad>
cube([50,40,20], anchor=TOP+BACK);
```
![Figure 5](images/tutorials/Shapes3d_5.png)

```openscad
include <BOSL2/std.scad>
cube([50,40,20], anchor=TOP+FRONT+LEFT);
```
![Figure 6](images/tutorials/Shapes3d_6.png)

You can use `spin=` to rotate around the Z axis:

```openscad
include <BOSL2/std.scad>
cube([50,40,20], anchor=FRONT, spin=30);
```
![Figure 7](images/tutorials/Shapes3d_7.png)

3D objects also gain the ability to use an extra trick with `spin=`;
if you pass a list of `[X,Y,Z]` rotation angles to `spin=`, it will
rotate by the three given axis angles, similar to using `rotate()`:

```openscad
include <BOSL2/std.scad>
cube([50,40,20], anchor=FRONT, spin=[15,0,30]);
```
![Figure 8](images/tutorials/Shapes3d_8.png)

3D objects also can be given an `orient=` argument as a vector, pointing
to where the top of the shape should be rotated towards.

```openscad
include <BOSL2/std.scad>
cube([50,40,20], orient=UP+BACK+RIGHT);
```
![Figure 9](images/tutorials/Shapes3d_9.png)

If you use `anchor=`, `spin=`, and `orient=` together, the anchor is performed
first, then the spin, then the orient:

```openscad
include <BOSL2/std.scad>
cube([50,40,20], anchor=FRONT);
```
![Figure 10](images/tutorials/Shapes3d_10.png)

```openscad
include <BOSL2/std.scad>
cube([50,40,20], anchor=FRONT, spin=45);
```
![Figure 11](images/tutorials/Shapes3d_11.png)

```openscad
include <BOSL2/std.scad>
cube([50,40,20], anchor=FRONT, spin=45, orient=UP+FWD+RIGHT);
```
![Figure 12](images/tutorials/Shapes3d_12.png)

BOSL2 provides a `cuboid()` module that expands on `cube()`, by providing
rounding and chamfering of edges.  You can use it similarly to `cube()`,
except that `cuboid()` centers by default.

You can round the edges with the `rounding=` argument:

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=20);
```
![Figure 13](images/tutorials/Shapes3d_13.png)

Similarly, you can chamfer the edges with the `chamfer=` argument:

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], chamfer=10);
```
![Figure 14](images/tutorials/Shapes3d_14.png)

You can round only some edges, by using the `edges=` arguments.  It can be
given a few types of arguments. If you gave it a vector pointed at a face,
it will only round the edges surrounding that face:

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=20, edges=TOP);
```
![Figure 15](images/tutorials/Shapes3d_15.png)

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=20, edges=RIGHT);
```
![Figure 16](images/tutorials/Shapes3d_16.png)

If you give `edges=` a vector pointing at a corner, it will round all edges
that meet at that corner:

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=20, edges=RIGHT+FRONT+TOP);
```
![Figure 17](images/tutorials/Shapes3d_17.png)

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=20, edges=LEFT+FRONT+TOP);
```
![Figure 18](images/tutorials/Shapes3d_18.png)

If you give `edges=` a vector pointing at an edge, it will round only that edge:

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=10, edges=FRONT+TOP);
```
![Figure 19](images/tutorials/Shapes3d_19.png)

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=10, edges=RIGHT+FRONT);
```
![Figure 20](images/tutorials/Shapes3d_20.png)

If you give the string "X", "Y", or "Z", then all edges aligned with the specified
axis will be rounded:

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=10, edges="X");
```
![Figure 21](images/tutorials/Shapes3d_21.png)

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=10, edges="Y");
```
![Figure 22](images/tutorials/Shapes3d_22.png)

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=10, edges="Z");
```
![Figure 23](images/tutorials/Shapes3d_23.png)

If you give a list of edge specs, then all edges referenced in the list will
be rounded:

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=10, edges=[TOP,"Z",BOTTOM+RIGHT]);
```
![Figure 24](images/tutorials/Shapes3d_24.png)

The default value for `edges=` is `EDGES_ALL`, which is all edges.  You can also
give an `except_edges=` argument that specifies edges to NOT round:

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=10, except_edges=BOTTOM+RIGHT);
```
![Figure 25](images/tutorials/Shapes3d_25.png)

You can give the `except_edges=` argument any type of argument that you can
give to `edges=`:

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=10, except_edges=[BOTTOM,"Z",TOP+RIGHT]);
```
![Figure 26](images/tutorials/Shapes3d_26.png)

You can give both `edges=` and `except_edges=`, to simplify edge specs:

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], rounding=10, edges=[TOP,FRONT], except_edges=TOP+FRONT);
```
![Figure 27](images/tutorials/Shapes3d_27.png)

You can specify what edges to chamfer similarly:

```openscad
include <BOSL2/std.scad>
cuboid([100,80,60], chamfer=10, edges=[TOP,FRONT], except_edges=TOP+FRONT);
```
![Figure 28](images/tutorials/Shapes3d_28.png)


### 3D Cylinder
BOSL2 overrides the built-in `cylinder()` module.  It still can be used as you
expect from the built-in:

```openscad
include <BOSL2/std.scad>
cylinder(r=50,h=50);
```
![Figure 29](images/tutorials/Shapes3d_29.png)

```openscad
include <BOSL2/std.scad>
cylinder(r=50,h=50,center=true);
```
![Figure 30](images/tutorials/Shapes3d_30.png)

```openscad
include <BOSL2/std.scad>
cylinder(d=100,h=50,center=true);
```
![Figure 31](images/tutorials/Shapes3d_31.png)

```openscad
include <BOSL2/std.scad>
cylinder(d1=100,d2=80,h=50,center=true);
```
![Figure 32](images/tutorials/Shapes3d_32.png)

You can also anchor, spin, orient, and attach like the `cuboid()` module:

```openscad
include <BOSL2/std.scad>
cylinder(r=50, h=50, anchor=TOP+FRONT);
```
![Figure 33](images/tutorials/Shapes3d_33.png)

```openscad
include <BOSL2/std.scad>
cylinder(r=50, h=50, anchor=BOTTOM+LEFT);
```
![Figure 34](images/tutorials/Shapes3d_34.png)

```openscad
include <BOSL2/std.scad>
cylinder(r=50, h=50, anchor=BOTTOM+LEFT, spin=30);
```
![Figure 35](images/tutorials/Shapes3d_35.png)

```openscad
include <BOSL2/std.scad>
cylinder(r=50, h=50, anchor=BOTTOM, orient=UP+BACK+RIGHT);
```
![Figure 36](images/tutorials/Shapes3d_36.png)


BOSL2 provides a `cyl()` module that expands on `cylinder()`, by providing
rounding and chamfering of edges.  You can use it similarly to `cylinder()`,
except that `cyl()` centers the cylinder by default.

```openscad
include <BOSL2/std.scad>
cyl(r=60, l=100);
```
![Figure 37](images/tutorials/Shapes3d_37.png)

```openscad
include <BOSL2/std.scad>
cyl(d=100, l=100);
```
![Figure 38](images/tutorials/Shapes3d_38.png)

```openscad
include <BOSL2/std.scad>
cyl(d=100, l=100, anchor=TOP);
```
![Figure 39](images/tutorials/Shapes3d_39.png)

You can round the edges with the `rounding=` argument:

```openscad
include <BOSL2/std.scad>
cyl(d=100, l=100, rounding=20);
```
![Figure 40](images/tutorials/Shapes3d_40.png)

Similarly, you can chamfer the edges with the `chamfer=` argument:

```openscad
include <BOSL2/std.scad>
cyl(d=100, l=100, chamfer=10);
```
![Figure 41](images/tutorials/Shapes3d_41.png)

You can specify rounding and chamfering for each end individually:

```openscad
include <BOSL2/std.scad>
cyl(d=100, l=100, rounding1=20);
```
![Figure 42](images/tutorials/Shapes3d_42.png)

```openscad
include <BOSL2/std.scad>
cyl(d=100, l=100, rounding2=20);
```
![Figure 43](images/tutorials/Shapes3d_43.png)

```openscad
include <BOSL2/std.scad>
cyl(d=100, l=100, chamfer1=10);
```
![Figure 44](images/tutorials/Shapes3d_44.png)

```openscad
include <BOSL2/std.scad>
cyl(d=100, l=100, chamfer2=10);
```
![Figure 45](images/tutorials/Shapes3d_45.png)

You can even mix and match rounding and chamfering:

```openscad
include <BOSL2/std.scad>
cyl(d=100, l=100, rounding1=20, chamfer2=10);
```
![Figure 46](images/tutorials/Shapes3d_46.png)

```openscad
include <BOSL2/std.scad>
cyl(d=100, l=100, rounding2=20, chamfer1=10);
```
![Figure 47](images/tutorials/Shapes3d_47.png)


### 3D Spheres
BOSL2 overrides the built-in `sphere()` module.  It still can be used as you
expect from the built-in:

```openscad
include <BOSL2/std.scad>
sphere(r=50);
```
![Figure 48](images/tutorials/Shapes3d_48.png)

```openscad
include <BOSL2/std.scad>
sphere(d=100);
```
![Figure 49](images/tutorials/Shapes3d_49.png)

You can anchor, spin, and orient `sphere()`s, much like you can with `cylinder()`
and `cube()`:

```openscad
include <BOSL2/std.scad>
sphere(d=100, anchor=FRONT);
```
![Figure 50](images/tutorials/Shapes3d_50.png)

```openscad
include <BOSL2/std.scad>
sphere(d=100, anchor=FRONT, spin=30);
```
![Figure 51](images/tutorials/Shapes3d_51.png)

```openscad
include <BOSL2/std.scad>
sphere(d=100, anchor=BOTTOM, orient=RIGHT+TOP);
```
![Figure 52](images/tutorials/Shapes3d_52.png)

BOSL2 also provides `spheroid()`, which enhances `sphere()` with a few features
like the `circum=` and `style=` arguments:

You can use the `circum=true` argument to force the sphere to circumscribe the
ideal sphere, as opposed to the default inscribing:

```openscad
include <BOSL2/std.scad>
spheroid(d=100, circum=true);
```
![Figure 53](images/tutorials/Shapes3d_53.png)

The `style=` argument can choose the way that the sphere will be constructed:
The "orig" style matches the `sphere()` built-in's construction. 

```openscad
include <BOSL2/std.scad>
spheroid(d=100, style="orig", $fn=20);
```
![Figure 54](images/tutorials/Shapes3d_54.png)

The "aligned" style will ensure that there is a vertex at each axis extrema,
so long as `$fn` is a multiple of 4.

```openscad
include <BOSL2/std.scad>
spheroid(d=100, style="aligned", $fn=20);
```
![Figure 55](images/tutorials/Shapes3d_55.png)

The "stagger" style will stagger the triangulation of the vertical rows:

```openscad
include <BOSL2/std.scad>
spheroid(d=100, style="stagger", $fn=20);
```
![Figure 56](images/tutorials/Shapes3d_56.png)

The "icosa" style will make for roughly equal-sized triangles for the entire
sphere surface, based on subdividing an icosahedron.  This style will round the
effective `$fn` to a multiple of 5 when constructing the spheroid:

```openscad
include <BOSL2/std.scad>
spheroid(d=100, style="icosa", $fn=20);
```
![Figure 57](images/tutorials/Shapes3d_57.png)

The "octa" style will also make for roughly equal-sized triangles for the entire
sphere surface, but based on subdividing an octahedron.  This is useful in that it
guarantees vertices at the axis extrema.  This style will round the effective `$fn`
to a multiple of 4 when constructing the spheroid:

```openscad
include <BOSL2/std.scad>
spheroid(d=100, style="octa", $fn=20);
```
![Figure 58](images/tutorials/Shapes3d_58.png)

