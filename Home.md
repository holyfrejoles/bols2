![BOSL2 Logo](https://raw.githubusercontent.com/revarbat/BOSL2/master/images/BOSL2logo.png)

# Belfry OpenScad Library v2

- [Index by File (Table of Contents)](TOC)
- [Index by Function/Module Name](Index)
- [Index by Topic](Topics)
- [Usage Cheat Sheet](CheatSheet)
- [List of Tutorials](Tutorials)

## Terminology

For purposes of these library files, the following terms apply:

- **Left**: Towards X–
- **Right**: Towards X+
- **Front**/**Forward**: Towards Y–
- **Back**/**Behind**: Towards Y+
- **Bottom**/**Down**/**Below**: Towards Z–
- **Top**/**Up**/**Above**: Towards Z+

- **Vector**: A list of finite numbers.
- **Coordinate** / **Vertex:** A 2 or 3 element vector representing a point in 2D or 3D space.
- **Path:** A list of connected coordinates, either all 2D or all 3D.
- **Polygon:** A closed Path whose last segment is between the last point and the first point.
- **Region:** A list of non-crossing 2D polygons which describes a set of perimeters with possible holes.
- **VNF:** A 2-item list of Vertices 'N' Faces, which provides an easier way to construct a `polyhedron()` in parts.

## Installation

1. Download the .zip or .tar.gz release file for this library.
2. Unpack it. Make sure that you unpack the whole file structure. Some zipfile unpackers call this option "Use folder names". It should create either a `BOSL-v2.0` or `BOSL2-master` directory with the library files within it.  You should see "examples", "scripts", "tests", and other subdirectories.
3. Rename the unpacked main directory to `BOSL2`.
4. Move the `BOSL2` directory into the apropriate OpenSCAD library directory for your platform:
    - Windows: `My Documents\OpenSCAD\libraries\`
    - Linux: `$HOME/.local/share/OpenSCAD/libraries/`
    - Mac OS X: `$HOME/Documents/OpenSCAD/libraries/`
5. Restart OpenSCAD.

