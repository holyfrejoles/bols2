# Topic Index

An index of topics, with related functions, modules, and constants.

- [A](#A): [Affine](#affine), [Angle](#angle), [Area](#area), [Argument Handling](#argument-handling), [Attachable](#attachable), [Attachments](#attachments)
- [B](#B): [Bezier Curves](#bezier-curves), [Bezier Patches](#bezier-patches), [Bezier Paths](#bezier-paths), [Boolean Operations](#boolean-operations), [Bounding Boxes](#bounding-boxes), [Bounds](#bounds)
- [C](#C): [Centroid](#centroid), [Circles](#circles), [Clockwise](#clockwise), [Closest](#closest), [Collinearity](#collinearity), [Collision](#collision), [Constants](#constants), [Convexity](#convexity), [Coordinates](#coordinates), [Coplanarity](#coplanarity)
- [D](#D): [Data Structures](#data-structures), [Debugging](#debugging), [Distance](#distance), [Drawing Tools](#drawing-tools)
- [E](#E): [Error Checking](#error-checking), [Extrusions](#extrusions)
- [F](#F): [Filters](#filters), [Function Literal Factories](#function-literal-factories), [Function Literals](#function-literals)
- [G](#G): [Gears](#gears), [Geometry](#geometry)
- [H](#H): [Hashing](#hashing)
- [I](#I): [Intersection](#intersection), [Iteration](#iteration)
- [L](#L): [Lines](#lines), [List Handling](#list-handling), [Logic](#logic), [Looping](#looping)
- [M](#M): [Masks (2D)](#masks-2d), [Math Operators](#math-operators), [Matrices](#matrices), [Mini-Language](#mini-language), [Mirroring](#mirroring)
- [P](#P): [Path Generators](#path-generators), [Path Generators (2D)](#path-generators-2d), [Path Subdivision](#path-subdivision), [Paths](#paths), [Paths (2D)](#paths-2d), [Paths (3D)](#paths-3d), [Planes](#planes), [Points](#points), [Polygon](#polygon), [Polygons](#polygons), [Polyhedra](#polyhedra), [Projection](#projection)
- [R](#R): [Random](#random), [Reflection](#reflection), [Rotation](#rotation), [Rounding](#rounding)
- [S](#S): [Scaling](#scaling), [Search](#search), [Searching](#searching), [Segments](#segments), [Set Handling](#set-handling), [Shapes (2D)](#shapes-2d), [Shapes (3D)](#shapes-3d), [Skewing](#skewing), [Spheres](#spheres), [String Operators](#string-operators)
- [T](#T): [Tangents](#tangents), [Test](#test), [Testing](#testing), [Text](#text), [Transforms](#transforms), [Translation](#translation), [Triangles](#triangles), [Trigonometry](#trigonometry), [Trusses](#trusses), [Type Checking](#type-checking), [Type Conversion](#type-conversion), [Type Queries](#type-queries)
- [U](#U): [Undef Handling](#undef-handling)
- [V](#V): [VNF Generators](#vnf-generators), [Vectors](#vectors)

## A

### Affine

- [`apply()`](transforms.scad#function-apply) (in transforms.scad)
- [`back()`](transforms.scad#functionmodule-back) (in transforms.scad)
- [`down()`](transforms.scad#functionmodule-down) (in transforms.scad)
- [`frame_map()`](transforms.scad#functionmodule-frame_map) (in transforms.scad)
- [`fwd()`](transforms.scad#functionmodule-fwd) (in transforms.scad)
- [`ident()`](linalg.scad#function-ident) (in linalg.scad)
- [`left()`](transforms.scad#functionmodule-left) (in transforms.scad)
- [`mirror()`](transforms.scad#functionmodule-mirror) (in transforms.scad)
- [`move()`](transforms.scad#functionmodule-move) (in transforms.scad)
- [`right()`](transforms.scad#functionmodule-right) (in transforms.scad)
- [`rot()`](transforms.scad#functionmodule-rot) (in transforms.scad)
- [`rot_decode()`](geometry.scad#function-rot_decode) (in geometry.scad)
- [`scale()`](transforms.scad#functionmodule-scale) (in transforms.scad)
- [`skew()`](transforms.scad#functionmodule-skew) (in transforms.scad)
- [`translate()`](transforms.scad#functionmodule-move) (in transforms.scad)
- [`up()`](transforms.scad#functionmodule-up) (in transforms.scad)
- [`xflip()`](transforms.scad#functionmodule-xflip) (in transforms.scad)
- [`xmove()`](transforms.scad#functionmodule-right) (in transforms.scad)
- [`xrot()`](transforms.scad#functionmodule-xrot) (in transforms.scad)
- [`xscale()`](transforms.scad#functionmodule-xscale) (in transforms.scad)
- [`yflip()`](transforms.scad#functionmodule-yflip) (in transforms.scad)
- [`ymove()`](transforms.scad#functionmodule-back) (in transforms.scad)
- [`yrot()`](transforms.scad#functionmodule-yrot) (in transforms.scad)
- [`yscale()`](transforms.scad#functionmodule-yscale) (in transforms.scad)
- [`zflip()`](transforms.scad#functionmodule-zflip) (in transforms.scad)
- [`zmove()`](transforms.scad#functionmodule-up) (in transforms.scad)
- [`zrot()`](transforms.scad#functionmodule-zrot) (in transforms.scad)
- [`zscale()`](transforms.scad#functionmodule-zscale) (in transforms.scad)

### Angle

- [`plane_line_angle()`](geometry.scad#function-plane_line_angle) (in geometry.scad)

### Area

- [`polygon_area()`](geometry.scad#function-polygon_area) (in geometry.scad)
- [`triangle_area()`](trigonometry.scad#function-triangle_area) (in trigonometry.scad)

### Argument Handling

- [`get_anchor()`](utility.scad#function-get_anchor) (in utility.scad)
- [`get_radius()`](utility.scad#function-get_radius) (in utility.scad)
- [`scalar_vec3()`](utility.scad#function-scalar_vec3) (in utility.scad)

### Attachable

- [`cube()`](shapes3d.scad#functionmodule-cube) (in shapes3d.scad)
- [`cubetruss()`](cubetruss.scad#module-cubetruss) (in cubetruss.scad)
- [`cubetruss_clip()`](cubetruss.scad#module-cubetruss_clip) (in cubetruss.scad)
- [`cubetruss_corner()`](cubetruss.scad#module-cubetruss_corner) (in cubetruss.scad)
- [`cubetruss_foot()`](cubetruss.scad#module-cubetruss_foot) (in cubetruss.scad)
- [`cubetruss_joiner()`](cubetruss.scad#module-cubetruss_joiner) (in cubetruss.scad)
- [`cubetruss_segment()`](cubetruss.scad#module-cubetruss_segment) (in cubetruss.scad)
- [`cubetruss_support()`](cubetruss.scad#module-cubetruss_support) (in cubetruss.scad)
- [`cubetruss_uclip()`](cubetruss.scad#module-cubetruss_uclip) (in cubetruss.scad)
- [`cylinder()`](shapes3d.scad#functionmodule-cylinder) (in shapes3d.scad)
- [`egg()`](shapes2d.scad#functionmodule-egg) (in shapes2d.scad)
- [`ellipse()`](shapes2d.scad#functionmodule-ellipse) (in shapes2d.scad)
- [`glued_circles()`](shapes2d.scad#functionmodule-glued_circles) (in shapes2d.scad)
- [`hexagon()`](shapes2d.scad#functionmodule-hexagon) (in shapes2d.scad)
- [`mask2d_chamfer()`](masks2d.scad#functionmodule-mask2d_chamfer) (in masks2d.scad)
- [`mask2d_cove()`](masks2d.scad#functionmodule-mask2d_cove) (in masks2d.scad)
- [`mask2d_dovetail()`](masks2d.scad#functionmodule-mask2d_dovetail) (in masks2d.scad)
- [`mask2d_ogee()`](masks2d.scad#functionmodule-mask2d_ogee) (in masks2d.scad)
- [`mask2d_rabbet()`](masks2d.scad#functionmodule-mask2d_rabbet) (in masks2d.scad)
- [`mask2d_roundover()`](masks2d.scad#functionmodule-mask2d_roundover) (in masks2d.scad)
- [`mask2d_teardrop()`](masks2d.scad#functionmodule-mask2d_teardrop) (in masks2d.scad)
- [`octagon()`](shapes2d.scad#functionmodule-octagon) (in shapes2d.scad)
- [`pentagon()`](shapes2d.scad#functionmodule-pentagon) (in shapes2d.scad)
- [`rect()`](shapes2d.scad#functionmodule-rect) (in shapes2d.scad)
- [`regular_ngon()`](shapes2d.scad#functionmodule-regular_ngon) (in shapes2d.scad)
- [`reuleaux_polygon()`](shapes2d.scad#functionmodule-reuleaux_polygon) (in shapes2d.scad)
- [`sphere()`](shapes3d.scad#functionmodule-sphere) (in shapes3d.scad)
- [`star()`](shapes2d.scad#functionmodule-star) (in shapes2d.scad)
- [`supershape()`](shapes2d.scad#functionmodule-supershape) (in shapes2d.scad)
- [`teardrop2d()`](shapes2d.scad#functionmodule-teardrop2d) (in shapes2d.scad)
- [`trapezoid()`](shapes2d.scad#functionmodule-trapezoid) (in shapes2d.scad)

### Attachments

- [`attach()`](attachments.scad#module-attach) (in attachments.scad)
- [`attachable()`](attachments.scad#module-attachable) (in attachments.scad)
- [`corner_mask()`](attachments.scad#module-corner_mask) (in attachments.scad)
- [`corner_profile()`](attachments.scad#module-corner_profile) (in attachments.scad)
- [`diff()`](attachments.scad#module-diff) (in attachments.scad)
- [`edge_mask()`](attachments.scad#module-edge_mask) (in attachments.scad)
- [`edge_profile()`](attachments.scad#module-edge_profile) (in attachments.scad)
- [`face_profile()`](attachments.scad#module-face_profile) (in attachments.scad)
- [`hide()`](attachments.scad#module-hide) (in attachments.scad)
- [`hulling()`](attachments.scad#module-hulling) (in attachments.scad)
- [`intersect()`](attachments.scad#module-intersect) (in attachments.scad)
- [`named_anchor()`](attachments.scad#function-named_anchor) (in attachments.scad)
- [`orient()`](attachments.scad#module-orient) (in attachments.scad)
- [`position()`](attachments.scad#module-position) (in attachments.scad)
- [`recolor()`](attachments.scad#module-recolor) (in attachments.scad)
- [`reorient()`](attachments.scad#function-reorient) (in attachments.scad)
- [`show()`](attachments.scad#module-show) (in attachments.scad)
- [`tags()`](attachments.scad#module-tags) (in attachments.scad)
- [`text()`](shapes2d.scad#module-text) (in shapes2d.scad)
- [`text3d()`](shapes3d.scad#module-text3d) (in shapes3d.scad)

## B

### Bezier Curves

- [`bezier_closest_point()`](beziers.scad#function-bezier_closest_point) (in beziers.scad)
- [`bezier_curvature()`](beziers.scad#function-bezier_curvature) (in beziers.scad)
- [`bezier_curve()`](beziers.scad#function-bezier_curve) (in beziers.scad)
- [`bezier_derivative()`](beziers.scad#function-bezier_derivative) (in beziers.scad)
- [`bezier_length()`](beziers.scad#function-bezier_length) (in beziers.scad)
- [`bezier_line_intersection()`](beziers.scad#function-bezier_line_intersection) (in beziers.scad)
- [`bezier_points()`](beziers.scad#function-bezier_points) (in beziers.scad)
- [`bezier_tangent()`](beziers.scad#function-bezier_tangent) (in beziers.scad)

### Bezier Patches

- [`bezier_patch_flat()`](beziers.scad#function-bezier_patch_flat) (in beziers.scad)
- [`bezier_patch_points()`](beziers.scad#function-bezier_patch_points) (in beziers.scad)
- [`bezier_patch_reverse()`](beziers.scad#function-bezier_patch_reverse) (in beziers.scad)
- [`bezier_vnf()`](beziers.scad#function-bezier_vnf) (in beziers.scad)
- [`debug_bezier_patches()`](beziers.scad#module-debug_bezier_patches) (in beziers.scad)
- [`is_bezier_patch()`](beziers.scad#function-is_bezier_patch) (in beziers.scad)

### Bezier Paths

- [`bez_begin()`](beziers.scad#function-bez_begin) (in beziers.scad)
- [`bez_end()`](beziers.scad#function-bez_end) (in beziers.scad)
- [`bez_joint()`](beziers.scad#function-bez_joint) (in beziers.scad)
- [`bez_tang()`](beziers.scad#function-bez_tang) (in beziers.scad)
- [`bezpath_close_to_axis()`](beziers.scad#function-bezpath_close_to_axis) (in beziers.scad)
- [`bezpath_closest_point()`](beziers.scad#function-bezpath_closest_point) (in beziers.scad)
- [`bezpath_curve()`](beziers.scad#function-bezpath_curve) (in beziers.scad)
- [`bezpath_length()`](beziers.scad#function-bezpath_length) (in beziers.scad)
- [`bezpath_offset()`](beziers.scad#function-bezpath_offset) (in beziers.scad)
- [`bezpath_points()`](beziers.scad#function-bezpath_points) (in beziers.scad)
- [`debug_bezier()`](beziers.scad#module-debug_bezier) (in beziers.scad)
- [`path_to_bezpath()`](beziers.scad#function-path_to_bezpath) (in beziers.scad)

### Boolean Operations

- [`f_and()`](fnliterals.scad#function-f_and) (in fnliterals.scad)
- [`f_nand()`](fnliterals.scad#function-f_nand) (in fnliterals.scad)
- [`f_nor()`](fnliterals.scad#function-f_nor) (in fnliterals.scad)
- [`f_not()`](fnliterals.scad#function-f_not) (in fnliterals.scad)
- [`f_or()`](fnliterals.scad#function-f_or) (in fnliterals.scad)
- [`f_xor()`](fnliterals.scad#function-f_xor) (in fnliterals.scad)

### Bounding Boxes

- [`pointlist_bounds()`](vectors.scad#function-pointlist_bounds) (in vectors.scad)

### Bounds

- [`pointlist_bounds()`](vectors.scad#function-pointlist_bounds) (in vectors.scad)

## C

### Centroid

- [`centroid()`](geometry.scad#function-centroid) (in geometry.scad)

### Circles

- [`circle_2tangents()`](geometry.scad#functionmodule-circle_2tangents) (in geometry.scad)
- [`circle_3points()`](geometry.scad#functionmodule-circle_3points) (in geometry.scad)
- [`circle_circle_intersection()`](geometry.scad#function-circle_circle_intersection) (in geometry.scad)
- [`circle_circle_tangents()`](geometry.scad#function-circle_circle_tangents) (in geometry.scad)
- [`circle_line_intersection()`](geometry.scad#function-circle_line_intersection) (in geometry.scad)
- [`circle_point_tangents()`](geometry.scad#function-circle_point_tangents) (in geometry.scad)

### Clockwise

- [`ccw_polygon()`](geometry.scad#function-ccw_polygon) (in geometry.scad)
- [`clockwise_polygon()`](geometry.scad#function-clockwise_polygon) (in geometry.scad)
- [`is_polygon_clockwise()`](geometry.scad#function-is_polygon_clockwise) (in geometry.scad)
- [`reverse_polygon()`](geometry.scad#function-reverse_polygon) (in geometry.scad)

### Closest

- [`vector_search()`](vectors.scad#function-vector_search) (in vectors.scad)
- [`vector_search_tree()`](vectors.scad#function-vector_search_tree) (in vectors.scad)

### Collinearity

- [`is_collinear()`](geometry.scad#function-is_collinear) (in geometry.scad)

### Collision

- [`convex_collision()`](geometry.scad#function-convex_collision) (in geometry.scad)

### Constants

- [`BACK`](constants.scad#constant-back) (in constants.scad)
- [`BOT`](constants.scad#constant-bottom) (in constants.scad)
- [`BOTTOM`](constants.scad#constant-bottom) (in constants.scad)
- [`CENTER`](constants.scad#constant-center) (in constants.scad)
- [`CENTRE`](constants.scad#constant-center) (in constants.scad)
- [`CTR`](constants.scad#constant-center) (in constants.scad)
- [`DOWN`](constants.scad#constant-bottom) (in constants.scad)
- [`FORWARD`](constants.scad#constant-front) (in constants.scad)
- [`FRONT`](constants.scad#constant-front) (in constants.scad)
- [`FWD`](constants.scad#constant-front) (in constants.scad)
- [`LEFT`](constants.scad#constant-left) (in constants.scad)
- [`LINE`](constants.scad#constant-line) (in constants.scad)
- [`RAY`](constants.scad#constant-ray) (in constants.scad)
- [`RIGHT`](constants.scad#constant-right) (in constants.scad)
- [`SEGMENT`](constants.scad#constant-segment) (in constants.scad)
- [`TOP`](constants.scad#constant-top) (in constants.scad)
- [`UP`](constants.scad#constant-top) (in constants.scad)

### Convexity

- [`convex_collision()`](geometry.scad#function-convex_collision) (in geometry.scad)
- [`convex_distance()`](geometry.scad#function-convex_distance) (in geometry.scad)
- [`is_polygon_convex()`](geometry.scad#function-is_polygon_convex) (in geometry.scad)

### Coordinates

- [`altaz_to_xyz()`](coords.scad#function-altaz_to_xyz) (in coords.scad)
- [`cylindrical_to_xyz()`](coords.scad#function-cylindrical_to_xyz) (in coords.scad)
- [`lift_plane()`](coords.scad#function-lift_plane) (in coords.scad)
- [`path2d()`](coords.scad#function-path2d) (in coords.scad)
- [`path3d()`](coords.scad#function-path3d) (in coords.scad)
- [`path4d()`](coords.scad#function-path4d) (in coords.scad)
- [`point2d()`](coords.scad#function-point2d) (in coords.scad)
- [`point3d()`](coords.scad#function-point3d) (in coords.scad)
- [`point4d()`](coords.scad#function-point4d) (in coords.scad)
- [`polar_to_xy()`](coords.scad#function-polar_to_xy) (in coords.scad)
- [`project_plane()`](coords.scad#function-project_plane) (in coords.scad)
- [`spherical_to_xyz()`](coords.scad#function-spherical_to_xyz) (in coords.scad)
- [`xy_to_polar()`](coords.scad#function-xy_to_polar) (in coords.scad)
- [`xyz_to_altaz()`](coords.scad#function-xyz_to_altaz) (in coords.scad)
- [`xyz_to_cylindrical()`](coords.scad#function-xyz_to_cylindrical) (in coords.scad)
- [`xyz_to_spherical()`](coords.scad#function-xyz_to_spherical) (in coords.scad)

### Coplanarity

- [`is_coplanar()`](geometry.scad#function-is_coplanar) (in geometry.scad)

## D

### Data Structures

- [`binsearch()`](fnliterals.scad#function-binsearch) (in fnliterals.scad)
- [`hashmap()`](fnliterals.scad#function-hashmap) (in fnliterals.scad)
- [`simple_hash()`](fnliterals.scad#function-simple_hash) (in fnliterals.scad)

### Debugging

- [`assert_approx()`](utility.scad#module-assert_approx) (in utility.scad)
- [`assert_equal()`](utility.scad#module-assert_equal) (in utility.scad)
- [`debug_bezier()`](beziers.scad#module-debug_bezier) (in beziers.scad)
- [`debug_bezier_patches()`](beziers.scad#module-debug_bezier_patches) (in beziers.scad)
- [`debug_vnf()`](vnf.scad#module-debug_vnf) (in vnf.scad)
- [`shape_compare()`](utility.scad#module-shape_compare) (in utility.scad)

### Distance

- [`closest_point()`](vectors.scad#function-closest_point) (in vectors.scad)
- [`convex_distance()`](geometry.scad#function-convex_distance) (in geometry.scad)
- [`furthest_point()`](vectors.scad#function-furthest_point) (in vectors.scad)
- [`line_closest_point()`](geometry.scad#function-line_closest_point) (in geometry.scad)
- [`point_line_distance()`](geometry.scad#function-point_line_distance) (in geometry.scad)
- [`point_plane_distance()`](geometry.scad#function-point_plane_distance) (in geometry.scad)
- [`segment_distance()`](geometry.scad#function-segment_distance) (in geometry.scad)

### Drawing Tools

- [`dashed_stroke()`](drawing.scad#functionmodule-dashed_stroke) (in drawing.scad)
- [`stroke()`](drawing.scad#module-stroke) (in drawing.scad)

## E

### Error Checking

- [`assert_approx()`](utility.scad#module-assert_approx) (in utility.scad)
- [`assert_equal()`](utility.scad#module-assert_equal) (in utility.scad)
- [`no_children()`](utility.scad#module-no_children) (in utility.scad)
- [`no_function()`](utility.scad#function-no_function) (in utility.scad)
- [`no_module()`](utility.scad#module-no_module) (in utility.scad)
- [`shape_compare()`](utility.scad#module-shape_compare) (in utility.scad)

### Extrusions

- [`jittered_poly()`](shapes2d.scad#module-jittered_poly) (in shapes2d.scad)

## F

### Filters

- [`filter()`](fnliterals.scad#function-filter) (in fnliterals.scad)
- [`find_all()`](fnliterals.scad#function-find_all) (in fnliterals.scad)

### Function Literal Factories

- [`f_1arg()`](fnliterals.scad#function-f_1arg) (in fnliterals.scad)
- [`f_2arg()`](fnliterals.scad#function-f_2arg) (in fnliterals.scad)
- [`f_2arg_simple()`](fnliterals.scad#function-f_2arg_simple) (in fnliterals.scad)
- [`f_3arg()`](fnliterals.scad#function-f_3arg) (in fnliterals.scad)

### Function Literals

- [`accumulate()`](fnliterals.scad#function-accumulate) (in fnliterals.scad)
- [`binsearch()`](fnliterals.scad#function-binsearch) (in fnliterals.scad)
- [`f_1arg()`](fnliterals.scad#function-f_1arg) (in fnliterals.scad)
- [`f_2arg()`](fnliterals.scad#function-f_2arg) (in fnliterals.scad)
- [`f_2arg_simple()`](fnliterals.scad#function-f_2arg_simple) (in fnliterals.scad)
- [`f_3arg()`](fnliterals.scad#function-f_3arg) (in fnliterals.scad)
- [`f_abs()`](fnliterals.scad#function-f_abs) (in fnliterals.scad)
- [`f_acos()`](fnliterals.scad#function-f_acos) (in fnliterals.scad)
- [`f_add()`](fnliterals.scad#function-f_add) (in fnliterals.scad)
- [`f_and()`](fnliterals.scad#function-f_and) (in fnliterals.scad)
- [`f_asin()`](fnliterals.scad#function-f_asin) (in fnliterals.scad)
- [`f_atan()`](fnliterals.scad#function-f_atan) (in fnliterals.scad)
- [`f_atan2()`](fnliterals.scad#function-f_atan2) (in fnliterals.scad)
- [`f_ceil()`](fnliterals.scad#function-f_ceil) (in fnliterals.scad)
- [`f_chr()`](fnliterals.scad#function-f_chr) (in fnliterals.scad)
- [`f_cos()`](fnliterals.scad#function-f_cos) (in fnliterals.scad)
- [`f_cross()`](fnliterals.scad#function-f_cross) (in fnliterals.scad)
- [`f_div()`](fnliterals.scad#function-f_div) (in fnliterals.scad)
- [`f_even()`](fnliterals.scad#function-f_even) (in fnliterals.scad)
- [`f_exp()`](fnliterals.scad#function-f_exp) (in fnliterals.scad)
- [`f_floor()`](fnliterals.scad#function-f_floor) (in fnliterals.scad)
- [`f_is_bool()`](fnliterals.scad#function-f_is_bool) (in fnliterals.scad)
- [`f_is_def()`](fnliterals.scad#function-f_is_def) (in fnliterals.scad)
- [`f_is_finite()`](fnliterals.scad#function-f_is_finite) (in fnliterals.scad)
- [`f_is_function()`](fnliterals.scad#function-f_is_function) (in fnliterals.scad)
- [`f_is_int()`](fnliterals.scad#function-f_is_int) (in fnliterals.scad)
- [`f_is_list()`](fnliterals.scad#function-f_is_list) (in fnliterals.scad)
- [`f_is_nan()`](fnliterals.scad#function-f_is_nan) (in fnliterals.scad)
- [`f_is_num()`](fnliterals.scad#function-f_is_num) (in fnliterals.scad)
- [`f_is_patch()`](fnliterals.scad#function-f_is_patch) (in fnliterals.scad)
- [`f_is_path()`](fnliterals.scad#function-f_is_path) (in fnliterals.scad)
- [`f_is_range()`](fnliterals.scad#function-f_is_range) (in fnliterals.scad)
- [`f_is_region()`](fnliterals.scad#function-f_is_region) (in fnliterals.scad)
- [`f_is_string()`](fnliterals.scad#function-f_is_string) (in fnliterals.scad)
- [`f_is_undef()`](fnliterals.scad#function-f_is_undef) (in fnliterals.scad)
- [`f_is_vector()`](fnliterals.scad#function-f_is_vector) (in fnliterals.scad)
- [`f_is_vnf()`](fnliterals.scad#function-f_is_vnf) (in fnliterals.scad)
- [`f_len()`](fnliterals.scad#function-f_len) (in fnliterals.scad)
- [`f_ln()`](fnliterals.scad#function-f_ln) (in fnliterals.scad)
- [`f_log()`](fnliterals.scad#function-f_log) (in fnliterals.scad)
- [`f_max()`](fnliterals.scad#function-f_max) (in fnliterals.scad)
- [`f_max2()`](fnliterals.scad#function-f_max2) (in fnliterals.scad)
- [`f_max3()`](fnliterals.scad#function-f_max3) (in fnliterals.scad)
- [`f_min()`](fnliterals.scad#function-f_min) (in fnliterals.scad)
- [`f_min2()`](fnliterals.scad#function-f_min2) (in fnliterals.scad)
- [`f_min3()`](fnliterals.scad#function-f_min3) (in fnliterals.scad)
- [`f_mod()`](fnliterals.scad#function-f_mod) (in fnliterals.scad)
- [`f_mul()`](fnliterals.scad#function-f_mul) (in fnliterals.scad)
- [`f_nand()`](fnliterals.scad#function-f_nand) (in fnliterals.scad)
- [`f_neg()`](fnliterals.scad#function-f_neg) (in fnliterals.scad)
- [`f_nor()`](fnliterals.scad#function-f_nor) (in fnliterals.scad)
- [`f_norm()`](fnliterals.scad#function-f_norm) (in fnliterals.scad)
- [`f_not()`](fnliterals.scad#function-f_not) (in fnliterals.scad)
- [`f_odd()`](fnliterals.scad#function-f_odd) (in fnliterals.scad)
- [`f_or()`](fnliterals.scad#function-f_or) (in fnliterals.scad)
- [`f_ord()`](fnliterals.scad#function-f_ord) (in fnliterals.scad)
- [`f_pow()`](fnliterals.scad#function-f_pow) (in fnliterals.scad)
- [`f_round()`](fnliterals.scad#function-f_round) (in fnliterals.scad)
- [`f_sign()`](fnliterals.scad#function-f_sign) (in fnliterals.scad)
- [`f_sin()`](fnliterals.scad#function-f_sin) (in fnliterals.scad)
- [`f_sqr()`](fnliterals.scad#function-f_sqr) (in fnliterals.scad)
- [`f_sqrt()`](fnliterals.scad#function-f_sqrt) (in fnliterals.scad)
- [`f_str()`](fnliterals.scad#function-f_str) (in fnliterals.scad)
- [`f_str2()`](fnliterals.scad#function-f_str2) (in fnliterals.scad)
- [`f_str3()`](fnliterals.scad#function-f_str3) (in fnliterals.scad)
- [`f_sub()`](fnliterals.scad#function-f_sub) (in fnliterals.scad)
- [`f_tan()`](fnliterals.scad#function-f_tan) (in fnliterals.scad)
- [`f_xor()`](fnliterals.scad#function-f_xor) (in fnliterals.scad)
- [`filter()`](fnliterals.scad#function-filter) (in fnliterals.scad)
- [`find_all()`](fnliterals.scad#function-find_all) (in fnliterals.scad)
- [`find_first()`](fnliterals.scad#function-find_first) (in fnliterals.scad)
- [`for_n()`](fnliterals.scad#function-for_n) (in fnliterals.scad)
- [`hashmap()`](fnliterals.scad#function-hashmap) (in fnliterals.scad)
- [`map()`](fnliterals.scad#function-map) (in fnliterals.scad)
- [`reduce()`](fnliterals.scad#function-reduce) (in fnliterals.scad)
- [`simple_hash()`](fnliterals.scad#function-simple_hash) (in fnliterals.scad)
- [`while()`](fnliterals.scad#function-while) (in fnliterals.scad)

## G

### Gears

- [`adendum()`](gears.scad#function-adendum) (in gears.scad)
- [`base_radius()`](gears.scad#function-base_radius) (in gears.scad)
- [`bevel_gear()`](gears.scad#functionmodule-bevel_gear) (in gears.scad)
- [`bevel_pitch_angle()`](gears.scad#function-bevel_pitch_angle) (in gears.scad)
- [`circular_pitch()`](gears.scad#function-circular_pitch) (in gears.scad)
- [`dedendum()`](gears.scad#function-dedendum) (in gears.scad)
- [`diametral_pitch()`](gears.scad#function-diametral_pitch) (in gears.scad)
- [`gear_tooth_profile()`](gears.scad#functionmodule-gear_tooth_profile) (in gears.scad)
- [`module_value()`](gears.scad#function-module_value) (in gears.scad)
- [`outer_radius()`](gears.scad#function-outer_radius) (in gears.scad)
- [`pitch_radius()`](gears.scad#function-pitch_radius) (in gears.scad)
- [`pitch_value()`](gears.scad#function-pitch_value) (in gears.scad)
- [`rack()`](gears.scad#functionmodule-rack) (in gears.scad)
- [`rack2d()`](gears.scad#functionmodule-rack2d) (in gears.scad)
- [`root_radius()`](gears.scad#function-root_radius) (in gears.scad)
- [`spur_gear()`](gears.scad#functionmodule-spur_gear) (in gears.scad)
- [`spur_gear2d()`](gears.scad#functionmodule-spur_gear2d) (in gears.scad)
- [`worm()`](gears.scad#functionmodule-worm) (in gears.scad)
- [`worm_gear()`](gears.scad#functionmodule-worm_gear) (in gears.scad)
- [`worm_gear_thickness()`](gears.scad#function-worm_gear_thickness) (in gears.scad)

### Geometry

- [`adj_ang_to_hyp()`](trigonometry.scad#function-adj_ang_to_hyp) (in trigonometry.scad)
- [`adj_ang_to_opp()`](trigonometry.scad#function-adj_ang_to_opp) (in trigonometry.scad)
- [`adj_hyp_to_opp()`](trigonometry.scad#function-hyp_adj_to_opp) (in trigonometry.scad)
- [`adj_opp_to_ang()`](trigonometry.scad#function-adj_opp_to_ang) (in trigonometry.scad)
- [`adj_opp_to_hyp()`](trigonometry.scad#function-adj_opp_to_hyp) (in trigonometry.scad)
- [`align_polygon()`](geometry.scad#function-align_polygon) (in geometry.scad)
- [`ang_adj_to_hyp()`](trigonometry.scad#function-adj_ang_to_hyp) (in trigonometry.scad)
- [`ang_adj_to_opp()`](trigonometry.scad#function-adj_ang_to_opp) (in trigonometry.scad)
- [`ang_hyp_to_adj()`](trigonometry.scad#function-hyp_ang_to_adj) (in trigonometry.scad)
- [`ang_hyp_to_opp()`](trigonometry.scad#function-hyp_ang_to_opp) (in trigonometry.scad)
- [`ang_opp_to_adj()`](trigonometry.scad#function-opp_ang_to_adj) (in trigonometry.scad)
- [`ang_opp_to_hyp()`](trigonometry.scad#function-opp_ang_to_hyp) (in trigonometry.scad)
- [`are_points_on_plane()`](geometry.scad#function-are_points_on_plane) (in geometry.scad)
- [`bezier_line_intersection()`](beziers.scad#function-bezier_line_intersection) (in beziers.scad)
- [`ccw_polygon()`](geometry.scad#function-ccw_polygon) (in geometry.scad)
- [`centroid()`](geometry.scad#function-centroid) (in geometry.scad)
- [`circle_2tangents()`](geometry.scad#functionmodule-circle_2tangents) (in geometry.scad)
- [`circle_3points()`](geometry.scad#functionmodule-circle_3points) (in geometry.scad)
- [`circle_circle_intersection()`](geometry.scad#function-circle_circle_intersection) (in geometry.scad)
- [`circle_circle_tangents()`](geometry.scad#function-circle_circle_tangents) (in geometry.scad)
- [`circle_line_intersection()`](geometry.scad#function-circle_line_intersection) (in geometry.scad)
- [`circle_point_tangents()`](geometry.scad#function-circle_point_tangents) (in geometry.scad)
- [`clockwise_polygon()`](geometry.scad#function-clockwise_polygon) (in geometry.scad)
- [`closest_point()`](vectors.scad#function-closest_point) (in vectors.scad)
- [`convex_collision()`](geometry.scad#function-convex_collision) (in geometry.scad)
- [`convex_distance()`](geometry.scad#function-convex_distance) (in geometry.scad)
- [`furthest_point()`](vectors.scad#function-furthest_point) (in vectors.scad)
- [`hyp_adj_to_opp()`](trigonometry.scad#function-hyp_adj_to_opp) (in trigonometry.scad)
- [`hyp_ang_to_adj()`](trigonometry.scad#function-hyp_ang_to_adj) (in trigonometry.scad)
- [`hyp_ang_to_opp()`](trigonometry.scad#function-hyp_ang_to_opp) (in trigonometry.scad)
- [`hyp_opp_to_adj()`](trigonometry.scad#function-hyp_opp_to_adj) (in trigonometry.scad)
- [`hyp_opp_to_ang()`](trigonometry.scad#function-hyp_opp_to_ang) (in trigonometry.scad)
- [`is_collinear()`](geometry.scad#function-is_collinear) (in geometry.scad)
- [`is_coplanar()`](geometry.scad#function-is_coplanar) (in geometry.scad)
- [`is_point_on_line()`](geometry.scad#function-is_point_on_line) (in geometry.scad)
- [`is_polygon_clockwise()`](geometry.scad#function-is_polygon_clockwise) (in geometry.scad)
- [`is_polygon_convex()`](geometry.scad#function-is_polygon_convex) (in geometry.scad)
- [`law_of_cosines()`](trigonometry.scad#function-law_of_cosines) (in trigonometry.scad)
- [`law_of_sines()`](trigonometry.scad#function-law_of_sines) (in trigonometry.scad)
- [`line_closest_point()`](geometry.scad#function-line_closest_point) (in geometry.scad)
- [`line_from_points()`](geometry.scad#function-line_from_points) (in geometry.scad)
- [`line_normal()`](geometry.scad#function-line_normal) (in geometry.scad)
- [`opp_adj_to_ang()`](trigonometry.scad#function-adj_opp_to_ang) (in trigonometry.scad)
- [`opp_adj_to_hyp()`](trigonometry.scad#function-adj_opp_to_hyp) (in trigonometry.scad)
- [`opp_ang_to_adj()`](trigonometry.scad#function-opp_ang_to_adj) (in trigonometry.scad)
- [`opp_ang_to_hyp()`](trigonometry.scad#function-opp_ang_to_hyp) (in trigonometry.scad)
- [`opp_hyp_to_adj()`](trigonometry.scad#function-hyp_opp_to_adj) (in trigonometry.scad)
- [`opp_hyp_to_ang()`](trigonometry.scad#function-hyp_opp_to_ang) (in trigonometry.scad)
- [`plane3pt()`](geometry.scad#function-plane3pt) (in geometry.scad)
- [`plane3pt_indexed()`](geometry.scad#function-plane3pt_indexed) (in geometry.scad)
- [`plane_closest_point()`](geometry.scad#function-plane_closest_point) (in geometry.scad)
- [`plane_from_normal()`](geometry.scad#function-plane_from_normal) (in geometry.scad)
- [`plane_from_points()`](geometry.scad#function-plane_from_points) (in geometry.scad)
- [`plane_from_polygon()`](geometry.scad#function-plane_from_polygon) (in geometry.scad)
- [`plane_intersection()`](geometry.scad#function-plane_intersection) (in geometry.scad)
- [`plane_line_angle()`](geometry.scad#function-plane_line_angle) (in geometry.scad)
- [`plane_line_intersection()`](geometry.scad#function-plane_line_intersection) (in geometry.scad)
- [`plane_normal()`](geometry.scad#function-plane_normal) (in geometry.scad)
- [`plane_offset()`](geometry.scad#function-plane_offset) (in geometry.scad)
- [`point_in_polygon()`](geometry.scad#function-point_in_polygon) (in geometry.scad)
- [`point_line_distance()`](geometry.scad#function-point_line_distance) (in geometry.scad)
- [`point_plane_distance()`](geometry.scad#function-point_plane_distance) (in geometry.scad)
- [`pointlist_bounds()`](vectors.scad#function-pointlist_bounds) (in vectors.scad)
- [`polygon_area()`](geometry.scad#function-polygon_area) (in geometry.scad)
- [`polygon_line_intersection()`](geometry.scad#function-polygon_line_intersection) (in geometry.scad)
- [`polygon_normal()`](geometry.scad#function-polygon_normal) (in geometry.scad)
- [`reindex_polygon()`](geometry.scad#function-reindex_polygon) (in geometry.scad)
- [`reverse_polygon()`](geometry.scad#function-reverse_polygon) (in geometry.scad)
- [`segment_distance()`](geometry.scad#function-segment_distance) (in geometry.scad)
- [`segs()`](utility.scad#function-segs) (in utility.scad)
- [`sphere_line_intersection()`](geometry.scad#function-sphere_line_intersection) (in geometry.scad)
- [`triangle_area()`](trigonometry.scad#function-triangle_area) (in trigonometry.scad)

## H

### Hashing

- [`hashmap()`](fnliterals.scad#function-hashmap) (in fnliterals.scad)
- [`simple_hash()`](fnliterals.scad#function-simple_hash) (in fnliterals.scad)

## I

### Intersection

- [`bezier_line_intersection()`](beziers.scad#function-bezier_line_intersection) (in beziers.scad)
- [`circle_line_intersection()`](geometry.scad#function-circle_line_intersection) (in geometry.scad)
- [`convex_collision()`](geometry.scad#function-convex_collision) (in geometry.scad)
- [`plane_intersection()`](geometry.scad#function-plane_intersection) (in geometry.scad)
- [`plane_line_intersection()`](geometry.scad#function-plane_line_intersection) (in geometry.scad)
- [`polygon_line_intersection()`](geometry.scad#function-polygon_line_intersection) (in geometry.scad)
- [`sphere_line_intersection()`](geometry.scad#function-sphere_line_intersection) (in geometry.scad)

### Iteration

- [`combinations()`](lists.scad#function-combinations) (in lists.scad)
- [`for_n()`](fnliterals.scad#function-for_n) (in fnliterals.scad)
- [`idx()`](lists.scad#function-idx) (in lists.scad)
- [`loop_done()`](utility.scad#function-loop_done) (in utility.scad)
- [`loop_while()`](utility.scad#function-loop_while) (in utility.scad)
- [`looping()`](utility.scad#function-looping) (in utility.scad)
- [`pair()`](lists.scad#function-pair) (in lists.scad)
- [`permutations()`](lists.scad#function-permutations) (in lists.scad)
- [`triplet()`](lists.scad#function-triplet) (in lists.scad)
- [`while()`](fnliterals.scad#function-while) (in fnliterals.scad)

## L

### Lines

- [`circle_line_intersection()`](geometry.scad#function-circle_line_intersection) (in geometry.scad)
- [`LINE`](constants.scad#constant-line) (in constants.scad)
- [`line_closest_point()`](geometry.scad#function-line_closest_point) (in geometry.scad)
- [`line_from_points()`](geometry.scad#function-line_from_points) (in geometry.scad)
- [`line_normal()`](geometry.scad#function-line_normal) (in geometry.scad)
- [`plane_line_angle()`](geometry.scad#function-plane_line_angle) (in geometry.scad)
- [`plane_line_intersection()`](geometry.scad#function-plane_line_intersection) (in geometry.scad)
- [`point_line_distance()`](geometry.scad#function-point_line_distance) (in geometry.scad)
- [`polygon_line_intersection()`](geometry.scad#function-polygon_line_intersection) (in geometry.scad)
- [`RAY`](constants.scad#constant-ray) (in constants.scad)
- [`SEGMENT`](constants.scad#constant-segment) (in constants.scad)
- [`sphere_line_intersection()`](geometry.scad#function-sphere_line_intersection) (in geometry.scad)

### List Handling

- [`add_scalar()`](vectors.scad#function-add_scalar) (in vectors.scad)
- [`bselect()`](lists.scad#function-bselect) (in lists.scad)
- [`column()`](linalg.scad#function-column) (in linalg.scad)
- [`combinations()`](lists.scad#function-combinations) (in lists.scad)
- [`deduplicate()`](comparisons.scad#function-deduplicate) (in comparisons.scad)
- [`deduplicate_indexed()`](comparisons.scad#function-deduplicate_indexed) (in comparisons.scad)
- [`find_approx()`](comparisons.scad#function-find_approx) (in comparisons.scad)
- [`flatten()`](lists.scad#function-flatten) (in lists.scad)
- [`force_list()`](lists.scad#function-force_list) (in lists.scad)
- [`full_flatten()`](lists.scad#function-full_flatten) (in lists.scad)
- [`group_data()`](comparisons.scad#function-group_data) (in comparisons.scad)
- [`group_sort()`](comparisons.scad#function-group_sort) (in comparisons.scad)
- [`idx()`](lists.scad#function-idx) (in lists.scad)
- [`in_list()`](lists.scad#function-in_list) (in lists.scad)
- [`is_decreasing()`](comparisons.scad#function-is_decreasing) (in comparisons.scad)
- [`is_homogeneous()`](lists.scad#function-is_homogeneous) (in lists.scad)
- [`is_homogenous()`](lists.scad#function-is_homogeneous) (in lists.scad)
- [`is_increasing()`](comparisons.scad#function-is_increasing) (in comparisons.scad)
- [`last()`](lists.scad#function-last) (in lists.scad)
- [`list()`](lists.scad#function-list) (in lists.scad)
- [`list_bset()`](lists.scad#function-list_bset) (in lists.scad)
- [`list_head()`](lists.scad#function-list_head) (in lists.scad)
- [`list_insert()`](lists.scad#function-list_insert) (in lists.scad)
- [`list_pad()`](lists.scad#function-list_pad) (in lists.scad)
- [`list_remove()`](lists.scad#function-list_remove) (in lists.scad)
- [`list_remove_values()`](lists.scad#function-list_remove_values) (in lists.scad)
- [`list_rotate()`](lists.scad#function-list_rotate) (in lists.scad)
- [`list_set()`](lists.scad#function-list_set) (in lists.scad)
- [`list_shape()`](lists.scad#function-list_shape) (in lists.scad)
- [`list_tail()`](lists.scad#function-list_tail) (in lists.scad)
- [`list_to_matrix()`](lists.scad#function-list_to_matrix) (in lists.scad)
- [`max_index()`](comparisons.scad#function-max_index) (in comparisons.scad)
- [`max_length()`](lists.scad#function-max_length) (in lists.scad)
- [`min_index()`](comparisons.scad#function-min_index) (in comparisons.scad)
- [`min_length()`](lists.scad#function-min_length) (in lists.scad)
- [`pair()`](lists.scad#function-pair) (in lists.scad)
- [`permutations()`](lists.scad#function-permutations) (in lists.scad)
- [`repeat()`](lists.scad#function-repeat) (in lists.scad)
- [`repeat_entries()`](lists.scad#function-repeat_entries) (in lists.scad)
- [`reverse()`](lists.scad#function-reverse) (in lists.scad)
- [`select()`](lists.scad#function-select) (in lists.scad)
- [`set_difference()`](lists.scad#function-set_difference) (in lists.scad)
- [`set_intersection()`](lists.scad#function-set_intersection) (in lists.scad)
- [`set_union()`](lists.scad#function-set_union) (in lists.scad)
- [`shuffle()`](lists.scad#function-shuffle) (in lists.scad)
- [`sort()`](comparisons.scad#function-sort) (in comparisons.scad)
- [`sortidx()`](comparisons.scad#function-sortidx) (in comparisons.scad)
- [`triplet()`](lists.scad#function-triplet) (in lists.scad)
- [`unique()`](comparisons.scad#function-unique) (in comparisons.scad)
- [`unique_count()`](comparisons.scad#function-unique_count) (in comparisons.scad)

### Logic

- [`f_and()`](fnliterals.scad#function-f_and) (in fnliterals.scad)
- [`f_nand()`](fnliterals.scad#function-f_nand) (in fnliterals.scad)
- [`f_nor()`](fnliterals.scad#function-f_nor) (in fnliterals.scad)
- [`f_not()`](fnliterals.scad#function-f_not) (in fnliterals.scad)
- [`f_or()`](fnliterals.scad#function-f_or) (in fnliterals.scad)
- [`f_xor()`](fnliterals.scad#function-f_xor) (in fnliterals.scad)

### Looping

- [`accumulate()`](fnliterals.scad#function-accumulate) (in fnliterals.scad)
- [`filter()`](fnliterals.scad#function-filter) (in fnliterals.scad)
- [`find_all()`](fnliterals.scad#function-find_all) (in fnliterals.scad)
- [`for_n()`](fnliterals.scad#function-for_n) (in fnliterals.scad)
- [`map()`](fnliterals.scad#function-map) (in fnliterals.scad)
- [`reduce()`](fnliterals.scad#function-reduce) (in fnliterals.scad)
- [`while()`](fnliterals.scad#function-while) (in fnliterals.scad)

## M

### Masks (2D)

- [`mask2d_chamfer()`](masks2d.scad#functionmodule-mask2d_chamfer) (in masks2d.scad)
- [`mask2d_cove()`](masks2d.scad#functionmodule-mask2d_cove) (in masks2d.scad)
- [`mask2d_dovetail()`](masks2d.scad#functionmodule-mask2d_dovetail) (in masks2d.scad)
- [`mask2d_ogee()`](masks2d.scad#functionmodule-mask2d_ogee) (in masks2d.scad)
- [`mask2d_rabbet()`](masks2d.scad#functionmodule-mask2d_rabbet) (in masks2d.scad)
- [`mask2d_roundover()`](masks2d.scad#functionmodule-mask2d_roundover) (in masks2d.scad)
- [`mask2d_teardrop()`](masks2d.scad#functionmodule-mask2d_teardrop) (in masks2d.scad)

### Math Operators

- [`f_acos()`](fnliterals.scad#function-f_acos) (in fnliterals.scad)
- [`f_add()`](fnliterals.scad#function-f_add) (in fnliterals.scad)
- [`f_asin()`](fnliterals.scad#function-f_asin) (in fnliterals.scad)
- [`f_atan()`](fnliterals.scad#function-f_atan) (in fnliterals.scad)
- [`f_atan2()`](fnliterals.scad#function-f_atan2) (in fnliterals.scad)
- [`f_cos()`](fnliterals.scad#function-f_cos) (in fnliterals.scad)
- [`f_div()`](fnliterals.scad#function-f_div) (in fnliterals.scad)
- [`f_even()`](fnliterals.scad#function-f_even) (in fnliterals.scad)
- [`f_max()`](fnliterals.scad#function-f_max) (in fnliterals.scad)
- [`f_max2()`](fnliterals.scad#function-f_max2) (in fnliterals.scad)
- [`f_max3()`](fnliterals.scad#function-f_max3) (in fnliterals.scad)
- [`f_min()`](fnliterals.scad#function-f_min) (in fnliterals.scad)
- [`f_min2()`](fnliterals.scad#function-f_min2) (in fnliterals.scad)
- [`f_min3()`](fnliterals.scad#function-f_min3) (in fnliterals.scad)
- [`f_mod()`](fnliterals.scad#function-f_mod) (in fnliterals.scad)
- [`f_mul()`](fnliterals.scad#function-f_mul) (in fnliterals.scad)
- [`f_neg()`](fnliterals.scad#function-f_neg) (in fnliterals.scad)
- [`f_odd()`](fnliterals.scad#function-f_odd) (in fnliterals.scad)
- [`f_pow()`](fnliterals.scad#function-f_pow) (in fnliterals.scad)
- [`f_sin()`](fnliterals.scad#function-f_sin) (in fnliterals.scad)
- [`f_str3()`](fnliterals.scad#function-f_str3) (in fnliterals.scad)
- [`f_sub()`](fnliterals.scad#function-f_sub) (in fnliterals.scad)
- [`f_tan()`](fnliterals.scad#function-f_tan) (in fnliterals.scad)

### Matrices

- [`apply()`](transforms.scad#function-apply) (in transforms.scad)
- [`back()`](transforms.scad#functionmodule-back) (in transforms.scad)
- [`block_matrix()`](linalg.scad#function-block_matrix) (in linalg.scad)
- [`column()`](linalg.scad#function-column) (in linalg.scad)
- [`diagonal_matrix()`](linalg.scad#function-diagonal_matrix) (in linalg.scad)
- [`down()`](transforms.scad#functionmodule-down) (in transforms.scad)
- [`flatten()`](lists.scad#function-flatten) (in lists.scad)
- [`frame_map()`](transforms.scad#functionmodule-frame_map) (in transforms.scad)
- [`full_flatten()`](lists.scad#function-full_flatten) (in lists.scad)
- [`fwd()`](transforms.scad#functionmodule-fwd) (in transforms.scad)
- [`hstack()`](linalg.scad#function-hstack) (in linalg.scad)
- [`ident()`](linalg.scad#function-ident) (in linalg.scad)
- [`left()`](transforms.scad#functionmodule-left) (in transforms.scad)
- [`list_shape()`](lists.scad#function-list_shape) (in lists.scad)
- [`list_to_matrix()`](lists.scad#function-list_to_matrix) (in lists.scad)
- [`mirror()`](transforms.scad#functionmodule-mirror) (in transforms.scad)
- [`move()`](transforms.scad#functionmodule-move) (in transforms.scad)
- [`right()`](transforms.scad#functionmodule-right) (in transforms.scad)
- [`rot()`](transforms.scad#functionmodule-rot) (in transforms.scad)
- [`rot_decode()`](geometry.scad#function-rot_decode) (in geometry.scad)
- [`scale()`](transforms.scad#functionmodule-scale) (in transforms.scad)
- [`skew()`](transforms.scad#functionmodule-skew) (in transforms.scad)
- [`submatrix()`](linalg.scad#function-submatrix) (in linalg.scad)
- [`submatrix_set()`](linalg.scad#function-submatrix_set) (in linalg.scad)
- [`translate()`](transforms.scad#functionmodule-move) (in transforms.scad)
- [`transpose()`](linalg.scad#function-transpose) (in linalg.scad)
- [`up()`](transforms.scad#functionmodule-up) (in transforms.scad)
- [`xflip()`](transforms.scad#functionmodule-xflip) (in transforms.scad)
- [`xmove()`](transforms.scad#functionmodule-right) (in transforms.scad)
- [`xrot()`](transforms.scad#functionmodule-xrot) (in transforms.scad)
- [`xscale()`](transforms.scad#functionmodule-xscale) (in transforms.scad)
- [`yflip()`](transforms.scad#functionmodule-yflip) (in transforms.scad)
- [`ymove()`](transforms.scad#functionmodule-back) (in transforms.scad)
- [`yrot()`](transforms.scad#functionmodule-yrot) (in transforms.scad)
- [`yscale()`](transforms.scad#functionmodule-yscale) (in transforms.scad)
- [`zflip()`](transforms.scad#functionmodule-zflip) (in transforms.scad)
- [`zmove()`](transforms.scad#functionmodule-up) (in transforms.scad)
- [`zrot()`](transforms.scad#functionmodule-zrot) (in transforms.scad)
- [`zscale()`](transforms.scad#functionmodule-zscale) (in transforms.scad)

### Mini-Language

- [`turtle()`](drawing.scad#function-turtle) (in drawing.scad)

### Mirroring

- [`mirror()`](transforms.scad#functionmodule-mirror) (in transforms.scad)
- [`xflip()`](transforms.scad#functionmodule-xflip) (in transforms.scad)
- [`yflip()`](transforms.scad#functionmodule-yflip) (in transforms.scad)
- [`zflip()`](transforms.scad#functionmodule-zflip) (in transforms.scad)

## P

### Path Generators

- [`arc()`](drawing.scad#functionmodule-arc) (in drawing.scad)
- [`egg()`](shapes2d.scad#functionmodule-egg) (in shapes2d.scad)
- [`ellipse()`](shapes2d.scad#functionmodule-ellipse) (in shapes2d.scad)
- [`glued_circles()`](shapes2d.scad#functionmodule-glued_circles) (in shapes2d.scad)
- [`hexagon()`](shapes2d.scad#functionmodule-hexagon) (in shapes2d.scad)
- [`mask2d_chamfer()`](masks2d.scad#functionmodule-mask2d_chamfer) (in masks2d.scad)
- [`mask2d_cove()`](masks2d.scad#functionmodule-mask2d_cove) (in masks2d.scad)
- [`mask2d_dovetail()`](masks2d.scad#functionmodule-mask2d_dovetail) (in masks2d.scad)
- [`mask2d_ogee()`](masks2d.scad#functionmodule-mask2d_ogee) (in masks2d.scad)
- [`mask2d_rabbet()`](masks2d.scad#functionmodule-mask2d_rabbet) (in masks2d.scad)
- [`mask2d_roundover()`](masks2d.scad#functionmodule-mask2d_roundover) (in masks2d.scad)
- [`mask2d_teardrop()`](masks2d.scad#functionmodule-mask2d_teardrop) (in masks2d.scad)
- [`octagon()`](shapes2d.scad#functionmodule-octagon) (in shapes2d.scad)
- [`pentagon()`](shapes2d.scad#functionmodule-pentagon) (in shapes2d.scad)
- [`rect()`](shapes2d.scad#functionmodule-rect) (in shapes2d.scad)
- [`regular_ngon()`](shapes2d.scad#functionmodule-regular_ngon) (in shapes2d.scad)
- [`reuleaux_polygon()`](shapes2d.scad#functionmodule-reuleaux_polygon) (in shapes2d.scad)
- [`star()`](shapes2d.scad#functionmodule-star) (in shapes2d.scad)
- [`supershape()`](shapes2d.scad#functionmodule-supershape) (in shapes2d.scad)
- [`teardrop2d()`](shapes2d.scad#functionmodule-teardrop2d) (in shapes2d.scad)
- [`trapezoid()`](shapes2d.scad#functionmodule-trapezoid) (in shapes2d.scad)

### Path Generators (2D)

- [`circle()`](shapes2d.scad#functionmodule-circle) (in shapes2d.scad)
- [`square()`](shapes2d.scad#functionmodule-square) (in shapes2d.scad)
- [`turtle()`](drawing.scad#function-turtle) (in drawing.scad)

### Path Subdivision

- [`slice_profiles()`](skin.scad#function-slice_profiles) (in skin.scad)
- [`subdivide_and_slice()`](skin.scad#function-subdivide_and_slice) (in skin.scad)
- [`subdivide_long_segments()`](paths.scad#function-subdivide_long_segments) (in paths.scad)

### Paths

- [`altaz_to_xyz()`](coords.scad#function-altaz_to_xyz) (in coords.scad)
- [`cylindrical_to_xyz()`](coords.scad#function-cylindrical_to_xyz) (in coords.scad)
- [`dashed_stroke()`](drawing.scad#functionmodule-dashed_stroke) (in drawing.scad)
- [`lift_plane()`](coords.scad#function-lift_plane) (in coords.scad)
- [`path2d()`](coords.scad#function-path2d) (in coords.scad)
- [`path3d()`](coords.scad#function-path3d) (in coords.scad)
- [`path4d()`](coords.scad#function-path4d) (in coords.scad)
- [`path_cut()`](paths.scad#function-path_cut) (in paths.scad)
- [`polar_to_xy()`](coords.scad#function-polar_to_xy) (in coords.scad)
- [`project_plane()`](coords.scad#function-project_plane) (in coords.scad)
- [`slice_profiles()`](skin.scad#function-slice_profiles) (in skin.scad)
- [`spherical_to_xyz()`](coords.scad#function-spherical_to_xyz) (in coords.scad)
- [`subdivide_and_slice()`](skin.scad#function-subdivide_and_slice) (in skin.scad)
- [`subdivide_long_segments()`](paths.scad#function-subdivide_long_segments) (in paths.scad)
- [`xy_to_polar()`](coords.scad#function-xy_to_polar) (in coords.scad)
- [`xyz_to_altaz()`](coords.scad#function-xyz_to_altaz) (in coords.scad)
- [`xyz_to_cylindrical()`](coords.scad#function-xyz_to_cylindrical) (in coords.scad)
- [`xyz_to_spherical()`](coords.scad#function-xyz_to_spherical) (in coords.scad)

### Paths (2D)

- [`arc()`](drawing.scad#functionmodule-arc) (in drawing.scad)
- [`egg()`](shapes2d.scad#functionmodule-egg) (in shapes2d.scad)
- [`ellipse()`](shapes2d.scad#functionmodule-ellipse) (in shapes2d.scad)
- [`glued_circles()`](shapes2d.scad#functionmodule-glued_circles) (in shapes2d.scad)
- [`hexagon()`](shapes2d.scad#functionmodule-hexagon) (in shapes2d.scad)
- [`mask2d_chamfer()`](masks2d.scad#functionmodule-mask2d_chamfer) (in masks2d.scad)
- [`mask2d_cove()`](masks2d.scad#functionmodule-mask2d_cove) (in masks2d.scad)
- [`mask2d_dovetail()`](masks2d.scad#functionmodule-mask2d_dovetail) (in masks2d.scad)
- [`mask2d_ogee()`](masks2d.scad#functionmodule-mask2d_ogee) (in masks2d.scad)
- [`mask2d_rabbet()`](masks2d.scad#functionmodule-mask2d_rabbet) (in masks2d.scad)
- [`mask2d_roundover()`](masks2d.scad#functionmodule-mask2d_roundover) (in masks2d.scad)
- [`mask2d_teardrop()`](masks2d.scad#functionmodule-mask2d_teardrop) (in masks2d.scad)
- [`octagon()`](shapes2d.scad#functionmodule-octagon) (in shapes2d.scad)
- [`pentagon()`](shapes2d.scad#functionmodule-pentagon) (in shapes2d.scad)
- [`rect()`](shapes2d.scad#functionmodule-rect) (in shapes2d.scad)
- [`regular_ngon()`](shapes2d.scad#functionmodule-regular_ngon) (in shapes2d.scad)
- [`reuleaux_polygon()`](shapes2d.scad#functionmodule-reuleaux_polygon) (in shapes2d.scad)
- [`star()`](shapes2d.scad#functionmodule-star) (in shapes2d.scad)
- [`stroke()`](drawing.scad#module-stroke) (in drawing.scad)
- [`supershape()`](shapes2d.scad#functionmodule-supershape) (in shapes2d.scad)
- [`teardrop2d()`](shapes2d.scad#functionmodule-teardrop2d) (in shapes2d.scad)
- [`trapezoid()`](shapes2d.scad#functionmodule-trapezoid) (in shapes2d.scad)

### Paths (3D)

- [`arc()`](drawing.scad#functionmodule-arc) (in drawing.scad)
- [`stroke()`](drawing.scad#module-stroke) (in drawing.scad)

### Planes

- [`are_points_on_plane()`](geometry.scad#function-are_points_on_plane) (in geometry.scad)
- [`plane3pt()`](geometry.scad#function-plane3pt) (in geometry.scad)
- [`plane3pt_indexed()`](geometry.scad#function-plane3pt_indexed) (in geometry.scad)
- [`plane_closest_point()`](geometry.scad#function-plane_closest_point) (in geometry.scad)
- [`plane_from_normal()`](geometry.scad#function-plane_from_normal) (in geometry.scad)
- [`plane_from_points()`](geometry.scad#function-plane_from_points) (in geometry.scad)
- [`plane_from_polygon()`](geometry.scad#function-plane_from_polygon) (in geometry.scad)
- [`plane_intersection()`](geometry.scad#function-plane_intersection) (in geometry.scad)
- [`plane_line_angle()`](geometry.scad#function-plane_line_angle) (in geometry.scad)
- [`plane_line_intersection()`](geometry.scad#function-plane_line_intersection) (in geometry.scad)
- [`plane_normal()`](geometry.scad#function-plane_normal) (in geometry.scad)
- [`plane_offset()`](geometry.scad#function-plane_offset) (in geometry.scad)
- [`point_plane_distance()`](geometry.scad#function-point_plane_distance) (in geometry.scad)

### Points

- [`altaz_to_xyz()`](coords.scad#function-altaz_to_xyz) (in coords.scad)
- [`are_points_on_plane()`](geometry.scad#function-are_points_on_plane) (in geometry.scad)
- [`closest_point()`](vectors.scad#function-closest_point) (in vectors.scad)
- [`cylindrical_to_xyz()`](coords.scad#function-cylindrical_to_xyz) (in coords.scad)
- [`furthest_point()`](vectors.scad#function-furthest_point) (in vectors.scad)
- [`is_collinear()`](geometry.scad#function-is_collinear) (in geometry.scad)
- [`is_point_on_line()`](geometry.scad#function-is_point_on_line) (in geometry.scad)
- [`lift_plane()`](coords.scad#function-lift_plane) (in coords.scad)
- [`line_from_points()`](geometry.scad#function-line_from_points) (in geometry.scad)
- [`path2d()`](coords.scad#function-path2d) (in coords.scad)
- [`path3d()`](coords.scad#function-path3d) (in coords.scad)
- [`path4d()`](coords.scad#function-path4d) (in coords.scad)
- [`plane_from_points()`](geometry.scad#function-plane_from_points) (in geometry.scad)
- [`point2d()`](coords.scad#function-point2d) (in coords.scad)
- [`point3d()`](coords.scad#function-point3d) (in coords.scad)
- [`point4d()`](coords.scad#function-point4d) (in coords.scad)
- [`point_line_distance()`](geometry.scad#function-point_line_distance) (in geometry.scad)
- [`polar_to_xy()`](coords.scad#function-polar_to_xy) (in coords.scad)
- [`project_plane()`](coords.scad#function-project_plane) (in coords.scad)
- [`random_points()`](math.scad#function-random_points) (in math.scad)
- [`spherical_random_points()`](math.scad#function-spherical_random_points) (in math.scad)
- [`spherical_to_xyz()`](coords.scad#function-spherical_to_xyz) (in coords.scad)
- [`vector_search()`](vectors.scad#function-vector_search) (in vectors.scad)
- [`vector_search_tree()`](vectors.scad#function-vector_search_tree) (in vectors.scad)
- [`xy_to_polar()`](coords.scad#function-xy_to_polar) (in coords.scad)
- [`xyz_to_altaz()`](coords.scad#function-xyz_to_altaz) (in coords.scad)
- [`xyz_to_cylindrical()`](coords.scad#function-xyz_to_cylindrical) (in coords.scad)
- [`xyz_to_spherical()`](coords.scad#function-xyz_to_spherical) (in coords.scad)

### Polygon

- [`random_polygon()`](math.scad#function-random_polygon) (in math.scad)

### Polygons

- [`align_polygon()`](geometry.scad#function-align_polygon) (in geometry.scad)
- [`ccw_polygon()`](geometry.scad#function-ccw_polygon) (in geometry.scad)
- [`centroid()`](geometry.scad#function-centroid) (in geometry.scad)
- [`clockwise_polygon()`](geometry.scad#function-clockwise_polygon) (in geometry.scad)
- [`is_polygon_clockwise()`](geometry.scad#function-is_polygon_clockwise) (in geometry.scad)
- [`plane_from_polygon()`](geometry.scad#function-plane_from_polygon) (in geometry.scad)
- [`point_in_polygon()`](geometry.scad#function-point_in_polygon) (in geometry.scad)
- [`polygon_area()`](geometry.scad#function-polygon_area) (in geometry.scad)
- [`polygon_line_intersection()`](geometry.scad#function-polygon_line_intersection) (in geometry.scad)
- [`polygon_normal()`](geometry.scad#function-polygon_normal) (in geometry.scad)
- [`reindex_polygon()`](geometry.scad#function-reindex_polygon) (in geometry.scad)
- [`reverse_polygon()`](geometry.scad#function-reverse_polygon) (in geometry.scad)

### Polyhedra

- [`debug_vnf()`](vnf.scad#module-debug_vnf) (in vnf.scad)

### Projection

- [`plane_closest_point()`](geometry.scad#function-plane_closest_point) (in geometry.scad)

## R

### Random

- [`random_points()`](math.scad#function-random_points) (in math.scad)
- [`random_polygon()`](math.scad#function-random_polygon) (in math.scad)
- [`spherical_random_points()`](math.scad#function-spherical_random_points) (in math.scad)

### Reflection

- [`mirror()`](transforms.scad#functionmodule-mirror) (in transforms.scad)
- [`xflip()`](transforms.scad#functionmodule-xflip) (in transforms.scad)
- [`yflip()`](transforms.scad#functionmodule-yflip) (in transforms.scad)
- [`zflip()`](transforms.scad#functionmodule-zflip) (in transforms.scad)

### Rotation

- [`frame_map()`](transforms.scad#functionmodule-frame_map) (in transforms.scad)
- [`rot()`](transforms.scad#functionmodule-rot) (in transforms.scad)
- [`xrot()`](transforms.scad#functionmodule-xrot) (in transforms.scad)
- [`yrot()`](transforms.scad#functionmodule-yrot) (in transforms.scad)
- [`zrot()`](transforms.scad#functionmodule-zrot) (in transforms.scad)

### Rounding

- [`path_to_bezpath()`](beziers.scad#function-path_to_bezpath) (in beziers.scad)

## S

### Scaling

- [`scale()`](transforms.scad#functionmodule-scale) (in transforms.scad)
- [`xscale()`](transforms.scad#functionmodule-xscale) (in transforms.scad)
- [`yscale()`](transforms.scad#functionmodule-yscale) (in transforms.scad)
- [`zscale()`](transforms.scad#functionmodule-zscale) (in transforms.scad)

### Search

- [`vector_search()`](vectors.scad#function-vector_search) (in vectors.scad)
- [`vector_search_tree()`](vectors.scad#function-vector_search_tree) (in vectors.scad)

### Searching

- [`binsearch()`](fnliterals.scad#function-binsearch) (in fnliterals.scad)
- [`find_first()`](fnliterals.scad#function-find_first) (in fnliterals.scad)

### Segments

- [`is_point_on_line()`](geometry.scad#function-is_point_on_line) (in geometry.scad)
- [`segment_distance()`](geometry.scad#function-segment_distance) (in geometry.scad)

### Set Handling

- [`set_difference()`](lists.scad#function-set_difference) (in lists.scad)
- [`set_intersection()`](lists.scad#function-set_intersection) (in lists.scad)
- [`set_union()`](lists.scad#function-set_union) (in lists.scad)

### Shapes (2D)

- [`arc()`](drawing.scad#functionmodule-arc) (in drawing.scad)
- [`circle()`](shapes2d.scad#functionmodule-circle) (in shapes2d.scad)
- [`egg()`](shapes2d.scad#functionmodule-egg) (in shapes2d.scad)
- [`ellipse()`](shapes2d.scad#functionmodule-ellipse) (in shapes2d.scad)
- [`glued_circles()`](shapes2d.scad#functionmodule-glued_circles) (in shapes2d.scad)
- [`hexagon()`](shapes2d.scad#functionmodule-hexagon) (in shapes2d.scad)
- [`mask2d_chamfer()`](masks2d.scad#functionmodule-mask2d_chamfer) (in masks2d.scad)
- [`mask2d_cove()`](masks2d.scad#functionmodule-mask2d_cove) (in masks2d.scad)
- [`mask2d_dovetail()`](masks2d.scad#functionmodule-mask2d_dovetail) (in masks2d.scad)
- [`mask2d_ogee()`](masks2d.scad#functionmodule-mask2d_ogee) (in masks2d.scad)
- [`mask2d_rabbet()`](masks2d.scad#functionmodule-mask2d_rabbet) (in masks2d.scad)
- [`mask2d_roundover()`](masks2d.scad#functionmodule-mask2d_roundover) (in masks2d.scad)
- [`mask2d_teardrop()`](masks2d.scad#functionmodule-mask2d_teardrop) (in masks2d.scad)
- [`octagon()`](shapes2d.scad#functionmodule-octagon) (in shapes2d.scad)
- [`pentagon()`](shapes2d.scad#functionmodule-pentagon) (in shapes2d.scad)
- [`rect()`](shapes2d.scad#functionmodule-rect) (in shapes2d.scad)
- [`regular_ngon()`](shapes2d.scad#functionmodule-regular_ngon) (in shapes2d.scad)
- [`reuleaux_polygon()`](shapes2d.scad#functionmodule-reuleaux_polygon) (in shapes2d.scad)
- [`square()`](shapes2d.scad#functionmodule-square) (in shapes2d.scad)
- [`star()`](shapes2d.scad#functionmodule-star) (in shapes2d.scad)
- [`supershape()`](shapes2d.scad#functionmodule-supershape) (in shapes2d.scad)
- [`teardrop2d()`](shapes2d.scad#functionmodule-teardrop2d) (in shapes2d.scad)
- [`trapezoid()`](shapes2d.scad#functionmodule-trapezoid) (in shapes2d.scad)
- [`turtle()`](drawing.scad#function-turtle) (in drawing.scad)

### Shapes (3D)

- [`cube()`](shapes3d.scad#functionmodule-cube) (in shapes3d.scad)
- [`cylinder()`](shapes3d.scad#functionmodule-cylinder) (in shapes3d.scad)
- [`sphere()`](shapes3d.scad#functionmodule-sphere) (in shapes3d.scad)

### Skewing

- [`skew()`](transforms.scad#functionmodule-skew) (in transforms.scad)

### Spheres

- [`sphere_line_intersection()`](geometry.scad#function-sphere_line_intersection) (in geometry.scad)

### String Operators

- [`f_abs()`](fnliterals.scad#function-f_abs) (in fnliterals.scad)
- [`f_ceil()`](fnliterals.scad#function-f_ceil) (in fnliterals.scad)
- [`f_chr()`](fnliterals.scad#function-f_chr) (in fnliterals.scad)
- [`f_cross()`](fnliterals.scad#function-f_cross) (in fnliterals.scad)
- [`f_exp()`](fnliterals.scad#function-f_exp) (in fnliterals.scad)
- [`f_floor()`](fnliterals.scad#function-f_floor) (in fnliterals.scad)
- [`f_len()`](fnliterals.scad#function-f_len) (in fnliterals.scad)
- [`f_ln()`](fnliterals.scad#function-f_ln) (in fnliterals.scad)
- [`f_log()`](fnliterals.scad#function-f_log) (in fnliterals.scad)
- [`f_norm()`](fnliterals.scad#function-f_norm) (in fnliterals.scad)
- [`f_ord()`](fnliterals.scad#function-f_ord) (in fnliterals.scad)
- [`f_round()`](fnliterals.scad#function-f_round) (in fnliterals.scad)
- [`f_sign()`](fnliterals.scad#function-f_sign) (in fnliterals.scad)
- [`f_sqr()`](fnliterals.scad#function-f_sqr) (in fnliterals.scad)
- [`f_sqrt()`](fnliterals.scad#function-f_sqrt) (in fnliterals.scad)
- [`f_str()`](fnliterals.scad#function-f_str) (in fnliterals.scad)
- [`f_str2()`](fnliterals.scad#function-f_str2) (in fnliterals.scad)

## T

### Tangents

- [`circle_2tangents()`](geometry.scad#functionmodule-circle_2tangents) (in geometry.scad)
- [`circle_circle_tangents()`](geometry.scad#function-circle_circle_tangents) (in geometry.scad)
- [`circle_point_tangents()`](geometry.scad#function-circle_point_tangents) (in geometry.scad)

### Test

- [`is_polygon_convex()`](geometry.scad#function-is_polygon_convex) (in geometry.scad)

### Testing

- [`shape_compare()`](utility.scad#module-shape_compare) (in utility.scad)

### Text

- [`text()`](shapes2d.scad#module-text) (in shapes2d.scad)
- [`text3d()`](shapes3d.scad#module-text3d) (in shapes3d.scad)

### Transforms

- [`apply()`](transforms.scad#function-apply) (in transforms.scad)
- [`back()`](transforms.scad#functionmodule-back) (in transforms.scad)
- [`down()`](transforms.scad#functionmodule-down) (in transforms.scad)
- [`frame_map()`](transforms.scad#functionmodule-frame_map) (in transforms.scad)
- [`fwd()`](transforms.scad#functionmodule-fwd) (in transforms.scad)
- [`left()`](transforms.scad#functionmodule-left) (in transforms.scad)
- [`mirror()`](transforms.scad#functionmodule-mirror) (in transforms.scad)
- [`move()`](transforms.scad#functionmodule-move) (in transforms.scad)
- [`right()`](transforms.scad#functionmodule-right) (in transforms.scad)
- [`rot()`](transforms.scad#functionmodule-rot) (in transforms.scad)
- [`rot_decode()`](geometry.scad#function-rot_decode) (in geometry.scad)
- [`scale()`](transforms.scad#functionmodule-scale) (in transforms.scad)
- [`skew()`](transforms.scad#functionmodule-skew) (in transforms.scad)
- [`translate()`](transforms.scad#functionmodule-move) (in transforms.scad)
- [`up()`](transforms.scad#functionmodule-up) (in transforms.scad)
- [`xflip()`](transforms.scad#functionmodule-xflip) (in transforms.scad)
- [`xmove()`](transforms.scad#functionmodule-right) (in transforms.scad)
- [`xrot()`](transforms.scad#functionmodule-xrot) (in transforms.scad)
- [`xscale()`](transforms.scad#functionmodule-xscale) (in transforms.scad)
- [`yflip()`](transforms.scad#functionmodule-yflip) (in transforms.scad)
- [`ymove()`](transforms.scad#functionmodule-back) (in transforms.scad)
- [`yrot()`](transforms.scad#functionmodule-yrot) (in transforms.scad)
- [`yscale()`](transforms.scad#functionmodule-yscale) (in transforms.scad)
- [`zflip()`](transforms.scad#functionmodule-zflip) (in transforms.scad)
- [`zmove()`](transforms.scad#functionmodule-up) (in transforms.scad)
- [`zrot()`](transforms.scad#functionmodule-zrot) (in transforms.scad)
- [`zscale()`](transforms.scad#functionmodule-zscale) (in transforms.scad)

### Translation

- [`back()`](transforms.scad#functionmodule-back) (in transforms.scad)
- [`down()`](transforms.scad#functionmodule-down) (in transforms.scad)
- [`fwd()`](transforms.scad#functionmodule-fwd) (in transforms.scad)
- [`left()`](transforms.scad#functionmodule-left) (in transforms.scad)
- [`move()`](transforms.scad#functionmodule-move) (in transforms.scad)
- [`right()`](transforms.scad#functionmodule-right) (in transforms.scad)
- [`translate()`](transforms.scad#functionmodule-move) (in transforms.scad)
- [`up()`](transforms.scad#functionmodule-up) (in transforms.scad)
- [`xmove()`](transforms.scad#functionmodule-right) (in transforms.scad)
- [`ymove()`](transforms.scad#functionmodule-back) (in transforms.scad)
- [`zmove()`](transforms.scad#functionmodule-up) (in transforms.scad)

### Triangles

- [`adj_ang_to_hyp()`](trigonometry.scad#function-adj_ang_to_hyp) (in trigonometry.scad)
- [`adj_ang_to_opp()`](trigonometry.scad#function-adj_ang_to_opp) (in trigonometry.scad)
- [`adj_hyp_to_opp()`](trigonometry.scad#function-hyp_adj_to_opp) (in trigonometry.scad)
- [`adj_opp_to_ang()`](trigonometry.scad#function-adj_opp_to_ang) (in trigonometry.scad)
- [`adj_opp_to_hyp()`](trigonometry.scad#function-adj_opp_to_hyp) (in trigonometry.scad)
- [`ang_adj_to_hyp()`](trigonometry.scad#function-adj_ang_to_hyp) (in trigonometry.scad)
- [`ang_adj_to_opp()`](trigonometry.scad#function-adj_ang_to_opp) (in trigonometry.scad)
- [`ang_hyp_to_adj()`](trigonometry.scad#function-hyp_ang_to_adj) (in trigonometry.scad)
- [`ang_hyp_to_opp()`](trigonometry.scad#function-hyp_ang_to_opp) (in trigonometry.scad)
- [`ang_opp_to_adj()`](trigonometry.scad#function-opp_ang_to_adj) (in trigonometry.scad)
- [`ang_opp_to_hyp()`](trigonometry.scad#function-opp_ang_to_hyp) (in trigonometry.scad)
- [`hyp_adj_to_opp()`](trigonometry.scad#function-hyp_adj_to_opp) (in trigonometry.scad)
- [`hyp_ang_to_adj()`](trigonometry.scad#function-hyp_ang_to_adj) (in trigonometry.scad)
- [`hyp_ang_to_opp()`](trigonometry.scad#function-hyp_ang_to_opp) (in trigonometry.scad)
- [`hyp_opp_to_adj()`](trigonometry.scad#function-hyp_opp_to_adj) (in trigonometry.scad)
- [`hyp_opp_to_ang()`](trigonometry.scad#function-hyp_opp_to_ang) (in trigonometry.scad)
- [`law_of_cosines()`](trigonometry.scad#function-law_of_cosines) (in trigonometry.scad)
- [`law_of_sines()`](trigonometry.scad#function-law_of_sines) (in trigonometry.scad)
- [`opp_adj_to_ang()`](trigonometry.scad#function-adj_opp_to_ang) (in trigonometry.scad)
- [`opp_adj_to_hyp()`](trigonometry.scad#function-adj_opp_to_hyp) (in trigonometry.scad)
- [`opp_ang_to_adj()`](trigonometry.scad#function-opp_ang_to_adj) (in trigonometry.scad)
- [`opp_ang_to_hyp()`](trigonometry.scad#function-opp_ang_to_hyp) (in trigonometry.scad)
- [`opp_hyp_to_adj()`](trigonometry.scad#function-hyp_opp_to_adj) (in trigonometry.scad)
- [`opp_hyp_to_ang()`](trigonometry.scad#function-hyp_opp_to_ang) (in trigonometry.scad)
- [`triangle_area()`](trigonometry.scad#function-triangle_area) (in trigonometry.scad)

### Trigonometry

- [`adj_ang_to_hyp()`](trigonometry.scad#function-adj_ang_to_hyp) (in trigonometry.scad)
- [`adj_ang_to_opp()`](trigonometry.scad#function-adj_ang_to_opp) (in trigonometry.scad)
- [`adj_hyp_to_opp()`](trigonometry.scad#function-hyp_adj_to_opp) (in trigonometry.scad)
- [`adj_opp_to_ang()`](trigonometry.scad#function-adj_opp_to_ang) (in trigonometry.scad)
- [`adj_opp_to_hyp()`](trigonometry.scad#function-adj_opp_to_hyp) (in trigonometry.scad)
- [`ang_adj_to_hyp()`](trigonometry.scad#function-adj_ang_to_hyp) (in trigonometry.scad)
- [`ang_adj_to_opp()`](trigonometry.scad#function-adj_ang_to_opp) (in trigonometry.scad)
- [`ang_hyp_to_adj()`](trigonometry.scad#function-hyp_ang_to_adj) (in trigonometry.scad)
- [`ang_hyp_to_opp()`](trigonometry.scad#function-hyp_ang_to_opp) (in trigonometry.scad)
- [`ang_opp_to_adj()`](trigonometry.scad#function-opp_ang_to_adj) (in trigonometry.scad)
- [`ang_opp_to_hyp()`](trigonometry.scad#function-opp_ang_to_hyp) (in trigonometry.scad)
- [`hyp_adj_to_opp()`](trigonometry.scad#function-hyp_adj_to_opp) (in trigonometry.scad)
- [`hyp_ang_to_adj()`](trigonometry.scad#function-hyp_ang_to_adj) (in trigonometry.scad)
- [`hyp_ang_to_opp()`](trigonometry.scad#function-hyp_ang_to_opp) (in trigonometry.scad)
- [`hyp_opp_to_adj()`](trigonometry.scad#function-hyp_opp_to_adj) (in trigonometry.scad)
- [`hyp_opp_to_ang()`](trigonometry.scad#function-hyp_opp_to_ang) (in trigonometry.scad)
- [`law_of_cosines()`](trigonometry.scad#function-law_of_cosines) (in trigonometry.scad)
- [`law_of_sines()`](trigonometry.scad#function-law_of_sines) (in trigonometry.scad)
- [`opp_adj_to_ang()`](trigonometry.scad#function-adj_opp_to_ang) (in trigonometry.scad)
- [`opp_adj_to_hyp()`](trigonometry.scad#function-adj_opp_to_hyp) (in trigonometry.scad)
- [`opp_ang_to_adj()`](trigonometry.scad#function-opp_ang_to_adj) (in trigonometry.scad)
- [`opp_ang_to_hyp()`](trigonometry.scad#function-opp_ang_to_hyp) (in trigonometry.scad)
- [`opp_hyp_to_adj()`](trigonometry.scad#function-hyp_opp_to_adj) (in trigonometry.scad)
- [`opp_hyp_to_ang()`](trigonometry.scad#function-hyp_opp_to_ang) (in trigonometry.scad)
- [`triangle_area()`](trigonometry.scad#function-triangle_area) (in trigonometry.scad)

### Trusses

- [`cubetruss()`](cubetruss.scad#module-cubetruss) (in cubetruss.scad)
- [`cubetruss_clip()`](cubetruss.scad#module-cubetruss_clip) (in cubetruss.scad)
- [`cubetruss_corner()`](cubetruss.scad#module-cubetruss_corner) (in cubetruss.scad)
- [`cubetruss_dist()`](cubetruss.scad#function-cubetruss_dist) (in cubetruss.scad)
- [`cubetruss_foot()`](cubetruss.scad#module-cubetruss_foot) (in cubetruss.scad)
- [`cubetruss_joiner()`](cubetruss.scad#module-cubetruss_joiner) (in cubetruss.scad)
- [`cubetruss_segment()`](cubetruss.scad#module-cubetruss_segment) (in cubetruss.scad)
- [`cubetruss_support()`](cubetruss.scad#module-cubetruss_support) (in cubetruss.scad)
- [`cubetruss_uclip()`](cubetruss.scad#module-cubetruss_uclip) (in cubetruss.scad)

### Type Checking

- [`is_bezier_patch()`](beziers.scad#function-is_bezier_patch) (in beziers.scad)
- [`is_bool_list()`](utility.scad#function-is_bool_list) (in utility.scad)
- [`is_consistent()`](utility.scad#function-is_consistent) (in utility.scad)
- [`is_def()`](utility.scad#function-is_def) (in utility.scad)
- [`is_finite()`](utility.scad#function-is_finite) (in utility.scad)
- [`is_homogeneous()`](lists.scad#function-is_homogeneous) (in lists.scad)
- [`is_homogenous()`](lists.scad#function-is_homogeneous) (in lists.scad)
- [`is_int()`](utility.scad#function-is_int) (in utility.scad)
- [`is_integer()`](utility.scad#function-is_int) (in utility.scad)
- [`is_nan()`](utility.scad#function-is_nan) (in utility.scad)
- [`is_range()`](utility.scad#function-is_range) (in utility.scad)
- [`is_str()`](utility.scad#function-is_str) (in utility.scad)
- [`is_type()`](utility.scad#function-is_type) (in utility.scad)
- [`same_shape()`](utility.scad#function-same_shape) (in utility.scad)
- [`typeof()`](utility.scad#function-typeof) (in utility.scad)
- [`valid_range()`](utility.scad#function-valid_range) (in utility.scad)

### Type Conversion

- [`list()`](lists.scad#function-list) (in lists.scad)

### Type Queries

- [`f_is_bool()`](fnliterals.scad#function-f_is_bool) (in fnliterals.scad)
- [`f_is_def()`](fnliterals.scad#function-f_is_def) (in fnliterals.scad)
- [`f_is_finite()`](fnliterals.scad#function-f_is_finite) (in fnliterals.scad)
- [`f_is_function()`](fnliterals.scad#function-f_is_function) (in fnliterals.scad)
- [`f_is_int()`](fnliterals.scad#function-f_is_int) (in fnliterals.scad)
- [`f_is_list()`](fnliterals.scad#function-f_is_list) (in fnliterals.scad)
- [`f_is_nan()`](fnliterals.scad#function-f_is_nan) (in fnliterals.scad)
- [`f_is_num()`](fnliterals.scad#function-f_is_num) (in fnliterals.scad)
- [`f_is_patch()`](fnliterals.scad#function-f_is_patch) (in fnliterals.scad)
- [`f_is_path()`](fnliterals.scad#function-f_is_path) (in fnliterals.scad)
- [`f_is_range()`](fnliterals.scad#function-f_is_range) (in fnliterals.scad)
- [`f_is_region()`](fnliterals.scad#function-f_is_region) (in fnliterals.scad)
- [`f_is_string()`](fnliterals.scad#function-f_is_string) (in fnliterals.scad)
- [`f_is_undef()`](fnliterals.scad#function-f_is_undef) (in fnliterals.scad)
- [`f_is_vector()`](fnliterals.scad#function-f_is_vector) (in fnliterals.scad)
- [`f_is_vnf()`](fnliterals.scad#function-f_is_vnf) (in fnliterals.scad)

## U

### Undef Handling

- [`any_defined()`](utility.scad#function-any_defined) (in utility.scad)
- [`default()`](utility.scad#function-default) (in utility.scad)
- [`first_defined()`](utility.scad#function-first_defined) (in utility.scad)
- [`num_defined()`](utility.scad#function-num_defined) (in utility.scad)
- [`one_defined()`](utility.scad#function-one_defined) (in utility.scad)

## V

### VNF Generators

- [`cube()`](shapes3d.scad#functionmodule-cube) (in shapes3d.scad)
- [`cylinder()`](shapes3d.scad#functionmodule-cylinder) (in shapes3d.scad)
- [`sphere()`](shapes3d.scad#functionmodule-sphere) (in shapes3d.scad)

### Vectors

- [`BACK`](constants.scad#constant-back) (in constants.scad)
- [`BOT`](constants.scad#constant-bottom) (in constants.scad)
- [`BOTTOM`](constants.scad#constant-bottom) (in constants.scad)
- [`CENTER`](constants.scad#constant-center) (in constants.scad)
- [`CENTRE`](constants.scad#constant-center) (in constants.scad)
- [`CTR`](constants.scad#constant-center) (in constants.scad)
- [`DOWN`](constants.scad#constant-bottom) (in constants.scad)
- [`FORWARD`](constants.scad#constant-front) (in constants.scad)
- [`FRONT`](constants.scad#constant-front) (in constants.scad)
- [`FWD`](constants.scad#constant-front) (in constants.scad)
- [`LEFT`](constants.scad#constant-left) (in constants.scad)
- [`RIGHT`](constants.scad#constant-right) (in constants.scad)
- [`TOP`](constants.scad#constant-top) (in constants.scad)
- [`UP`](constants.scad#constant-top) (in constants.scad)

