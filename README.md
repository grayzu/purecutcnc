# PureCutCNC

`PureCutCNC` is a browser-based 2.5D CAD / CAM workspace for designing parts, defining machining operations, previewing toolpaths, and checking the result in 3D and simulation before export. The core focus is 2.5D, but the app also handles 3D surface machining of imported meshes (rough and finish passes).

The durable product scope, supported surfaces, terminology, and CNC safety contract are defined in [`PROJECT.md`](PROJECT.md). Contributors and AI agents should start at [`INDEX.md`](INDEX.md) and follow [`AGENTS.md`](AGENTS.md).

For a complete user-facing feature guide, see [`docs/FEATURE_REFERENCE.md`](docs/FEATURE_REFERENCE.md).

It is aimed at the kind of work where you want one place to:

- draw or import geometry
- organize features into machinable shapes
- assign operations such as pockets, contours, carving, and V-carving
- inspect the toolpath strategy visually
- export the result when it looks right
