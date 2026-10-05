# PureCutCNC User Feature Reference

This reference covers the user-visible features in the current PureCutCNC workflow. It is meant to complement the project overview in [`README.md`](../README.md) and the product contract in [`PROJECT.md`](../PROJECT.md). It focuses on what a user can do in the app, what each major feature is for, and where it fits in the workflow.

## Overview

PureCutCNC helps you turn an idea into a machinable part in one place. Typical work starts with a project, stock, and tool setup, then moves into sketching or importing geometry, adding CAM operations, checking the toolpaths in preview and simulation, and exporting final G-code.

The main working surfaces are:

- Sketch view for 2D geometry and feature editing
- 3D view for model and toolpath preview
- Simulation view for replaying toolpaths against stock
- Project and CAM panels for organizing features, setting parameters, and exporting output

## Project setup and machine context

Before machining, a project defines the stock, tool library, machine selection, and workspace units. These settings affect how geometry is interpreted and how final G-code is generated.

Key user-visible project elements include:

- Stock definition and material setup
- Units selection and conversion handling
- Tool library selection and tool parameters
- Machine definition and origin setup
- Project save and project file compatibility checks

This context is important because the same geometry can be machined differently depending on stock, tool, machine origin, and exported postprocessor behavior.

## Sketching and feature creation

The Sketch view is the primary workspace for creating part geometry. It supports direct 2D design and editing using a mix of drawing tools, snapping, transforms, and measurement aids.

### Geometry creation

Users can create and edit common 2D geometry such as:

- rectangles
- circles
- polygons
- profiles composed of connected segments
- splines and curved profiles
- text features built from a vector font

Sketch features can also be transformed and reused. Common editing actions include:

- snapping to grid, midpoint, center, and feature reference points
- marquee selection
- move, copy, rotate, resize, and offset operations
- direct point editing
- corner fillet and edge modification
- measuring while drawing or editing

### Feature roles and organization

PureCutCNC organizes geometry as feature definitions and feature instances. This makes it easier to reuse geometry, move it around, and assign machining intent. The user can group, select, reorder, and manage features without losing the original geometric intent.

Important feature concepts visible in the UI include:

- feature rows in the project tree
- feature visibility toggles
- feature selection, grouping, and ordering
- editable properties for position, dimensions, and operation context

## Imported geometry and model workflows

PureCutCNC supports importing source geometry and 3D models as part of the workflow.

### 2D imports

The app accepts common vector inputs such as:

- SVG import
- DXF import

Imported 2D geometry becomes a native sketch feature that can then be positioned, transformed, assigned operations, and edited like hand-drawn geometry.

### 3D model imports

The app also accepts mesh-based 3D models for surfacing workflows, including:

- STL import
- OBJ import
- STEP import

Imported 3D models can be used to drive roughing and finishing operations. The app can also extract a silhouette from the model so it can act as a sketch feature or region for placement and machining context.

When model geometry is imported, users typically align the part, inspect the model in 3D, and then choose surface-based operations to machine the imported form.

## Text features

Text is treated as a first-class feature rather than a flattened collection of raw geometry. This allows the user to work with text as an editable part feature while keeping the text workflow consistent with the rest of the design environment.

Visible text capabilities include:

- single-line text
- skeleton and outline text styles
- built-in font selection
- shared operation and Z settings across text features
- text-frame transforms and positioning

Text can be used as a feature for decorative or functional machining, and it participates in the same project organization and operation workflow as other geometry.

## CAM operations

CAM operations are created from selected geometry and managed from the CAM panel. The operation list represents how the chosen feature should be machined.

Current operation types visible in the app include:

- Pocket Rough
- Pocket Finish
- Surface Rough
- Surface Finish
- Edge Route
- Follow Line
- V-Carve
- Drilling

Each operation can be tuned in context with tool selection, finishing strategy, depth settings, stepdown, stepover, tabs, clamps, and operation visibility. Many operations also support multiple target features and task-specific parameters.

### Operation behaviors users can rely on

- multiple operations can target the same geometry
- operations can be selectively hidden or shown
- toolpath generation can be inspected before export
- operation parameters can be adjusted after creation
- operation selection and preview helps confirm the correct toolpath strategy

## Inspection and verification workflow

Before export, PureCutCNC emphasizes inspection so users can verify toolpaths and machine motion instead of guessing.

### Sketch preview

The Sketch view lets the user inspect selected toolpaths in 2D while checking geometry ordering, direction, snapping, and selected features.

### 3D preview

The 3D view shows geometry and toolpaths in context, making it easier to inspect entry/exit behavior, cut direction, and toolpath relationships across the model.

### Simulation view

The Simulation view replays toolpaths against stock, allowing the user to verify roughing behavior, wall clearance, tabs, islands, and machining intent before export.

This is a safety and quality checkpoint: users can inspect how material is removed and catch issues before sending output to a machine.

## Export and machine output

When the toolpath looks correct, the user exports the result. Export is a final verification step rather than a blind action.

The export workflow includes:

- operation selection for export
- machine definition and postprocessor context
- controller-specific G-code output
- review before saving or sending to a machine

The app is designed to keep the machine origin, project units, and operation selection visible so the user understands what is being exported.

## Safety and operating expectations

PureCutCNC is a verification tool, not a guarantee that a job is safe to run. Users remain responsible for:

- machine setup
- workholding
- stock and tooling choices
- controller configuration
- feeds and speeds
- physical testing before production use

The app does not replace engineering judgment. It exists to help the user reason about toolpaths, simulation, and export decisions with better visibility.

## Typical user workflow

A standard part workflow looks like this:

1. Create a project and define stock, units, and machine context.
2. Draw or import part geometry.
3. Refine the sketch, add text, or import model geometry when needed.
4. Assign machining operations to the relevant features.
5. Tune tools, cut depths, stepover, and operation parameters.
6. Inspect the result in Sketch, 3D, and Simulation.
7. Export the verified G-code when the result matches the design intent.

## Related documentation

- [`README.md`](../README.md) — high-level project overview and setup
- [`PROJECT.md`](../PROJECT.md) — product contract, scope, and safety boundaries
- [`INDEX.md`](../INDEX.md) — repository navigation and entry points
- [`planning/INDEX.md`](../planning/INDEX.md) — durable design and implementation references

This document intentionally describes the user-facing features that appear in the product workflow today, without drifting into implementation-only or internal architecture detail.















































































































































































































































































































































































































































































































































































































































n











































n


















































































n
























n






n








