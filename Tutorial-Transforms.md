# Transforms Tutorial

<!-- TOC -->

## Translation
The `translate()` command is very simple:
```openscad
include <BOSL2/std.scad>
#sphere(d=20);
translate([0,0,30]) sphere(d=20);
```
![Figure 1](images/tutorials/Transforms_1.png)

But at a glance, or when the formula to calculate the move is complex, it can be difficult to see
just what axis is being moved along, and in which direction.  It's also a bit verbose for such a
frequently used command.  For these reasons, BOSL2 provides you with shortcuts for each direction.
These shortcuts are `up()`, `down()`, `fwd()`, `back()`, `left()`, and `right()`:
```openscad
include <BOSL2/std.scad>
#sphere(d=20);
up(30) sphere(d=20);
```
![Figure 2](images/tutorials/Transforms_2.png)

```openscad
include <BOSL2/std.scad>
#sphere(d=20);
down(30) sphere(d=20);
```
![Figure 3](images/tutorials/Transforms_3.png)

```openscad
include <BOSL2/std.scad>
#sphere(d=20);
fwd(30) sphere(d=20);
```
![Figure 4](images/tutorials/Transforms_4.png)

```openscad
include <BOSL2/std.scad>
#sphere(d=20);
back(30) sphere(d=20);
```
![Figure 5](images/tutorials/Transforms_5.png)

```openscad
include <BOSL2/std.scad>
#sphere(d=20);
left(30) sphere(d=20);
```
![Figure 6](images/tutorials/Transforms_6.png)

```openscad
include <BOSL2/std.scad>
#sphere(d=20);
right(30) sphere(d=20);
```
![Figure 7](images/tutorials/Transforms_7.png)

There is also a more generic `move()` command that can work just like `translate()`, or you can
specify the motion on each axis more clearly:
```openscad
include <BOSL2/std.scad>
#sphere(d=20);
move([30,-10]) sphere(d=20);
```
![Figure 8](images/tutorials/Transforms_8.png)

```openscad
include <BOSL2/std.scad>
#sphere(d=20);
move(x=30,y=10) sphere(d=20);
```
![Figure 9](images/tutorials/Transforms_9.png)


## Scaling
The `scale()` command is also fairly simple:
```openscad
include <BOSL2/std.scad>
scale(2) cube(10, center=true);
```
![Figure 10](images/tutorials/Transforms_10.png)

```openscad
include <BOSL2/std.scad>
scale([1,2,3]) cube(10, center=true);
```
![Figure 11](images/tutorials/Transforms_11.png)

If you want to only change the scaling on one axis, though, BOSL2 provides clearer
commands to do just that; `xscale()`, `yscale()`, and `zscale()`:
```openscad
include <BOSL2/std.scad>
xscale(2) cube(10, center=true);
```
![Figure 12](images/tutorials/Transforms_12.png)
```openscad
include <BOSL2/std.scad>
yscale(2) cube(10, center=true);
```
![Figure 13](images/tutorials/Transforms_13.png)
```openscad
include <BOSL2/std.scad>
zscale(2) cube(10, center=true);
```
![Figure 14](images/tutorials/Transforms_14.png)


## Rotation
The `rotate()` command is fairly straightforward:
```openscad
include <BOSL2/std.scad>
rotate([0,30,0]) cube(20, center=true);
```
![Figure 15](images/tutorials/Transforms_15.png)

It is also a bit verbose, and can, at a glance, be difficult to tell just how it is rotating.
BOSL2 provides shortcuts for rotating around each axis, for clarity; `xrot()`, `yrot()`, and `zrot()`:
```openscad
include <BOSL2/std.scad>
xrot(30) cube(20, center=true);
```
![Figure 16](images/tutorials/Transforms_16.png)

```openscad
include <BOSL2/std.scad>
yrot(30) cube(20, center=true);
```
![Figure 17](images/tutorials/Transforms_17.png)

```openscad
include <BOSL2/std.scad>
zrot(30) cube(20, center=true);
```
![Figure 18](images/tutorials/Transforms_18.png)

The `rot()` command is a more generic rotation command, and shorter to type than `rotate()`:
```openscad
include <BOSL2/std.scad>
rot([0,30,15]) cube(20, center=true);
```
![Figure 19](images/tutorials/Transforms_19.png)

All of the rotation shortcuts can take a `cp=` argument, that lets you specify a
centerpoint to rotate around:
```openscad
include <BOSL2/std.scad>
cp = [0,0,40];
color("blue") move(cp) sphere(d=3);
#cube(20, center=true);
xrot(45, cp=cp) cube(20, center=true);
```
![Figure 20](images/tutorials/Transforms_20.png)

```openscad
include <BOSL2/std.scad>
cp = [0,0,40];
color("blue") move(cp) sphere(d=3);
#cube(20, center=true);
yrot(45, cp=cp) cube(20, center=true);
```
![Figure 21](images/tutorials/Transforms_21.png)

```openscad
include <BOSL2/std.scad>
cp = [0,40,0];
color("blue") move(cp) sphere(d=3);
#cube(20, center=true);
zrot(45, cp=cp) cube(20, center=true);
```
![Figure 22](images/tutorials/Transforms_22.png)

