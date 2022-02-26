# Table of Contents

## List of Files

**Basic Modeling:** 

- [transforms.scad](#1-transformsscad) ([docs](transforms.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Shortcuts for translation, rotation, etc.  Can act on geometry, paths, or can return a matrix.
- [attachments.scad](#2-attachmentsscad) ([docs](attachments.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Positioning objects on or relative to other objects.  Making your own objects support attachment.
- [shapes2d.scad](#3-shapes2dscad) ([docs](shapes2d.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Attachable circles, squares, polygons, teardrop.  Can make geometry or paths.
- [shapes3d.scad](#4-shapes3dscad) ([docs](shapes3d.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Attachable cubes, cylinders, spheres, ruler, and text.  Many can produce a VNF.
- [drawing.scad](#5-drawingscad) ([docs](drawing.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Create and draw 2D and 3D paths: arc, helix, turtle graphics
- [masks2d.scad](#6-masks2dscad) ([docs](masks2d.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
2D masking shapes for edge profiling: including roundover, cove, teardrop, ogee.
- [masks3d.scad](#7-masks3dscad) ([docs](masks3d.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
3D masks for rounding edges and corners.
- [distributors.scad](#8-distributorsscad) ([docs](distributors.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Copy or distribute objects onto a line or grid.  Mirror shortcuts.
- [color.scad](#9-colorscad) ([docs](color.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
HSV and HSL conversion, color multiple objects
- [mutators.scad](#11-mutatorsscad) ([docs](mutators.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Modules and Functions to mutate items.

**Advanced Modeling:** 

- [partitions.scad](#10-partitionsscad) ([docs](partitions.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Cut objects with a plane or partition them into interlocking pieces.
- [paths.scad](#12-pathsscad) ([docs](paths.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Operations on paths: length, resampling, tangents, splitting into subpaths
- [regions.scad](#13-regionsscad) ([docs](regions.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Offsets and boolean geometry of 2D paths and regions.
- [vnf.scad](#14-vnfscad) ([docs](vnf.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Vertices 'n' Faces structure.  Makes polyhedron() easier to use.
- [beziers.scad](#15-beziersscad) ([docs](beziers.scad))
Bezier curves and surfaces.
- [rounding.scad](#16-roundingscad) ([docs](rounding.scad))
Round path corners, rounded prisms, rounded cutouts in tubes.
- [skin.scad](#17-skinscad) ([docs](skin.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Construct 3D shapes from 2D cross sections of the desired shape.
- [turtle3d.scad](#18-turtle3dscad) ([docs](turtle3d.scad))
3D turtle graphics for making paths or lists of transformations.

**Math:** 

- [math.scad](#19-mathscad) ([docs](math.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
General miscellaneous math function.
- [linalg.scad](#20-linalgscad) ([docs](linalg.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Linear Algebra: solve linear systems, construct and modify matrices.
- [vectors.scad](#21-vectorsscad) ([docs](vectors.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Vector arithmetic, angle, and searching.
- [quaternions.scad](#22-quaternionsscad) ([docs](quaternions.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Quaternion based rotations that avoid gimbal lock issues.
- [coords.scad](#23-coordsscad) ([docs](coords.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Conversions between coordinate systems.
- [geometry.scad](#24-geometryscad) ([docs](geometry.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Geometrical calculations including intersections of lines, circles and planes, circle from 3 points
- [trigonometry.scad](#25-trigonometryscad) ([docs](trigonometry.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Trigonometry shortcuts for when you can't recall the mnemonic SOHCAHTOA.

**Data Management:** 

- [version.scad](#27-versionscad) ([docs](version.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Parse and compare semantic versions.
- [comparisons.scad](#28-comparisonsscad) ([docs](comparisons.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Comparisons and sorting.
- [lists.scad](#29-listsscad) ([docs](lists.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
List indexing, change list structure, rearrange/modify lists
- [utility.scad](#30-utilityscad) ([docs](utility.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
Type checking, dealing with undefs, processing function args
- [strings.scad](#31-stringsscad) ([docs](strings.scad)) <sup title="Included in std.scad">[STD](#file-footnotes)</sup>
String manipulation functions.
- [structs.scad](#32-structsscad) ([docs](structs.scad))
Structure/Dictionary Manipulation
- [fnliterals.scad](#33-fnliteralsscad) ([docs](fnliterals.scad))
Function Literal Algorithms, and factories for generating function literals for builtin functions.

**Threaded Parts:** 

- [threading.scad](#34-threadingscad) ([docs](threading.scad))
Various types of threaded rods and nuts.
- [screws.scad](#35-screwsscad) ([docs](screws.scad))
ISO (metric) and UTS screws and nuts.
- [metric\_screws.scad](#36-metric_screwsscad) ([docs](metric_screws.scad))
Metric screws, nuts, and screwholes.
- [bottlecaps.scad](#37-bottlecapsscad) ([docs](bottlecaps.scad))
Standard bottle caps and necks.
- [screw\_drive.scad](#38-screw_drivescad) ([docs](screw_drive.scad))
Masks for Phillips/Torx/etc driver holes.

**Parts:** 

- [linear\_bearings.scad](#39-linear_bearingsscad) ([docs](linear_bearings.scad))
Mounts for LMxUU style linear bearings.
- [joiners.scad](#40-joinersscad) ([docs](joiners.scad))
Joiner shapes for connecting separately printed objects.
- [polyhedra.scad](#41-polyhedrascad) ([docs](polyhedra.scad))
Platonic, Archimidean, Catalan, and stellated polyhedra.
- [cubetruss.scad](#42-cubetrussscad) ([docs](cubetruss.scad))
Modular open-framed trusses and joiners.
- [gears.scad](#43-gearsscad) ([docs](gears.scad))
Gears, racks, worms, and worm gears.
- [modular\_hose.scad](#44-modular_hosescad) ([docs](modular_hose.scad))
Modular flexible hose parts.
- [hingesnaps.scad](#45-hingesnapsscad) ([docs](hingesnaps.scad))
Foldable, snap-locking parts.
- [nema\_steppers.scad](#46-nema_steppersscad) ([docs](nema_steppers.scad))
Mounting holes for NEMA motors, and simple motor models.
- [walls.scad](#47-wallsscad) ([docs](walls.scad))
Walls and structural elements that 3D print without support.
- [wiring.scad](#48-wiringscad) ([docs](wiring.scad))
Routed bundles of wires.
- [knurling.scad](#49-knurlingscad) ([docs](knurling.scad))
Masks and shapes to create knurling.
- [sliders.scad](#50-slidersscad) ([docs](sliders.scad))
Simple sliders and rails.

**Miscellaneous:** 

- [constants.scad](#26-constantsscad) ([docs](constants.scad))



## File Footnotes:

STD = Included in std.scad  

## 1. [transforms.scad](transforms.scad)

Shortcuts for translation, rotation, etc.  Can act on geometry, paths, or can return a matrix.  
*Included in std.scad*  
- [Affine Transformations](transforms.scad#section-affine-transformations)  
    
- [Translations](transforms.scad#section-translations)  
    [`move()`](transforms.scad#functionmodule-move) [`left()`](transforms.scad#functionmodule-left) [`right()`](transforms.scad#functionmodule-right) [`fwd()`](transforms.scad#functionmodule-fwd) [`back()`](transforms.scad#functionmodule-back) [`down()`](transforms.scad#functionmodule-down) [`up()`](transforms.scad#functionmodule-up)
- [Rotations](transforms.scad#section-rotations)  
    [`rot()`](transforms.scad#functionmodule-rot) [`xrot()`](transforms.scad#functionmodule-xrot) [`yrot()`](transforms.scad#functionmodule-yrot) [`zrot()`](transforms.scad#functionmodule-zrot)
- [Scaling](transforms.scad#section-scaling)  
    [`scale()`](transforms.scad#functionmodule-scale) [`xscale()`](transforms.scad#functionmodule-xscale) [`yscale()`](transforms.scad#functionmodule-yscale) [`zscale()`](transforms.scad#functionmodule-zscale)
- [Reflection (Mirroring)](transforms.scad#section-reflection-mirroring)  
    [`mirror()`](transforms.scad#functionmodule-mirror) [`xflip()`](transforms.scad#functionmodule-xflip) [`yflip()`](transforms.scad#functionmodule-yflip) [`zflip()`](transforms.scad#functionmodule-zflip)
- [Other Transformations](transforms.scad#section-other-transformations)  
    [`frame_map()`](transforms.scad#functionmodule-frame_map) [`skew()`](transforms.scad#functionmodule-skew)
- [Applying transformation matrices to data](transforms.scad#section-applying-transformation-matrices-to-data)  
    [`apply()`](transforms.scad#function-apply)

## 2. [attachments.scad](attachments.scad)

Positioning objects on or relative to other objects.  Making your own objects support attachment.  
*Included in std.scad*  
- [Terminology and Shortcuts](attachments.scad#section-terminology-and-shortcuts)  
    - [Anchor](attachments.scad#subsection-anchor)
    - [Spin](attachments.scad#subsection-spin)
    - [Orient](attachments.scad#subsection-orient)
    - [Specifying Directions](attachments.scad#subsection-specifying-directions)
    - [Specifying Faces](attachments.scad#subsection-specifying-faces)
    - [Specifying Edges](attachments.scad#subsection-specifying-edges)
    - [Specifying Corners](attachments.scad#subsection-specifying-corners)

    
- [Attachment Positioning](attachments.scad#section-attachment-positioning)  
    [`position()`](attachments.scad#module-position) [`orient()`](attachments.scad#module-orient) [`attach()`](attachments.scad#module-attach)
- [Attachment Modifiers](attachments.scad#section-attachment-modifiers)  
    [`tags()`](attachments.scad#module-tags) [`diff()`](attachments.scad#module-diff) [`intersect()`](attachments.scad#module-intersect) [`hulling()`](attachments.scad#module-hulling) [`recolor()`](attachments.scad#module-recolor) [`hide()`](attachments.scad#module-hide) [`show()`](attachments.scad#module-show)
- [Attachable Masks](attachments.scad#section-attachable-masks)  
    [`edge_mask()`](attachments.scad#module-edge_mask) [`corner_mask()`](attachments.scad#module-corner_mask) [`face_profile()`](attachments.scad#module-face_profile) [`edge_profile()`](attachments.scad#module-edge_profile) [`corner_profile()`](attachments.scad#module-corner_profile)
- [Making your objects attachable](attachments.scad#section-making-your-objects-attachable)  
    [`attachable()`](attachments.scad#module-attachable) [`reorient()`](attachments.scad#function-reorient) [`named_anchor()`](attachments.scad#function-named_anchor)
- [Visualizing Anchors](attachments.scad#section-visualizing-anchors)  
    [`show_anchors()`](attachments.scad#module-show_anchors) [`anchor_arrow()`](attachments.scad#module-anchor_arrow) [`anchor_arrow2d()`](attachments.scad#module-anchor_arrow2d) [`expose_anchors()`](attachments.scad#module-expose_anchors) [`frame_ref()`](attachments.scad#module-frame_ref)

## 3. [shapes2d.scad](shapes2d.scad)

Attachable circles, squares, polygons, teardrop.  Can make geometry or paths.  
*Included in std.scad*  
- [2D Primitives](shapes2d.scad#section-2d-primitives)  
    [`square()`](shapes2d.scad#functionmodule-square) [`rect()`](shapes2d.scad#functionmodule-rect) [`circle()`](shapes2d.scad#functionmodule-circle) [`ellipse()`](shapes2d.scad#functionmodule-ellipse)
- [Polygons](shapes2d.scad#section-polygons)  
    [`regular_ngon()`](shapes2d.scad#functionmodule-regular_ngon) [`pentagon()`](shapes2d.scad#functionmodule-pentagon) [`hexagon()`](shapes2d.scad#functionmodule-hexagon) [`octagon()`](shapes2d.scad#functionmodule-octagon) [`right_triangle()`](shapes2d.scad#functionmodule-right_triangle) [`trapezoid()`](shapes2d.scad#functionmodule-trapezoid) [`star()`](shapes2d.scad#functionmodule-star) [`jittered_poly()`](shapes2d.scad#module-jittered_poly)
- [Curved 2D Shapes](shapes2d.scad#section-curved-2d-shapes)  
    [`teardrop2d()`](shapes2d.scad#functionmodule-teardrop2d) [`egg()`](shapes2d.scad#functionmodule-egg) [`glued_circles()`](shapes2d.scad#functionmodule-glued_circles) [`supershape()`](shapes2d.scad#functionmodule-supershape) [`reuleaux_polygon()`](shapes2d.scad#functionmodule-reuleaux_polygon)
- [Text](shapes2d.scad#section-text)  
    [`text()`](shapes2d.scad#module-text)
- [Rounding 2D shapes](shapes2d.scad#section-rounding-2d-shapes)  
    [`round2d()`](shapes2d.scad#module-round2d) [`shell2d()`](shapes2d.scad#module-shell2d)

## 4. [shapes3d.scad](shapes3d.scad)

Attachable cubes, cylinders, spheres, ruler, and text.  Many can produce a VNF.  
*Included in std.scad*  
- [Cuboids, Prismoids and Pyramids](shapes3d.scad#section-cuboids-prismoids-and-pyramids)  
    [`cube()`](shapes3d.scad#functionmodule-cube) [`cuboid()`](shapes3d.scad#module-cuboid) [`prismoid()`](shapes3d.scad#functionmodule-prismoid) [`octahedron()`](shapes3d.scad#functionmodule-octahedron) [`rect_tube()`](shapes3d.scad#module-rect_tube) [`wedge()`](shapes3d.scad#functionmodule-wedge)
- [Cylinders](shapes3d.scad#section-cylinders)  
    [`cylinder()`](shapes3d.scad#functionmodule-cylinder) [`cyl()`](shapes3d.scad#module-cyl) [`xcyl()`](shapes3d.scad#module-xcyl) [`ycyl()`](shapes3d.scad#module-ycyl) [`zcyl()`](shapes3d.scad#module-zcyl) [`tube()`](shapes3d.scad#module-tube) [`pie_slice()`](shapes3d.scad#functionmodule-pie_slice)
- [Other Round Objects](shapes3d.scad#section-other-round-objects)  
    [`sphere()`](shapes3d.scad#functionmodule-sphere) [`spheroid()`](shapes3d.scad#functionmodule-spheroid) [`torus()`](shapes3d.scad#functionmodule-torus) [`teardrop()`](shapes3d.scad#functionmodule-teardrop) [`onion()`](shapes3d.scad#functionmodule-onion)
- [Text](shapes3d.scad#section-text)  
    [`text3d()`](shapes3d.scad#module-text3d) [`path_text()`](shapes3d.scad#module-path_text)
- [Miscellaneous](shapes3d.scad#section-miscellaneous)  
    [`interior_fillet()`](shapes3d.scad#module-interior_fillet) [`heightfield()`](shapes3d.scad#functionmodule-heightfield) [`ruler()`](shapes3d.scad#module-ruler)

## 5. [drawing.scad](drawing.scad)

Create and draw 2D and 3D paths: arc, helix, turtle graphics  
*Included in std.scad*  
- [Line Drawing](drawing.scad#section-line-drawing)  
    [`stroke()`](drawing.scad#module-stroke) [`dashed_stroke()`](drawing.scad#functionmodule-dashed_stroke)
- [Computing paths](drawing.scad#section-computing-paths)  
    [`arc()`](drawing.scad#functionmodule-arc) [`helix()`](drawing.scad#function-helix) [`turtle()`](drawing.scad#function-turtle)
- [Debugging polygons](drawing.scad#section-debugging-polygons)  
    [`debug_polygon()`](drawing.scad#module-debug_polygon)

## 6. [masks2d.scad](masks2d.scad)

2D masking shapes for edge profiling: including roundover, cove, teardrop, ogee.  
*Included in std.scad*  
- [2D Masking Shapes](masks2d.scad#section-2d-masking-shapes)  
    [`mask2d_roundover()`](masks2d.scad#functionmodule-mask2d_roundover) [`mask2d_cove()`](masks2d.scad#functionmodule-mask2d_cove) [`mask2d_chamfer()`](masks2d.scad#functionmodule-mask2d_chamfer) [`mask2d_rabbet()`](masks2d.scad#functionmodule-mask2d_rabbet) [`mask2d_dovetail()`](masks2d.scad#functionmodule-mask2d_dovetail) [`mask2d_teardrop()`](masks2d.scad#functionmodule-mask2d_teardrop) [`mask2d_ogee()`](masks2d.scad#functionmodule-mask2d_ogee)

## 7. [masks3d.scad](masks3d.scad)

3D masks for rounding edges and corners.  
*Included in std.scad*  
- [Chamfer Masks](masks3d.scad#section-chamfer-masks)  
    [`chamfer_edge_mask()`](masks3d.scad#module-chamfer_edge_mask) [`chamfer_corner_mask()`](masks3d.scad#module-chamfer_corner_mask) [`chamfer_cylinder_mask()`](masks3d.scad#module-chamfer_cylinder_mask)
- [Rounding Masks](masks3d.scad#section-rounding-masks)  
    [`rounding_edge_mask()`](masks3d.scad#module-rounding_edge_mask) [`rounding_corner_mask()`](masks3d.scad#module-rounding_corner_mask) [`rounding_angled_edge_mask()`](masks3d.scad#module-rounding_angled_edge_mask) [`rounding_angled_corner_mask()`](masks3d.scad#module-rounding_angled_corner_mask) [`rounding_cylinder_mask()`](masks3d.scad#module-rounding_cylinder_mask) [`rounding_hole_mask()`](masks3d.scad#module-rounding_hole_mask)
- [Teardrop Masking](masks3d.scad#section-teardrop-masking)  
    [`teardrop_edge_mask()`](masks3d.scad#module-teardrop_edge_mask) [`teardrop_corner_mask()`](masks3d.scad#module-teardrop_corner_mask)

## 8. [distributors.scad](distributors.scad)

Copy or distribute objects onto a line or grid.  Mirror shortcuts.  
*Included in std.scad*  
- [Translating copies of all the children](distributors.scad#section-translating-copies-of-all-the-children)  
    [`move_copies()`](distributors.scad#module-move_copies) [`line_of()`](distributors.scad#functionmodule-line_of) [`xcopies()`](distributors.scad#module-xcopies) [`ycopies()`](distributors.scad#module-ycopies) [`zcopies()`](distributors.scad#module-zcopies) [`grid2d()`](distributors.scad#module-grid2d) [`grid3d()`](distributors.scad#module-grid3d)
- [Rotating copies of all children](distributors.scad#section-rotating-copies-of-all-children)  
    [`rot_copies()`](distributors.scad#module-rot_copies) [`xrot_copies()`](distributors.scad#module-xrot_copies) [`yrot_copies()`](distributors.scad#module-yrot_copies) [`zrot_copies()`](distributors.scad#module-zrot_copies) [`arc_of()`](distributors.scad#module-arc_of) [`ovoid_spread()`](distributors.scad#module-ovoid_spread)
- [Placing copies of all children on a path](distributors.scad#section-placing-copies-of-all-children-on-a-path)  
    [`path_spread()`](distributors.scad#module-path_spread)
- [Making a copy of all children with reflection](distributors.scad#section-making-a-copy-of-all-children-with-reflection)  
    [`mirror_copy()`](distributors.scad#module-mirror_copy) [`xflip_copy()`](distributors.scad#module-xflip_copy) [`yflip_copy()`](distributors.scad#module-yflip_copy) [`zflip_copy()`](distributors.scad#module-zflip_copy)
- [Distributing children individually along a line](distributors.scad#section-distributing-children-individually-along-a-line)  
    [`distribute()`](distributors.scad#module-distribute) [`xdistribute()`](distributors.scad#module-xdistribute) [`ydistribute()`](distributors.scad#module-ydistribute) [`zdistribute()`](distributors.scad#module-zdistribute)

## 9. [color.scad](color.scad)

HSV and HSL conversion, color multiple objects  
*Included in std.scad*  
- [Coloring Objects](color.scad#section-coloring-objects)  
    [`rainbow()`](color.scad#module-rainbow)
- [Colorspace Conversion](color.scad#section-colorspace-conversion)  
    [`HSL()`](color.scad#functionmodule-hsl) [`HSV()`](color.scad#functionmodule-hsv)

## 10. [partitions.scad](partitions.scad)

Cut objects with a plane or partition them into interlocking pieces.  
*Included in std.scad*  
- [Planar Cutting](partitions.scad#section-planar-cutting)  
    [`half_of()`](partitions.scad#functionmodule-half_of) [`left_half()`](partitions.scad#functionmodule-left_half) [`right_half()`](partitions.scad#functionmodule-right_half) [`front_half()`](partitions.scad#functionmodule-front_half) [`back_half()`](partitions.scad#functionmodule-back_half) [`bottom_half()`](partitions.scad#functionmodule-bottom_half) [`top_half()`](partitions.scad#functionmodule-top_half)
- [Partioning into Interlocking Pieces](partitions.scad#section-partioning-into-interlocking-pieces)  
    [`partition_mask()`](partitions.scad#module-partition_mask) [`partition_cut_mask()`](partitions.scad#module-partition_cut_mask) [`partition()`](partitions.scad#module-partition)

## 11. [mutators.scad](mutators.scad)

Modules and Functions to mutate items.  
*Included in std.scad*  
- [Bounding Box](mutators.scad#section-bounding-box)  
    [`bounding_box()`](mutators.scad#module-bounding_box)
- [Warp Mutators](mutators.scad#section-warp-mutators)  
    [`chain_hull()`](mutators.scad#module-chain_hull) [`path_extrude2d()`](mutators.scad#module-path_extrude2d) [`cylindrical_extrude()`](mutators.scad#module-cylindrical_extrude) [`extrude_from_to()`](mutators.scad#module-extrude_from_to) [`path_extrude()`](mutators.scad#module-path_extrude)
- [Offset Mutators](mutators.scad#section-offset-mutators)  
    [`minkowski_difference()`](mutators.scad#module-minkowski_difference) [`offset3d()`](mutators.scad#module-offset3d) [`round3d()`](mutators.scad#module-round3d)

## 12. [paths.scad](paths.scad)

Operations on paths: length, resampling, tangents, splitting into subpaths  
*Included in std.scad*  
- [Utility Functions](paths.scad#section-utility-functions)  
    [`is_path()`](paths.scad#function-is_path) [`is_1region()`](paths.scad#function-is_1region) [`force_path()`](paths.scad#function-force_path) [`is_closed_path()`](paths.scad#function-is_closed_path) [`close_path()`](paths.scad#function-close_path) [`cleanup_path()`](paths.scad#function-cleanup_path) [`path_merge_collinear()`](paths.scad#function-path_merge_collinear)
- [Path length calculation](paths.scad#section-path-length-calculation)  
    [`path_length()`](paths.scad#function-path_length) [`path_segment_lengths()`](paths.scad#function-path_segment_lengths) [`path_length_fractions()`](paths.scad#function-path_length_fractions)
- [Resampling---changing the number of points in a path](paths.scad#section-resampling---changing-the-number-of-points-in-a-path)  
    [`subdivide_path()`](paths.scad#function-subdivide_path) [`subdivide_long_segments()`](paths.scad#function-subdivide_long_segments) [`resample_path()`](paths.scad#function-resample_path)
- [Path Geometry](paths.scad#section-path-geometry)  
    [`is_path_simple()`](paths.scad#function-is_path_simple) [`path_closest_point()`](paths.scad#function-path_closest_point) [`path_tangents()`](paths.scad#function-path_tangents) [`path_normals()`](paths.scad#function-path_normals) [`path_curvature()`](paths.scad#function-path_curvature) [`path_torsion()`](paths.scad#function-path_torsion)
- [Breaking paths up into subpaths](paths.scad#section-breaking-paths-up-into-subpaths)  
    [`path_cut()`](paths.scad#function-path_cut) [`split_path_at_self_crossings()`](paths.scad#function-split_path_at_self_crossings) [`polygon_parts()`](paths.scad#function-polygon_parts)

## 13. [regions.scad](regions.scad)

Offsets and boolean geometry of 2D paths and regions.  
*Included in std.scad*  
- [Regions](regions.scad#section-regions)  
    [`is_region()`](regions.scad#function-is_region) [`is_valid_region()`](regions.scad#function-is_valid_region) [`is_region_simple()`](regions.scad#function-is_region_simple) [`make_region()`](regions.scad#function-make_region) [`force_region()`](regions.scad#function-force_region)
- [Turning a region into geometry](regions.scad#section-turning-a-region-into-geometry)  
    [`region()`](regions.scad#module-region)
- [Gometrical calculations with regions](regions.scad#section-gometrical-calculations-with-regions)  
    [`point_in_region()`](regions.scad#function-point_in_region) [`region_area()`](regions.scad#function-region_area) [`are_regions_equal()`](regions.scad#function-are_regions_equal)
- [Breaking up regions into subregions](regions.scad#section-breaking-up-regions-into-subregions)  
    [`split_region_at_region_crossings()`](regions.scad#function-split_region_at_region_crossings) [`region_parts()`](regions.scad#function-region_parts)
- [Offset and 2D Boolean Set Operations](regions.scad#section-offset-and-2d-boolean-set-operations)  
    [`offset()`](regions.scad#function-offset) [`union()`](regions.scad#functionmodule-union) [`difference()`](regions.scad#functionmodule-difference) [`intersection()`](regions.scad#functionmodule-intersection) [`exclusive_or()`](regions.scad#functionmodule-exclusive_or)

## 14. [vnf.scad](vnf.scad)

Vertices 'n' Faces structure.  Makes polyhedron() easier to use.  
*Included in std.scad*  
- [Creating Polyhedrons with VNF Structures](vnf.scad#section-creating-polyhedrons-with-vnf-structures)  
    [`vnf_vertex_array()`](vnf.scad#function-vnf_vertex_array) [`vnf_tri_array()`](vnf.scad#function-vnf_tri_array) [`vnf_join()`](vnf.scad#function-vnf_join) [`vnf_from_polygons()`](vnf.scad#function-vnf_from_polygons) [`vnf_from_region()`](vnf.scad#function-vnf_from_region)
- [VNF Testing and Access](vnf.scad#section-vnf-testing-and-access)  
    [`is_vnf()`](vnf.scad#function-is_vnf) [`is_vnf_list()`](vnf.scad#function-is_vnf_list) [`vnf_vertices()`](vnf.scad#function-vnf_vertices) [`vnf_faces()`](vnf.scad#function-vnf_faces)
- [Altering the VNF Internals](vnf.scad#section-altering-the-vnf-internals)  
    [`vnf_reverse_faces()`](vnf.scad#function-vnf_reverse_faces) [`vnf_quantize()`](vnf.scad#function-vnf_quantize) [`vnf_merge_points()`](vnf.scad#function-vnf_merge_points) [`vnf_drop_unused_points()`](vnf.scad#function-vnf_drop_unused_points) [`vnf_triangulate()`](vnf.scad#function-vnf_triangulate) [`vnf_slice()`](vnf.scad#function-vnf_slice)
- [Turning a VNF into geometry](vnf.scad#section-turning-a-vnf-into-geometry)  
    [`vnf_polyhedron()`](vnf.scad#module-vnf_polyhedron) [`vnf_wireframe()`](vnf.scad#module-vnf_wireframe)
- [Operations on VNFs](vnf.scad#section-operations-on-vnfs)  
    [`vnf_volume()`](vnf.scad#function-vnf_volume) [`vnf_area()`](vnf.scad#function-vnf_area) [`vnf_halfspace()`](vnf.scad#function-vnf_halfspace) [`vnf_bend()`](vnf.scad#function-vnf_bend)
- [Debugging Polyhedrons](vnf.scad#section-debugging-polyhedrons)  
    [`debug_vnf()`](vnf.scad#module-debug_vnf) [`vnf_validate()`](vnf.scad#functionmodule-vnf_validate)

## 15. [beziers.scad](beziers.scad)

Bezier curves and surfaces.  
- [Bezier Curves](beziers.scad#section-bezier-curves)  
    [`bezier_points()`](beziers.scad#function-bezier_points) [`bezier_curve()`](beziers.scad#function-bezier_curve) [`bezier_derivative()`](beziers.scad#function-bezier_derivative) [`bezier_tangent()`](beziers.scad#function-bezier_tangent) [`bezier_curvature()`](beziers.scad#function-bezier_curvature) [`bezier_closest_point()`](beziers.scad#function-bezier_closest_point) [`bezier_length()`](beziers.scad#function-bezier_length) [`bezier_line_intersection()`](beziers.scad#function-bezier_line_intersection)
- [Bezier Path Functions](beziers.scad#section-bezier-path-functions)  
    [`bezpath_points()`](beziers.scad#function-bezpath_points) [`bezpath_curve()`](beziers.scad#function-bezpath_curve) [`bezpath_closest_point()`](beziers.scad#function-bezpath_closest_point) [`bezpath_length()`](beziers.scad#function-bezpath_length) [`path_to_bezpath()`](beziers.scad#function-path_to_bezpath) [`bezpath_close_to_axis()`](beziers.scad#function-bezpath_close_to_axis) [`bezpath_offset()`](beziers.scad#function-bezpath_offset)
- [Cubic Bezier Path Construction](beziers.scad#section-cubic-bezier-path-construction)  
    [`bez_begin()`](beziers.scad#function-bez_begin) [`bez_tang()`](beziers.scad#function-bez_tang) [`bez_joint()`](beziers.scad#function-bez_joint) [`bez_end()`](beziers.scad#function-bez_end)
- [Bezier Surfaces](beziers.scad#section-bezier-surfaces)  
    [`is_bezier_patch()`](beziers.scad#function-is_bezier_patch) [`bezier_patch_flat()`](beziers.scad#function-bezier_patch_flat) [`bezier_patch_reverse()`](beziers.scad#function-bezier_patch_reverse) [`bezier_patch_points()`](beziers.scad#function-bezier_patch_points) [`bezier_vnf()`](beziers.scad#function-bezier_vnf) [`bezier_vnf_degenerate_patch()`](beziers.scad#function-bezier_vnf_degenerate_patch)
- [Debugging Beziers](beziers.scad#section-debugging-beziers)  
    [`debug_bezier()`](beziers.scad#module-debug_bezier) [`debug_bezier_patches()`](beziers.scad#module-debug_bezier_patches)

## 16. [rounding.scad](rounding.scad)

Round path corners, rounded prisms, rounded cutouts in tubes.  
- [Types of Roundovers](rounding.scad#section-types-of-roundovers)  
    
- [Rounding Paths](rounding.scad#section-rounding-paths)  
    [`round_corners()`](rounding.scad#function-round_corners) [`smooth_path()`](rounding.scad#function-smooth_path) [`path_join()`](rounding.scad#function-path_join) [`offset_stroke()`](rounding.scad#functionmodule-offset_stroke)
- [Three-Dimensional Rounding](rounding.scad#section-three-dimensional-rounding)  
    [`offset_sweep()`](rounding.scad#functionmodule-offset_sweep) [`convex_offset_extrude()`](rounding.scad#module-convex_offset_extrude) [`rounded_prism()`](rounding.scad#functionmodule-rounded_prism) [`bent_cutout_mask()`](rounding.scad#module-bent_cutout_mask)

## 17. [skin.scad](skin.scad)

Construct 3D shapes from 2D cross sections of the desired shape.  
*Included in std.scad*  
- [Skin and sweep](skin.scad#section-skin-and-sweep)  
    [`skin()`](skin.scad#functionmodule-skin) [`linear_sweep()`](skin.scad#functionmodule-linear_sweep) [`spiral_sweep()`](skin.scad#functionmodule-spiral_sweep) [`path_sweep()`](skin.scad#functionmodule-path_sweep) [`path_sweep2d()`](skin.scad#functionmodule-path_sweep2d) [`sweep()`](skin.scad#functionmodule-sweep)
- [Functions for resampling and slicing profile lists](skin.scad#section-functions-for-resampling-and-slicing-profile-lists)  
    [`subdivide_and_slice()`](skin.scad#function-subdivide_and_slice) [`slice_profiles()`](skin.scad#function-slice_profiles) [`rot_resample()`](skin.scad#function-rot_resample) [`associate_vertices()`](skin.scad#function-associate_vertices)

## 18. [turtle3d.scad](turtle3d.scad)

3D turtle graphics for making paths or lists of transformations.  
- [Functions](turtle3d.scad#section-functions)  
    [`turtle3d()`](turtle3d.scad#function-turtle3d)

## 19. [math.scad](math.scad)

General miscellaneous math function.  
*Included in std.scad*  
- [Math Constants](math.scad#section-math-constants)  
    [`PHI`](math.scad#constant-phi) [`EPSILON`](math.scad#constant-epsilon) [`INF`](math.scad#constant-inf) [`NAN`](math.scad#constant-nan)
- [Simple math](math.scad#section-simple-math)  
    [`sqr()`](math.scad#function-sqr) [`log2()`](math.scad#function-log2) [`hypot()`](math.scad#function-hypot) [`factorial()`](math.scad#function-factorial) [`binomial()`](math.scad#function-binomial) [`binomial_coefficient()`](math.scad#function-binomial_coefficient) [`lerp()`](math.scad#function-lerp) [`lerpn()`](math.scad#function-lerpn)
- [Undef Safe Math](math.scad#section-undef-safe-math)  
    [`u_add()`](math.scad#function-u_add) [`u_sub()`](math.scad#function-u_sub) [`u_mul()`](math.scad#function-u_mul) [`u_div()`](math.scad#function-u_div)
- [Hyperbolic Trigonometry](math.scad#section-hyperbolic-trigonometry)  
    [`sinh()`](math.scad#function-sinh) [`cosh()`](math.scad#function-cosh) [`tanh()`](math.scad#function-tanh) [`asinh()`](math.scad#function-asinh) [`acosh()`](math.scad#function-acosh) [`atanh()`](math.scad#function-atanh)
- [Quantization](math.scad#section-quantization)  
    [`quant()`](math.scad#function-quant) [`quantdn()`](math.scad#function-quantdn) [`quantup()`](math.scad#function-quantup)
- [Constraints and Modulos](math.scad#section-constraints-and-modulos)  
    [`constrain()`](math.scad#function-constrain) [`posmod()`](math.scad#function-posmod) [`modang()`](math.scad#function-modang)
- [Random Number Generation](math.scad#section-random-number-generation)  
    [`rand_int()`](math.scad#function-rand_int) [`random_points()`](math.scad#function-random_points) [`gaussian_rands()`](math.scad#function-gaussian_rands) [`spherical_random_points()`](math.scad#function-spherical_random_points) [`random_polygon()`](math.scad#function-random_polygon)
- [GCD/GCF, LCM](math.scad#section-gcdgcf-lcm)  
    [`gcd()`](math.scad#function-gcd) [`lcm()`](math.scad#function-lcm)
- [Sums, Products, Aggregate Functions.](math.scad#section-sums-products-aggregate-functions)  
    [`sum()`](math.scad#function-sum) [`cumsum()`](math.scad#function-cumsum) [`sum_of_sines()`](math.scad#function-sum_of_sines) [`deltas()`](math.scad#function-deltas) [`product()`](math.scad#function-product) [`cumprod()`](math.scad#function-cumprod) [`mean()`](math.scad#function-mean) [`median()`](math.scad#function-median) [`convolve()`](math.scad#function-convolve) [`all_integer()`](math.scad#function-all_integer) [`any()`](math.scad#function-any) [`all()`](math.scad#function-all) [`count_true()`](math.scad#function-count_true)
- [Calculus](math.scad#section-calculus)  
    [`deriv()`](math.scad#function-deriv) [`deriv2()`](math.scad#function-deriv2) [`deriv3()`](math.scad#function-deriv3)
- [Complex Numbers](math.scad#section-complex-numbers)  
    [`complex()`](math.scad#function-complex) [`c_mul()`](math.scad#function-c_mul) [`c_div()`](math.scad#function-c_div) [`c_conj()`](math.scad#function-c_conj) [`c_real()`](math.scad#function-c_real) [`c_imag()`](math.scad#function-c_imag) [`c_ident()`](math.scad#function-c_ident) [`c_norm()`](math.scad#function-c_norm)
- [Polynomials](math.scad#section-polynomials)  
    [`quadratic_roots()`](math.scad#function-quadratic_roots) [`polynomial()`](math.scad#function-polynomial) [`poly_mult()`](math.scad#function-poly_mult) [`poly_div()`](math.scad#function-poly_div) [`poly_add()`](math.scad#function-poly_add) [`poly_roots()`](math.scad#function-poly_roots) [`real_roots()`](math.scad#function-real_roots)
- [Operations on Functions](math.scad#section-operations-on-functions)  
    [`root_find()`](math.scad#function-root_find)

## 20. [linalg.scad](linalg.scad)

Linear Algebra: solve linear systems, construct and modify matrices.  
*Included in std.scad*  
- [Matrices](linalg.scad#section-matrices)  
    
- [Matrix testing and display](linalg.scad#section-matrix-testing-and-display)  
    [`is_matrix()`](linalg.scad#function-is_matrix) [`is_matrix_symmetric()`](linalg.scad#function-is_matrix_symmetric) [`echo_matrix()`](linalg.scad#functionmodule-echo_matrix)
- [Matrix indexing](linalg.scad#section-matrix-indexing)  
    [`column()`](linalg.scad#function-column) [`submatrix()`](linalg.scad#function-submatrix)
- [Matrix construction and modification](linalg.scad#section-matrix-construction-and-modification)  
    [`ident()`](linalg.scad#function-ident) [`diagonal_matrix()`](linalg.scad#function-diagonal_matrix) [`transpose()`](linalg.scad#function-transpose) [`outer_product()`](linalg.scad#function-outer_product) [`submatrix_set()`](linalg.scad#function-submatrix_set) [`hstack()`](linalg.scad#function-hstack) [`block_matrix()`](linalg.scad#function-block_matrix)
- [Solving Linear Equations and Matrix Factorizations](linalg.scad#section-solving-linear-equations-and-matrix-factorizations)  
    [`linear_solve()`](linalg.scad#function-linear_solve) [`linear_solve3()`](linalg.scad#function-linear_solve3) [`matrix_inverse()`](linalg.scad#function-matrix_inverse) [`rot_inverse()`](linalg.scad#function-rot_inverse) [`null_space()`](linalg.scad#function-null_space) [`qr_factor()`](linalg.scad#function-qr_factor) [`back_substitute()`](linalg.scad#function-back_substitute) [`cholesky()`](linalg.scad#function-cholesky)
- [Matrix Properties: Determinants, Norm, Trace](linalg.scad#section-matrix-properties-determinants-norm-trace)  
    [`det2()`](linalg.scad#function-det2) [`det3()`](linalg.scad#function-det3) [`det4()`](linalg.scad#function-det4) [`determinant()`](linalg.scad#function-determinant) [`norm_fro()`](linalg.scad#function-norm_fro) [`matrix_trace()`](linalg.scad#function-matrix_trace)

## 21. [vectors.scad](vectors.scad)

Vector arithmetic, angle, and searching.  
*Included in std.scad*  
- [Vector Testing](vectors.scad#section-vector-testing)  
    [`is_vector()`](vectors.scad#function-is_vector)
- [Scalar operations on vectors](vectors.scad#section-scalar-operations-on-vectors)  
    [`add_scalar()`](vectors.scad#function-add_scalar) [`v_mul()`](vectors.scad#function-v_mul) [`v_div()`](vectors.scad#function-v_div) [`v_abs()`](vectors.scad#function-v_abs) [`v_floor()`](vectors.scad#function-v_floor) [`v_ceil()`](vectors.scad#function-v_ceil) [`v_lookup()`](vectors.scad#function-v_lookup)
- [Vector Properties](vectors.scad#section-vector-properties)  
    [`unit()`](vectors.scad#function-unit) [`v_theta()`](vectors.scad#function-v_theta) [`vector_angle()`](vectors.scad#function-vector_angle) [`vector_axis()`](vectors.scad#function-vector_axis)
- [Vector Searching](vectors.scad#section-vector-searching)  
    [`pointlist_bounds()`](vectors.scad#function-pointlist_bounds) [`closest_point()`](vectors.scad#function-closest_point) [`furthest_point()`](vectors.scad#function-furthest_point) [`vector_search()`](vectors.scad#function-vector_search) [`vector_search_tree()`](vectors.scad#function-vector_search_tree) [`vector_nearest()`](vectors.scad#function-vector_nearest)

## 22. [quaternions.scad](quaternions.scad)

Quaternion based rotations that avoid gimbal lock issues.  
*Included in std.scad*  
- [Quaternions](quaternions.scad#section-quaternions)  
    [`is_quaternion()`](quaternions.scad#function-is_quaternion) [`quat()`](quaternions.scad#function-quat) [`quat_x()`](quaternions.scad#function-quat_x) [`quat_y()`](quaternions.scad#function-quat_y) [`quat_z()`](quaternions.scad#function-quat_z) [`quat_xyz()`](quaternions.scad#function-quat_xyz) [`q_from_to()`](quaternions.scad#function-q_from_to) [`q_ident()`](quaternions.scad#function-q_ident) [`q_add_s()`](quaternions.scad#function-q_add_s) [`q_sub_s()`](quaternions.scad#function-q_sub_s) [`q_mul_s()`](quaternions.scad#function-q_mul_s) [`q_div_s()`](quaternions.scad#function-q_div_s) [`q_add()`](quaternions.scad#function-q_add) [`q_sub()`](quaternions.scad#function-q_sub) [`q_mul()`](quaternions.scad#function-q_mul) [`q_cumulative()`](quaternions.scad#function-q_cumulative) [`q_dot()`](quaternions.scad#function-q_dot) [`q_neg()`](quaternions.scad#function-q_neg) [`q_conj()`](quaternions.scad#function-q_conj) [`q_inverse()`](quaternions.scad#function-q_inverse) [`q_norm()`](quaternions.scad#function-q_norm) [`q_normalize()`](quaternions.scad#function-q_normalize) [`q_dist()`](quaternions.scad#function-q_dist) [`q_slerp()`](quaternions.scad#function-q_slerp) [`q_matrix3()`](quaternions.scad#function-q_matrix3) [`q_matrix4()`](quaternions.scad#function-q_matrix4) [`q_axis()`](quaternions.scad#function-q_axis) [`q_angle()`](quaternions.scad#function-q_angle) [`q_rot()`](quaternions.scad#functionmodule-q_rot) [`q_rot_copies()`](quaternions.scad#module-q_rot_copies) [`q_rotation()`](quaternions.scad#function-q_rotation) [`q_rotation_path()`](quaternions.scad#functionmodule-q_rotation_path) [`q_nlerp()`](quaternions.scad#function-q_nlerp) [`q_squad()`](quaternions.scad#function-q_squad) [`q_exp()`](quaternions.scad#function-q_exp) [`q_ln()`](quaternions.scad#function-q_ln) [`q_pow()`](quaternions.scad#function-q_pow)

## 23. [coords.scad](coords.scad)

Conversions between coordinate systems.  
*Included in std.scad*  
- [Coordinate Manipulation](coords.scad#section-coordinate-manipulation)  
    [`point2d()`](coords.scad#function-point2d) [`path2d()`](coords.scad#function-path2d) [`point3d()`](coords.scad#function-point3d) [`path3d()`](coords.scad#function-path3d) [`point4d()`](coords.scad#function-point4d) [`path4d()`](coords.scad#function-path4d)
- [Coordinate Systems](coords.scad#section-coordinate-systems)  
    [`polar_to_xy()`](coords.scad#function-polar_to_xy) [`xy_to_polar()`](coords.scad#function-xy_to_polar) [`project_plane()`](coords.scad#function-project_plane) [`lift_plane()`](coords.scad#function-lift_plane) [`cylindrical_to_xyz()`](coords.scad#function-cylindrical_to_xyz) [`xyz_to_cylindrical()`](coords.scad#function-xyz_to_cylindrical) [`spherical_to_xyz()`](coords.scad#function-spherical_to_xyz) [`xyz_to_spherical()`](coords.scad#function-xyz_to_spherical) [`altaz_to_xyz()`](coords.scad#function-altaz_to_xyz) [`xyz_to_altaz()`](coords.scad#function-xyz_to_altaz)

## 24. [geometry.scad](geometry.scad)

Geometrical calculations including intersections of lines, circles and planes, circle from 3 points  
*Included in std.scad*  
- [Lines, Rays, and Segments](geometry.scad#section-lines-rays-and-segments)  
    [`is_point_on_line()`](geometry.scad#function-is_point_on_line) [`is_collinear()`](geometry.scad#function-is_collinear) [`point_line_distance()`](geometry.scad#function-point_line_distance) [`segment_distance()`](geometry.scad#function-segment_distance) [`line_normal()`](geometry.scad#function-line_normal) [`line_intersection()`](geometry.scad#function-line_intersection) [`line_closest_point()`](geometry.scad#function-line_closest_point) [`line_from_points()`](geometry.scad#function-line_from_points)
- [Planes](geometry.scad#section-planes)  
    [`is_coplanar()`](geometry.scad#function-is_coplanar) [`plane3pt()`](geometry.scad#function-plane3pt) [`plane3pt_indexed()`](geometry.scad#function-plane3pt_indexed) [`plane_from_normal()`](geometry.scad#function-plane_from_normal) [`plane_from_points()`](geometry.scad#function-plane_from_points) [`plane_from_polygon()`](geometry.scad#function-plane_from_polygon) [`plane_normal()`](geometry.scad#function-plane_normal) [`plane_offset()`](geometry.scad#function-plane_offset) [`plane_line_intersection()`](geometry.scad#function-plane_line_intersection) [`plane_intersection()`](geometry.scad#function-plane_intersection) [`plane_line_angle()`](geometry.scad#function-plane_line_angle) [`plane_closest_point()`](geometry.scad#function-plane_closest_point) [`point_plane_distance()`](geometry.scad#function-point_plane_distance) [`are_points_on_plane()`](geometry.scad#function-are_points_on_plane)
- [Circle Calculations](geometry.scad#section-circle-calculations)  
    [`circle_line_intersection()`](geometry.scad#function-circle_line_intersection) [`circle_circle_intersection()`](geometry.scad#function-circle_circle_intersection) [`circle_2tangents()`](geometry.scad#functionmodule-circle_2tangents) [`circle_3points()`](geometry.scad#functionmodule-circle_3points) [`circle_point_tangents()`](geometry.scad#function-circle_point_tangents) [`circle_circle_tangents()`](geometry.scad#function-circle_circle_tangents)
- [Sphere Calculations](geometry.scad#section-sphere-calculations)  
    [`sphere_line_intersection()`](geometry.scad#function-sphere_line_intersection)
- [Polygons](geometry.scad#section-polygons)  
    [`polygon_area()`](geometry.scad#function-polygon_area) [`centroid()`](geometry.scad#function-centroid) [`polygon_normal()`](geometry.scad#function-polygon_normal) [`point_in_polygon()`](geometry.scad#function-point_in_polygon) [`polygon_line_intersection()`](geometry.scad#function-polygon_line_intersection) [`polygon_triangulate()`](geometry.scad#function-polygon_triangulate) [`is_polygon_clockwise()`](geometry.scad#function-is_polygon_clockwise) [`clockwise_polygon()`](geometry.scad#function-clockwise_polygon) [`ccw_polygon()`](geometry.scad#function-ccw_polygon) [`reverse_polygon()`](geometry.scad#function-reverse_polygon) [`reindex_polygon()`](geometry.scad#function-reindex_polygon) [`align_polygon()`](geometry.scad#function-align_polygon) [`are_polygons_equal()`](geometry.scad#function-are_polygons_equal)
- [Convex Hull](geometry.scad#section-convex-hull)  
    [`hull()`](geometry.scad#function-hull) [`hull_points()`](geometry.scad#module-hull_points) [`hull2d_path()`](geometry.scad#function-hull2d_path) [`hull3d_faces()`](geometry.scad#function-hull3d_faces)
- [Convex Sets](geometry.scad#section-convex-sets)  
    [`is_polygon_convex()`](geometry.scad#function-is_polygon_convex) [`convex_distance()`](geometry.scad#function-convex_distance) [`convex_collision()`](geometry.scad#function-convex_collision)
- [Rotation Decoding](geometry.scad#section-rotation-decoding)  
    [`rot_decode()`](geometry.scad#function-rot_decode)

## 25. [trigonometry.scad](trigonometry.scad)

Trigonometry shortcuts for when you can't recall the mnemonic SOHCAHTOA.  
*Included in std.scad*  
- [2D General Triangle Functions](trigonometry.scad#section-2d-general-triangle-functions)  
    [`law_of_cosines()`](trigonometry.scad#function-law_of_cosines) [`law_of_sines()`](trigonometry.scad#function-law_of_sines) [`triangle_area()`](trigonometry.scad#function-triangle_area)
- [2D Right Triangle Functions](trigonometry.scad#section-2d-right-triangle-functions)  
    [`hyp_opp_to_adj()`](trigonometry.scad#function-hyp_opp_to_adj) [`hyp_ang_to_adj()`](trigonometry.scad#function-hyp_ang_to_adj) [`opp_ang_to_adj()`](trigonometry.scad#function-opp_ang_to_adj) [`hyp_adj_to_opp()`](trigonometry.scad#function-hyp_adj_to_opp) [`hyp_ang_to_opp()`](trigonometry.scad#function-hyp_ang_to_opp) [`adj_ang_to_opp()`](trigonometry.scad#function-adj_ang_to_opp) [`adj_opp_to_hyp()`](trigonometry.scad#function-adj_opp_to_hyp) [`adj_ang_to_hyp()`](trigonometry.scad#function-adj_ang_to_hyp) [`opp_ang_to_hyp()`](trigonometry.scad#function-opp_ang_to_hyp) [`hyp_adj_to_ang()`](trigonometry.scad#function-hyp_adj_to_ang) [`hyp_opp_to_ang()`](trigonometry.scad#function-hyp_opp_to_ang) [`adj_opp_to_ang()`](trigonometry.scad#function-adj_opp_to_ang)

## 26. [constants.scad](constants.scad)

- [General Constants](constants.scad#section-general-constants)  
    [`$slop`](constants.scad#constant-slop) [`INCH`](constants.scad#constant-inch)
- [Directional Vectors](constants.scad#section-directional-vectors)  
    [`LEFT`](constants.scad#constant-left) [`RIGHT`](constants.scad#constant-right) [`FRONT`](constants.scad#constant-front) [`BACK`](constants.scad#constant-back) [`BOTTOM`](constants.scad#constant-bottom) [`TOP`](constants.scad#constant-top) [`CENTER`](constants.scad#constant-center)
- [Line specifiers](constants.scad#section-line-specifiers)  
    [`SEGMENT`](constants.scad#constant-segment) [`RAY`](constants.scad#constant-ray) [`LINE`](constants.scad#constant-line)

## 27. [version.scad](version.scad)

Parse and compare semantic versions.  
*Included in std.scad*  
- [BOSL Library Version Functions](version.scad#section-bosl-library-version-functions)  
    [`bosl_version()`](version.scad#function-bosl_version) [`bosl_version_num()`](version.scad#function-bosl_version_num) [`bosl_version_str()`](version.scad#function-bosl_version_str) [`bosl_required()`](version.scad#module-bosl_required)
- [Generic Version Functions](version.scad#section-generic-version-functions)  
    [`version_to_list()`](version.scad#function-version_to_list) [`version_to_str()`](version.scad#function-version_to_str) [`version_to_num()`](version.scad#function-version_to_num) [`version_cmp()`](version.scad#function-version_cmp)

## 28. [comparisons.scad](comparisons.scad)

Comparisons and sorting.  
*Included in std.scad*  
- [List comparison operations](comparisons.scad#section-list-comparison-operations)  
    [`approx()`](comparisons.scad#function-approx) [`all_zero()`](comparisons.scad#function-all_zero) [`all_nonzero()`](comparisons.scad#function-all_nonzero) [`all_positive()`](comparisons.scad#function-all_positive) [`all_negative()`](comparisons.scad#function-all_negative) [`all_nonpositive()`](comparisons.scad#function-all_nonpositive) [`all_nonnegative()`](comparisons.scad#function-all_nonnegative) [`all_equal()`](comparisons.scad#function-all_equal) [`is_increasing()`](comparisons.scad#function-is_increasing) [`is_decreasing()`](comparisons.scad#function-is_decreasing) [`compare_vals()`](comparisons.scad#function-compare_vals) [`compare_lists()`](comparisons.scad#function-compare_lists)
- [Finding the index of the minimum or maximum of a list](comparisons.scad#section-finding-the-index-of-the-minimum-or-maximum-of-a-list)  
    [`min_index()`](comparisons.scad#function-min_index) [`max_index()`](comparisons.scad#function-max_index)
- [Dealing with duplicate list entries](comparisons.scad#section-dealing-with-duplicate-list-entries)  
    [`find_approx()`](comparisons.scad#function-find_approx) [`deduplicate()`](comparisons.scad#function-deduplicate) [`deduplicate_indexed()`](comparisons.scad#function-deduplicate_indexed) [`unique()`](comparisons.scad#function-unique) [`unique_count()`](comparisons.scad#function-unique_count)
- [Sorting](comparisons.scad#section-sorting)  
    [`sort()`](comparisons.scad#function-sort) [`sortidx()`](comparisons.scad#function-sortidx) [`group_sort()`](comparisons.scad#function-group_sort) [`group_data()`](comparisons.scad#function-group_data) [`list_smallest()`](comparisons.scad#function-list_smallest)

## 29. [lists.scad](lists.scad)

List indexing, change list structure, rearrange/modify lists  
*Included in std.scad*  
- [List Query Operations](lists.scad#section-list-query-operations)  
    [`is_homogeneous()`](lists.scad#function-is_homogeneous) [`min_length()`](lists.scad#function-min_length) [`max_length()`](lists.scad#function-max_length) [`list_shape()`](lists.scad#function-list_shape) [`in_list()`](lists.scad#function-in_list)
- [List Indexing](lists.scad#section-list-indexing)  
    [`select()`](lists.scad#function-select) [`slice()`](lists.scad#function-slice) [`last()`](lists.scad#function-last) [`list_head()`](lists.scad#function-list_head) [`list_tail()`](lists.scad#function-list_tail) [`bselect()`](lists.scad#function-bselect)
- [List Construction](lists.scad#section-list-construction)  
    [`repeat()`](lists.scad#function-repeat) [`count()`](lists.scad#function-count) [`list_bset()`](lists.scad#function-list_bset) [`list()`](lists.scad#function-list) [`force_list()`](lists.scad#function-force_list)
- [List Modification](lists.scad#section-list-modification)  
    [`reverse()`](lists.scad#function-reverse) [`list_rotate()`](lists.scad#function-list_rotate) [`shuffle()`](lists.scad#function-shuffle) [`repeat_entries()`](lists.scad#function-repeat_entries) [`list_pad()`](lists.scad#function-list_pad) [`list_set()`](lists.scad#function-list_set) [`list_insert()`](lists.scad#function-list_insert) [`list_remove()`](lists.scad#function-list_remove) [`list_remove_values()`](lists.scad#function-list_remove_values)
- [Lists of Subsets](lists.scad#section-lists-of-subsets)  
    [`idx()`](lists.scad#function-idx) [`pair()`](lists.scad#function-pair) [`triplet()`](lists.scad#function-triplet) [`combinations()`](lists.scad#function-combinations) [`permutations()`](lists.scad#function-permutations)
- [Changing list structure](lists.scad#section-changing-list-structure)  
    [`list_to_matrix()`](lists.scad#function-list_to_matrix) [`flatten()`](lists.scad#function-flatten) [`full_flatten()`](lists.scad#function-full_flatten)
- [Set Manipulation](lists.scad#section-set-manipulation)  
    [`set_union()`](lists.scad#function-set_union) [`set_difference()`](lists.scad#function-set_difference) [`set_intersection()`](lists.scad#function-set_intersection)

## 30. [utility.scad](utility.scad)

Type checking, dealing with undefs, processing function args  
*Included in std.scad*  
- [Type Checking](utility.scad#section-type-checking)  
    [`typeof()`](utility.scad#function-typeof) [`is_type()`](utility.scad#function-is_type) [`is_def()`](utility.scad#function-is_def) [`is_str()`](utility.scad#function-is_str) [`is_int()`](utility.scad#function-is_int) [`is_nan()`](utility.scad#function-is_nan) [`is_finite()`](utility.scad#function-is_finite) [`is_range()`](utility.scad#function-is_range) [`valid_range()`](utility.scad#function-valid_range) [`is_func()`](utility.scad#function-is_func) [`is_consistent()`](utility.scad#function-is_consistent) [`same_shape()`](utility.scad#function-same_shape) [`is_bool_list()`](utility.scad#function-is_bool_list)
- [Handling `undef`s.](utility.scad#section-handling-undefs)  
    [`default()`](utility.scad#function-default) [`first_defined()`](utility.scad#function-first_defined) [`one_defined()`](utility.scad#function-one_defined) [`num_defined()`](utility.scad#function-num_defined) [`any_defined()`](utility.scad#function-any_defined) [`all_defined()`](utility.scad#function-all_defined)
- [Processing Arguments to Functions and Modules](utility.scad#section-processing-arguments-to-functions-and-modules)  
    [`get_anchor()`](utility.scad#function-get_anchor) [`get_radius()`](utility.scad#function-get_radius) [`scalar_vec3()`](utility.scad#function-scalar_vec3) [`segs()`](utility.scad#function-segs) [`no_children()`](utility.scad#module-no_children) [`no_function()`](utility.scad#function-no_function) [`no_module()`](utility.scad#module-no_module)
- [Testing Helpers](utility.scad#section-testing-helpers)  
    [`assert_approx()`](utility.scad#module-assert_approx) [`assert_equal()`](utility.scad#module-assert_equal) [`shape_compare()`](utility.scad#module-shape_compare)
- [Looping Helpers](utility.scad#section-looping-helpers)  
    [`looping()`](utility.scad#function-looping) [`loop_while()`](utility.scad#function-loop_while) [`loop_done()`](utility.scad#function-loop_done)

## 31. [strings.scad](strings.scad)

String manipulation functions.  
*Included in std.scad*  
- [Extracting substrings](strings.scad#section-extracting-substrings)  
    [`substr()`](strings.scad#function-substr) [`suffix()`](strings.scad#function-suffix)
- [String Searching](strings.scad#section-string-searching)  
    [`str_find()`](strings.scad#function-str_find) [`starts_with()`](strings.scad#function-starts_with) [`ends_with()`](strings.scad#function-ends_with) [`str_split()`](strings.scad#function-str_split)
- [String modification](strings.scad#section-string-modification)  
    [`str_join()`](strings.scad#function-str_join) [`str_strip()`](strings.scad#function-str_strip) [`str_pad()`](strings.scad#function-str_pad) [`str_replace_char()`](strings.scad#function-str_replace_char) [`downcase()`](strings.scad#function-downcase) [`upcase()`](strings.scad#function-upcase)
- [Parsing strings into numbers](strings.scad#section-parsing-strings-into-numbers)  
    [`parse_int()`](strings.scad#function-parse_int) [`parse_float()`](strings.scad#function-parse_float) [`parse_frac()`](strings.scad#function-parse_frac) [`parse_num()`](strings.scad#function-parse_num)
- [Formatting numbers into strings](strings.scad#section-formatting-numbers-into-strings)  
    [`format_int()`](strings.scad#function-format_int) [`format_fixed()`](strings.scad#function-format_fixed) [`format_float()`](strings.scad#function-format_float) [`format()`](strings.scad#function-format)
- [Checking character class](strings.scad#section-checking-character-class)  
    [`is_lower()`](strings.scad#function-is_lower) [`is_upper()`](strings.scad#function-is_upper) [`is_digit()`](strings.scad#function-is_digit) [`is_hexdigit()`](strings.scad#function-is_hexdigit) [`is_letter()`](strings.scad#function-is_letter)

## 32. [structs.scad](structs.scad)

Structure/Dictionary Manipulation  
- [struct operations](structs.scad#section-struct-operations)  
    [`struct_set()`](structs.scad#function-struct_set) [`struct_remove()`](structs.scad#function-struct_remove) [`struct_val()`](structs.scad#function-struct_val) [`struct_keys()`](structs.scad#function-struct_keys) [`struct_echo()`](structs.scad#functionmodule-struct_echo) [`is_struct()`](structs.scad#function-is_struct)

## 33. [fnliterals.scad](fnliterals.scad)

Function Literal Algorithms, and factories for generating function literals for builtin functions.  
- [Function Literal Algorithms](fnliterals.scad#section-function-literal-algorithms)  
    [`map()`](fnliterals.scad#function-map) [`filter()`](fnliterals.scad#function-filter) [`reduce()`](fnliterals.scad#function-reduce) [`accumulate()`](fnliterals.scad#function-accumulate) [`while()`](fnliterals.scad#function-while) [`for_n()`](fnliterals.scad#function-for_n) [`find_all()`](fnliterals.scad#function-find_all) [`find_first()`](fnliterals.scad#function-find_first) [`binsearch()`](fnliterals.scad#function-binsearch) [`simple_hash()`](fnliterals.scad#function-simple_hash) [`hashmap()`](fnliterals.scad#function-hashmap)
- [Function Meta-Generators](fnliterals.scad#section-function-meta-generators)  
    [`f_1arg()`](fnliterals.scad#function-f_1arg) [`f_2arg()`](fnliterals.scad#function-f_2arg) [`f_2arg_simple()`](fnliterals.scad#function-f_2arg_simple) [`f_3arg()`](fnliterals.scad#function-f_3arg) [`ival()`](fnliterals.scad#function-ival) [`xval()`](fnliterals.scad#function-xval)
- [Comparator Generators](fnliterals.scad#section-comparator-generators)  
    [`f_cmp()`](fnliterals.scad#function-f_cmp) [`f_gt()`](fnliterals.scad#function-f_gt) [`f_lt()`](fnliterals.scad#function-f_lt) [`f_gte()`](fnliterals.scad#function-f_gte) [`f_lte()`](fnliterals.scad#function-f_lte) [`f_eq()`](fnliterals.scad#function-f_eq) [`f_neq()`](fnliterals.scad#function-f_neq) [`f_approx()`](fnliterals.scad#function-f_approx) [`f_napprox()`](fnliterals.scad#function-f_napprox)
- [Logic Operators](fnliterals.scad#section-logic-operators)  
    [`f_or()`](fnliterals.scad#function-f_or) [`f_and()`](fnliterals.scad#function-f_and) [`f_nor()`](fnliterals.scad#function-f_nor) [`f_nand()`](fnliterals.scad#function-f_nand) [`f_xor()`](fnliterals.scad#function-f_xor) [`f_not()`](fnliterals.scad#function-f_not) [`f_even()`](fnliterals.scad#function-f_even) [`f_odd()`](fnliterals.scad#function-f_odd)
- [Math Operators](fnliterals.scad#section-math-operators)  
    [`f_add()`](fnliterals.scad#function-f_add) [`f_sub()`](fnliterals.scad#function-f_sub) [`f_mul()`](fnliterals.scad#function-f_mul) [`f_div()`](fnliterals.scad#function-f_div) [`f_mod()`](fnliterals.scad#function-f_mod) [`f_pow()`](fnliterals.scad#function-f_pow) [`f_neg()`](fnliterals.scad#function-f_neg)
- [Min/Max Operators](fnliterals.scad#section-minmax-operators)  
    [`f_min()`](fnliterals.scad#function-f_min) [`f_max()`](fnliterals.scad#function-f_max) [`f_min2()`](fnliterals.scad#function-f_min2) [`f_max2()`](fnliterals.scad#function-f_max2) [`f_min3()`](fnliterals.scad#function-f_min3) [`f_max3()`](fnliterals.scad#function-f_max3)
- [Trigonometry Operators](fnliterals.scad#section-trigonometry-operators)  
    [`f_sin()`](fnliterals.scad#function-f_sin) [`f_cos()`](fnliterals.scad#function-f_cos) [`f_tan()`](fnliterals.scad#function-f_tan) [`f_asin()`](fnliterals.scad#function-f_asin) [`f_acos()`](fnliterals.scad#function-f_acos) [`f_atan()`](fnliterals.scad#function-f_atan) [`f_atan2()`](fnliterals.scad#function-f_atan2)
- [String Operators](fnliterals.scad#section-string-operators)  
    [`f_len()`](fnliterals.scad#function-f_len) [`f_chr()`](fnliterals.scad#function-f_chr) [`f_ord()`](fnliterals.scad#function-f_ord) [`f_str()`](fnliterals.scad#function-f_str) [`f_str2()`](fnliterals.scad#function-f_str2) [`f_str3()`](fnliterals.scad#function-f_str3)
- [Miscellaneous Operators](fnliterals.scad#section-miscellaneous-operators)  
    [`f_floor()`](fnliterals.scad#function-f_floor) [`f_round()`](fnliterals.scad#function-f_round) [`f_ceil()`](fnliterals.scad#function-f_ceil) [`f_abs()`](fnliterals.scad#function-f_abs) [`f_sign()`](fnliterals.scad#function-f_sign) [`f_ln()`](fnliterals.scad#function-f_ln) [`f_log()`](fnliterals.scad#function-f_log) [`f_exp()`](fnliterals.scad#function-f_exp) [`f_sqr()`](fnliterals.scad#function-f_sqr) [`f_sqrt()`](fnliterals.scad#function-f_sqrt) [`f_norm()`](fnliterals.scad#function-f_norm) [`f_cross()`](fnliterals.scad#function-f_cross)
- [Type Queries](fnliterals.scad#section-type-queries)  
    [`f_is_def()`](fnliterals.scad#function-f_is_def) [`f_is_undef()`](fnliterals.scad#function-f_is_undef) [`f_is_bool()`](fnliterals.scad#function-f_is_bool) [`f_is_num()`](fnliterals.scad#function-f_is_num) [`f_is_int()`](fnliterals.scad#function-f_is_int) [`f_is_nan()`](fnliterals.scad#function-f_is_nan) [`f_is_finite()`](fnliterals.scad#function-f_is_finite) [`f_is_string()`](fnliterals.scad#function-f_is_string) [`f_is_list()`](fnliterals.scad#function-f_is_list) [`f_is_range()`](fnliterals.scad#function-f_is_range) [`f_is_function()`](fnliterals.scad#function-f_is_function) [`f_is_vector()`](fnliterals.scad#function-f_is_vector) [`f_is_path()`](fnliterals.scad#function-f_is_path) [`f_is_region()`](fnliterals.scad#function-f_is_region) [`f_is_vnf()`](fnliterals.scad#function-f_is_vnf) [`f_is_patch()`](fnliterals.scad#function-f_is_patch)

## 34. [threading.scad](threading.scad)

Various types of threaded rods and nuts.  
- [Standard (UTS/ISO) Threading](threading.scad#section-standard-utsiso-threading)  
    [`threaded_rod()`](threading.scad#module-threaded_rod) [`threaded_nut()`](threading.scad#module-threaded_nut)
- [Trapezoidal Threading](threading.scad#section-trapezoidal-threading)  
    [`trapezoidal_threaded_rod()`](threading.scad#module-trapezoidal_threaded_rod) [`trapezoidal_threaded_nut()`](threading.scad#module-trapezoidal_threaded_nut) [`acme_threaded_rod()`](threading.scad#module-acme_threaded_rod) [`acme_threaded_nut()`](threading.scad#module-acme_threaded_nut)
- [Pipe Threading](threading.scad#section-pipe-threading)  
    [`npt_threaded_rod()`](threading.scad#module-npt_threaded_rod)
- [Buttress Threading](threading.scad#section-buttress-threading)  
    [`buttress_threaded_rod()`](threading.scad#module-buttress_threaded_rod) [`buttress_threaded_nut()`](threading.scad#module-buttress_threaded_nut)
- [Square Threading](threading.scad#section-square-threading)  
    [`square_threaded_rod()`](threading.scad#module-square_threaded_rod) [`square_threaded_nut()`](threading.scad#module-square_threaded_nut)
- [Ball Screws](threading.scad#section-ball-screws)  
    [`ball_screw_rod()`](threading.scad#module-ball_screw_rod)
- [Generic Threading](threading.scad#section-generic-threading)  
    [`generic_threaded_rod()`](threading.scad#module-generic_threaded_rod) [`generic_threaded_nut()`](threading.scad#module-generic_threaded_nut) [`thread_helix()`](threading.scad#module-thread_helix)

## 35. [screws.scad](screws.scad)

ISO (metric) and UTS screws and nuts.  
- [Generic Screw Creation](screws.scad#section-generic-screw-creation)  
    [`screw_info()`](screws.scad#function-screw_info) [`screw_head()`](screws.scad#module-screw_head) [`screw()`](screws.scad#module-screw) [`thread_specification()`](screws.scad#function-thread_specification) [`nut()`](screws.scad#module-nut)

## 36. [metric\_screws.scad](metric_screws.scad)

Metric screws, nuts, and screwholes.  
- [Functions](metric_screws.scad#section-functions)  
    [`get_metric_bolt_head_size()`](metric_screws.scad#function-get_metric_bolt_head_size) [`get_metric_bolt_head_height()`](metric_screws.scad#function-get_metric_bolt_head_height) [`get_metric_socket_cap_diam()`](metric_screws.scad#function-get_metric_socket_cap_diam) [`get_metric_socket_cap_height()`](metric_screws.scad#function-get_metric_socket_cap_height) [`get_metric_socket_cap_socket_size()`](metric_screws.scad#function-get_metric_socket_cap_socket_size) [`get_metric_socket_cap_socket_depth()`](metric_screws.scad#function-get_metric_socket_cap_socket_depth) [`get_metric_iso_coarse_thread_pitch()`](metric_screws.scad#function-get_metric_iso_coarse_thread_pitch) [`get_metric_iso_fine_thread_pitch()`](metric_screws.scad#function-get_metric_iso_fine_thread_pitch) [`get_metric_iso_superfine_thread_pitch()`](metric_screws.scad#function-get_metric_iso_superfine_thread_pitch) [`get_metric_jis_thread_pitch()`](metric_screws.scad#function-get_metric_jis_thread_pitch) [`get_metric_nut_size()`](metric_screws.scad#function-get_metric_nut_size) [`get_metric_nut_thickness()`](metric_screws.scad#function-get_metric_nut_thickness)
- [Modules](metric_screws.scad#section-modules)  
    [`generic_screw()`](metric_screws.scad#module-generic_screw) [`metric_bolt()`](metric_screws.scad#module-metric_bolt) [`metric_nut()`](metric_screws.scad#module-metric_nut)

## 37. [bottlecaps.scad](bottlecaps.scad)

Standard bottle caps and necks.  
- [PCO-1810 Bottle Threading](bottlecaps.scad#section-pco-1810-bottle-threading)  
    [`pco1810_neck()`](bottlecaps.scad#module-pco1810_neck) [`pco1810_cap()`](bottlecaps.scad#module-pco1810_cap)
- [PCO-1881 Bottle Threading](bottlecaps.scad#section-pco-1881-bottle-threading)  
    [`pco1881_neck()`](bottlecaps.scad#module-pco1881_neck) [`pco1881_cap()`](bottlecaps.scad#module-pco1881_cap)
- [Generic Bottle Connectors](bottlecaps.scad#section-generic-bottle-connectors)  
    [`generic_bottle_neck()`](bottlecaps.scad#module-generic_bottle_neck) [`generic_bottle_cap()`](bottlecaps.scad#module-generic_bottle_cap) [`bottle_adapter_neck_to_cap()`](bottlecaps.scad#module-bottle_adapter_neck_to_cap) [`bottle_adapter_cap_to_cap()`](bottlecaps.scad#module-bottle_adapter_cap_to_cap) [`bottle_adapter_neck_to_neck()`](bottlecaps.scad#module-bottle_adapter_neck_to_neck)
- [SPI Bottle Threading](bottlecaps.scad#section-spi-bottle-threading)  
    [`sp_neck()`](bottlecaps.scad#module-sp_neck) [`sp_diameter()`](bottlecaps.scad#function-sp_diameter)

## 38. [screw\_drive.scad](screw_drive.scad)

Masks for Phillips/Torx/etc driver holes.  
- [Phillips Drive](screw_drive.scad#section-phillips-drive)  
    [`phillips_mask()`](screw_drive.scad#module-phillips_mask) [`phillips_depth()`](screw_drive.scad#function-phillips_depth) [`phillips_diam()`](screw_drive.scad#function-phillips_diam)
- [Torx Drive](screw_drive.scad#section-torx-drive)  
    [`torx_outer_diam()`](screw_drive.scad#function-torx_outer_diam) [`torx_inner_diam()`](screw_drive.scad#function-torx_inner_diam) [`torx_depth()`](screw_drive.scad#function-torx_depth) [`torx_tip_radius()`](screw_drive.scad#function-torx_tip_radius) [`torx_rounding_radius()`](screw_drive.scad#function-torx_rounding_radius) [`torx_mask2d()`](screw_drive.scad#module-torx_mask2d) [`torx_mask()`](screw_drive.scad#module-torx_mask)
- [Robertson/Square Drives](screw_drive.scad#section-robertsonsquare-drives)  
    [`robertson_mask()`](screw_drive.scad#module-robertson_mask)

## 39. [linear\_bearings.scad](linear_bearings.scad)

Mounts for LMxUU style linear bearings.  
- [Functions](linear_bearings.scad#section-functions)  
    [`get_lmXuu_bearing_diam()`](linear_bearings.scad#function-get_lmxuu_bearing_diam) [`get_lmXuu_bearing_length()`](linear_bearings.scad#function-get_lmxuu_bearing_length) [`linear_bearing_housing()`](linear_bearings.scad#module-linear_bearing_housing) [`lmXuu_housing()`](linear_bearings.scad#module-lmxuu_housing)

## 40. [joiners.scad](joiners.scad)

Joiner shapes for connecting separately printed objects.  
- [Half Joiners](joiners.scad#section-half-joiners)  
    [`half_joiner_clear()`](joiners.scad#module-half_joiner_clear) [`half_joiner()`](joiners.scad#module-half_joiner) [`half_joiner2()`](joiners.scad#module-half_joiner2)
- [Full Joiners](joiners.scad#section-full-joiners)  
    [`joiner_clear()`](joiners.scad#module-joiner_clear) [`joiner()`](joiners.scad#module-joiner)
- [Full Joiners Pairs/Sets](joiners.scad#section-full-joiners-pairssets)  
    [`joiner_pair_clear()`](joiners.scad#module-joiner_pair_clear) [`joiner_pair()`](joiners.scad#module-joiner_pair)
- [Full Joiners Quads/Sets](joiners.scad#section-full-joiners-quadssets)  
    [`joiner_quad_clear()`](joiners.scad#module-joiner_quad_clear) [`joiner_quad()`](joiners.scad#module-joiner_quad)
- [Dovetails](joiners.scad#section-dovetails)  
    [`dovetail()`](joiners.scad#module-dovetail)
- [Tension Clips](joiners.scad#section-tension-clips)  
    [`snap_pin()`](joiners.scad#module-snap_pin) [`snap_pin_socket()`](joiners.scad#module-snap_pin_socket) [`rabbit_clip()`](joiners.scad#module-rabbit_clip)

## 41. [polyhedra.scad](polyhedra.scad)

Platonic, Archimidean, Catalan, and stellated polyhedra.  
- [Polyhedra](polyhedra.scad#section-polyhedra)  
    [`regular_polyhedron()`](polyhedra.scad#module-regular_polyhedron) [`regular_polyhedron_info()`](polyhedra.scad#function-regular_polyhedron_info)

## 42. [cubetruss.scad](cubetruss.scad)

Modular open-framed trusses and joiners.  
- [Cube Trusses](cubetruss.scad#section-cube-trusses)  
    [`cubetruss_dist()`](cubetruss.scad#function-cubetruss_dist) [`cubetruss_segment()`](cubetruss.scad#module-cubetruss_segment) [`cubetruss_support()`](cubetruss.scad#module-cubetruss_support) [`cubetruss_clip()`](cubetruss.scad#module-cubetruss_clip) [`cubetruss_foot()`](cubetruss.scad#module-cubetruss_foot) [`cubetruss_joiner()`](cubetruss.scad#module-cubetruss_joiner) [`cubetruss_uclip()`](cubetruss.scad#module-cubetruss_uclip) [`cubetruss()`](cubetruss.scad#module-cubetruss) [`cubetruss_corner()`](cubetruss.scad#module-cubetruss_corner)

## 43. [gears.scad](gears.scad)

Gears, racks, worms, and worm gears.  
- [Terminology](gears.scad#section-terminology)  
    
- [Functions](gears.scad#section-functions)  
    [`circular_pitch()`](gears.scad#function-circular_pitch) [`diametral_pitch()`](gears.scad#function-diametral_pitch) [`pitch_value()`](gears.scad#function-pitch_value) [`module_value()`](gears.scad#function-module_value) [`adendum()`](gears.scad#function-adendum) [`dedendum()`](gears.scad#function-dedendum) [`pitch_radius()`](gears.scad#function-pitch_radius) [`outer_radius()`](gears.scad#function-outer_radius) [`root_radius()`](gears.scad#function-root_radius) [`base_radius()`](gears.scad#function-base_radius) [`bevel_pitch_angle()`](gears.scad#function-bevel_pitch_angle) [`worm_gear_thickness()`](gears.scad#function-worm_gear_thickness)
- [2D Profiles](gears.scad#section-2d-profiles)  
    [`gear_tooth_profile()`](gears.scad#functionmodule-gear_tooth_profile) [`spur_gear2d()`](gears.scad#functionmodule-spur_gear2d) [`rack2d()`](gears.scad#functionmodule-rack2d)
- [3D Gears and Racks](gears.scad#section-3d-gears-and-racks)  
    [`spur_gear()`](gears.scad#functionmodule-spur_gear) [`bevel_gear()`](gears.scad#functionmodule-bevel_gear) [`rack()`](gears.scad#functionmodule-rack) [`worm()`](gears.scad#functionmodule-worm) [`worm_gear()`](gears.scad#functionmodule-worm_gear)

## 44. [modular\_hose.scad](modular_hose.scad)

Modular flexible hose parts.  
- [Modular Hose Parts](modular_hose.scad#section-modular-hose-parts)  
    [`modular_hose()`](modular_hose.scad#module-modular_hose) [`modular_hose_radius()`](modular_hose.scad#function-modular_hose_radius)

## 45. [hingesnaps.scad](hingesnaps.scad)

Foldable, snap-locking parts.  
- [Hinges and Snaps](hingesnaps.scad#section-hinges-and-snaps)  
    [`folding_hinge_mask()`](hingesnaps.scad#module-folding_hinge_mask) [`snap_lock()`](hingesnaps.scad#module-snap_lock) [`snap_socket()`](hingesnaps.scad#module-snap_socket) [`apply_folding_hinges_and_snaps()`](hingesnaps.scad#module-apply_folding_hinges_and_snaps)

## 46. [nema\_steppers.scad](nema_steppers.scad)

Mounting holes for NEMA motors, and simple motor models.  
- [Functions](nema_steppers.scad#section-functions)  
    [`nema_motor_width()`](nema_steppers.scad#function-nema_motor_width) [`nema_motor_plinth_height()`](nema_steppers.scad#function-nema_motor_plinth_height) [`nema_motor_plinth_diam()`](nema_steppers.scad#function-nema_motor_plinth_diam) [`nema_motor_screw_spacing()`](nema_steppers.scad#function-nema_motor_screw_spacing) [`nema_motor_screw_size()`](nema_steppers.scad#function-nema_motor_screw_size) [`nema_motor_screw_depth()`](nema_steppers.scad#function-nema_motor_screw_depth)
- [Motor Models](nema_steppers.scad#section-motor-models)  
    [`nema11_stepper()`](nema_steppers.scad#module-nema11_stepper) [`nema14_stepper()`](nema_steppers.scad#module-nema14_stepper) [`nema17_stepper()`](nema_steppers.scad#module-nema17_stepper) [`nema23_stepper()`](nema_steppers.scad#module-nema23_stepper) [`nema34_stepper()`](nema_steppers.scad#module-nema34_stepper)
- [Masking Modules](nema_steppers.scad#section-masking-modules)  
    [`nema_mount_holes()`](nema_steppers.scad#module-nema_mount_holes) [`nema11_mount_holes()`](nema_steppers.scad#module-nema11_mount_holes) [`nema14_mount_holes()`](nema_steppers.scad#module-nema14_mount_holes) [`nema17_mount_holes()`](nema_steppers.scad#module-nema17_mount_holes) [`nema23_mount_holes()`](nema_steppers.scad#module-nema23_mount_holes) [`nema34_mount_holes()`](nema_steppers.scad#module-nema34_mount_holes)

## 47. [walls.scad](walls.scad)

Walls and structural elements that 3D print without support.  
- [Walls](walls.scad#section-walls)  
    [`narrowing_strut()`](walls.scad#module-narrowing_strut) [`thinning_wall()`](walls.scad#module-thinning_wall) [`thinning_triangle()`](walls.scad#module-thinning_triangle) [`sparse_strut()`](walls.scad#module-sparse_strut) [`sparse_strut3d()`](walls.scad#module-sparse_strut3d) [`corrugated_wall()`](walls.scad#module-corrugated_wall)

## 48. [wiring.scad](wiring.scad)

Routed bundles of wires.  
- [Functions](wiring.scad#section-functions)  
    [`hex_offset_ring()`](wiring.scad#function-hex_offset_ring) [`hex_offsets()`](wiring.scad#function-hex_offsets)
- [Modules](wiring.scad#section-modules)  
    [`wiring()`](wiring.scad#module-wiring)

## 49. [knurling.scad](knurling.scad)

Masks and shapes to create knurling.  
- [Knurling](knurling.scad#section-knurling)  
    [`knurled_cylinder()`](knurling.scad#module-knurled_cylinder) [`knurled_cylinder_mask()`](knurling.scad#module-knurled_cylinder_mask)

## 50. [sliders.scad](sliders.scad)

Simple sliders and rails.  
- [Modules](sliders.scad#section-modules)  
    [`slider()`](sliders.scad#module-slider) [`rail()`](sliders.scad#module-rail)

