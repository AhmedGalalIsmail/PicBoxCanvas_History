# Copilot Instructions — PicBoxCanvas

Short, actionable guidance to get an AI coding agent productive in this repository.

## Big picture (what this repo is)
- This is a Windows Forms control library (VB.NET) that implements a picture/measurement control (PicBoxCanvas). The solution is centered on `PicBoxCanvas.sln` / `PicBoxCanvas.vbproj` and key control implementation files like `PicBoxCanvasControl.vb` and `PicBoxCanvasControl.Designer.vb`.
- Major concerns: rendering/drawing, measurement system, rulers, selection boxes, custom cursors, and UI interaction (zoom/pan). Relevant files:
  - Rendering & helpers: `BackImageGraphics.vb`, `CoordinatesBox.vb`, `MeasureSys.vb`, `PublicTypes.vb`
  - UI elements: `Rulers.vb`, `SelectionBoxElement.vb`, `ZoomButton.vb`, `ZoomButton.Designer.vb`
  - Utility: `DistanceRuler.vb`, `Rulers.vb` (ruler drawing & logic)
  - Cursors: `Cursors/*` (e.g., `cCommonCursors.vb`, `CrossCursor.vb`)

## Integration & data flow
- The control is intended to be used as a WinForms control (DLL). Typical flow:
  1. Host form creates/embeds `PicBoxCanvasControl`
  2. Control loads image(s) and uses `BackImageGraphics` and `MeasureSys` to compute measurements
  3. User interactions (mouse events) are handled in `PicBoxCanvasControl.vb` and routed to helper classes (ruler, selection element, zoom button handlers)
- Resources are kept in `My Project/Resources.resx` and `Resources/` directories. References to images, cursors, and localized resources use the standard `My.Resources` pattern.

## Build & debug (how to reproduce and run locally)
- Preferred developer flow:
  - Open `PicBoxCanvas.sln` in Visual Studio (Windows) and build via the IDE.
  - Or build from command line using MSBuild: `msbuild PicBoxCanvas.sln /p:Configuration=Release` (standard .NET Framework tooling expected).
- No automated tests or CI configuration were detected in the repository; assume manual testing using a sample host WinForms app.
- Debugging: create a small test WinForms app, add a project reference to the control project, place `PicBoxCanvasControl` on a form and step through event handlers in Visual Studio. When changing drawing code, watch for high-frequency allocations (GDI+ pressure) and test performance with large images.

## Project conventions & patterns (observe these)
- File / symbol naming: PascalCase for files, types, and methods (e.g., `ZoomButton`, `SelectionBoxElement`). Keep public API names stable—these types are likely consumed by external projects.
- UI code separation: drawing code is kept in dedicated helper files (`BackImageGraphics.vb`, `Rulers.vb`) rather than in the main control where possible—maintain that separation when adding features.
- Resource usage: use `My.Resources` and `My Project/Resources.resx` for images, icons, and cursors to match the project pattern.

## Useful file examples to reference
- `PicBoxCanvasControl.vb` — central control & event handling (mouse, paint, resize, etc.). Use this for behavioral changes or event wiring examples.
- `Rulers.vb` and `DistanceRuler.vb` — measurement math and drawing patterns (text layout, tick spacing). Follow existing spacing/tick logic when adjusting measurement behavior.
- `ZoomButton.vb` & `ZoomButton.Designer.vb` — small custom control pattern, including designer resource wiring.
- `Cursors/cCommonCursors.vb` — how custom cursors are defined and applied to the control.

## Typical change guidelines (do this, not that)
- Do: Add new drawing helpers for complex visuals and unit-testable math in separate files (e.g., extract coordinate math out of paint code into a helper so it's testable).
- Do: Keep public API stable; prefer adding new methods or optional params over renaming existing public members.
- Don’t: Introduce unfamiliar third-party UI frameworks; this repo uses WinForms and the standard GDI+ drawing model.

## PR + review hints for the maintainers
- Demonstrate performance considerations for rendering-heavy changes (memory allocations, invalidation regions, frame rate).
- Include a short manual test plan describing how to exercise the feature in a host WinForms app (e.g., steps to reproduce and expected behavior).

## Notes & limitations (what the agent couldn't find)
- No automated tests, CI config, or contribution guide were detected; presume that maintainers rely on manual verification and Visual Studio builds.
- Target framework & external package details should be verified in `PicBoxCanvas.vbproj` before significant project-system edits.