You can also do a new trick with it.  You can rotate from pointing in one direction, towards another.
You give these directions using vectors:
```openscad
include <BOSL2/std.scad>
#cylinder(d=10, h=50);
rot(from=[0,0,1], to=[1,0,1]) cylinder(d=10, h=50);
```
![Figure 23](images/tutorials/Transforms_23.png)

There are several direction vectors constants and aliases you can use for clarity:

Constant                       | Value        | Direction
------------------------------ | ------------ | --------------
`CENTER`, `CTR`                | `[ 0, 0, 0]` | Centered
`LEFT`                         | `[-1, 0, 0]` | Towards X-
`RIGHT`                        | `[ 1, 0, 0]` | Towards X+
`FWD`, `FORWARD`, `FRONT`      | `[ 0,-1, 0]` | Towards Y-
`BACK`                         | `[ 0, 1, 0]` | Towards Y+
`DOWN`, `BOTTOM`, `BOT`, `BTM` | `[ 0, 0,-1]` | Towards Z-
`UP`, `TOP`                    | `[ 0, 0, 1]` | Towards Z+
`ALLNEG`                       | `[-1,-1,-1]` | Towards X-Y-Z-
`ALLPOS`                       | `[ 1, 1, 1]` | Towards X+Y+Z+

This lets you rewrite the above vector rotation more clearly as:
```openscad
include <BOSL2/std.scad>
#cylinder(d=10, h=50);
rot(from=UP, to=UP+RIGHT) cylinder(d=10, h=50);
```
![Figure 24](images/tutorials/Transforms_24.png)


## Mirroring
The standard `mirror()` command works like this:
```openscad
include <BOSL2/std.scad>
#yrot(60) cylinder(h=50, d1=20, d2=10);
mirror([1,0,0]) yrot(60) cylinder(h=50, d1=20, d2=10);
```
![Figure 25](images/tutorials/Transforms_25.png)

BOSL2 provides shortcuts for mirroring across the standard axes; `xflip()`, `yflip()`, and `zflip()`:
```openscad
include <BOSL2/std.scad>
#yrot(60) cylinder(h=50, d1=20, d2=10);
xflip() yrot(60) cylinder(h=50, d1=20, d2=10);
```
![Figure 26](images/tutorials/Transforms_26.png)

```openscad
include <BOSL2/std.scad>
#xrot(60) cylinder(h=50, d1=20, d2=10);
yflip() xrot(60) cylinder(h=50, d1=20, d2=10);
```
![Figure 27](images/tutorials/Transforms_27.png)

```openscad
include <BOSL2/std.scad>
#cylinder(h=50, d1=20, d2=10);
zflip() cylinder(h=50, d1=20, d2=10);
```
![Figure 28](images/tutorials/Transforms_28.png)

All of the flip commands can offset where the mirroring is performed:
```openscad
include <BOSL2/std.scad>
#zrot(30) cube(20, center=true);
xflip(x=-20) zrot(30) cube(20, center=true);
color("blue",0.25) left(20) cube([0.1,50,50], center=true);
```
![Figure 29](images/tutorials/Transforms_29.png)

```openscad
include <BOSL2/std.scad>
#zrot(30) cube(20, center=true);
yflip(y=20) zrot(30) cube(20, center=true);
color("blue",0.25) back(20) cube([40,0.1,40], center=true);
```
![Figure 30](images/tutorials/Transforms_30.png)

```openscad
include <BOSL2/std.scad>
#xrot(30) cube(20, center=true);
zflip(z=-20) xrot(30) cube(20, center=true);
color("blue",0.25) down(20) cube([40,40,0.1], center=true);
```
![Figure 31](images/tutorials/Transforms_31.png)


## Skewing
One transform that OpenSCAD does not perform natively is skewing.
BOSL2 provides the `skew()` command for that.  You give it multipliers
for the skews you want to perform.  The arguments used all start with `s`,
followed by the axis you want to skew along, followed by the axis that
the skewing will increase along.  For example, to skew along the X axis as
you get farther along the Y axis, use the `sxy=` argument.  If you give it
a multiplier of `0.5`, then for each unit further along the Y axis you get,
you will add `0.5` units of skew to the X axis.  Giving a negative multiplier
reverses the direction it skews:
```openscad
include <BOSL2/std.scad>
skew(sxy=0.5) cube(10,center=false);
```
![Figure 32](images/tutorials/Transforms_32.png)

```openscad
include <BOSL2/std.scad>
skew(sxz=-0.5) cube(10,center=false);
```
![Figure 33](images/tutorials/Transforms_33.png)

```openscad
include <BOSL2/std.scad>
skew(syx=-0.5) cube(10,center=false);
```
![Figure 34](images/tutorials/Transforms_34.png)

```openscad
include <BOSL2/std.scad>
skew(syz=0.5) cube(10,center=false);
```
![Figure 35](images/tutorials/Transforms_35.png)

```openscad
include <BOSL2/std.scad>
skew(szx=-0.5) cube(10,center=false);
```
![Figure 36](images/tutorials/Transforms_36.png)

```openscad
include <BOSL2/std.scad>
skew(szy=0.5) cube(10,center=false);
```
![Figure 37](images/tutorials/Transforms_37.png)


