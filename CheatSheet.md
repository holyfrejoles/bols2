# The The Belfry OpenScad Library, v2. (BOSL2) Cheat Sheet

## LibFile: transforms.scad

### Section: Translations

<code>[move](transforms.scad#functionmodule-move)([x=], [y=], [z=]) ...</code>  <code>[move](transforms.scad#functionmodule-move)(v) ...</code>  <code>pts = [move](transforms.scad#functionmodule-move)(v, p);</code>  <code>pts = [move](transforms.scad#functionmodule-move)([x=], [y=], [z=], p=);</code>  <code>pts = [move](transforms.scad#functionmodule-move)(STRING, p);</code>  <code>mat = [move](transforms.scad#functionmodule-move)(v);</code>  <code>mat = [move](transforms.scad#functionmodule-move)([x=], [y=], [z=]);</code>  
<code>[left](transforms.scad#functionmodule-left)(x) ...</code>  <code>pts = [left](transforms.scad#functionmodule-left)(x, p);</code>  <code>mat = [left](transforms.scad#functionmodule-left)(x);</code>  
<code>[right](transforms.scad#functionmodule-right)(x) ...</code>  <code>pts = [right](transforms.scad#functionmodule-right)(x, p);</code>  <code>mat = [right](transforms.scad#functionmodule-right)(x);</code>  
<code>[fwd](transforms.scad#functionmodule-fwd)(y) ...</code>  <code>pts = [fwd](transforms.scad#functionmodule-fwd)(y, p);</code>  <code>mat = [fwd](transforms.scad#functionmodule-fwd)(y);</code>  
<code>[back](transforms.scad#functionmodule-back)(y) ...</code>  <code>pts = [back](transforms.scad#functionmodule-back)(y, p);</code>  <code>mat = [back](transforms.scad#functionmodule-back)(y);</code>  
<code>[down](transforms.scad#functionmodule-down)(z) ...</code>  <code>pts = [down](transforms.scad#functionmodule-down)(z, p);</code>  <code>mat = [down](transforms.scad#functionmodule-down)(z);</code>  
<code>[up](transforms.scad#functionmodule-up)(z) ...</code>  <code>pts = [up](transforms.scad#functionmodule-up)(z, p);</code>  <code>mat = [up](transforms.scad#functionmodule-up)(z);</code>  

### Section: Rotations

<code>[rot](transforms.scad#functionmodule-rot)(a, [cp], [reverse]) {...}</code>  <code>[rot](transforms.scad#functionmodule-rot)([X,Y,Z], [cp], [reverse]) {...}</code>  <code>[rot](transforms.scad#functionmodule-rot)(a, v, [cp], [reverse]) {...}</code>  <code>[rot](transforms.scad#functionmodule-rot)(from, to, [a], [reverse]) {...}</code>  <code>pts = [rot](transforms.scad#functionmodule-rot)(a, p=, [cp=], [reverse=]);</code>  <code>pts = [rot](transforms.scad#functionmodule-rot)([X,Y,Z], p=, [cp=], [reverse=]);</code>  <code>pts = [rot](transforms.scad#functionmodule-rot)(a, v, p=, [cp=], [reverse=]);</code>  <code>pts = [rot](transforms.scad#functionmodule-rot)([a], from=, to=, p=, [reverse=]);</code>  <code>M = [rot](transforms.scad#functionmodule-rot)(a, [cp=], [reverse=]);</code>  <code>M = [rot](transforms.scad#functionmodule-rot)([X,Y,Z], [cp=], [reverse=]);</code>  <code>M = [rot](transforms.scad#functionmodule-rot)(a, v, [cp=], [reverse=]);</code>  <code>M = [rot](transforms.scad#functionmodule-rot)(from=, to=, [a=], [reverse=]);</code>  
<code>[xrot](transforms.scad#functionmodule-xrot)(a, [cp=]) ...</code>  <code>rotated = [xrot](transforms.scad#functionmodule-xrot)(a, p, [cp=]);</code>  <code>mat = [xrot](transforms.scad#functionmodule-xrot)(a, [cp=]);</code>  
<code>[yrot](transforms.scad#functionmodule-yrot)(a, [cp=]) ...</code>  <code>rotated = [yrot](transforms.scad#functionmodule-yrot)(a, p, [cp=]);</code>  <code>mat = [yrot](transforms.scad#functionmodule-yrot)(a, [cp=]);</code>  
<code>[zrot](transforms.scad#functionmodule-zrot)(a, [cp=]) ...</code>  <code>rotated = [zrot](transforms.scad#functionmodule-zrot)(a, p, [cp=]);</code>  <code>mat = [zrot](transforms.scad#functionmodule-zrot)(a, [cp=]);</code>  

### Section: Scaling

<code>[scale](transforms.scad#functionmodule-scale)(SCALAR) ...</code>  <code>[scale](transforms.scad#functionmodule-scale)([X,Y,Z]) ...</code>  <code>pts = [scale](transforms.scad#functionmodule-scale)(v, p, [cp=]);</code>  <code>mat = [scale](transforms.scad#functionmodule-scale)(v, [cp=]);</code>  
<code>[xscale](transforms.scad#functionmodule-xscale)(x, [cp=]) ...</code>  <code>scaled = [xscale](transforms.scad#functionmodule-xscale)(x, p, [cp=]);</code>  <code>mat = [xscale](transforms.scad#functionmodule-xscale)(x, [cp=]);</code>  
<code>[yscale](transforms.scad#functionmodule-yscale)(y, [cp=]) ...</code>  <code>scaled = [yscale](transforms.scad#functionmodule-yscale)(y, p, [cp=]);</code>  <code>mat = [yscale](transforms.scad#functionmodule-yscale)(y, [cp=]);</code>  
<code>[zscale](transforms.scad#functionmodule-zscale)(z, [cp=]) ...</code>  <code>scaled = [zscale](transforms.scad#functionmodule-zscale)(z, p, [cp=]);</code>  <code>mat = [zscale](transforms.scad#functionmodule-zscale)(z, [cp=]);</code>  

### Section: Reflection (Mirroring)

<code>[mirror](transforms.scad#functionmodule-mirror)(v) ...</code>  <code>pt = [mirror](transforms.scad#functionmodule-mirror)(v, p);</code>  <code>mat = [mirror](transforms.scad#functionmodule-mirror)(v);</code>  
<code>[xflip](transforms.scad#functionmodule-xflip)([x]) ...</code>  <code>pt = [xflip](transforms.scad#functionmodule-xflip)(p, [x]);</code>  <code>pt = [xflip](transforms.scad#functionmodule-xflip)([x]);</code>  
<code>[yflip](transforms.scad#functionmodule-yflip)([y]) ...</code>  <code>pt = [yflip](transforms.scad#functionmodule-yflip)(p, [y]);</code>  <code>pt = [yflip](transforms.scad#functionmodule-yflip)([y]);</code>  
<code>[zflip](transforms.scad#functionmodule-zflip)([z]) ...</code>  <code>pt = [zflip](transforms.scad#functionmodule-zflip)(p, [z]);</code>  <code>pt = [zflip](transforms.scad#functionmodule-zflip)([z]);</code>  

### Section: Other Transformations

<code>[frame\_map](transforms.scad#functionmodule-frame_map)(v1, v2, v3, [reverse=]) { ... }</code>  <code>transformed = [frame\_map](transforms.scad#functionmodule-frame_map)(v1, v2, v3, p=points, [reverse=]);</code>  <code>map = [frame\_map](transforms.scad#functionmodule-frame_map)(v1, v2, v3, [reverse=]);</code>  <code>map = [frame\_map](transforms.scad#functionmodule-frame_map)(x=VECTOR1, y=VECTOR2, [reverse=]);</code>  <code>map = [frame\_map](transforms.scad#functionmodule-frame_map)(x=VECTOR1, z=VECTOR2, [reverse=]);</code>  <code>map = [frame\_map](transforms.scad#functionmodule-frame_map)(y=VECTOR1, z=VECTOR2, [reverse=]);</code>  
<code>[skew](transforms.scad#functionmodule-skew)([sxy=], [sxz=], [syx=], [syz=], [szx=], [szy=]) ...</code>  <code>pts = [skew](transforms.scad#functionmodule-skew)(p, [sxy=], [sxz=], [syx=], [syz=], [szx=], [szy=]);</code>  <code>mat = [skew](transforms.scad#functionmodule-skew)([sxy=], [sxz=], [syx=], [syz=], [szx=], [szy=]);</code>  

### Section: Applying transformation matrices to data

<code>pts = [apply](transforms.scad#function-apply)(transform, points);</code>  

## LibFile: attachments.scad

### Section: Attachment Positioning

<code>[position](attachments.scad#module-position)(from) {...}</code>  
<code>[orient](attachments.scad#module-orient)(dir, &lt;spin=&gt;) ...</code>  <code>[orient](attachments.scad#module-orient)(anchor=, &lt;spin=&gt;) ...</code>  
<code>[attach](attachments.scad#module-attach)(from, [overlap=], [norot=]) {...}</code>  <code>[attach](attachments.scad#module-attach)(from, to, [overlap=], [norot=]) {...}</code>  

### Section: Attachment Modifiers

<code>[tags](attachments.scad#module-tags)([tags](attachments.scad#module-tags)) {...}</code>  
<code>[diff](attachments.scad#module-diff)(neg, [keep]) {...}</code>  <code>[diff](attachments.scad#module-diff)(neg, pos, [keep]) {...}</code>  
<code>[intersect](attachments.scad#module-intersect)(a, [keep=]) {...}</code>  <code>[intersect](attachments.scad#module-intersect)(a, b, [keep=]) {...}</code>  
<code>[hulling](attachments.scad#module-hulling)(a) {...}</code>  
<code>[recolor](attachments.scad#module-recolor)(c) {...}</code>  
<code>[hide](attachments.scad#module-hide)(tags) {...}</code>  
<code>[show](attachments.scad#module-show)(tags) {...}</code>  

### Section: Attachable Masks

<code>[edge\_mask](attachments.scad#module-edge_mask)([edges], [except]) {...}</code>  
<code>[corner\_mask](attachments.scad#module-corner_mask)([corners], [except]) {...}</code>  
<code>[face\_profile](attachments.scad#module-face_profile)(faces, r|d=, [convexity=]) {...}</code>  
<code>[edge\_profile](attachments.scad#module-edge_profile)([edges], [except], [convexity]) {...}</code>  
<code>[corner\_profile](attachments.scad#module-corner_profile)([corners], [except], &lt;r=|d=&gt;, [convexity=]) {...}</code>  

### Section: Making your objects attachable

<code>[attachable](attachments.scad#module-attachable)(anchor, spin, two\_d=true, size=, [size2=], [shift=], ...) {...}</code>  <code>[attachable](attachments.scad#module-attachable)(anchor, spin, two\_d=true, r=|d=, ...) {...}</code>  <code>[attachable](attachments.scad#module-attachable)(anchor, spin, two\_d=true, path=, [extent=], ...) {...}</code>  <code>[attachable](attachments.scad#module-attachable)(anchor, spin, two\_d=true, region=, [extent=], ...) {...}</code>  <code>[attachable](attachments.scad#module-attachable)(anchor, spin, [orient], size=, [size2=], [shift=], ...) {...}</code>  <code>[attachable](attachments.scad#module-attachable)(anchor, spin, [orient], r=|d=, l=, [axis=], ...) {...}</code>  <code>[attachable](attachments.scad#module-attachable)(anchor, spin, [orient], r1=|d1=, r2=|d2=, l=, [axis=], ...) {...}</code>  <code>[attachable](attachments.scad#module-attachable)(anchor, spin, [orient], r=|d=, ...) {...}</code>  <code>[attachable](attachments.scad#module-attachable)(anchor, spin, path=, l=|h=, [extent=], ...) {...}</code>  <code>[attachable](attachments.scad#module-attachable)(anchor, spin, region=, l=|h=, [extent=], ...) {...}</code>  <code>[attachable](attachments.scad#module-attachable)(anchor, spin, [orient], vnf=, [extent=], ...) {...}</code>  
<code>mat = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], two\_d=true, size=, [size2=], [shift=], ...);</code>  <code>pts = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], two\_d=true, size=, [size2=], [shift=], p=, ...);</code>  <code>mat = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], two\_d=true, r=|d=, ...);</code>  <code>pts = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], two\_d=true, r=|d=, p=, ...);</code>  <code>mat = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], two\_d=true, path=, [extent=], ...);</code>  <code>pts = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], two\_d=true, path=, [extent=], p=, ...);</code>  <code>mat = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], two\_d=true, region=, [extent=], ...);</code>  <code>pts = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], two\_d=true, region=, [extent=], p=, ...);</code>  <code>mat = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], size=, [size2=], [shift=], ...);</code>  <code>pts = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], size=, [size2=], [shift=], p=, ...);</code>  <code>mat = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], r=|d=, l=, [axis=], ...);</code>  <code>pts = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], r=|d=, l=, [axis=], p=, ...);</code>  <code>mat = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], r1=|d1=, r2=|d2=, l=, [axis=], ...);</code>  <code>pts = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], r1=|d1=, r2=|d2=, l=, [axis=], p=, ...);</code>  <code>mat = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], r|d=, ...);</code>  <code>pts = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], r|d=, p=, ...);</code>  <code>mat = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], path=, l=|h=, [extent=], ...);</code>  <code>pts = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], path=, l=|h=, [extent=], p=, ...);</code>  <code>mat = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], region=, l=|h=, [extent=], ...);</code>  <code>pts = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], region=, l=|h=, [extent=], p=, ...);</code>  <code>mat = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], vnf, [extent], ...);</code>  <code>pts = [reorient](attachments.scad#function-reorient)(anchor, spin, [orient], vnf, [extent], p=, ...);</code>  
<code>a = [named\_anchor](attachments.scad#function-named_anchor)(name, pos, [orient], [spin]);</code>  

### Section: Visualizing Anchors

<code>... [show\_anchors](attachments.scad#module-show_anchors)([s], [std=], [custom=]);</code>  
<code>[anchor\_arrow](attachments.scad#module-anchor_arrow)([s], [color], [flag]);</code>  
<code>[anchor\_arrow2d](attachments.scad#module-anchor_arrow2d)([s], [color], [flag]);</code>  
<code>[expose\_anchors](attachments.scad#module-expose_anchors)(opacity) {child1() show\_anchors(); child2() show\_anchors(); ...}</code>  
<code>[frame\_ref](attachments.scad#module-frame_ref)(s, opacity);</code>  

## LibFile: shapes2d.scad

### Section: 2D Primitives

<code>[square](shapes2d.scad#functionmodule-square)(size, [center], ...);</code>  <code>[square](shapes2d.scad#functionmodule-square)(size, [center], ...) { attachables }</code>  <code>path = [square](shapes2d.scad#functionmodule-square)(size, [center], ...);</code>  
<code>[rect](shapes2d.scad#functionmodule-rect)(size, [rounding], [chamfer], ...);</code>  <code>[rect](shapes2d.scad#functionmodule-rect)(size, ...) { attachables }</code>  <code>path = [rect](shapes2d.scad#functionmodule-rect)(size, [rounding], [chamfer], ...);</code>  
<code>[circle](shapes2d.scad#functionmodule-circle)(r|d=, ...);</code>  <code>[circle](shapes2d.scad#functionmodule-circle)(r|d=, ...) { attachables }</code>  <code>path = [circle](shapes2d.scad#functionmodule-circle)(r|d=, ...);</code>  
<code>[ellipse](shapes2d.scad#functionmodule-ellipse)(r|d=, [realign=], [circum=], ...);</code>  <code>[ellipse](shapes2d.scad#functionmodule-ellipse)(r|d=, [realign=], [circum=], ...) { attachables }</code>  <code>path = [ellipse](shapes2d.scad#functionmodule-ellipse)(r|d=, [realign=], [circum=], ...);</code>  

### Section: Polygons

<code>[regular\_ngon](shapes2d.scad#functionmodule-regular_ngon)(n, r/d=/or=/od=, [realign=]);</code>  <code>[regular\_ngon](shapes2d.scad#functionmodule-regular_ngon)(n, ir=/id=, [realign=]);</code>  <code>[regular\_ngon](shapes2d.scad#functionmodule-regular_ngon)(n, side=, [realign=]);</code>  
<code>[pentagon](shapes2d.scad#functionmodule-pentagon)(or|od=, [realign=]);</code>  <code>[pentagon](shapes2d.scad#functionmodule-pentagon)(ir=|id=, [realign=]);</code>  <code>[pentagon](shapes2d.scad#functionmodule-pentagon)(side=, [realign=]);</code>  
<code>[hexagon](shapes2d.scad#functionmodule-hexagon)(r/or, [realign=], &lt;align\_tip=|align\_side=&gt;, [rounding=], ...);</code>  <code>[hexagon](shapes2d.scad#functionmodule-hexagon)(d=/od=, ...);</code>  <code>[hexagon](shapes2d.scad#functionmodule-hexagon)(ir=/id=, ...);</code>  <code>[hexagon](shapes2d.scad#functionmodule-hexagon)(side=, ...);</code>  <code>[hexagon](shapes2d.scad#functionmodule-hexagon)(r/or, ...) { attachments }</code>  <code>path = [hexagon](shapes2d.scad#functionmodule-hexagon)(r/or, ...);</code>  <code>path = [hexagon](shapes2d.scad#functionmodule-hexagon)(d=/od=, ...);</code>  <code>path = [hexagon](shapes2d.scad#functionmodule-hexagon)(ir=/id=, ...);</code>  <code>path = [hexagon](shapes2d.scad#functionmodule-hexagon)(side=, ...);</code>  
<code>[octagon](shapes2d.scad#functionmodule-octagon)(r/or, [realign=], &lt;align\_tip=|align\_side=&gt;, [rounding=], ...);</code>  <code>[octagon](shapes2d.scad#functionmodule-octagon)(d=/od=, ...);</code>  <code>[octagon](shapes2d.scad#functionmodule-octagon)(ir=/id=, ...);</code>  <code>[octagon](shapes2d.scad#functionmodule-octagon)(side=, ...);</code>  <code>[octagon](shapes2d.scad#functionmodule-octagon)(r/or, ...) { attachments }</code>  <code>path = [octagon](shapes2d.scad#functionmodule-octagon)(r/or, ...);</code>  <code>path = [octagon](shapes2d.scad#functionmodule-octagon)(d=/od=, ...);</code>  <code>path = [octagon](shapes2d.scad#functionmodule-octagon)(ir=/id=, ...);</code>  <code>path = [octagon](shapes2d.scad#functionmodule-octagon)(side=, ...);</code>  
<code>[right\_triangle](shapes2d.scad#functionmodule-right_triangle)(size, [center], ...);</code>  <code>[right\_triangle](shapes2d.scad#functionmodule-right_triangle)(size, [center], ...) { attachments }</code>  <code>path = [right\_triangle](shapes2d.scad#functionmodule-right_triangle)(size, [center], ...);</code>  
<code>[trapezoid](shapes2d.scad#functionmodule-trapezoid)(h, w1, w2, [shift=], [rounding=], [chamfer=], ...);</code>  <code>[trapezoid](shapes2d.scad#functionmodule-trapezoid)(h, w1, angle=, ...);</code>  <code>[trapezoid](shapes2d.scad#functionmodule-trapezoid)(h, w2, angle=, ...);</code>  <code>[trapezoid](shapes2d.scad#functionmodule-trapezoid)(w1, w2, angle=, ...);</code>  <code>[trapezoid](shapes2d.scad#functionmodule-trapezoid)(h, w1, w2, ...) { attachments }</code>  <code>path = [trapezoid](shapes2d.scad#functionmodule-trapezoid)(h, w1, w2, ...);</code>  <code>path = [trapezoid](shapes2d.scad#functionmodule-trapezoid)(h, w1, angle=, ...);</code>  <code>path = [trapezoid](shapes2d.scad#functionmodule-trapezoid)(h, w2=, angle=, ...);</code>  <code>path = [trapezoid](shapes2d.scad#functionmodule-trapezoid)(w1=, w2=, angle=, ...);</code>  
<code>[star](shapes2d.scad#functionmodule-star)(n, r/or, ir, [realign=], [align\_tip=], [align\_pit=], ...);</code>  <code>[star](shapes2d.scad#functionmodule-star)(n, r/or, step=, ...);</code>  <code>[star](shapes2d.scad#functionmodule-star)(n, r/or, ir, ...) { attachments }</code>  <code>path = [star](shapes2d.scad#functionmodule-star)(n, r/or, ir, [realign=], [align\_tip=], [align\_pit=], ...);</code>  <code>path = [star](shapes2d.scad#functionmodule-star)(n, r/or, step=, ...);</code>  
<code>[jittered\_poly](shapes2d.scad#module-jittered_poly)(path, [dist]);</code>  

### Section: Curved 2D Shapes

<code>[teardrop2d](shapes2d.scad#functionmodule-teardrop2d)(r/d=, [ang], [cap\_h]);</code>  <code>[teardrop2d](shapes2d.scad#functionmodule-teardrop2d)(r/d=, [ang], [cap\_h], ...) { attachments }</code>  <code>path = [teardrop2d](shapes2d.scad#functionmodule-teardrop2d)(r/d=, [ang], [cap\_h]);</code>  
<code>[egg](shapes2d.scad#functionmodule-egg)(length, r1, r2, R);</code>  <code>path = [egg](shapes2d.scad#functionmodule-egg)(length, r1|d2, r2|d2, R|D);</code>  
<code>[glued\_circles](shapes2d.scad#functionmodule-glued_circles)(r/d=, [spread=], [tangent=], ...);</code>  <code>[glued\_circles](shapes2d.scad#functionmodule-glued_circles)(r/d=, [spread=], [tangent=], ...) { attachments }</code>  <code>path = [glued\_circles](shapes2d.scad#functionmodule-glued_circles)(r/d=, [spread=], [tangent=], ...);</code>  
<code>[supershape](shapes2d.scad#functionmodule-supershape)(step, [m1=], [m2=], [n1=], [n2=], [n3=], [a=], [b=], &lt;r=/d=&gt;);</code>  <code>[supershape](shapes2d.scad#functionmodule-supershape)(step, [m1=], [m2=], [n1=], [n2=], [n3=], [a=], [b=], &lt;r=/d=&gt;) { attachments }</code>  <code>path = [supershape](shapes2d.scad#functionmodule-supershape)(step, [m1=], [m2=], [n1=], [n2=], [n3=], [a=], [b=], &lt;r=/d=&gt;);</code>  
<code>[reuleaux\_polygon](shapes2d.scad#functionmodule-reuleaux_polygon)(N, r|d, ...);</code>  <code>path = [reuleaux\_polygon](shapes2d.scad#functionmodule-reuleaux_polygon)(N, r|d, ...);</code>  

### Section: Text

<code>[text](shapes2d.scad#module-text)([text](shapes2d.scad#module-text), [size], [font], ...);</code>  

### Section: Rounding 2D shapes

<code>[round2d](shapes2d.scad#module-round2d)(r) ...</code>  <code>[round2d](shapes2d.scad#module-round2d)(or) ...</code>  <code>[round2d](shapes2d.scad#module-round2d)(ir) ...</code>  <code>[round2d](shapes2d.scad#module-round2d)(or, ir) ...</code>  
<code>[shell2d](shapes2d.scad#module-shell2d)(thickness, [or], [ir], [fill], [round])</code>  

## LibFile: shapes3d.scad

### Section: Cuboids, Prismoids and Pyramids

<code>[cube](shapes3d.scad#functionmodule-cube)(size, [center], ...);</code>  <code>[cube](shapes3d.scad#functionmodule-cube)(size, [center], ...) { attachments }</code>  <code>vnf = [cube](shapes3d.scad#functionmodule-cube)(size, [center], ...);</code>  
<code>[cuboid](shapes3d.scad#module-cuboid)(size, [anchor=], [spin=], [orient=]);</code>  <code>[cuboid](shapes3d.scad#module-cuboid)(size, p1=, ...);</code>  <code>[cuboid](shapes3d.scad#module-cuboid)(p1=, p2=, ...);</code>  <code>[cuboid](shapes3d.scad#module-cuboid)(size, [chamfer=], [edges=], [except=], [trimcorners=], ...);</code>  <code>[cuboid](shapes3d.scad#module-cuboid)(size, [rounding=], [teardrop=], [edges=], [except=], [trimcorners=], ...);</code>  <code>[cuboid](shapes3d.scad#module-cuboid)(size, [anchor=], ...) [attachments];</code>  
<code>[prismoid](shapes3d.scad#functionmodule-prismoid)(size1, size2, h|l, [shift], ...);</code>  <code>[prismoid](shapes3d.scad#functionmodule-prismoid)(size1, size2, h|l, [shift], ...) [attachments];</code>  <code>[prismoid](shapes3d.scad#functionmodule-prismoid)(size1, size2, h|l, [chamfer=], ...);</code>  <code>[prismoid](shapes3d.scad#functionmodule-prismoid)(size1, size2, h|l, [chamfer1=], [chamfer2=], ...);</code>  <code>[prismoid](shapes3d.scad#functionmodule-prismoid)(size1, size2, h|l, [rounding=], ...);</code>  <code>[prismoid](shapes3d.scad#functionmodule-prismoid)(size1, size2, h|l, [rounding1=], [rounding2=], ...);</code>  <code>vnf = [prismoid](shapes3d.scad#functionmodule-prismoid)(size1, size2, h|l, [shift], [rounding], [chamfer]);</code>  <code>vnf = [prismoid](shapes3d.scad#functionmodule-prismoid)(size1, size2, h|l, [shift], [rounding1], [rounding2], [chamfer1], [chamfer2]);</code>  
<code>[octahedron](shapes3d.scad#functionmodule-octahedron)(size, ...);</code>  <code>[octahedron](shapes3d.scad#functionmodule-octahedron)(size, ...) { attachments }</code>  <code>vnf = [octahedron](shapes3d.scad#functionmodule-octahedron)(size, ...);</code>  
<code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, [center], [shift]);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, wall=, [center=]);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, isize=, wall=, [center=]);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size1=, size2=, wall=, ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, isize1=, isize2=, wall=, ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size1=, size2=, isize1=, isize2=, ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, chamfer=, ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, chamfer1=, chamfer2= ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, ichamfer=, ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, ichamfer1=, ichamfer2= ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, chamfer=, ichamfer=, ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, rounding=, ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, rounding1=, rounding2= ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, irounding=, ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, irounding1=, irounding2= ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, rounding=, irounding=, ...);</code>  <code>[rect\_tube](shapes3d.scad#module-rect_tube)(h, size, isize, ...) [attachments];</code>  
<code>[wedge](shapes3d.scad#functionmodule-wedge)(size, [center], ...);</code>  <code>[wedge](shapes3d.scad#functionmodule-wedge)(size, [center], ...) { attachments }</code>  <code>vnf = [wedge](shapes3d.scad#functionmodule-wedge)(size, [center], ...);</code>  

### Section: Cylinders

<code>[cylinder](shapes3d.scad#functionmodule-cylinder)(h, r=/d=, [center=], ...);</code>  <code>[cylinder](shapes3d.scad#functionmodule-cylinder)(h, r1/d1=, r2/d2=, [center=], ...);</code>  <code>[cylinder](shapes3d.scad#functionmodule-cylinder)(h, r=/d=, [center=]) {attachments}</code>  <code>vnf = [cylinder](shapes3d.scad#functionmodule-cylinder)(h, r=/d=, [center=], ...);</code>  <code>vnf = [cylinder](shapes3d.scad#functionmodule-cylinder)(h, r1/d1=, r2/d2=, [center=], ...);</code>  
<code>[cyl](shapes3d.scad#module-cyl)(l|h, r, [center], [circum=], [realign=]);</code>  <code>[cyl](shapes3d.scad#module-cyl)(l|h, d=, ...);</code>  <code>[cyl](shapes3d.scad#module-cyl)(l|h, r1=, r2=, ...);</code>  <code>[cyl](shapes3d.scad#module-cyl)(l|h, d1=, d2=, ...);</code>  <code>[cyl](shapes3d.scad#module-cyl)(l|h, r|d, chamfer=, [chamfang=], [from\_end=], ...);</code>  <code>[cyl](shapes3d.scad#module-cyl)(l|h, r|d, chamfer1=, [chamfang1=], [from\_end=], ...);</code>  <code>[cyl](shapes3d.scad#module-cyl)(l|h, r|d, chamfer2=, [chamfang2=], [from\_end=], ...);</code>  <code>[cyl](shapes3d.scad#module-cyl)(l|h, r|d, chamfer1=, chamfer2=, [chamfang1=], [chamfang2=], [from\_end=], ...);</code>  <code>[cyl](shapes3d.scad#module-cyl)(l|h, r|d, rounding=, ...);</code>  <code>[cyl](shapes3d.scad#module-cyl)(l|h, r|d, rounding1=, ...);</code>  <code>[cyl](shapes3d.scad#module-cyl)(l|h, r|d, rounding2=, ...);</code>  <code>[cyl](shapes3d.scad#module-cyl)(l|h, r|d, rounding1=, rounding2=, ...);</code>  
<code>[xcyl](shapes3d.scad#module-xcyl)(l|h, r, [anchor=]);</code>  <code>[xcyl](shapes3d.scad#module-xcyl)(l|h, d=, [anchor=]);</code>  <code>[xcyl](shapes3d.scad#module-xcyl)(l|h, r1=|d1=, r2=|d2=, [anchor=]);</code>  <code>[xcyl](shapes3d.scad#module-xcyl)(l|h, r, [anchor=]) [attachments];</code>  
<code>[ycyl](shapes3d.scad#module-ycyl)(l|h, r, [anchor=]);</code>  <code>[ycyl](shapes3d.scad#module-ycyl)(l|h, d=, [anchor=]);</code>  <code>[ycyl](shapes3d.scad#module-ycyl)(l|h, r1=|d1=, r2=|d2=, [anchor=]);</code>  <code>[ycyl](shapes3d.scad#module-ycyl)(l|h, r, [anchor=]) [attachments];</code>  
<code>[zcyl](shapes3d.scad#module-zcyl)(l|h, r, [anchor=]);</code>  <code>[zcyl](shapes3d.scad#module-zcyl)(l|h, d=, [anchor=]);</code>  <code>[zcyl](shapes3d.scad#module-zcyl)(l|h, r1=|d1=, r2=|d2=, [anchor=]);</code>  <code>[zcyl](shapes3d.scad#module-zcyl)(l|h, r, [anchor=]) [attachments];</code>  
<code>[tube](shapes3d.scad#module-tube)(h|l, or, ir, [center], [realign=]);</code>  <code>[tube](shapes3d.scad#module-tube)(h|l, or=|od=, ir=|id=, ...);</code>  <code>[tube](shapes3d.scad#module-tube)(h|l, ir|id, wall, ...);</code>  <code>[tube](shapes3d.scad#module-tube)(h|l, or|od, wall, ...);</code>  <code>[tube](shapes3d.scad#module-tube)(h|l, ir1|id1, ir2|id2, wall, ...);</code>  <code>[tube](shapes3d.scad#module-tube)(h|l, or1|od1, or2|od2, wall, ...);</code>  <code>[tube](shapes3d.scad#module-tube)(h|l, ir1|id1, ir2|id2, or1|od1, or2|od2, [realign]);</code>  <code>[tube](shapes3d.scad#module-tube)(h|l, or, ir, [center]) [attachments];</code>  
<code>[pie\_slice](shapes3d.scad#functionmodule-pie_slice)(l|h, r, ang, [center]);</code>  <code>[pie\_slice](shapes3d.scad#functionmodule-pie_slice)(l|h, d=, ang=, ...);</code>  <code>[pie\_slice](shapes3d.scad#functionmodule-pie_slice)(l|h, r1=|d1=, r2=|d2=, ang=, ...);</code>  <code>vnf = [pie\_slice](shapes3d.scad#functionmodule-pie_slice)(l|h, r, ang, [center]);</code>  <code>vnf = [pie\_slice](shapes3d.scad#functionmodule-pie_slice)(l|h, d=, ang=, ...);</code>  <code>vnf = [pie\_slice](shapes3d.scad#functionmodule-pie_slice)(l|h, r1=|d1=, r2=|d2=, ang=, ...);</code>  <code>[pie\_slice](shapes3d.scad#functionmodule-pie_slice)(l|h, r, ang, ...) [attachments];</code>  

### Section: Other Round Objects

<code>[sphere](shapes3d.scad#functionmodule-sphere)(r|d=, [circum=], [style=], ...);</code>  <code>[sphere](shapes3d.scad#functionmodule-sphere)(r|d=, ...) { attachments }</code>  <code>vnf = [sphere](shapes3d.scad#functionmodule-sphere)(r|d=, [circum=], [style=], ...);</code>  
<code>[spheroid](shapes3d.scad#functionmodule-spheroid)(r|d, [circum], [style]);</code>  <code>[spheroid](shapes3d.scad#functionmodule-spheroid)(r|d, [circum], [style]) [attachments];</code>  <code>vnf = [spheroid](shapes3d.scad#functionmodule-spheroid)(r|d, [circum], [style]);</code>  
<code>[torus](shapes3d.scad#functionmodule-torus)(r\_maj|d\_maj, r\_min|d\_min, [center], ...);</code>  <code>[torus](shapes3d.scad#functionmodule-torus)(or|od, ir|id, ...);</code>  <code>[torus](shapes3d.scad#functionmodule-torus)(r\_maj|d\_maj, or|od, ...);</code>  <code>[torus](shapes3d.scad#functionmodule-torus)(r\_maj|d\_maj, ir|id, ...);</code>  <code>[torus](shapes3d.scad#functionmodule-torus)(r\_min|d\_min, or|od, ...);</code>  <code>[torus](shapes3d.scad#functionmodule-torus)(r\_min|d\_min, ir|id, ...);</code>  <code>[torus](shapes3d.scad#functionmodule-torus)(or|od, ir|id, ...) [attachments];</code>  <code>vnf = [torus](shapes3d.scad#functionmodule-torus)(r\_maj|d\_maj, r\_min|d\_min, [center], ...);</code>  <code>vnf = [torus](shapes3d.scad#functionmodule-torus)(or|od, ir|id, ...);</code>  <code>vnf = [torus](shapes3d.scad#functionmodule-torus)(r\_maj|d\_maj, or|od, ...);</code>  <code>vnf = [torus](shapes3d.scad#functionmodule-torus)(r\_maj|d\_maj, ir|id, ...);</code>  <code>vnf = [torus](shapes3d.scad#functionmodule-torus)(r\_min|d\_min, or|od, ...);</code>  <code>vnf = [torus](shapes3d.scad#functionmodule-torus)(r\_min|d\_min, ir|id, ...);</code>  
<code>[teardrop](shapes3d.scad#functionmodule-teardrop)(h|l, r, [ang], [cap\_h], ...);</code>  <code>[teardrop](shapes3d.scad#functionmodule-teardrop)(h|l, d=, [ang=], [cap\_h=], ...);</code>  <code>[teardrop](shapes3d.scad#functionmodule-teardrop)(h|l, r1=, r2=, [ang=], [cap\_h1=], [cap\_h2=], ...);</code>  <code>[teardrop](shapes3d.scad#functionmodule-teardrop)(h|l, d1=, d2=, [ang=], [cap\_h1=], [cap\_h2=], ...);</code>  <code>[teardrop](shapes3d.scad#functionmodule-teardrop)(h|l, r, ...) [attachments];</code>  <code>vnf = [teardrop](shapes3d.scad#functionmodule-teardrop)(h|l=, r|d=, [ang=], [cap\_h=], ...);</code>  <code>vnf = [teardrop](shapes3d.scad#functionmodule-teardrop)(h|l=, r1=|d1=, r2=|d2=, [ang=], [cap\_h=], ...);</code>  <code>vnf = [teardrop](shapes3d.scad#functionmodule-teardrop)(h|l=, r1=|d1=, r2=|d2=, [ang=], [cap\_h1=], [cap\_h2=], ...);</code>  
<code>[onion](shapes3d.scad#functionmodule-onion)(r|d=, [ang=], [cap\_h=], ...);</code>  <code>[onion](shapes3d.scad#functionmodule-onion)(r, ...) [attachments];</code>  <code>vnf = [onion](shapes3d.scad#functionmodule-onion)(r|d=, [ang=], [cap\_h=], ...);</code>  

### Section: Text

<code>[text3d](shapes3d.scad#module-text3d)(text, [h], [size], [font], ...);</code>  
<code>[path\_text](shapes3d.scad#module-path_text)(path, text, [size], [thickness], [font], [lettersize], [offset], [reverse], [normal], [top], [textmetrics])</code>  

### Section: Miscellaneous

<code>[interior\_fillet](shapes3d.scad#module-interior_fillet)(l, r, [ang], [overlap], ...);</code>  <code>[interior\_fillet](shapes3d.scad#module-interior_fillet)(l, d=, [ang=], [overlap=], ...);</code>  <code>[interior\_fillet](shapes3d.scad#module-interior_fillet)(l, r, [ang], [overlap], ...) [attachments];</code>  
<code>[heightfield](shapes3d.scad#functionmodule-heightfield)(data, [size], [bottom], [maxz], [xrange], [yrange], [style], [convexity], ...);</code>  <code>[heightfield](shapes3d.scad#functionmodule-heightfield)(data, [size], ...) [attachments];</code>  <code>vnf = [heightfield](shapes3d.scad#functionmodule-heightfield)(data, [size], [bottom], [maxz], [xrange], [yrange], [style], ...);</code>  
<code>[ruler](shapes3d.scad#module-ruler)(length, width, [thickness=], [depth=], [labels=], [pipscale=], [maxscale=], [colors=], [alpha=], [unit=], [inch=]);</code>  

## LibFile: drawing.scad

### Section: Line Drawing

<code>[stroke](drawing.scad#module-stroke)(path, [width], [closed], [endcaps], [endcap\_width], [endcap\_length], [endcap\_extent], [trim]);</code>  <code>[stroke](drawing.scad#module-stroke)(path, [width], [closed], [endcap1], [endcap2], [endcap\_width1], [endcap\_width2], [endcap\_length1], [endcap\_length2], [endcap\_extent1], [endcap\_extent2], [trim1], [trim2]);</code>  
<code>[dashed\_stroke](drawing.scad#functionmodule-dashed_stroke)(path, dashpat, [closed=]);</code>  <code>dashes = [dashed\_stroke](drawing.scad#functionmodule-dashed_stroke)(path, dashpat, width=, [closed=]);</code>  

### Section: Computing paths

<code>[arc](drawing.scad#functionmodule-arc)(N, r|d=, angle);</code>  <code>[arc](drawing.scad#functionmodule-arc)(N, r|d=, angle=[START,END])</code>  <code>[arc](drawing.scad#functionmodule-arc)(N, r|d=, start=, angle=)</code>  <code>[arc](drawing.scad#functionmodule-arc)(N, width=, thickness=)</code>  <code>[arc](drawing.scad#functionmodule-arc)(N, cp=, points=[P0,P1], [long=], [cw=], [ccw=])</code>  <code>[arc](drawing.scad#functionmodule-arc)(N, points=[P0,P1,P2])</code>  
<code>[helix](drawing.scad#function-helix)([l|h], [turns], [angle], r|r1|r2, d|d1|d2)</code>  
<code>[turtle](drawing.scad#function-turtle)(commands, [state], [full\_state=], [repeat=])</code>  

### Section: Debugging polygons

<code>[debug\_polygon](drawing.scad#module-debug_polygon)(points, paths, [vertices=], [edges=], [convexity=], [size=]);</code>  

## LibFile: masks2d.scad

### Section: 2D Masking Shapes

<code>[mask2d\_roundover](masks2d.scad#functionmodule-mask2d_roundover)(r|d, [inset], [excess]);</code>  <code>[mask2d\_roundover](masks2d.scad#functionmodule-mask2d_roundover)(r|d, [inset], [excess]) { attachments }</code>  <code>path = [mask2d\_roundover](masks2d.scad#functionmodule-mask2d_roundover)(r|d, [inset], [excess]);</code>  
<code>[mask2d\_cove](masks2d.scad#functionmodule-mask2d_cove)(r|d, [inset], [excess]);</code>  <code>[mask2d\_cove](masks2d.scad#functionmodule-mask2d_cove)(r|d, [inset], [excess]) { attachments }</code>  <code>path = [mask2d\_cove](masks2d.scad#functionmodule-mask2d_cove)(r|d, [inset], [excess]);</code>  
<code>[mask2d\_chamfer](masks2d.scad#functionmodule-mask2d_chamfer)(edge, [angle], [inset], [excess]);</code>  <code>[mask2d\_chamfer](masks2d.scad#functionmodule-mask2d_chamfer)(y, [angle], [inset], [excess]);</code>  <code>[mask2d\_chamfer](masks2d.scad#functionmodule-mask2d_chamfer)(x, [angle], [inset], [excess]);</code>  <code>[mask2d\_chamfer](masks2d.scad#functionmodule-mask2d_chamfer)(edge, [angle], [inset], [excess]) { attachments }</code>  <code>path = [mask2d\_chamfer](masks2d.scad#functionmodule-mask2d_chamfer)(edge, [angle], [inset], [excess]);</code>  <code>path = [mask2d\_chamfer](masks2d.scad#functionmodule-mask2d_chamfer)(y, [angle], [inset], [excess]);</code>  <code>path = [mask2d\_chamfer](masks2d.scad#functionmodule-mask2d_chamfer)(x, [angle], [inset], [excess]);</code>  
<code>[mask2d\_rabbet](masks2d.scad#functionmodule-mask2d_rabbet)(size, [excess]);</code>  <code>[mask2d\_rabbet](masks2d.scad#functionmodule-mask2d_rabbet)(size, [excess]) { attachments }</code>  <code>path = [mask2d\_rabbet](masks2d.scad#functionmodule-mask2d_rabbet)(size, [excess]);</code>  
<code>[mask2d\_dovetail](masks2d.scad#functionmodule-mask2d_dovetail)(edge, [angle], [inset], [shelf], [excess], ...);</code>  <code>[mask2d\_dovetail](masks2d.scad#functionmodule-mask2d_dovetail)(x=, [angle=], [inset=], [shelf=], [excess=], ...);</code>  <code>[mask2d\_dovetail](masks2d.scad#functionmodule-mask2d_dovetail)(y=, [angle=], [inset=], [shelf=], [excess=], ...);</code>  <code>[mask2d\_dovetail](masks2d.scad#functionmodule-mask2d_dovetail)(edge, [angle], [inset], [shelf], ...) { attachments }</code>  <code>path = [mask2d\_dovetail](masks2d.scad#functionmodule-mask2d_dovetail)(edge, [angle], [inset], [shelf], [excess]);</code>  
<code>[mask2d\_teardrop](masks2d.scad#functionmodule-mask2d_teardrop)(r|d, [angle], [excess]);</code>  <code>[mask2d\_teardrop](masks2d.scad#functionmodule-mask2d_teardrop)(r|d, [angle], [excess]) { attachments }</code>  <code>path = [mask2d\_teardrop](masks2d.scad#functionmodule-mask2d_teardrop)(r|d, [angle], [excess]);</code>  
<code>[mask2d\_ogee](masks2d.scad#functionmodule-mask2d_ogee)(pattern, [excess], ...);</code>  <code>[mask2d\_ogee](masks2d.scad#functionmodule-mask2d_ogee)(pattern, [excess], ...) { attachments }</code>  <code>path = [mask2d\_ogee](masks2d.scad#functionmodule-mask2d_ogee)(pattern, [excess], ...);</code>  

## LibFile: masks3d.scad

### Section: Chamfer Masks

<code>[chamfer\_edge\_mask](masks3d.scad#module-chamfer_edge_mask)(l, chamfer, [excess]);</code>  
<code>[chamfer\_corner\_mask](masks3d.scad#module-chamfer_corner_mask)(chamfer);</code>  
<code>[chamfer\_cylinder\_mask](masks3d.scad#module-chamfer_cylinder_mask)(r|d, chamfer, [ang], [from\_end])</code>  

### Section: Rounding Masks

<code>[rounding\_edge\_mask](masks3d.scad#module-rounding_edge_mask)(l|h, r|d)</code>  <code>[rounding\_edge\_mask](masks3d.scad#module-rounding_edge_mask)(l|h, r1|d1, r2|d2)</code>  
<code>[rounding\_corner\_mask](masks3d.scad#module-rounding_corner_mask)(r|d, [excess=], [style=]);</code>  
<code>[rounding\_angled\_edge\_mask](masks3d.scad#module-rounding_angled_edge_mask)(h, r|d, [ang]);</code>  <code>[rounding\_angled\_edge\_mask](masks3d.scad#module-rounding_angled_edge_mask)(h, r1|d1, r2|d2, [ang]);</code>  
<code>[rounding\_angled\_corner\_mask](masks3d.scad#module-rounding_angled_corner_mask)(r|d, ang);</code>  
<code>[rounding\_cylinder\_mask](masks3d.scad#module-rounding_cylinder_mask)(r|d, rounding);</code>  
<code>[rounding\_hole\_mask](masks3d.scad#module-rounding_hole_mask)(r|d, rounding, [excess]);</code>  

### Section: Teardrop Masking

<code>[teardrop\_edge\_mask](masks3d.scad#module-teardrop_edge_mask)(r|d, [angle], [excess]);</code>  
<code>[teardrop\_corner\_mask](masks3d.scad#module-teardrop_corner_mask)(r|d, [angle], [excess]);</code>  

## LibFile: distributors.scad

### Section: Translating copies of all the children

<code>[move\_copies](distributors.scad#module-move_copies)(a) ...</code>  
<code>[line\_of](distributors.scad#functionmodule-line_of)(spacing, [n], [p1=]) ...</code>  <code>[line\_of](distributors.scad#functionmodule-line_of)(spacing, [l=], [p1=]) ...</code>  <code>[line\_of](distributors.scad#functionmodule-line_of)([n=], [l=], [p1=]) ...</code>  <code>[line\_of](distributors.scad#functionmodule-line_of)([n=], [p1=], [p2=]) ...</code>  <code>[line\_of](distributors.scad#functionmodule-line_of)([spacing], [p1=], [p2=]) ...</code>  <code>pts = [line\_of](distributors.scad#functionmodule-line_of)([spacing], [n], [p1=]);</code>  <code>pts = [line\_of](distributors.scad#functionmodule-line_of)([spacing], [l=], [p1=]);</code>  <code>pts = [line\_of](distributors.scad#functionmodule-line_of)([n=], [l=], [p1=]);</code>  <code>pts = [line\_of](distributors.scad#functionmodule-line_of)([n=], [p1=], [p2=]);</code>  <code>pts = [line\_of](distributors.scad#functionmodule-line_of)([spacing], [p1=], [p2=]);</code>  
<code>[xcopies](distributors.scad#module-xcopies)(spacing, [n], [sp]) ...</code>  <code>[xcopies](distributors.scad#module-xcopies)(l, [n], [sp]) ...</code>  
<code>[ycopies](distributors.scad#module-ycopies)(spacing, [n], [sp]) ...</code>  <code>[ycopies](distributors.scad#module-ycopies)(l, [n], [sp]) ...</code>  
<code>[zcopies](distributors.scad#module-zcopies)(spacing, [n], [sp]) ...</code>  <code>[zcopies](distributors.scad#module-zcopies)(l, [n], [sp]) ...</code>  
<code>[grid2d](distributors.scad#module-grid2d)(spacing, size, [stagger], [scale], [inside]) ...</code>  <code>[grid2d](distributors.scad#module-grid2d)(n, size, [stagger], [scale], [inside]) ...</code>  <code>[grid2d](distributors.scad#module-grid2d)(spacing, n, [stagger], [scale], [inside]) ...</code>  <code>[grid2d](distributors.scad#module-grid2d)(spacing, inside, [stagger], [scale]) ...</code>  <code>[grid2d](distributors.scad#module-grid2d)(n, inside, [stagger], [scale]) ...</code>  
<code>[grid3d](distributors.scad#module-grid3d)(n, spacing) ...</code>  <code>[grid3d](distributors.scad#module-grid3d)(n=[Xn,Yn,Zn], spacing=[dX,dY,dZ]) ...</code>  <code>[grid3d](distributors.scad#module-grid3d)([xa], [ya], [za]) ...</code>  

### Section: Rotating copies of all children

<code>[rot\_copies](distributors.scad#module-rot_copies)(rots, [cp], [sa], [delta], [subrot]) ...</code>  <code>[rot\_copies](distributors.scad#module-rot_copies)(rots, v, [cp], [sa], [delta], [subrot]) ...</code>  <code>[rot\_copies](distributors.scad#module-rot_copies)(n, [v], [cp], [sa], [delta], [subrot]) ...</code>  
<code>[xrot\_copies](distributors.scad#module-xrot_copies)(rots, [r], [cp], [sa], [subrot]) ...</code>  <code>[xrot\_copies](distributors.scad#module-xrot_copies)(n, [r], [cp], [sa], [subrot]) ...</code>  
<code>[yrot\_copies](distributors.scad#module-yrot_copies)(rots, [r], [cp], [sa], [subrot]) ...</code>  <code>[yrot\_copies](distributors.scad#module-yrot_copies)(n, [r], [cp], [sa], [subrot]) ...</code>  
<code>[zrot\_copies](distributors.scad#module-zrot_copies)(rots, [r], [cp], [sa], [subrot]) ...</code>  <code>[zrot\_copies](distributors.scad#module-zrot_copies)(n, [r], [cp], [sa], [subrot]) ...</code>  
<code>[arc\_of](distributors.scad#module-arc_of)(r|d, n, [sa], [ea], [rot]</code>  <code>[arc\_of](distributors.scad#module-arc_of)(rx|dx, ry|dy, n, [sa], [ea], [rot]</code>  
<code>[ovoid\_spread](distributors.scad#module-ovoid_spread)(r|d, n, [cone\_ang], [scale], [perp]) ...</code>  

### Section: Placing copies of all children on a path

<code>[path\_spread](distributors.scad#module-path_spread)(path), [n], [spacing], [sp], [rotate\_children], [closed]) ...</code>  

### Section: Making a copy of all children with reflection

<code>[mirror\_copy](distributors.scad#module-mirror_copy)(v, [cp], [offset]) ...</code>  
<code>[xflip\_copy](distributors.scad#module-xflip_copy)([x], [offset]) ...</code>  
<code>[yflip\_copy](distributors.scad#module-yflip_copy)([y], [offset]) ...</code>  
<code>[zflip\_copy](distributors.scad#module-zflip_copy)([z], [offset]) ...</code>  

### Section: Distributing children individually along a line

<code>[distribute](distributors.scad#module-distribute)(spacing, dir, [sizes]) ...</code>  <code>[distribute](distributors.scad#module-distribute)(l, dir, [sizes]) ...</code>  
<code>[xdistribute](distributors.scad#module-xdistribute)(spacing, [sizes]) ...</code>  <code>[xdistribute](distributors.scad#module-xdistribute)(l, [sizes]) ...</code>  
<code>[ydistribute](distributors.scad#module-ydistribute)(spacing, [sizes])</code>  <code>[ydistribute](distributors.scad#module-ydistribute)(l, [sizes])</code>  
<code>[zdistribute](distributors.scad#module-zdistribute)(spacing, [sizes])</code>  <code>[zdistribute](distributors.scad#module-zdistribute)(l, [sizes])</code>  

## LibFile: color.scad

### Section: Coloring Objects

<code>[rainbow](color.scad#module-rainbow)(list) ...</code>  

### Section: Colorspace Conversion

<code>[HSL](color.scad#functionmodule-hsl)(h,[s],[l],[a]) ...</code>  <code>rgb = [HSL](color.scad#functionmodule-hsl)(h,[s],[l]);</code>  
<code>[HSV](color.scad#functionmodule-hsv)(h,[s],[v],[a]) ...</code>  <code>rgb = [HSV](color.scad#functionmodule-hsv)(h,[s],[v]);</code>  

## LibFile: partitions.scad

### Section: Planar Cutting

<code>[half\_of](partitions.scad#functionmodule-half_of)(v, [cp], [s], [planar]) ...</code>  <code>result = [half\_of](partitions.scad#functionmodule-half_of)(p,v,[cp]);</code>  
<code>[left\_half](partitions.scad#functionmodule-left_half)([s], [x]) ...</code>  <code>[left\_half](partitions.scad#functionmodule-left_half)(planar=true, [s], [x]) ...</code>  <code>result = [left\_half](partitions.scad#functionmodule-left_half)(p, [x]);</code>  
<code>[right\_half](partitions.scad#functionmodule-right_half)([s=], [x=]) ...</code>  <code>[right\_half](partitions.scad#functionmodule-right_half)(planar=true, [s=], [x=]) ...</code>  <code>result = [right\_half](partitions.scad#functionmodule-right_half)(p=, [x=]);</code>  
<code>[front\_half](partitions.scad#functionmodule-front_half)([s], [y]) ...</code>  <code>[front\_half](partitions.scad#functionmodule-front_half)(planar=true, [s], [y]) ...</code>  <code>result = [front\_half](partitions.scad#functionmodule-front_half)(p, [y]);</code>  
<code>[back\_half](partitions.scad#functionmodule-back_half)([s], [y]) ...</code>  <code>[back\_half](partitions.scad#functionmodule-back_half)(planar=true, [s], [y]) ...</code>  <code>result = [back\_half](partitions.scad#functionmodule-back_half)(p, [y]);</code>  
<code>[bottom\_half](partitions.scad#functionmodule-bottom_half)([s], [z]) ...</code>  <code>result = [bottom\_half](partitions.scad#functionmodule-bottom_half)(p, [z]);</code>  
<code>[top\_half](partitions.scad#functionmodule-top_half)([s], [z]) ...</code>  <code>result = [top\_half](partitions.scad#functionmodule-top_half)(p, [z]);</code>  

### Section: Partioning into Interlocking Pieces

<code>[partition\_mask](partitions.scad#module-partition_mask)(l, w, h, [cutsize], [cutpath], [gap], [inverse], [spin], [orient],);</code>  
<code>[partition\_cut\_mask](partitions.scad#module-partition_cut_mask)(l, w, h, [cutsize], [cutpath], [gap], [inverse], [spin], [orient]);</code>  
<code>[partition](partitions.scad#module-partition)(size, [spread], [cutsize], [cutpath], [gap], [spin]) ...</code>  

## LibFile: mutators.scad

### Section: Bounding Box

<code>[bounding\_box](mutators.scad#module-bounding_box)() ...</code>  

### Section: Warp Mutators

<code>[chain\_hull](mutators.scad#module-chain_hull)() ...</code>  
<code>[path\_extrude2d](mutators.scad#module-path_extrude2d)(path, [caps], [closed]) {...}</code>  
<code>[cylindrical\_extrude](mutators.scad#module-cylindrical_extrude)(size, ir|id, or|od, [convexity]) ...</code>  

### Section: Offset Mutators

<code>[minkowski\_difference](mutators.scad#module-minkowski_difference)() { base\_shape(); diff\_shape(); ... }</code>  
<code>[offset3d](mutators.scad#module-offset3d)(r, [size], [convexity]);</code>  
<code>[round3d](mutators.scad#module-round3d)(r) ...</code>  <code>[round3d](mutators.scad#module-round3d)(or) ...</code>  <code>[round3d](mutators.scad#module-round3d)(ir) ...</code>  <code>[round3d](mutators.scad#module-round3d)(or, ir) ...</code>  

## LibFile: paths.scad

### Section: Utility Functions

<code>[is\_path](paths.scad#function-is_path)(list, [dim], [fast])</code>  
<code>bool = [is\_1region](paths.scad#function-is_1region)(path, [name])</code>  
<code>outpath = [force\_path](paths.scad#function-force_path)(path, [name])</code>  
<code>[is\_closed\_path](paths.scad#function-is_closed_path)(path, [eps]);</code>  
<code>[close\_path](paths.scad#function-close_path)(path);</code>  
<code>[cleanup\_path](paths.scad#function-cleanup_path)(path);</code>  
<code>[path\_merge\_collinear](paths.scad#function-path_merge_collinear)(path, [eps])</code>  

### Section: Path length calculation

<code>[path\_length](paths.scad#function-path_length)(path,[closed])</code>  
<code>[path\_segment\_lengths](paths.scad#function-path_segment_lengths)(path,[closed])</code>  
<code>fracs = [path\_length\_fractions](paths.scad#function-path_length_fractions)(path, [closed]);</code>  

### Section: Resampling---changing the number of points in a path

<code>newpath = [subdivide\_path](paths.scad#function-subdivide_path)(path, [N|refine], method, [closed], [exact]);</code>  
<code>spath = [subdivide\_long\_segments](paths.scad#function-subdivide_long_segments)(path, maxlen, [closed=]);</code>  
<code>newpath = [resample\_path](paths.scad#function-resample_path)(path, N|spacing, [closed]);</code>  

### Section: Path Geometry

<code>bool = [is\_path\_simple](paths.scad#function-is_path_simple)(path, [closed], [eps]);</code>  
<code>[path\_closest\_point](paths.scad#function-path_closest_point)(path, pt);</code>  
<code>tangs = [path\_tangents](paths.scad#function-path_tangents)(path, [closed], [uniform]);</code>  
<code>norms = [path\_normals](paths.scad#function-path_normals)(path, [tangents], [closed]);</code>  
<code>curvs = [path\_curvature](paths.scad#function-path_curvature)(path, [closed]);</code>  
<code>torsions = [path\_torsion](paths.scad#function-path_torsion)(path, [closed]);</code>  

### Section: Breaking paths up into subpaths

<code>path\_list = [path\_cut](paths.scad#function-path_cut)(path, cutdist, [closed=]);</code>  
<code>paths = [split\_path\_at\_self\_crossings](paths.scad#function-split_path_at_self_crossings)(path, [closed], [eps]);</code>  
<code>splitpolys = [polygon\_parts](paths.scad#function-polygon_parts)(poly, [nonzero], [eps]);</code>  

## LibFile: regions.scad

### Section: Regions

<code>[is\_region](regions.scad#function-is_region)(x);</code>  
<code>bool = [is\_valid\_region](regions.scad#function-is_valid_region)(region, [eps]);</code>  
<code>bool = [is\_region\_simple](regions.scad#function-is_region_simple)(region, [eps]);</code>  
<code>region = [make\_region](regions.scad#function-make_region)(polys, [nonzero], [eps]);</code>  
<code>region = [force\_region](regions.scad#function-force_region)(poly)</code>  

### Section: Turning a region into geometry

<code>[region](regions.scad#module-region)(r, [anchor], [spin], [cp]) { ... };</code>  

### Section: Gometrical calculations with regions

<code>check = [point\_in\_region](regions.scad#function-point_in_region)(point, region, [eps]);</code>  
<code>area=[region\_area](regions.scad#function-region_area)(region);</code>  
<code>b = [are\_regions\_equal](regions.scad#function-are_regions_equal)(region1, region2, [eps])</code>  

### Section: Breaking up regions into subregions

<code>split\_region = [split\_region\_at\_region\_crossings](regions.scad#function-split_region_at_region_crossings)(region1, region2, [closed1], [closed2], [eps])</code>  
<code>rgns = [region\_parts](regions.scad#function-region_parts)(region);</code>  

### Section: Offset and 2D Boolean Set Operations

<code>[offset](regions.scad#function-offset)path = [offset](regions.scad#function-offset)(path, [r|delta], [chamfer], [closed], [check\_valid], [quality])</code>  <code>path\_faces = [offset](regions.scad#function-offset)(path, return\_faces=true, [r|delta], [chamfer], [closed], [check\_valid], [quality], [firstface\_index], [flip\_faces])</code>  
<code>[union](regions.scad#functionmodule-union)() {...}</code>  <code>region = [union](regions.scad#functionmodule-union)(regions);</code>  <code>region = [union](regions.scad#functionmodule-union)(REGION1,REGION2);</code>  <code>region = [union](regions.scad#functionmodule-union)(REGION1,REGION2,REGION3);</code>  
<code>[difference](regions.scad#functionmodule-difference)() {...}</code>  <code>region = [difference](regions.scad#functionmodule-difference)(regions);</code>  <code>region = [difference](regions.scad#functionmodule-difference)(REGION1,REGION2);</code>  <code>region = [difference](regions.scad#functionmodule-difference)(REGION1,REGION2,REGION3);</code>  
<code>[intersection](regions.scad#functionmodule-intersection)() {...}</code>  <code>region = [intersection](regions.scad#functionmodule-intersection)(regions);</code>  <code>region = [intersection](regions.scad#functionmodule-intersection)(REGION1,REGION2);</code>  <code>region = [intersection](regions.scad#functionmodule-intersection)(REGION1,REGION2,REGION3);</code>  
<code>[exclusive\_or](regions.scad#functionmodule-exclusive_or)() {...}</code>  <code>region = [exclusive\_or](regions.scad#functionmodule-exclusive_or)(regions);</code>  <code>region = [exclusive\_or](regions.scad#functionmodule-exclusive_or)(REGION1,REGION2);</code>  <code>region = [exclusive\_or](regions.scad#functionmodule-exclusive_or)(REGION1,REGION2,REGION3);</code>  

## LibFile: vnf.scad

### Section: Creating Polyhedrons with VNF Structures

<code>vnf = [vnf\_vertex\_array](vnf.scad#function-vnf_vertex_array)(points, [caps], [cap1], [cap2], [style], [reverse], [col\_wrap], [row\_wrap]);</code>  
<code>vnf = [vnf\_tri\_array](vnf.scad#function-vnf_tri_array)(points, [row\_wrap], [reverse])</code>  
<code>vnf = [vnf\_join](vnf.scad#function-vnf_join)([VNF, VNF, VNF, ...]);</code>  
<code>vnf = [vnf\_from\_polygons](vnf.scad#function-vnf_from_polygons)(polygons);</code>  
<code>vnf = [vnf\_from\_region](vnf.scad#function-vnf_from_region)(region, [transform], [reverse]);</code>  

### Section: VNF Testing and Access

<code>bool = [is\_vnf](vnf.scad#function-is_vnf)(x);</code>  

### Section: Altering the VNF Internals

<code>rvnf = [vnf\_reverse\_faces](vnf.scad#function-vnf_reverse_faces)(vnf);</code>  
<code>vnf2 = [vnf\_quantize](vnf.scad#function-vnf_quantize)(vnf,[q]);</code>  
<code>new\_vnf = [vnf\_merge\_points](vnf.scad#function-vnf_merge_points)(vnf, [eps]);</code>  
<code>clean\_vnf=[vnf\_drop\_unused\_points](vnf.scad#function-vnf_drop_unused_points)(vnf);</code>  
<code>vnf2 = [vnf\_triangulate](vnf.scad#function-vnf_triangulate)(vnf);</code>  
<code>sliced = [vnf\_slice](vnf.scad#function-vnf_slice)(vnf, dir, cuts);</code>  

### Section: Turning a VNF into geometry

<code>[vnf\_polyhedron](vnf.scad#module-vnf_polyhedron)(vnf);</code>  <code>[vnf\_polyhedron](vnf.scad#module-vnf_polyhedron)([VNF, VNF, VNF, ...]);</code>  
<code>[vnf\_wireframe](vnf.scad#module-vnf_wireframe)(vnf, [width]);</code>  

### Section: Operations on VNFs

<code>vol = [vnf\_volume](vnf.scad#function-vnf_volume)(vnf);</code>  
<code>area = [vnf\_area](vnf.scad#function-vnf_area)(vnf);</code>  
<code>newvnf = [vnf\_halfspace](vnf.scad#function-vnf_halfspace)(plane, vnf, [closed]);</code>  
<code>bentvnf = [vnf\_bend](vnf.scad#function-vnf_bend)(vnf,r,d,[axis]);</code>  

### Section: Debugging Polyhedrons

<code>[debug\_vnf](vnf.scad#module-debug_vnf)(vnfs, [faces], [vertices], [opacity], [size], [convexity]);</code>  
<code>fails = [vnf\_validate](vnf.scad#functionmodule-vnf_validate)(vnf);</code>  <code>[vnf\_validate](vnf.scad#functionmodule-vnf_validate)(vnf, [size]);</code>  

## LibFile: beziers.scad

### Section: Bezier Curves

<code>pt = [bezier\_points](beziers.scad#function-bezier_points)(bezier, u);</code>  <code>ptlist = [bezier\_points](beziers.scad#function-bezier_points)(bezier, RANGE);</code>  <code>ptlist = [bezier\_points](beziers.scad#function-bezier_points)(bezier, LIST);</code>  
<code>path = [bezier\_curve](beziers.scad#function-bezier_curve)(bezier, [splinesteps], [endpoint]);</code>  
<code>deriv = [bezier\_derivative](beziers.scad#function-bezier_derivative)(bezier, u, [order]);</code>  <code>derivs = [bezier\_derivative](beziers.scad#function-bezier_derivative)(bezier, LIST, [order]);</code>  <code>derivs = [bezier\_derivative](beziers.scad#function-bezier_derivative)(bezier, RANGE, [order]);</code>  
<code>tanvec = [bezier\_tangent](beziers.scad#function-bezier_tangent)(bezier, u);</code>  <code>tanvecs = [bezier\_tangent](beziers.scad#function-bezier_tangent)(bezier, LIST);</code>  <code>tanvecs = [bezier\_tangent](beziers.scad#function-bezier_tangent)(bezier, RANGE);</code>  
<code>crv = [bezier\_curvature](beziers.scad#function-bezier_curvature)(curve, u);</code>  <code>crvlist = [bezier\_curvature](beziers.scad#function-bezier_curvature)(curve, LIST);</code>  <code>crvlist = [bezier\_curvature](beziers.scad#function-bezier_curvature)(curve, RANGE);</code>  
<code>u = [bezier\_closest\_point](beziers.scad#function-bezier_closest_point)(bezier, pt, [max\_err]);</code>  
<code>pathlen = [bezier\_length](beziers.scad#function-bezier_length)(bezier, [start\_u], [end\_u], [max\_deflect]);</code>  
<code>u = [bezier\_line\_intersection](beziers.scad#function-bezier_line_intersection)(curve, line);</code>  

### Section: Bezier Path Functions

<code>pt = [bezpath\_points](beziers.scad#function-bezpath_points)(bezpath, curveind, u, [N]);</code>  <code>ptlist = [bezpath\_points](beziers.scad#function-bezpath_points)(bezpath, curveind, LIST, [N]);</code>  <code>path = [bezpath\_points](beziers.scad#function-bezpath_points)(bezpath, curveind, RANGE, [N]);</code>  
<code>path = [bezpath\_curve](beziers.scad#function-bezpath_curve)(bezpath, [splinesteps], [N], [endpoint])</code>  
<code>res = [bezpath\_closest\_point](beziers.scad#function-bezpath_closest_point)(bezpath, pt, [N], [max\_err]);</code>  
<code>plen = [bezpath\_length](beziers.scad#function-bezpath_length)(path, [N], [max\_deflect]);</code>  
<code>bezpath = [path\_to\_bezpath](beziers.scad#function-path_to_bezpath)(path, [closed], [tangents], [uniform], [size=]|[relsize=]);</code>  
<code>bezpath = [bezpath\_close\_to\_axis](beziers.scad#function-bezpath_close_to_axis)(bezpath, [axis], [N]);</code>  
<code>bezpath = [bezpath\_offset](beziers.scad#function-bezpath_offset)(offset, bezier, [N]);</code>  

### Section: Cubic Bezier Path Construction

<code>pts = [bez\_begin](beziers.scad#function-bez_begin)(pt, a, r, [p=]);</code>  <code>pts = [bez\_begin](beziers.scad#function-bez_begin)(pt, VECTOR, [r], [p=]);</code>  
<code>pts = [bez\_tang](beziers.scad#function-bez_tang)(pt, a, r1, r2, [p=]);</code>  <code>pts = [bez\_tang](beziers.scad#function-bez_tang)(pt, VECTOR, [r1], [r2], [p=]);</code>  
<code>pts = [bez\_joint](beziers.scad#function-bez_joint)(pt, a1, a2, r1, r2, [p1=], [p2=]);</code>  <code>pts = [bez\_joint](beziers.scad#function-bez_joint)(pt, VEC1, VEC2, [r1=], [r2=], [p1=], [p2=]);</code>  
<code>pts = [bez\_end](beziers.scad#function-bez_end)(pt, a, r, [p=]);</code>  <code>pts = [bez\_end](beziers.scad#function-bez_end)(pt, VECTOR, [r], [p=]);</code>  

### Section: Bezier Surfaces

<code>bool = [is\_bezier\_patch](beziers.scad#function-is_bezier_patch)(x);</code>  
<code>patch = [bezier\_patch\_flat](beziers.scad#function-bezier_patch_flat)(size, [N=], [spin=], [orient=], [trans=]);</code>  
<code>rpatch = [bezier\_patch\_reverse](beziers.scad#function-bezier_patch_reverse)(patch);</code>  
<code>pt = [bezier\_patch\_points](beziers.scad#function-bezier_patch_points)(patch, u, v);</code>  <code>ptgrid = [bezier\_patch\_points](beziers.scad#function-bezier_patch_points)(patch, LIST, LIST);</code>  <code>ptgrid = [bezier\_patch\_points](beziers.scad#function-bezier_patch_points)(patch, RANGE, RANGE);</code>  
<code>vnf = [bezier\_vnf](beziers.scad#function-bezier_vnf)(patches, [splinesteps], [style]);</code>  
<code>vnf = [bezier\_vnf\_degenerate\_patch](beziers.scad#function-bezier_vnf_degenerate_patch)(patch, [splinesteps], [reverse]);</code>  <code>vnf\_edges = [bezier\_vnf\_degenerate\_patch](beziers.scad#function-bezier_vnf_degenerate_patch)(patch, [splinesteps], [reverse], return\_edges=true);</code>  

### Section: Debugging Beziers

<code>[debug\_bezier](beziers.scad#module-debug_bezier)(bez, [size], [N=]);</code>  
<code>[debug\_bezier\_patches](beziers.scad#module-debug_bezier_patches)(patches, [size=], [splinesteps=], [showcps=], [showdots=], [showpatch=], [convexity=], [style=]);</code>  

## LibFile: rounding.scad

### Section: Rounding Paths

<code>rounded\_path = [round\_corners](rounding.scad#function-round_corners)(path, [method], [radius=], [cut=], [joint=], [closed=], [verbose=]);</code>  
<code>smoothed = [smooth\_path](rounding.scad#function-smooth_path)(path, [tangents], &lt;size=|relsize=&gt;, [splinesteps=], [closed=], [uniform=]);</code>  
<code>joined\_path = [path\_join](rounding.scad#function-path_join)(paths, [joint], [k=], [relocate=], [closed=]);</code>  
<code>[offset\_stroke](rounding.scad#functionmodule-offset_stroke)(path, [width], [rounded=], [chamfer=], [start=], [end=], [check\_valid=], [quality=], [closed=]);</code>  <code>path = [offset\_stroke](rounding.scad#functionmodule-offset_stroke)(path, [width], closed=false, [rounded=], [chamfer=], [start=], [end=], [check\_valid=], [quality=]);</code>  <code>region = [offset\_stroke](rounding.scad#functionmodule-offset_stroke)(path, [width], closed=true, [rounded=], [chamfer=], [start=], [end=], [check\_valid=], [quality=]);</code>  

### Section: Three-Dimensional Rounding

<code>[offset\_sweep](rounding.scad#functionmodule-offset_sweep)(path, &lt;height|h|l&gt;, [bottom], [top], [offset=], [convexity=],...) [attachments]</code>  <code>vnf = [offset\_sweep](rounding.scad#functionmodule-offset_sweep)(path, &lt;height|h|l&gt;, [bottom], [top], [offset=], ...)</code>  
<code>[rounded\_prism](rounding.scad#functionmodule-rounded_prism)(bottom, [top], &lt;height=|h=|length=|l=&gt;, [joint\_top=], [joint\_bot=], [joint\_sides=], [k=], [k\_top=], [k\_bot=], [k\_sides=], [splinesteps=], [debug=], [convexity=],...) [attachments];</code>  <code>vnf = [rounded\_prism](rounding.scad#functionmodule-rounded_prism)(bottom, [top], &lt;height=|h=|length=|l=&gt;, [joint\_top=], [joint\_bot=], [joint\_sides=], [k=], [k\_top=], [k\_bot=], [k\_sides=], [splinesteps=], [debug=]);</code>  
<code>[bent\_cutout\_mask](rounding.scad#module-bent_cutout_mask)(r|radius, thickness, path);</code>  

## LibFile: skin.scad

### Section: Skin and sweep

<code>[skin](skin.scad#functionmodule-skin)(profiles, slices, [z=], [refine=], [method=], [sampling=], [caps=], [closed=], [style=], [convexity=], [anchor=],[cp=],[spin=],[orient=],[atype=]) {attachments};</code>  <code>vnf = [skin](skin.scad#functionmodule-skin)(profiles, slices, [z=], [refine=], [method=], [sampling=], [caps=], [closed=], [style=], [anchor=],[cp=],[spin=],[orient=],[atype=]);</code>  
<code>[linear\_sweep](skin.scad#functionmodule-linear_sweep)(region, height, [center], [slices], [twist], [scale], [style], [convexity]) {attachments};</code>  
<code>[spiral\_sweep](skin.scad#functionmodule-spiral_sweep)(poly, h, r, turns, [higbee], [center], [r1], [r2], [d], [d1], [d2], [higbee1], [higbee2], [internal], [anchor], [spin], [orient]);</code>  <code>vnf = [spiral\_sweep](skin.scad#functionmodule-spiral_sweep)(poly, h, r, turns, ...);</code>  
<code>[path\_sweep](skin.scad#functionmodule-path_sweep)(shape, path, [method], [normal=], [closed=], [twist=], [twist\_by\_length=], [symmetry=], [last\_normal=], [tangent=], [uniform=], [relaxed=], [caps=], [style=], [convexity=], [anchor=], [cp=], [spin=], [orient=], [atype=]) {attachments};</code>  <code>vnf = [path\_sweep](skin.scad#functionmodule-path_sweep)(shape, path, [method], [normal=], [closed=], [twist=], [twist\_by\_length=], [symmetry=], [last\_normal=], [tangent=], [uniform=], [relaxed=], [caps=], [style=], [transforms=], [anchor=], [cp=], [spin=], [orient=], [atype=]) {attachments};</code>  
<code>[path\_sweep2d](skin.scad#functionmodule-path_sweep2d)(shape, path, [closed], [caps], [quality], [style], [convexity=], [anchor=], [spin=], [orient=], [atype=], [cp=]) {attachments};</code>  <code>vnf = [path\_sweep2d](skin.scad#functionmodule-path_sweep2d)(shape, path, [closed], [caps], [quality], [style], [anchor=], [spin=], [orient=], [atype=], [cp=]);</code>  
<code>[sweep](skin.scad#functionmodule-sweep)(shape, transforms, [closed], [caps], [style], [convexity=], [anchor=], [spin=], [orient=], [atype=]) [attachments];</code>  <code>vnf = [sweep](skin.scad#functionmodule-sweep)(shape, transforms, [closed], [caps], [style], [anchor=], [spin=], [orient=], [atype=]);</code>  

### Section: Functions for resampling and slicing profile lists

<code>newprof = [subdivide\_and\_slice](skin.scad#function-subdivide_and_slice)(profiles, slices, [numpoints], [method], [closed]);</code>  
<code>profs = [slice\_profiles](skin.scad#function-slice_profiles)(profiles, slices, [closed]);</code>  
<code>rlist = [rot\_resample](skin.scad#function-rot_resample)(rotlist, N, [method], [twist], [scale], [smoothlen], [long], [turns], [closed])</code>  
<code>newpoly = [associate\_vertices](skin.scad#function-associate_vertices)(polygons, split);</code>  

## LibFile: turtle3d.scad

### Section: Functions

<code>[turtle3d](turtle3d.scad#function-turtle3d)(commands, [state], [transforms], [full\_state], [repeat])</code>  

## LibFile: math.scad

### Section: Math Constants

Constants: [`PHI`](math.scad#constant-phi) [`EPSILON`](math.scad#constant-epsilon) [`INF`](math.scad#constant-inf) [`NAN`](math.scad#constant-nan)

### Section: Simple math

<code>x2 = [sqr](math.scad#function-sqr)(x);</code>  
<code>foo = [log2](math.scad#function-log2)(x);</code>  
<code>l = [hypot](math.scad#function-hypot)(x, y, [z]);</code>  
<code>x = [factorial](math.scad#function-factorial)(n, [d]);</code>  
<code>x = [binomial](math.scad#function-binomial)(n);</code>  
<code>x = [binomial\_coefficient](math.scad#function-binomial_coefficient)(n, k);</code>  
<code>x = [lerp](math.scad#function-lerp)(a, b, u);</code>  <code>l = [lerp](math.scad#function-lerp)(a, b, LIST);</code>  
<code>x = [lerpn](math.scad#function-lerpn)(a, b, n);</code>  <code>x = [lerpn](math.scad#function-lerpn)(a, b, n, [endpoint]);</code>  

### Section: Undef Safe Math

<code>x = [u\_add](math.scad#function-u_add)(a, b);</code>  
<code>x = [u\_sub](math.scad#function-u_sub)(a, b);</code>  
<code>x = [u\_mul](math.scad#function-u_mul)(a, b);</code>  
<code>x = [u\_div](math.scad#function-u_div)(a, b);</code>  

### Section: Hyperbolic Trigonometry

<code>a = [sinh](math.scad#function-sinh)(x);</code>  
<code>a = [cosh](math.scad#function-cosh)(x);</code>  
<code>a = [tanh](math.scad#function-tanh)(x);</code>  
<code>a = [asinh](math.scad#function-asinh)(x);</code>  
<code>a = [acosh](math.scad#function-acosh)(x);</code>  
<code>a = [atanh](math.scad#function-atanh)(x);</code>  

### Section: Quantization

<code>num = [quant](math.scad#function-quant)(x, y);</code>  
<code>num = [quantdn](math.scad#function-quantdn)(x, y);</code>  
<code>num = [quantup](math.scad#function-quantup)(x, y);</code>  

### Section: Constraints and Modulos

<code>val = [constrain](math.scad#function-constrain)(v, minval, maxval);</code>  
<code>mod = [posmod](math.scad#function-posmod)(x, m)</code>  
<code>ang = [modang](math.scad#function-modang)(x);</code>  

### Section: Random Number Generation

<code>[rand\_int](math.scad#function-rand_int)(minval, maxval, N, [seed]);</code>  
<code>points = [random\_points](math.scad#function-random_points)([N], [dim], [scale], [seed]);</code>  
<code>arr = [gaussian\_rands](math.scad#function-gaussian_rands)([N],[mean], [cov], [seed]);</code>  
<code>points = [spherical\_random\_points](math.scad#function-spherical_random_points)([N], [radius], [seed]);</code>  
<code>points = [random\_polygon](math.scad#function-random_polygon)(n, size, [seed]);</code>  

### Section: GCD/GCF, LCM

<code>x = [gcd](math.scad#function-gcd)(a,b)</code>  
<code>div = [lcm](math.scad#function-lcm)(a, b);</code>  <code>divs = [lcm](math.scad#function-lcm)(list);</code>  

### Section: Sums, Products, Aggregate Functions.

<code>x = [sum](math.scad#function-sum)(v, [dflt]);</code>  
<code>sums = [cumsum](math.scad#function-cumsum)(v);</code>  
<code>[sum\_of\_sines](math.scad#function-sum_of_sines)(a,sines)</code>  
<code>delts = [deltas](math.scad#function-deltas)(v);</code>  
<code>x = [product](math.scad#function-product)(v);</code>  
<code>x = [mean](math.scad#function-mean)(v);</code>  
<code>middle = [median](math.scad#function-median)(v)</code>  
<code>x = [convolve](math.scad#function-convolve)(p,q);</code>  
<code>bool = [all\_integer](math.scad#function-all_integer)(x);</code>  
<code>bool = [any](math.scad#function-any)(l);</code>  <code>bool = [any](math.scad#function-any)(l, func);   // Requires OpenSCAD 2021.01 or later.</code>  
<code>bool = [all](math.scad#function-all)(l);</code>  <code>bool = [all](math.scad#function-all)(l, func);   // Requires OpenSCAD 2021.01 or later.</code>  
<code>seq = [count\_true](math.scad#function-count_true)(l, [nmax=]);</code>  <code>seq = [count\_true](math.scad#function-count_true)(l, func, [nmax=]);  // Requires OpenSCAD 2021.01 or later.</code>  

### Section: Calculus

<code>x = [deriv](math.scad#function-deriv)(data, [h], [closed])</code>  
<code>x = [deriv2](math.scad#function-deriv2)(data, [h], [closed])</code>  
<code>x = [deriv3](math.scad#function-deriv3)(data, [h], [closed])</code>  

### Section: Complex Numbers

<code>z = [complex](math.scad#function-complex)(list)</code>  
<code>c = [c\_mul](math.scad#function-c_mul)(z1,z2)</code>  
<code>x = [c\_div](math.scad#function-c_div)(z1,z2)</code>  
<code>w = [c\_conj](math.scad#function-c_conj)(z)</code>  
<code>x = [c\_real](math.scad#function-c_real)(z)</code>  
<code>x = [c\_imag](math.scad#function-c_imag)(z)</code>  
<code>I = [c\_ident](math.scad#function-c_ident)(n)</code>  
<code>n = [c\_norm](math.scad#function-c_norm)(z)</code>  

### Section: Polynomials

<code>roots = [quadratic\_roots](math.scad#function-quadratic_roots)(a, b, c, [real])</code>  
<code>x = [polynomial](math.scad#function-polynomial)(p, z)</code>  
<code>x = polymult(p,q)</code>  <code>x = polymult([p1,p2,p3,...])</code>  
<code>[quotient,remainder] = [poly\_div](math.scad#function-poly_div)(n,d)</code>  
<code>sum = [poly\_add](math.scad#function-poly_add)(p,q)</code>  
<code>roots = [poly\_roots](math.scad#function-poly_roots)(p, [tol]);</code>  
<code>roots = [real\_roots](math.scad#function-real_roots)(p, [eps], [tol])</code>  

### Section: Operations on Functions

<code>x = [root\_find](math.scad#function-root_find)(f, x0, x1, [tol])</code>  

## LibFile: linalg.scad

### Section: Matrix testing and display

<code>test = [is\_matrix](linalg.scad#function-is_matrix)(A, [m], [n], [square])</code>  
<code>b = [is\_matrix\_symmetric](linalg.scad#function-is_matrix_symmetric)(A, [eps])</code>  
<code>[echo\_matrix](linalg.scad#functionmodule-echo_matrix)(M, [description], [sig], [sep], [eps]);</code>  <code>dummy = [echo\_matrix](linalg.scad#functionmodule-echo_matrix)(M, [description], [sig], [sep], [eps]),</code>  

### Section: Matrix indexing

<code>list = [column](linalg.scad#function-column)(M, i);</code>  
<code>mat = [submatrix](linalg.scad#function-submatrix)(M, idx1, idx2);</code>  

### Section: Matrix construction and modification

<code>mat = [ident](linalg.scad#function-ident)(n);</code>  
<code>mat = [diagonal\_matrix](linalg.scad#function-diagonal_matrix)(diag, [offdiag]);</code>  
<code>M = [transpose](linalg.scad#function-transpose)(M, [reverse]);</code>  
<code>x = [outer\_product](linalg.scad#function-outer_product)(u,v);</code>  <code>M = [outer\_product](linalg.scad#function-outer_product)(u,v);</code>  
<code>mat = [submatrix\_set](linalg.scad#function-submatrix_set)(M, A, [m], [n]);</code>  
<code>A = [hstack](linalg.scad#function-hstack)(M1, M2)</code>  <code>A = [hstack](linalg.scad#function-hstack)(M1, M2, M3)</code>  <code>A = [hstack](linalg.scad#function-hstack)([M1, M2, M3, ...])</code>  
<code>bmat = [block\_matrix](linalg.scad#function-block_matrix)([[M11, M12,...],[M21, M22,...], ... ]);</code>  

### Section: Solving Linear Equations and Matrix Factorizations

<code>solv = [linear\_solve](linalg.scad#function-linear_solve)(A,b,[pivot])</code>  <code>A = Matrix describing the linear system, which need not be square</code>  <code>b = right hand side for linear system, which can be a matrix to solve several cases simultaneously.  Must be consistent with A.</code>  <code>pivot = if true use pivoting when computing the QR factorization.  Default: true</code>  
<code>x = [linear\_solve3](linalg.scad#function-linear_solve3)(A,b)</code>  
<code>mat = [matrix\_inverse](linalg.scad#function-matrix_inverse)(A)</code>  
<code>B = [rot\_inverse](linalg.scad#function-rot_inverse)(A)</code>  
<code>x = [null\_space](linalg.scad#function-null_space)(A)</code>  
<code>qr = [qr\_factor](linalg.scad#function-qr_factor)(A,[pivot]);</code>  
<code>x = [back\_substitute](linalg.scad#function-back_substitute)(R, b, [transpose]);</code>  
<code>L = [cholesky](linalg.scad#function-cholesky)(A);</code>  

### Section: Matrix Properties: Determinants, Norm, Trace

<code>d = [det2](linalg.scad#function-det2)(M);</code>  
<code>d = [det3](linalg.scad#function-det3)(M);</code>  
<code>d = [det4](linalg.scad#function-det4)(M);</code>  
<code>d = [determinant](linalg.scad#function-determinant)(M);</code>  
<code>[norm\_fro](linalg.scad#function-norm_fro)(A)</code>  
<code>[matrix\_trace](linalg.scad#function-matrix_trace)(M)</code>  

## LibFile: vectors.scad

### Section: Vector Testing

<code>[is\_vector](vectors.scad#function-is_vector)(v, [length], ...);</code>  

### Section: Scalar operations on vectors

<code>v\_new = [add\_scalar](vectors.scad#function-add_scalar)(v, s);</code>  
<code>v3 = [v\_mul](vectors.scad#function-v_mul)(v1, v2);</code>  
<code>v3 = [v\_div](vectors.scad#function-v_div)(v1, v2);</code>  
<code>v2 = [v\_abs](vectors.scad#function-v_abs)(v);</code>  
<code>v2 = [v\_floor](vectors.scad#function-v_floor)(v);</code>  
<code>v2 = [v\_ceil](vectors.scad#function-v_ceil)(v);</code>  
<code>v2 = v\_ceil(x, v);</code>  

### Section: Vector Properties

<code>v = [unit](vectors.scad#function-unit)(v, [error]);</code>  
<code>theta = [v\_theta](vectors.scad#function-v_theta)([X,Y]);</code>  
<code>ang = [vector\_angle](vectors.scad#function-vector_angle)(v1,v2);</code>  <code>ang = [vector\_angle](vectors.scad#function-vector_angle)([v1,v2]);</code>  <code>ang = [vector\_angle](vectors.scad#function-vector_angle)(PT1,PT2,PT3);</code>  <code>ang = [vector\_angle](vectors.scad#function-vector_angle)([PT1,PT2,PT3]);</code>  
<code>axis = [vector\_axis](vectors.scad#function-vector_axis)(v1,v2);</code>  <code>axis = [vector\_axis](vectors.scad#function-vector_axis)([v1,v2]);</code>  <code>axis = [vector\_axis](vectors.scad#function-vector_axis)(PT1,PT2,PT3);</code>  <code>axis = [vector\_axis](vectors.scad#function-vector_axis)([PT1,PT2,PT3]);</code>  

### Section: Vector Searching

<code>pt\_pair = [pointlist\_bounds](vectors.scad#function-pointlist_bounds)(pts);</code>  
<code>index = [closest\_point](vectors.scad#function-closest_point)(pt, points);</code>  
<code>index = [furthest\_point](vectors.scad#function-furthest_point)(pt, points);</code>  
<code>indices = [vector\_search](vectors.scad#function-vector_search)(query, r, target);</code>  
<code>tree = [vector\_search\_tree](vectors.scad#function-vector_search_tree)(points,leafsize);</code>  
<code>indices = [vector\_nearest](vectors.scad#function-vector_nearest)(query, k, target);</code>  

## LibFile: quaternions.scad

### Section: Quaternions

<code>if([is\_quaternion](quaternions.scad#function-is_quaternion)(q)) a=0;</code>  
<code>[quat](quaternions.scad#function-quat)(ax, ang);</code>  
<code>[quat\_x](quaternions.scad#function-quat_x)(a);</code>  
<code>[quat\_y](quaternions.scad#function-quat_y)(a);</code>  
<code>[quat\_z](quaternions.scad#function-quat_z)(a);</code>  
<code>[quat\_xyz](quaternions.scad#function-quat_xyz)([X,Y,Z])</code>  
<code>q = [q\_from\_to](quaternions.scad#function-q_from_to)(v1, v2);</code>  
<code>[q\_add\_s](quaternions.scad#function-q_add_s)(q, s)</code>  
<code>[q\_sub\_s](quaternions.scad#function-q_sub_s)(q, s)</code>  
<code>[q\_mul\_s](quaternions.scad#function-q_mul_s)(q, s)</code>  
<code>[q\_div\_s](quaternions.scad#function-q_div_s)(q, s)</code>  
<code>[q\_add](quaternions.scad#function-q_add)(a, b)</code>  
<code>[q\_sub](quaternions.scad#function-q_sub)(a, b)</code>  
<code>[q\_mul](quaternions.scad#function-q_mul)(a, b)</code>  
<code>[q\_cumulative](quaternions.scad#function-q_cumulative)(v);</code>  
<code>[q\_dot](quaternions.scad#function-q_dot)(a, b)</code>  
<code>[q\_neg](quaternions.scad#function-q_neg)(q)</code>  
<code>[q\_conj](quaternions.scad#function-q_conj)(q)</code>  
<code>qc = [q\_inverse](quaternions.scad#function-q_inverse)(q)</code>  
<code>[q\_norm](quaternions.scad#function-q_norm)(q)</code>  
<code>[q\_normalize](quaternions.scad#function-q_normalize)(q)</code>  
<code>[q\_dist](quaternions.scad#function-q_dist)(q1, q2)</code>  
<code>[q\_slerp](quaternions.scad#function-q_slerp)(q1, q2, u);</code>  
<code>[q\_matrix3](quaternions.scad#function-q_matrix3)(q);</code>  
<code>[q\_matrix4](quaternions.scad#function-q_matrix4)(q);</code>  
<code>[q\_axis](quaternions.scad#function-q_axis)(q)</code>  
<code>a = [q\_angle](quaternions.scad#function-q_angle)(q)</code>  <code>a12 = [q\_angle](quaternions.scad#function-q_angle)(q1,q2);</code>  
<code>[q\_rot](quaternions.scad#functionmodule-q_rot)(q) ...</code>  <code>pts = [q\_rot](quaternions.scad#functionmodule-q_rot)(q,p);</code>  
<code>[q\_rot\_copies](quaternions.scad#module-q_rot_copies)(quats) ...</code>  
<code>[q\_rotation](quaternions.scad#function-q_rotation)(R)</code>  
<code>path = [q\_rotation\_path](quaternions.scad#functionmodule-q_rotation_path)(q1, n, q2);</code>  <code>path = [q\_rotation\_path](quaternions.scad#functionmodule-q_rotation_path)(q1, n);</code>  <code>[q\_rotation\_path](quaternions.scad#functionmodule-q_rotation_path)(q1, n, q2) ...</code>  
<code>q = [q\_nlerp](quaternions.scad#function-q_nlerp)(q1, q2, u);</code>  
<code>qn = [q\_squad](quaternions.scad#function-q_squad)(q1,q2,q3,q4,u);</code>  
<code>q2 = [q\_exp](quaternions.scad#function-q_exp)(q);</code>  
<code>q2 = [q\_ln](quaternions.scad#function-q_ln)(q);</code>  
<code>q2 = [q\_pow](quaternions.scad#function-q_pow)(q, r);</code>  

## LibFile: coords.scad

### Section: Coordinate Manipulation

<code>pt = [point2d](coords.scad#function-point2d)(p, [fill]);</code>  
<code>pts = [path2d](coords.scad#function-path2d)(points);</code>  
<code>pt = [point3d](coords.scad#function-point3d)(p, [fill]);</code>  
<code>pts = [path3d](coords.scad#function-path3d)(points, [fill]);</code>  
<code>pt = [point4d](coords.scad#function-point4d)(p, [fill]);</code>  
<code>pt = [path4d](coords.scad#function-path4d)(points, [fill]);</code>  

### Section: Coordinate Systems

<code>pt = [polar\_to\_xy](coords.scad#function-polar_to_xy)(r, theta);</code>  <code>pt = [polar\_to\_xy](coords.scad#function-polar_to_xy)([r, theta]);</code>  
<code>r\_theta = [xy\_to\_polar](coords.scad#function-xy_to_polar)(x,y);</code>  <code>r\_theta = [xy\_to\_polar](coords.scad#function-xy_to_polar)([X,Y]);</code>  
<code>xy = [project\_plane](coords.scad#function-project_plane)(plane, p);</code>  <code>M = [project\_plane](coords.scad#function-project_plane)(plane)</code>  
<code>xyz = [lift\_plane](coords.scad#function-lift_plane)(plane, p);</code>  <code>M =  [lift\_plane](coords.scad#function-lift_plane)(plane);</code>  
<code>pt = [cylindrical\_to\_xyz](coords.scad#function-cylindrical_to_xyz)(r, theta, z);</code>  <code>pt = [cylindrical\_to\_xyz](coords.scad#function-cylindrical_to_xyz)([r, theta, z]);</code>  
<code>rtz = [xyz\_to\_cylindrical](coords.scad#function-xyz_to_cylindrical)(x,y,z);</code>  <code>rtz = [xyz\_to\_cylindrical](coords.scad#function-xyz_to_cylindrical)([X,Y,Z]);</code>  
<code>pt = [spherical\_to\_xyz](coords.scad#function-spherical_to_xyz)(r, theta, phi);</code>  <code>pt = [spherical\_to\_xyz](coords.scad#function-spherical_to_xyz)([r, theta, phi]);</code>  
<code>r\_theta\_phi = [xyz\_to\_spherical](coords.scad#function-xyz_to_spherical)(x,y,z)</code>  <code>r\_theta\_phi = [xyz\_to\_spherical](coords.scad#function-xyz_to_spherical)([X,Y,Z])</code>  
<code>pt = [altaz\_to\_xyz](coords.scad#function-altaz_to_xyz)(alt, az, r);</code>  <code>pt = [altaz\_to\_xyz](coords.scad#function-altaz_to_xyz)([alt, az, r]);</code>  
<code>alt\_az\_r = [xyz\_to\_altaz](coords.scad#function-xyz_to_altaz)(x,y,z);</code>  <code>alt\_az\_r = [xyz\_to\_altaz](coords.scad#function-xyz_to_altaz)([X,Y,Z]);</code>  

## LibFile: geometry.scad

### Section: Lines, Rays, and Segments

<code>pt = [is\_point\_on\_line](geometry.scad#function-is_point_on_line)(point, line, [bounded], [eps]);</code>  
<code>test = [is\_collinear](geometry.scad#function-is_collinear)(a, [b, c], [eps]);</code>  
<code>pt = [point\_line\_distance](geometry.scad#function-point_line_distance)(line, pt, bounded);</code>  
<code>dist = [segment\_distance](geometry.scad#function-segment_distance)(seg1, seg2, [eps]);</code>  
<code>vec = [line\_normal](geometry.scad#function-line_normal)([P1,P2])</code>  <code>vec = [line\_normal](geometry.scad#function-line_normal)(p1,p2)</code>  
<code>pt = [line\_intersection](geometry.scad#function-line_intersection)(line1, line2, [bounded1], [bounded2], [bounded=], [eps=]);</code>  
<code>pt = [line\_closest\_point](geometry.scad#function-line_closest_point)(line, pt, [bounded]);</code>  
<code>line = [line\_from\_points](geometry.scad#function-line_from_points)(points, [fast], [eps]);</code>  

### Section: Planes

<code>test = [is\_coplanar](geometry.scad#function-is_coplanar)(points,[eps]);</code>  
<code>plane = [plane3pt](geometry.scad#function-plane3pt)(p1, p2, p3);</code>  
<code>plane = [plane3pt\_indexed](geometry.scad#function-plane3pt_indexed)(points, i1, i2, i3);</code>  
<code>plane = [plane\_from\_normal](geometry.scad#function-plane_from_normal)(normal, [pt])</code>  
<code>plane = [plane\_from\_points](geometry.scad#function-plane_from_points)(points, [fast], [eps]);</code>  
<code>plane = [plane\_from\_polygon](geometry.scad#function-plane_from_polygon)(points, [fast], [eps]);</code>  
<code>vec = [plane\_normal](geometry.scad#function-plane_normal)(plane);</code>  
<code>d = [plane\_offset](geometry.scad#function-plane_offset)(plane);</code>  
<code>pt = [plane\_line\_intersection](geometry.scad#function-plane_line_intersection)(plane, line, [bounded], [eps]);</code>  
<code>line = [plane\_intersection](geometry.scad#function-plane_intersection)(plane1, plane2)</code>  <code>pt = [plane\_intersection](geometry.scad#function-plane_intersection)(plane1, plane2, plane3)</code>  
<code>angle = [plane\_line\_angle](geometry.scad#function-plane_line_angle)(plane,line);</code>  
<code>pts = [plane\_closest\_point](geometry.scad#function-plane_closest_point)(plane, points);</code>  
<code>dist = [point\_plane\_distance](geometry.scad#function-point_plane_distance)(plane, point)</code>  
<code>test = [are\_points\_on\_plane](geometry.scad#function-are_points_on_plane)(points, plane, [eps]);</code>  

### Section: Circle Calculations

<code>isect = [circle\_line\_intersection](geometry.scad#function-circle_line_intersection)(c,&lt;r|d&gt;,[line],[bounded],[eps]);</code>  
<code>pts = circle\_circle\_tangents(c1, r1|d1, c2, r2|d2, [eps]);</code>  
<code>circ = [circle\_2tangents](geometry.scad#functionmodule-circle_2tangents)(pt1, pt2, pt3, r|d, [tangents]);</code>  <code>[circle\_2tangents](geometry.scad#functionmodule-circle_2tangents)(pt1, pt2, pt3, r|d, [h], [center]);</code>  
<code>circ = [circle\_3points](geometry.scad#functionmodule-circle_3points)(pt1, pt2, pt3);</code>  <code>circ = [circle\_3points](geometry.scad#functionmodule-circle_3points)([pt1, pt2, pt3]);</code>  <code>[circle\_3points](geometry.scad#functionmodule-circle_3points)(pt1, pt2, pt3, [h], [center]);</code>  <code>[circle\_3points](geometry.scad#functionmodule-circle_3points)([pt1, pt2, pt3], [h], [center]);</code>  
<code>tangents = [circle\_point\_tangents](geometry.scad#function-circle_point_tangents)(r|d, cp, pt);</code>  
<code>segs = [circle\_circle\_tangents](geometry.scad#function-circle_circle_tangents)(c1, r1|d1, c2, r2|d2);</code>  

### Section: Sphere Calculations

<code>isect = [sphere\_line\_intersection](geometry.scad#function-sphere_line_intersection)(c,&lt;r|d&gt;,[line],[bounded],[eps]);</code>  

### Section: Polygons

<code>area = [polygon\_area](geometry.scad#function-polygon_area)(poly);</code>  
<code>c = [centroid](geometry.scad#function-centroid)(object, [eps]);</code>  
<code>vec = [polygon\_normal](geometry.scad#function-polygon_normal)(poly);</code>  
<code>test = [point\_in\_polygon](geometry.scad#function-point_in_polygon)(point, poly, [nonzero], [eps])</code>  
<code>pt = [polygon\_line\_intersection](geometry.scad#function-polygon_line_intersection)(poly, line, [bounded], [nonzero], [eps]);</code>  
<code>triangles = [polygon\_triangulate](geometry.scad#function-polygon_triangulate)(poly, [ind], [error], [eps])</code>  
<code>test = [is\_polygon\_clockwise](geometry.scad#function-is_polygon_clockwise)(poly);</code>  
<code>newpoly = [clockwise\_polygon](geometry.scad#function-clockwise_polygon)(poly);</code>  
<code>newpoly = [ccw\_polygon](geometry.scad#function-ccw_polygon)(poly);</code>  
<code>newpoly = [reverse\_polygon](geometry.scad#function-reverse_polygon)(poly)</code>  
<code>newpoly = [reindex\_polygon](geometry.scad#function-reindex_polygon)(reference, poly);</code>  
<code>newpoly = [align\_polygon](geometry.scad#function-align_polygon)(reference, poly, [angles], [cp], [tran], [return\_ind]);</code>  
<code>b = [are\_polygons\_equal](geometry.scad#function-are_polygons_equal)(poly1, poly2, [eps])</code>  

### Section: Convex Hull

<code>[hull](geometry.scad#function-hull)(points);</code>  
<code>[hull\_points](geometry.scad#module-hull_points)(points, [fast]);</code>  
<code>[hull2d\_path](geometry.scad#function-hull2d_path)(points,all)</code>  
<code>[hull3d\_faces](geometry.scad#function-hull3d_faces)(points)</code>  

### Section: Convex Sets

<code>test = [is\_polygon\_convex](geometry.scad#function-is_polygon_convex)(poly);</code>  
<code>dist = [convex\_distance](geometry.scad#function-convex_distance)(pts1, pts2,[eps=]);</code>  
<code>test = [convex\_collision](geometry.scad#function-convex_collision)(pts1, pts2, [eps=]);</code>  

### Section: Rotation Decoding

<code>info = [rot\_decode](geometry.scad#function-rot_decode)(rotation,[long]); // Returns: [angle,axis,cp,translation]</code>  

## LibFile: trigonometry.scad

### Section: 2D General Triangle Functions

<code>C = [law\_of\_cosines](trigonometry.scad#function-law_of_cosines)(a, b, c);</code>  <code>c = [law\_of\_cosines](trigonometry.scad#function-law_of_cosines)(a, b, C=);</code>  
<code>B = [law\_of\_sines](trigonometry.scad#function-law_of_sines)(a, A, b);</code>  <code>b = [law\_of\_sines](trigonometry.scad#function-law_of_sines)(a, A, B=);</code>  
<code>area = [triangle\_area](trigonometry.scad#function-triangle_area)(p1,p2,p3);</code>  

### Section: 2D Right Triangle Functions

<code>adj = [hyp\_opp\_to\_adj](trigonometry.scad#function-hyp_opp_to_adj)(hyp,opp);</code>  <code>adj = opp\_hyp\_to\_adj(opp,hyp);</code>  
<code>adj = [hyp\_ang\_to\_adj](trigonometry.scad#function-hyp_ang_to_adj)(hyp,ang);</code>  <code>adj = ang\_hyp\_to\_adj(ang,hyp);</code>  
<code>adj = [opp\_ang\_to\_adj](trigonometry.scad#function-opp_ang_to_adj)(opp,ang);</code>  <code>adj = ang\_opp\_to\_adj(ang,opp);</code>  
<code>opp = [hyp\_adj\_to\_opp](trigonometry.scad#function-hyp_adj_to_opp)(hyp,adj);</code>  <code>opp = adj\_hyp\_to\_opp(adj,hyp);</code>  
<code>opp = [hyp\_ang\_to\_opp](trigonometry.scad#function-hyp_ang_to_opp)(hyp,ang);</code>  <code>opp = ang\_hyp\_to\_opp(ang,hyp);</code>  
<code>opp = [adj\_ang\_to\_opp](trigonometry.scad#function-adj_ang_to_opp)(adj,ang);</code>  <code>opp = ang\_adj\_to\_opp(ang,adj);</code>  
<code>hyp = [adj\_opp\_to\_hyp](trigonometry.scad#function-adj_opp_to_hyp)(adj,opp);</code>  <code>hyp = opp\_adj\_to\_hyp(opp,adj);</code>  
<code>hyp = [adj\_ang\_to\_hyp](trigonometry.scad#function-adj_ang_to_hyp)(adj,ang);</code>  <code>hyp = ang\_adj\_to\_hyp(ang,adj);</code>  
<code>hyp = [opp\_ang\_to\_hyp](trigonometry.scad#function-opp_ang_to_hyp)(opp,ang);</code>  <code>hyp = ang\_opp\_to\_hyp(ang,opp);</code>  
<code>ang = [hyp\_adj\_to\_ang](trigonometry.scad#function-hyp_adj_to_ang)(hyp,adj);</code>  <code>ang = adj\_hyp\_to\_ang(adj,hyp);</code>  
<code>ang = [hyp\_opp\_to\_ang](trigonometry.scad#function-hyp_opp_to_ang)(hyp,opp);</code>  <code>ang = opp\_hyp\_to\_ang(opp,hyp);</code>  
<code>ang = [adj\_opp\_to\_ang](trigonometry.scad#function-adj_opp_to_ang)(adj,opp);</code>  <code>ang = opp\_adj\_to\_ang(opp,adj);</code>  

## LibFile: constants.scad

### Section: General Constants

Constants: [`$slop`](constants.scad#constant-slop) [`INCH`](constants.scad#constant-inch)

### Section: Directional Vectors

Constants: [`LEFT`](constants.scad#constant-left) [`RIGHT`](constants.scad#constant-right) [`FRONT`](constants.scad#constant-front) [`FWD`](constants.scad#constant-front) [`FORWARD`](constants.scad#constant-front) [`BACK`](constants.scad#constant-back) [`BOTTOM`](constants.scad#constant-bottom) [`BOT`](constants.scad#constant-bottom) [`DOWN`](constants.scad#constant-bottom) [`TOP`](constants.scad#constant-top) [`UP`](constants.scad#constant-top) [`CENTER`](constants.scad#constant-center) [`CTR`](constants.scad#constant-center) [`CENTRE`](constants.scad#constant-center)

### Section: Line specifiers

Constants: [`SEGMENT`](constants.scad#constant-segment) [`RAY`](constants.scad#constant-ray) [`LINE`](constants.scad#constant-line)

## LibFile: version.scad

### Section: BOSL Library Version Functions

<code>ver = [bosl\_version](version.scad#function-bosl_version)();</code>  
<code>ver = [bosl\_version\_num](version.scad#function-bosl_version_num)();</code>  
<code>ver = [bosl\_version\_str](version.scad#function-bosl_version_str)();</code>  
<code>[bosl\_required](version.scad#module-bosl_required)(x);</code>  

### Section: Generic Version Functions

<code>ver = [version\_to\_list](version.scad#function-version_to_list)(x);</code>  
<code>str = [version\_to\_str](version.scad#function-version_to_str)(x);</code>  
<code>str = [version\_to\_num](version.scad#function-version_to_num)(x);</code>  
<code>cmp = [version\_cmp](version.scad#function-version_cmp)(a,b);</code>  

## LibFile: comparisons.scad

### Section: List comparison operations

<code>test = [approx](comparisons.scad#function-approx)(a, b, [eps])</code>  
<code>x = [all\_zero](comparisons.scad#function-all_zero)(x, [eps]);</code>  
<code>test = [all\_nonzero](comparisons.scad#function-all_nonzero)(x, [eps]);</code>  
<code>test = [all\_positive](comparisons.scad#function-all_positive)(x,[eps]);</code>  
<code>test = [all\_negative](comparisons.scad#function-all_negative)(x, [eps]);</code>  
<code>[all\_nonpositive](comparisons.scad#function-all_nonpositive)(x, [eps]);</code>  
<code>[all\_nonnegative](comparisons.scad#function-all_nonnegative)(x, [eps]);</code>  
<code>b = [all\_equal](comparisons.scad#function-all_equal)(vec, [eps]);</code>  
<code>bool = [is\_increasing](comparisons.scad#function-is_increasing)(list);</code>  
<code>bool = [is\_decreasing](comparisons.scad#function-is_decreasing)(list);</code>  
<code>test = [compare\_vals](comparisons.scad#function-compare_vals)(a, b);</code>  
<code>test = [compare\_lists](comparisons.scad#function-compare_lists)(a, b)</code>  

### Section: Finding the index of the minimum or maximum of a list

<code>idx = [min\_index](comparisons.scad#function-min_index)(vals);</code>  <code>idxlist = [min\_index](comparisons.scad#function-min_index)(vals, all=true);</code>  
<code>idx = [max\_index](comparisons.scad#function-max_index)(vals);</code>  <code>idxlist = [max\_index](comparisons.scad#function-max_index)(vals, all=true);</code>  

### Section: Dealing with duplicate list entries

<code>idx = [find\_approx](comparisons.scad#function-find_approx)(val, list, [start=], [eps=]);</code>  <code>indices = [find\_approx](comparisons.scad#function-find_approx)(val, list, all=true, [start=], [eps=]);</code>  
<code>list = [deduplicate](comparisons.scad#function-deduplicate)(list, [close], [eps]);</code>  
<code>new\_idxs = [deduplicate\_indexed](comparisons.scad#function-deduplicate_indexed)(list, indices, [closed], [eps]);</code>  
<code>ulist = [unique](comparisons.scad#function-unique)(list);</code>  
<code>counts = [unique\_count](comparisons.scad#function-unique_count)(list);</code>  

### Section: Sorting

<code>slist = [sort](comparisons.scad#function-sort)(list, [idx]);</code>  
<code>idxlist = [sortidx](comparisons.scad#function-sortidx)(list, [idx]);</code>  
<code>ulist = [group\_sort](comparisons.scad#function-group_sort)(list);</code>  
<code>groupings = [group\_data](comparisons.scad#function-group_data)(groups, values);</code>  
<code>small = [list\_smallest](comparisons.scad#function-list_smallest)(list, k)</code>  

## LibFile: lists.scad

### Section: List Query Operations

<code>bool = [is\_homogeneous](lists.scad#function-is_homogeneous)(list, depth);</code>  
<code>llen = [min\_length](lists.scad#function-min_length)(list);</code>  
<code>llen = [max\_length](lists.scad#function-max_length)(list);</code>  
<code>dims = [list\_shape](lists.scad#function-list_shape)(v, [depth]);</code>  
<code>bool = [in\_list](lists.scad#function-in_list)(val, list, [idx]);</code>  

### Section: List Indexing

<code>item = [select](lists.scad#function-select)(list, start);</code>  <code>item = [select](lists.scad#function-select)(list, [s:d:e]);</code>  <code>item = [select](lists.scad#function-select)(list, [i0,i1...,ik]);</code>  <code>list = [select](lists.scad#function-select)(list, start, end);</code>  
<code>list = [slice](lists.scad#function-slice)(list, s, e);</code>  
<code>item = [last](lists.scad#function-last)(list);</code>  
<code>list = [list\_head](lists.scad#function-list_head)(list, [to]);</code>  
<code>list = [list\_tail](lists.scad#function-list_tail)(list, [from]);</code>  
<code>sublist = [bselect](lists.scad#function-bselect)(list, index);</code>  

### Section: List Construction

<code>list = [repeat](lists.scad#function-repeat)(val, n);</code>  
<code>list = [count](lists.scad#function-count)(n, [s], [step], [reverse]);</code>  
<code>arr = [list\_bset](lists.scad#function-list_bset)(indexset, valuelist, [dflt]);</code>  
<code>[list](lists.scad#function-list) = [list](lists.scad#function-list)(l)</code>  
<code>list = [force\_list](lists.scad#function-force_list)(value, [n], [fill]);</code>  

### Section: List Modification

<code>rlist = [reverse](lists.scad#function-reverse)(list);</code>  
<code>rlist = [list\_rotate](lists.scad#function-list_rotate)(list, [n]);</code>  
<code>[shuffle](lists.scad#function-shuffle)d = [shuffle](lists.scad#function-shuffle)(list, [seed]);</code>  
<code>newlist = [repeat\_entries](lists.scad#function-repeat_entries)(list, N, [exact]);</code>  
<code>newlist = [list\_pad](lists.scad#function-list_pad)(list, minlen, [fill]);</code>  
<code>list = [list\_set](lists.scad#function-list_set)(list, indices, values, [dflt], [minlen]);</code>  
<code>list = [list\_insert](lists.scad#function-list_insert)(list, indices, values);</code>  
<code>list = [list\_remove](lists.scad#function-list_remove)(list, ind);</code>  
<code>list = [list\_remove\_values](lists.scad#function-list_remove_values)(list, values);</code>  <code>list = [list\_remove\_values](lists.scad#function-list_remove_values)(list, values, all=true);</code>  

### Section: Lists of Subsets

<code>rng = [idx](lists.scad#function-idx)(list, [s=], [e=], [step=]);</code>  <code>for(i=[idx](lists.scad#function-idx)(list, [s=], [e=], [step=])) ...</code>  
<code>p = [pair](lists.scad#function-pair)(list, [wrap]);</code>  <code>for (p = [pair](lists.scad#function-pair)(list, [wrap])) ...  // On each iteration, p contains a list of two adjacent items.</code>  
<code>list = [triplet](lists.scad#function-triplet)(list, [wrap]);</code>  <code>for (t = [triplet](lists.scad#function-triplet)(list, [wrap])) ...</code>  
<code>list = [combinations](lists.scad#function-combinations)(l, [n]);</code>  
<code>list = [permutations](lists.scad#function-permutations)(l, [n]);</code>  

### Section: Changing list structure

<code>groups = [list\_to\_matrix](lists.scad#function-list_to_matrix)(v, cnt, [dflt]);</code>  
<code>list = [flatten](lists.scad#function-flatten)(l);</code>  
<code>list = [full\_flatten](lists.scad#function-full_flatten)(l);</code>  

### Section: Set Manipulation

<code>s = [set\_union](lists.scad#function-set_union)(a, b, [get\_indices]);</code>  
<code>s = [set\_difference](lists.scad#function-set_difference)(a, b);</code>  
<code>s = [set\_intersection](lists.scad#function-set_intersection)(a, b);</code>  

## LibFile: utility.scad

### Section: Type Checking

<code>typ = [typeof](utility.scad#function-typeof)(x);</code>  
<code>bool = [is\_type](utility.scad#function-is_type)(x, types);</code>  
<code>bool = [is\_def](utility.scad#function-is_def)(x);</code>  
<code>bool = [is\_str](utility.scad#function-is_str)(x);</code>  
<code>bool = [is\_int](utility.scad#function-is_int)(n);</code>  <code>bool = [is\_int](utility.scad#function-is_int)eger(n);</code>  
<code>bool = [is\_nan](utility.scad#function-is_nan)(x);</code>  
<code>bool = [is\_finite](utility.scad#function-is_finite)(x);</code>  
<code>bool = [is\_range](utility.scad#function-is_range)(x);</code>  
<code>bool = [valid\_range](utility.scad#function-valid_range)(x);</code>  
<code>bool = [is\_func](utility.scad#function-is_func)(x);</code>  
<code>bool = [is\_consistent](utility.scad#function-is_consistent)(list, [pattern]);</code>  
<code>bool = [same\_shape](utility.scad#function-same_shape)(a,b);</code>  
<code>check = [is\_bool\_list](utility.scad#function-is_bool_list)(list,[length])</code>  

### Section: Handling `undef`s.

<code>val = [default](utility.scad#function-default)(val, dflt);</code>  
<code>val = [first\_defined](utility.scad#function-first_defined)(v, [recursive]);</code>  
<code>val = [one\_defined](utility.scad#function-one_defined)(vals, names, [dflt])</code>  
<code>cnt = [num\_defined](utility.scad#function-num_defined)(v);</code>  
<code>bool = [any\_defined](utility.scad#function-any_defined)(v, [recursive]);</code>  
<code>bool = [all\_defined](utility.scad#function-all_defined)(v, [recursive]);</code>  

### Section: Processing Arguments to Functions and Modules

<code>anchr = [get\_anchor](utility.scad#function-get_anchor)(anchor,center,[uncentered],[dflt]);</code>  
<code>r = [get\_radius](utility.scad#function-get_radius)([r1=], [r2=], [r=], [d1=], [d2=], [d=], [dflt=]);</code>  
<code>vec = [scalar\_vec3](utility.scad#function-scalar_vec3)(v, [dflt]);</code>  
<code>sides = [segs](utility.scad#function-segs)(r);</code>  
<code>[no\_children](utility.scad#module-no_children)($children);</code>  
<code>dummy = [no\_function](utility.scad#function-no_function)(name)</code>  
<code>[no\_module](utility.scad#module-no_module)();</code>  

### Section: Testing Helpers

<code>[assert\_approx](utility.scad#module-assert_approx)(got, expected, [info]);</code>  
<code>[assert\_equal](utility.scad#module-assert_equal)(got, expected, [info]);</code>  
<code>[shape\_compare](utility.scad#module-shape_compare)([eps]) {test\_shape(); expected\_shape();}</code>  

### Section: Looping Helpers

<code>bool = [looping](utility.scad#function-looping)(state);</code>  
<code>state = [loop\_while](utility.scad#function-loop_while)(state, continue);</code>  
<code>bool = [loop\_done](utility.scad#function-loop_done)(state);</code>  

## LibFile: strings.scad

### Section: Extracting substrings

<code>[substr](strings.scad#function-substr)(str, [pos], [len])</code>  
<code>[suffix](strings.scad#function-suffix)(str,len)</code>  

### Section: String Searching

<code>[str\_find](strings.scad#function-str_find)(str,pattern,[last],[all],[start])</code>  
<code>[starts\_with](strings.scad#function-starts_with)(str,pattern)</code>  
<code>[ends\_with](strings.scad#function-ends_with)(str,pattern)</code>  
<code>[str\_split](strings.scad#function-str_split)(str, sep, [keep\_nulls])</code>  

### Section: String modification

<code>[str\_join](strings.scad#function-str_join)(list, [sep])</code>  
<code>[str\_strip](strings.scad#function-str_strip)(s,c,[start],[end]);</code>  
<code>padded = [str\_pad](strings.scad#function-str_pad)(str, length, char, [left]);</code>  
<code>newstr = [str\_replace\_char](strings.scad#function-str_replace_char)(str, char, replace)</code>  
<code>[downcase](strings.scad#function-downcase)(str)</code>  
<code>[upcase](strings.scad#function-upcase)(str)</code>  

### Section: Parsing strings into numbers

<code>[parse\_int](strings.scad#function-parse_int)(str, [base])</code>  
<code>[parse\_float](strings.scad#function-parse_float)(str)</code>  
<code>[parse\_frac](strings.scad#function-parse_frac)(str,[mixed],[improper],[signed])</code>  
<code>[parse\_num](strings.scad#function-parse_num)(str)</code>  

### Section: Formatting numbers into strings

<code>[format\_int](strings.scad#function-format_int)(i, [mindigits]);</code>  
<code>s = [format\_fixed](strings.scad#function-format_fixed)(f, [digits]);</code>  
<code>[format\_float](strings.scad#function-format_float)(f,[sig]);</code>  
<code>s = [format](strings.scad#function-format)(fmt, vals);</code>  

### Section: Checking character class

<code>x = [is\_lower](strings.scad#function-is_lower)(s);</code>  
<code>x = [is\_upper](strings.scad#function-is_upper)(s);</code>  
<code>x = [is\_digit](strings.scad#function-is_digit)(s);</code>  
<code>x = [is\_hexdigit](strings.scad#function-is_hexdigit)(s);</code>  
<code>x = [is\_letter](strings.scad#function-is_letter)(s);</code>  

## LibFile: structs.scad

### Section: struct operations

<code>[struct\_set](structs.scad#function-struct_set)(struct, keyword, value, [grow])</code>  <code>[struct\_set](structs.scad#function-struct_set)(struct, [keyword1, value1, keyword2, value2, ...], [grow])</code>  
<code>[struct\_remove](structs.scad#function-struct_remove)(struct, keyword)</code>  
<code>[struct\_val](structs.scad#function-struct_val)(struct, keyword, default)</code>  
<code>keys = [struct\_keys](structs.scad#function-struct_keys)(struct)</code>  
<code>[struct\_echo](structs.scad#functionmodule-struct_echo)(struct, [name])</code>  
<code>[is\_struct](structs.scad#function-is_struct)(struct)</code>  

## LibFile: fnliterals.scad

### Section: Function Literal Algorithms

<code>lst = [map](fnliterals.scad#function-map)(func, list);</code>  <code>lst = [map](fnliterals.scad#function-map)(function (x) x+1, list);</code>  
<code>lst = [filter](fnliterals.scad#function-filter)(func, list);</code>  <code>lst = [filter](fnliterals.scad#function-filter)(function (x) x&gt;1, list);</code>  
<code>res = [reduce](fnliterals.scad#function-reduce)(func, list, [init]);</code>  <code>res = [reduce](fnliterals.scad#function-reduce)(function (a,b) a+b, list, &lt;init=);</code>  
<code>res = [accumulate](fnliterals.scad#function-accumulate)(func, list, [init]);</code>  <code>res = [accumulate](fnliterals.scad#function-accumulate)(function (a,b) a+b, list, [init=]);</code>  
<code>x = [while](fnliterals.scad#function-while)(init, cond, func);</code>  
<code>x = [for\_n](fnliterals.scad#function-for_n)(n, init, func);</code>  
<code>indices = [find\_all](fnliterals.scad#function-find_all)(func, list);</code>  <code>indices = [find\_all](fnliterals.scad#function-find_all)(function (x) x&gt;1, list);</code>  
<code>idx = [find\_first](fnliterals.scad#function-find_first)(func, list, [start=]);</code>  
<code>idx = [binsearch](fnliterals.scad#function-binsearch)(key,list, [cmp]);</code>  
<code>hx = [simple\_hash](fnliterals.scad#function-simple_hash)(x);</code>  
<code>hm = [hashmap](fnliterals.scad#function-hashmap)([hashsize=]);</code>  <code>hm = [hashmap](fnliterals.scad#function-hashmap)(items=KEYVAL\_LIST, [hashsize=]);</code>  <code>hm2 = hm(key, val);</code>  <code>hm2 = hm(additems=KEYVAL\_LIST);</code>  <code>hm2 = hm(del=KEY);</code>  <code>x = hm(key);</code>  <code>for (kv=hm()) let(k=kv[0], v=kv[1]) ...</code>  

### Section: Function Meta-Generators

<code>fn = [f\_1arg](fnliterals.scad#function-f_1arg)(func);</code>  
<code>fn = [f\_2arg](fnliterals.scad#function-f_2arg)(target\_func);</code>  
<code>fn = [f\_2arg\_simple](fnliterals.scad#function-f_2arg_simple)(target\_func);</code>  
<code>fn = [f\_3arg](fnliterals.scad#function-f_3arg)(target\_func);</code>  
<code>newfunc = [ival](fnliterals.scad#function-ival)(func);</code>  
<code>newfunc = [xval](fnliterals.scad#function-xval)(func);</code>  

### Section: Comparator Generators

<code>fn = [f\_cmp](fnliterals.scad#function-f_cmp)();</code>  <code>fn = [f\_cmp](fnliterals.scad#function-f_cmp)(b);</code>  <code>fn = [f\_cmp](fnliterals.scad#function-f_cmp)(a,b);</code>  
<code>fn = [f\_gt](fnliterals.scad#function-f_gt)();</code>  <code>fn = [f\_gt](fnliterals.scad#function-f_gt)(b);</code>  <code>fn = [f\_gt](fnliterals.scad#function-f_gt)(a,b);</code>  
<code>fn = [f\_lt](fnliterals.scad#function-f_lt)();</code>  <code>fn = [f\_lt](fnliterals.scad#function-f_lt)(b);</code>  <code>fn = [f\_lt](fnliterals.scad#function-f_lt)(a,b);</code>  
<code>fn = [f\_gte](fnliterals.scad#function-f_gte)();</code>  <code>fn = [f\_gte](fnliterals.scad#function-f_gte)(b);</code>  <code>fn = [f\_gte](fnliterals.scad#function-f_gte)(a,b);</code>  
<code>fn = [f\_lte](fnliterals.scad#function-f_lte)();</code>  <code>fn = [f\_lte](fnliterals.scad#function-f_lte)(b);</code>  <code>fn = [f\_lte](fnliterals.scad#function-f_lte)(a,b);</code>  
<code>fn = [f\_eq](fnliterals.scad#function-f_eq)();</code>  <code>fn = [f\_eq](fnliterals.scad#function-f_eq)(b);</code>  <code>fn = [f\_eq](fnliterals.scad#function-f_eq)(a,b);</code>  
<code>fn = [f\_neq](fnliterals.scad#function-f_neq)();</code>  <code>fn = [f\_neq](fnliterals.scad#function-f_neq)(b);</code>  <code>fn = [f\_neq](fnliterals.scad#function-f_neq)(a,b);</code>  
<code>fn = [f\_approx](fnliterals.scad#function-f_approx)();</code>  <code>fn = [f\_approx](fnliterals.scad#function-f_approx)(b);</code>  <code>fn = [f\_approx](fnliterals.scad#function-f_approx)(a,b);</code>  
<code>fn = [f\_napprox](fnliterals.scad#function-f_napprox)();</code>  <code>fn = [f\_napprox](fnliterals.scad#function-f_napprox)(b);</code>  <code>fn = [f\_napprox](fnliterals.scad#function-f_napprox)(a,b);</code>  

### Section: Logic Operators

<code>fn = [f\_or](fnliterals.scad#function-f_or)();</code>  <code>fn = [f\_or](fnliterals.scad#function-f_or)(a=);</code>  <code>fn = [f\_or](fnliterals.scad#function-f_or)(b=);</code>  <code>fn = [f\_or](fnliterals.scad#function-f_or)(a=,b=);</code>  
<code>fn = [f\_and](fnliterals.scad#function-f_and)();</code>  <code>fn = [f\_and](fnliterals.scad#function-f_and)(a=);</code>  <code>fn = [f\_and](fnliterals.scad#function-f_and)(b=);</code>  <code>fn = [f\_and](fnliterals.scad#function-f_and)(a=,b=);</code>  
<code>fn = [f\_nor](fnliterals.scad#function-f_nor)();</code>  <code>fn = [f\_nor](fnliterals.scad#function-f_nor)(a=);</code>  <code>fn = [f\_nor](fnliterals.scad#function-f_nor)(b=);</code>  <code>fn = [f\_nor](fnliterals.scad#function-f_nor)(a=,b=);</code>  
<code>fn = [f\_nand](fnliterals.scad#function-f_nand)();</code>  <code>fn = [f\_nand](fnliterals.scad#function-f_nand)(a=);</code>  <code>fn = [f\_nand](fnliterals.scad#function-f_nand)(b=);</code>  <code>fn = [f\_nand](fnliterals.scad#function-f_nand)(a=,b=);</code>  
<code>fn = [f\_xor](fnliterals.scad#function-f_xor)();</code>  <code>fn = [f\_xor](fnliterals.scad#function-f_xor)(a=);</code>  <code>fn = [f\_xor](fnliterals.scad#function-f_xor)(b);</code>  <code>fn = [f\_xor](fnliterals.scad#function-f_xor)(a=,b=);</code>  
<code>fn = [f\_not](fnliterals.scad#function-f_not)();</code>  <code>fn = [f\_not](fnliterals.scad#function-f_not)(a);</code>  
<code>fn = [f\_even](fnliterals.scad#function-f_even)();</code>  <code>fn = [f\_even](fnliterals.scad#function-f_even)(a);</code>  
<code>fn = [f\_odd](fnliterals.scad#function-f_odd)();</code>  <code>fn = [f\_odd](fnliterals.scad#function-f_odd)(a);</code>  

### Section: Math Operators

<code>fn = [f\_add](fnliterals.scad#function-f_add)();</code>  <code>fn = [f\_add](fnliterals.scad#function-f_add)(a=);</code>  <code>fn = [f\_add](fnliterals.scad#function-f_add)(b);</code>  <code>fn = [f\_add](fnliterals.scad#function-f_add)(a=,b=);</code>  
<code>fn = [f\_sub](fnliterals.scad#function-f_sub)();</code>  <code>fn = [f\_sub](fnliterals.scad#function-f_sub)(a=);</code>  <code>fn = [f\_sub](fnliterals.scad#function-f_sub)(b);</code>  <code>fn = [f\_sub](fnliterals.scad#function-f_sub)(a=,b=);</code>  
<code>fn = [f\_mul](fnliterals.scad#function-f_mul)();</code>  <code>fn = [f\_mul](fnliterals.scad#function-f_mul)(a=);</code>  <code>fn = [f\_mul](fnliterals.scad#function-f_mul)(b);</code>  <code>fn = [f\_mul](fnliterals.scad#function-f_mul)(a=,b=);</code>  
<code>fn = [f\_div](fnliterals.scad#function-f_div)();</code>  <code>fn = [f\_div](fnliterals.scad#function-f_div)(a=);</code>  <code>fn = [f\_div](fnliterals.scad#function-f_div)(b);</code>  <code>fn = [f\_div](fnliterals.scad#function-f_div)(a=,b=);</code>  
<code>fn = [f\_mod](fnliterals.scad#function-f_mod)();</code>  <code>fn = [f\_mod](fnliterals.scad#function-f_mod)(a=);</code>  <code>fn = [f\_mod](fnliterals.scad#function-f_mod)(b);</code>  <code>fn = [f\_mod](fnliterals.scad#function-f_mod)(a=,b=);</code>  
<code>fn = [f\_pow](fnliterals.scad#function-f_pow)();</code>  <code>fn = [f\_pow](fnliterals.scad#function-f_pow)(a=);</code>  <code>fn = [f\_pow](fnliterals.scad#function-f_pow)(b);</code>  <code>fn = [f\_pow](fnliterals.scad#function-f_pow)(a=,b=);</code>  
<code>fn = [f\_neg](fnliterals.scad#function-f_neg)();</code>  <code>fn = [f\_neg](fnliterals.scad#function-f_neg)(a);</code>  

### Section: Min/Max Operators

<code>fn = [f\_min](fnliterals.scad#function-f_min)();</code>  <code>fn = [f\_min](fnliterals.scad#function-f_min)(a);</code>  
<code>fn = [f\_max](fnliterals.scad#function-f_max)();</code>  <code>fn = [f\_max](fnliterals.scad#function-f_max)(a);</code>  
<code>fn = [f\_min2](fnliterals.scad#function-f_min2)();</code>  <code>fn = [f\_min2](fnliterals.scad#function-f_min2)(a=);</code>  <code>fn = [f\_min2](fnliterals.scad#function-f_min2)(b);</code>  <code>fn = [f\_min2](fnliterals.scad#function-f_min2)(a=,b=);</code>  
<code>fn = [f\_max2](fnliterals.scad#function-f_max2)();</code>  <code>fn = [f\_max2](fnliterals.scad#function-f_max2)(a=);</code>  <code>fn = [f\_max2](fnliterals.scad#function-f_max2)(b);</code>  <code>fn = [f\_max2](fnliterals.scad#function-f_max2)(a=,b=);</code>  
<code>fn = [f\_min3](fnliterals.scad#function-f_min3)();</code>  <code>fn = [f\_min3](fnliterals.scad#function-f_min3)(a=);</code>  <code>fn = [f\_min3](fnliterals.scad#function-f_min3)(b=);</code>  <code>fn = [f\_min3](fnliterals.scad#function-f_min3)(c=);</code>  <code>fn = [f\_min3](fnliterals.scad#function-f_min3)(a=,b=);</code>  <code>fn = [f\_min3](fnliterals.scad#function-f_min3)(b=,c=);</code>  <code>fn = [f\_min3](fnliterals.scad#function-f_min3)(a=,c=);</code>  <code>fn = [f\_min3](fnliterals.scad#function-f_min3)(a=,b=,c=);</code>  
<code>fn = [f\_max3](fnliterals.scad#function-f_max3)();</code>  <code>fn = [f\_max3](fnliterals.scad#function-f_max3)(a=);</code>  <code>fn = [f\_max3](fnliterals.scad#function-f_max3)(b=);</code>  <code>fn = [f\_max3](fnliterals.scad#function-f_max3)(c=);</code>  <code>fn = [f\_max3](fnliterals.scad#function-f_max3)(a=,b=);</code>  <code>fn = [f\_max3](fnliterals.scad#function-f_max3)(b=,c=);</code>  <code>fn = [f\_max3](fnliterals.scad#function-f_max3)(a=,c=);</code>  <code>fn = [f\_max3](fnliterals.scad#function-f_max3)(a=,b=,c=);</code>  

### Section: Trigonometry Operators

<code>fn = [f\_sin](fnliterals.scad#function-f_sin)();</code>  <code>fn = [f\_sin](fnliterals.scad#function-f_sin)(a);</code>  
<code>fn = [f\_cos](fnliterals.scad#function-f_cos)();</code>  <code>fn = [f\_cos](fnliterals.scad#function-f_cos)(a);</code>  
<code>fn = [f\_tan](fnliterals.scad#function-f_tan)();</code>  <code>fn = [f\_tan](fnliterals.scad#function-f_tan)(a);</code>  
<code>fn = [f\_asin](fnliterals.scad#function-f_asin)();</code>  <code>fn = [f\_asin](fnliterals.scad#function-f_asin)(a);</code>  
<code>fn = [f\_acos](fnliterals.scad#function-f_acos)();</code>  <code>fn = [f\_acos](fnliterals.scad#function-f_acos)(a);</code>  
<code>fn = [f\_atan](fnliterals.scad#function-f_atan)();</code>  <code>fn = [f\_atan](fnliterals.scad#function-f_atan)(a);</code>  
<code>fn = [f\_atan2](fnliterals.scad#function-f_atan2)();</code>  <code>fn = [f\_atan2](fnliterals.scad#function-f_atan2)(a=);</code>  <code>fn = [f\_atan2](fnliterals.scad#function-f_atan2)(b);</code>  <code>fn = [f\_atan2](fnliterals.scad#function-f_atan2)(a=,b=);</code>  

### Section: String Operators

<code>fn = [f\_len](fnliterals.scad#function-f_len)();</code>  <code>fn = [f\_len](fnliterals.scad#function-f_len)(a);</code>  
<code>fn = [f\_chr](fnliterals.scad#function-f_chr)();</code>  <code>fn = [f\_chr](fnliterals.scad#function-f_chr)(a);</code>  
<code>fn = [f\_ord](fnliterals.scad#function-f_ord)();</code>  <code>fn = [f\_ord](fnliterals.scad#function-f_ord)(a);</code>  
<code>fn = [f\_str](fnliterals.scad#function-f_str)();</code>  <code>fn = [f\_str](fnliterals.scad#function-f_str)(a);</code>  
<code>fn = [f\_str2](fnliterals.scad#function-f_str2)();</code>  <code>fn = [f\_str2](fnliterals.scad#function-f_str2)(a=);</code>  <code>fn = [f\_str2](fnliterals.scad#function-f_str2)(b);</code>  <code>fn = [f\_str2](fnliterals.scad#function-f_str2)(a=,b=);</code>  
<code>fn = [f\_str3](fnliterals.scad#function-f_str3)();</code>  <code>fn = [f\_str3](fnliterals.scad#function-f_str3)(a=);</code>  <code>fn = [f\_str3](fnliterals.scad#function-f_str3)(b=);</code>  <code>fn = [f\_str3](fnliterals.scad#function-f_str3)(c=);</code>  <code>fn = [f\_str3](fnliterals.scad#function-f_str3)(a=,b=);</code>  <code>fn = [f\_str3](fnliterals.scad#function-f_str3)(b=,c=);</code>  <code>fn = [f\_str3](fnliterals.scad#function-f_str3)(a=,c=);</code>  <code>fn = [f\_str3](fnliterals.scad#function-f_str3)(a=,b=,c=);</code>  

### Section: Miscellaneous Operators

<code>fn = [f\_floor](fnliterals.scad#function-f_floor)();</code>  <code>fn = [f\_floor](fnliterals.scad#function-f_floor)(a);</code>  
<code>fn = [f\_round](fnliterals.scad#function-f_round)();</code>  <code>fn = [f\_round](fnliterals.scad#function-f_round)(a);</code>  
<code>fn = [f\_ceil](fnliterals.scad#function-f_ceil)();</code>  <code>fn = [f\_ceil](fnliterals.scad#function-f_ceil)(a);</code>  
<code>fn = [f\_abs](fnliterals.scad#function-f_abs)();</code>  <code>fn = [f\_abs](fnliterals.scad#function-f_abs)(a);</code>  
<code>fn = [f\_sign](fnliterals.scad#function-f_sign)();</code>  <code>fn = [f\_sign](fnliterals.scad#function-f_sign)(a);</code>  
<code>fn = [f\_ln](fnliterals.scad#function-f_ln)();</code>  <code>fn = [f\_ln](fnliterals.scad#function-f_ln)(a);</code>  
<code>fn = [f\_log](fnliterals.scad#function-f_log)();</code>  <code>fn = [f\_log](fnliterals.scad#function-f_log)(a);</code>  
<code>fn = [f\_exp](fnliterals.scad#function-f_exp)();</code>  <code>fn = [f\_exp](fnliterals.scad#function-f_exp)(a);</code>  
<code>fn = [f\_sqr](fnliterals.scad#function-f_sqr)();</code>  <code>fn = [f\_sqr](fnliterals.scad#function-f_sqr)(a);</code>  
<code>fn = [f\_sqrt](fnliterals.scad#function-f_sqrt)();</code>  <code>fn = [f\_sqrt](fnliterals.scad#function-f_sqrt)(a);</code>  
<code>fn = [f\_norm](fnliterals.scad#function-f_norm)();</code>  <code>fn = [f\_norm](fnliterals.scad#function-f_norm)(a);</code>  
<code>fn = [f\_cross](fnliterals.scad#function-f_cross)();</code>  <code>fn = [f\_cross](fnliterals.scad#function-f_cross)(a=);</code>  <code>fn = [f\_cross](fnliterals.scad#function-f_cross)(b);</code>  <code>fn = [f\_cross](fnliterals.scad#function-f_cross)(a=,b=);</code>  

### Section: Type Queries

<code>fn = [f\_is\_def](fnliterals.scad#function-f_is_def)();</code>  
<code>fn = [f\_is\_undef](fnliterals.scad#function-f_is_undef)();</code>  
<code>fn = [f\_is\_bool](fnliterals.scad#function-f_is_bool)();</code>  
<code>fn = [f\_is\_num](fnliterals.scad#function-f_is_num)();</code>  
<code>fn = [f\_is\_int](fnliterals.scad#function-f_is_int)();</code>  
<code>fn = [f\_is\_nan](fnliterals.scad#function-f_is_nan)();</code>  
<code>fn = [f\_is\_finite](fnliterals.scad#function-f_is_finite)();</code>  
<code>fn = [f\_is\_string](fnliterals.scad#function-f_is_string)();</code>  
<code>fn = [f\_is\_list](fnliterals.scad#function-f_is_list)();</code>  
<code>fn = [f\_is\_range](fnliterals.scad#function-f_is_range)();</code>  
<code>fn = [f\_is\_function](fnliterals.scad#function-f_is_function)();</code>  
<code>fn = [f\_is\_vector](fnliterals.scad#function-f_is_vector)();</code>  
<code>fn = [f\_is\_path](fnliterals.scad#function-f_is_path)();</code>  
<code>fn = [f\_is\_region](fnliterals.scad#function-f_is_region)();</code>  
<code>fn = [f\_is\_vnf](fnliterals.scad#function-f_is_vnf)();</code>  
<code>fn = [f\_is\_patch](fnliterals.scad#function-f_is_patch)();</code>  

## LibFile: threading.scad

### Section: Generic Threading

<code>[thread\_helix](threading.scad#module-thread_helix)(d, pitch, [thread\_depth], [flank\_angle], [twist], [profile=], [left\_handed=], [higbee=], [internal=]);</code>  

## LibFile: screws.scad

### Section: Generic Screw Creation

<code>info = [screw\_info](screws.scad#function-screw_info)(name, [head], [thread], [drive], [drive\_size], [oversize])</code>  
<code>[screw\_head](screws.scad#module-screw_head)(screw\_info, [details])</code>  
<code>[screw](screws.scad#module-screw)([name],[head],[thread],[drive],[drive\_size], [length], [shank], [oversize], [tolerance], [$slop], [spec], [details], [anchor], [anchor\_head], [orient], [spin])</code>  
<code>[thread\_specification](screws.scad#function-thread_specification)(screw\_spec, [tolerance], [internal])</code>  
<code>[nut](screws.scad#module-nut)([name],diameter, thickness,[thread],[oversize],[spec],[tolerance],[details],[$slop])</code>  

## LibFile: metric\_screws.scad

### Section: Modules

<code>[generic\_screw](metric_screws.scad#module-generic_screw)(screwsize, screwlen, headsize, headlen)</code>  

## LibFile: bottlecaps.scad

### Section: PCO-1810 Bottle Threading

<code>[pco1810\_neck](bottlecaps.scad#module-pco1810_neck)([wall])</code>  
<code>[pco1810\_cap](bottlecaps.scad#module-pco1810_cap)([wall], [texture]);</code>  

### Section: PCO-1881 Bottle Threading

<code>[pco1881\_neck](bottlecaps.scad#module-pco1881_neck)([wall])</code>  
<code>[pco1881\_cap](bottlecaps.scad#module-pco1881_cap)(wall, [texture]);</code>  

### Section: Generic Bottle Connectors

<code>[generic\_bottle\_neck](bottlecaps.scad#module-generic_bottle_neck)([wall], ...)</code>  
<code>[generic\_bottle\_cap](bottlecaps.scad#module-generic_bottle_cap)(wall, [texture], ...);</code>  
<code>[bottle\_adapter\_neck\_to\_cap](bottlecaps.scad#module-bottle_adapter_neck_to_cap)(wall, [texture]);</code>  
<code>[bottle\_adapter\_cap\_to\_cap](bottlecaps.scad#module-bottle_adapter_cap_to_cap)(wall, [texture]);</code>  
<code>[bottle\_adapter\_neck\_to\_neck](bottlecaps.scad#module-bottle_adapter_neck_to_neck)();</code>  

### Section: SPI Bottle Threading

<code>[sp\_neck](bottlecaps.scad#module-sp_neck)(diam, type, wall|id, [style], [bead], [anchor], [spin], [orient])</code>  
<code>true\_diam = [sp\_diameter](bottlecaps.scad#function-sp_diameter)(diam,type)</code>  

## LibFile: screw\_drive.scad

### Section: Phillips Drive

<code>depth = [phillips\_depth](screw_drive.scad#function-phillips_depth)(size, d);</code>  
<code>diam = [phillips\_diam](screw_drive.scad#function-phillips_diam)(size, depth);</code>  

### Section: Torx Drive

<code>diam = [torx\_outer\_diam](screw_drive.scad#function-torx_outer_diam)(size);</code>  
<code>diam = [torx\_inner\_diam](screw_drive.scad#function-torx_inner_diam)(size);</code>  
<code>depth = [torx\_depth](screw_drive.scad#function-torx_depth)(size);</code>  
<code>rad = [torx\_tip\_radius](screw_drive.scad#function-torx_tip_radius)(size);</code>  
<code>rad = [torx\_rounding\_radius](screw_drive.scad#function-torx_rounding_radius)(size);</code>  
<code>[torx\_mask2d](screw_drive.scad#module-torx_mask2d)(size);</code>  
<code>[torx\_mask](screw_drive.scad#module-torx_mask)(size, l, [center]);</code>  

### Section: Robertson/Square Drives

<code>[robertson\_mask](screw_drive.scad#module-robertson_mask)(size, [extra]);</code>  

## LibFile: joiners.scad

### Section: Half Joiners

<code>[half\_joiner\_clear](joiners.scad#module-half_joiner_clear)(h, w, [a], [clearance], [overlap])</code>  
<code>[half\_joiner](joiners.scad#module-half_joiner)(h, w, l, [a], [screwsize], [guides], [$slop])</code>  
<code>[half\_joiner2](joiners.scad#module-half_joiner2)(h, w, l, [a], [screwsize], [guides])</code>  

### Section: Full Joiners

<code>[joiner\_clear](joiners.scad#module-joiner_clear)(h, w, [a], [clearance], [overlap])</code>  
<code>[joiner](joiners.scad#module-joiner)(h, w, l, [a], [screwsize], [guides], [$slop])</code>  

### Section: Full Joiners Pairs/Sets

<code>[joiner\_pair\_clear](joiners.scad#module-joiner_pair_clear)(spacing, [n], [h], [w], [a], [clearance], [overlap])</code>  
<code>[joiner\_pair](joiners.scad#module-joiner_pair)(h, w, l, [a], [screwsize], [guides], [$slop])</code>  

### Section: Full Joiners Quads/Sets

<code>[joiner\_quad\_clear](joiners.scad#module-joiner_quad_clear)(spacing, [n], [h], [w], [a], [clearance], [overlap])</code>  
<code>[joiner\_quad](joiners.scad#module-joiner_quad)(h, w, l, [a], [screwsize], [guides], [$slop])</code>  

### Section: Dovetails

<code>[dovetail](joiners.scad#module-dovetail)(gender, w|width, h|height, slide, [slope|angle], [taper|back\_width], [chamfer], [r|radius], [round], [extra], [$slop])</code>  

### Section: Tension Clips

<code>[snap\_pin](joiners.scad#module-snap_pin)(size, [pointed], [anchor], [spin], [orient])</code>  <code>[snap\_pin](joiners.scad#module-snap_pin)(r|radius|d|diameter, l|length, nub\_depth, snap, thickness, [clearance], [preload], [pointed], [anchor], [spin], [orient])</code>  
<code>[snap\_pin\_socket](joiners.scad#module-snap_pin_socket)(size, [fixed], [fins], [pointed], [anchor], [spin], [orient]);</code>  <code>[snap\_pin\_socket](joiners.scad#module-snap_pin_socket)(r|radius|d|diameter, l|length, nub\_depth, snap, [fixed], [pointed], [fins], [anchor], [spin], [orient])</code>  
<code>[rabbit\_clip](joiners.scad#module-rabbit_clip)(type, length, width, snap, thickness, depth, [compression], [clearance], [lock], [lock\_clearance], [splineteps], [anchor], [orient], [spin])</code>  

## LibFile: polyhedra.scad

### Section: Polyhedra

<code>x = [regular\_polyhedron\_info](polyhedra.scad#function-regular_polyhedron_info)(info, ....);</code>  

## LibFile: cubetruss.scad

### Section: Cube Trusses

<code>[cubetruss\_dist](cubetruss.scad#function-cubetruss_dist)(cubes, gaps, [size], [strut]);</code>  
<code>[cubetruss\_segment](cubetruss.scad#module-cubetruss_segment)([size], [strut], [bracing]);</code>  
<code>[cubetruss\_support](cubetruss.scad#module-cubetruss_support)([size], [strut]);</code>  
<code>[cubetruss\_clip](cubetruss.scad#module-cubetruss_clip)(extents, [size], [strut], [clipthick]);</code>  
<code>[cubetruss\_foot](cubetruss.scad#module-cubetruss_foot)(w, [size], [strut], [clipthick]);</code>  
<code>[cubetruss\_joiner](cubetruss.scad#module-cubetruss_joiner)([w], [vert], [size], [strut], [clipthick]);</code>  
<code>[cubetruss\_uclip](cubetruss.scad#module-cubetruss_uclip)(dual, [size], [strut], [clipthick]);</code>  
<code>[cubetruss](cubetruss.scad#module-cubetruss)(extents, [clips], [bracing], [size], [strut], [clipthick]);</code>  
<code>[cubetruss\_corner](cubetruss.scad#module-cubetruss_corner)(h, extents, [bracing], [size], [strut], [clipthick]);</code>  

## LibFile: gears.scad

### Section: Functions

<code>circp = [circular\_pitch](gears.scad#function-circular_pitch)(pitch|mod);</code>  
<code>dp = [diametral\_pitch](gears.scad#function-diametral_pitch)(pitch|mod);</code>  
<code>pitch = [pitch\_value](gears.scad#function-pitch_value)(mod);</code>  
<code>mod = [module\_value](gears.scad#function-module_value)(pitch);</code>  
<code>ad = [adendum](gears.scad#function-adendum)(pitch|mod);</code>  
<code>ddn = [dedendum](gears.scad#function-dedendum)(pitch|mod, [clearance]);</code>  
<code>pr = [pitch\_radius](gears.scad#function-pitch_radius)(pitch|mod, teeth);</code>  
<code>or = [outer\_radius](gears.scad#function-outer_radius)(pitch|mod, teeth, [clearance], [interior]);</code>  
<code>rr = [root\_radius](gears.scad#function-root_radius)(pitch|mod, teeth, [clearance], [interior]);</code>  
<code>br = [base\_radius](gears.scad#function-base_radius)(pitch|mod, teeth, [pressure\_angle]);</code>  
<code>ang = [bevel\_pitch\_angle](gears.scad#function-bevel_pitch_angle)(teeth, mate\_teeth, [drive\_angle]);</code>  
<code>thick = [worm\_gear\_thickness](gears.scad#function-worm_gear_thickness)(pitch|mod, teeth, worm\_diam, [worm\_arc], [crowning], [clearance]);</code>  

### Section: 2D Profiles

<code>[gear\_tooth\_profile](gears.scad#functionmodule-gear_tooth_profile)(pitch|mod, teeth, [pressure\_angle], [clearance], [backlash], [interior], [valleys]);</code>  <code>path = [gear\_tooth\_profile](gears.scad#functionmodule-gear_tooth_profile)(pitch|mod, teeth, [pressure\_angle], [clearance], [backlash], [interior], [valleys]);</code>  
<code>[spur\_gear2d](gears.scad#functionmodule-spur_gear2d)(pitch|mod, teeth, [hide], [pressure\_angle], [clearance], [backlash], [interior]);</code>  <code>poly = [spur\_gear2d](gears.scad#functionmodule-spur_gear2d)(pitch|mod, teeth, [hide], [pressure\_angle], [clearance], [backlash], [interior]);</code>  
<code>path = [rack2d](gears.scad#functionmodule-rack2d)(pitch|mod, teeth, height, [pressure\_angle], [backlash]);</code>  <code>[rack2d](gears.scad#functionmodule-rack2d)(pitch|mod, teeth, height, [pressure\_angle], [backlash]);</code>  

### Section: 3D Gears and Racks

<code>[spur\_gear](gears.scad#functionmodule-spur_gear)(pitch, teeth, thickness, [shaft\_diam=], [hide], [pressure\_angle], [clearance], [backlash], [helical], [slices], [interior]);</code>  <code>[spur\_gear](gears.scad#functionmodule-spur_gear)(mod=, teeth=, thickness=, [shaft\_diam=], ...);</code>  <code>vnf = [spur\_gear](gears.scad#functionmodule-spur_gear)(pitch, teeth, thickness, [shaft\_diam], ...);</code>  <code>vnf = [spur\_gear](gears.scad#functionmodule-spur_gear)(mod=, teeth=, thickness=, [shaft\_diam], ...);</code>  
<code>[bevel\_gear](gears.scad#functionmodule-bevel_gear)(pitch|mod, teeth, face\_width, pitch\_angle, [shaft\_diam], [hide], [pressure\_angle], [clearance], [backlash], [cutter\_radius], [spiral\_angle], [slices], [interior]);</code>  <code>vnf = [bevel\_gear](gears.scad#functionmodule-bevel_gear)(pitch|mod, teeth, face\_width, pitch\_angle, [hide], [pressure\_angle], [clearance], [backlash], [cutter\_radius], [spiral\_angle], [slices], [interior]);</code>  
<code>[rack](gears.scad#functionmodule-rack)(pitch, teeth, thickness, height, [pressure\_angle=], [backlash=]);</code>  <code>[rack](gears.scad#functionmodule-rack)(mod=, teeth=, thickness=, height=, [pressure\_angle=], [backlash]=);</code>  <code>vnf = [rack](gears.scad#functionmodule-rack)(pitch, teeth, thickness, height, [pressure\_angle=], [backlash=]);</code>  <code>vnf = [rack](gears.scad#functionmodule-rack)(mod=, teeth=, thickness=, height=, [pressure\_angle=], [backlash=]);</code>  
<code>[worm](gears.scad#functionmodule-worm)(pitch|mod, d, l, [starts], [left\_handed], [pressure\_angle], [backlash], [clearance]);</code>  <code>vnf = [worm](gears.scad#functionmodule-worm)(pitch|mod, d, l, [starts], [left\_handed], [pressure\_angle], [backlash], [clearance]);</code>  
<code>[worm\_gear](gears.scad#functionmodule-worm_gear)(pitch|mod, teeth, worm\_diam, [worm\_starts], [crowning], [left\_handed], [pressure\_angle], [backlash], [slices], [clearance], [shaft\_diam]);</code>  <code>vnf = [worm\_gear](gears.scad#functionmodule-worm_gear)(pitch|mod, teeth, worm\_diam, [worm\_starts], [crowning], [left\_handed], [pressure\_angle], [backlash], [slices], [clearance]);</code>  

## LibFile: modular\_hose.scad

### Section: Modular Hose Parts

<code>[modular\_hose](modular_hose.scad#module-modular_hose)(size, type, [clearance], [waist\_len], [anchor], [spin], [orient]) [attachments]</code>  
<code>r = [modular\_hose\_radius](modular_hose.scad#function-modular_hose_radius)(size, [outer]);</code>  

## LibFile: hingesnaps.scad

### Section: Hinges and Snaps

<code>[folding\_hinge\_mask](hingesnaps.scad#module-folding_hinge_mask)(l, thick, [layerheight], [foldangle], [hingegap], [anchor], [spin], [orient]);</code>  
<code>[snap\_lock](hingesnaps.scad#module-snap_lock)(thick, [snaplen], [snapdiam], [layerheight], [foldangle], [hingegap], [anchor], [spin], [orient]);</code>  
<code>[snap\_socket](hingesnaps.scad#module-snap_socket)(thick, [snaplen], [snapdiam], [layerheight], [foldangle], [hingegap], [anchor], [spin], [orient]);</code>  
<code>[apply\_folding\_hinges\_and\_snaps](hingesnaps.scad#module-apply_folding_hinges_and_snaps)(thick, [foldangle], [hinges], [snaps], [sockets], [snaplen], [snapdiam], [hingegap], [layerheight]) ...</code>  

## LibFile: walls.scad

### Section: Walls

<code>[narrowing\_strut](walls.scad#module-narrowing_strut)(w, l, wall, [ang]);</code>  
<code>[thinning\_wall](walls.scad#module-thinning_wall)(h, l, thick, [ang], [strut], [wall]);</code>  
<code>[thinning\_triangle](walls.scad#module-thinning_triangle)(h, l, thick, [ang], [strut], [wall], [diagonly], [center]);</code>  
<code>[sparse\_strut](walls.scad#module-sparse_strut)(h, l, thick, [strut], [maxang], [max\_bridge])</code>  
<code>[sparse\_strut3d](walls.scad#module-sparse_strut3d)(h, w, l, [thick], [maxang], [max\_bridge], [strut]);</code>  
<code>[corrugated\_wall](walls.scad#module-corrugated_wall)(h, l, thick, [strut], [wall]);</code>  

## LibFile: wiring.scad

### Section: Functions

<code>[hex\_offset\_ring](wiring.scad#function-hex_offset_ring)(d, lev)</code>  
<code>[hex\_offsets](wiring.scad#function-hex_offsets)(n, d)</code>  

### Section: Modules

<code>[wiring](wiring.scad#module-wiring)(path, wires, [wirediam], [rounding], [wirenum], [bezsteps]);</code>  

## LibFile: knurling.scad

### Section: Knurling

<code>[knurled\_cylinder](knurling.scad#module-knurled_cylinder)(l, r|d, [overage], [count], [profile], [helix]);</code>  <code>[knurled\_cylinder](knurling.scad#module-knurled_cylinder)(l, r1|d1, r2|d2, [overage], [count], [profile], [helix]);</code>  
<code>[knurled\_cylinder\_mask](knurling.scad#module-knurled_cylinder_mask)(l, r|d, [overage], [count], [profile], [helix]);</code>  <code>[knurled\_cylinder\_mask](knurling.scad#module-knurled_cylinder_mask)(l, r1|d1, r2|d2, [overage], [count], [profile], [helix]);</code>  

## LibFile: sliders.scad

### Section: Modules

<code>[slider](sliders.scad#module-slider)(l, w, h, [base], [wall], [ang], [$slop])</code>  
<code>[rail](sliders.scad#module-rail)(l, w, h, [chamfer], [ang])</code>  

