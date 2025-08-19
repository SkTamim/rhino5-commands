# Gemvision Matrix & Rhino Command Analysis

---

## 1. 3DFace

### Short Info
Draw a single mesh face.

### Detailed Description
The **3DFace** command is a fundamental mesh-building tool used to create a single, flat polygon. This polygon, called a mesh face, is the most basic building block of any mesh object (like those used for 3D printing). This command allows you to construct a new mesh from scratch or, more commonly, to repair an existing mesh by manually adding missing faces one at a time. The face can be either a triangle (3 vertices) or a quadrangle (4 vertices). It is important to understand that this command creates mesh geometry, not the smooth, editable NURBS surfaces that are typically used for modeling.

### Steps to use the command
1.  At the command prompt, type **3DFace**.
2.  Pick the location for the **first corner**.
3.  Pick the location for the **second corner**.
4.  Pick the location for the **third corner**.
5.  Pick the location for the **fourth corner**, or press Enter to make a three-sided face.

### Command Options & Toggles
This command has no options or toggles in the command line. The choice between a 3-sided or 4-sided face is made by either pressing Enter after the third point or clicking a fourth point.

### Note for better use
The direction you pick the points (clockwise or counter-clockwise) determines the "normal" direction of the face, which is essentially the "front" or "outside" of the face. If you create a face and it appears darker than the surrounding mesh, its normal is likely flipped inward. This can be corrected later with the `Flip` command. For best results when repairing meshes, always use **Vertex** object snap to ensure the new face connects perfectly to the existing points.

### Practical Use Cases
* **Use Case 1 (Repair):** The most common use is to manually patch holes in an imported STL file. If a 3D scan or downloaded model has missing faces, `3DFace` is the direct tool to select the vertices around the hole and create the missing polygon, making the mesh "watertight" and ready for 3D printing.
* **Use Case 2 (Creation):** For creating very simple, low-polygon objects for stylistic reasons or as placeholders. For example, you could construct a basic, faceted pyramid by creating a 4-sided base and then four 3-sided faces for the sides, all snapping to a single apex point.

### Other Information
This is one of the most basic mesh creation commands and is a foundational tool for anyone who needs to perform low-level repairs on mesh files before printing or rendering.

---

## 2. 3View

### Short Info
Set up a three-viewport workspace.

### Detailed Description
The **3View** command is a viewport management tool that instantly resets your workspace to a standard three-viewport layout. This layout is designed to optimize the screen for 3D modeling tasks where a large perspective view is needed alongside key 2D orthographic views (like Top and Front) for reference and precision. It provides a middle ground between working in a single maximized viewport and the default four-viewport layout.

### Steps to use the command
1.  At the command prompt, type **3View**.
2.  Press Enter. The layout will change immediately.

### Command Options & Toggles
This command has no options; it is an immediate action.

### Note for better use
This command is an excellent way to quickly restore a standardized, functional workspace if you have accidentally closed or resized your viewports into a confusing state. For tasks that are primarily 3D (like sculpting or stone setting), using `3View` is more efficient than constantly maximizing and minimizing the Perspective window from the four-view layout.

### Practical Use Cases
* **Use Case 1 (3D Focus):** When doing detailed 3D work like sculpting an organic shape or arranging pavé stones on a complex surface, this view gives you the largest possible Perspective workspace without completely sacrificing your 2D reference views.
* **Use Case 2 (Tracing):** When modeling from a 2D reference image (using `BackgroundBitmap`), this layout allows you to keep the orthographic view (e.g., Front) clearly visible for tracing while providing a large, real-time 3D preview of your work in the Perspective view.

### Other Information
This is a sister command to `4View` and is purely for managing the modeling environment. It does not affect the geometry in any way.

---

## 3. 4View

### Short Info
Set up a four-viewport workspace.

### Detailed Description
The **4View** command is the most fundamental viewport management tool. It instantly resets your workspace to the default four-viewport layout, with each viewport having an equal size. This is the standard starting configuration for Rhino and Matrix, providing a comprehensive view of your model from all primary angles simultaneously (Top, Front, Right, and Perspective).

### Steps to use the command
1.  At the command prompt, type **4View**.
2.  Press Enter. The layout will reset to the default four-view configuration.

### Command Options & Toggles
This command has no options; it is an immediate action.

### Note for better use
The default workspace is standard for a reason: it provides all the necessary visual information at once for most modeling tasks. It's good practice to return to this view often to check your work from all angles. Remember that you can double-click on any viewport's title (e.g., "Top") to maximize it, and double-click again to return to the `4View` layout.

### Practical Use Cases
* **Use Case 1 (Standard Workflow):** This is the starting point for nearly all projects. It allows you to draw a 2D curve in the Top view, see its height in the Front and Right views, and understand its 3D form in the Perspective view, all without changing the screen layout. It is most often used to quickly get back to this balanced layout after having maximized a single viewport.
* **Use Case 2 (Precision Alignment):** When aligning a gemstone in a setting, this view is essential. You can ensure it's centered in the Top view, at the correct height in the Front view, and properly seated from the Right view, preventing mistakes that are easy to make when working in a single perspective view.

### Other Information
This command is purely for managing the modeling environment and does not affect your geometry.

---

## 4. AcadSchemes

### Short Info
Edit AutoCAD export schemes.

### Detailed Description
The **AcadSchemes** command is a configuration utility, not a modeling command. It opens the "AutoCAD Export Schemes" dialog box, which allows you to create, save, and manage different sets of rules (called "schemes") for how your Rhino geometry should be translated when you export it to AutoCAD file formats like **.DWG** or **.DXF**. This is crucial for collaborating with others who use AutoCAD, as Rhino's 3D NURBS objects must be converted into a format that AutoCAD can understand.

### Steps to use the command
1.  At the command prompt, type **AcadSchemes**.
2.  In the AutoCAD Export Schemes dialog box, select an existing scheme to modify or click New.
3.  Edit the settings.
4.  Click Save or Save As.

### Command Options & Toggles
The options are all contained within the dialog box:
* **General Tab:** Controls the AutoCAD version for compatibility, and how surfaces and meshes are converted (e.g., into meshes or wireframe curves).
* **Curves Tab:** Gives you precise control over how curves are exported, including options to simplify them or convert them into basic polylines.
* **Scheme Management Buttons:** Includes `New`, `Save`, `SaveAs`, `Delete`, `Rename`, `Import`, and `Export` to manage your saved schemes.

### Note for better use
The settings are saved in the registry. To transfer the settings to another computer, use the Export and Import buttons. When you export curves to DXF/DWG, polylines are created from the curves. In the export dialog box, you can set the way the polylines are created. The settings are saved in the scheme.

### Practical Use Cases
* **Use Case 1 (2D Collaboration):** You have designed a 3D ring, but a colleague needs to create a 2D technical drawing in AutoCAD. You would create a scheme that sets "Export surfaces as" to "Curves" and checks "Project to plane." When you export the Top view of your ring using this scheme, the drafter will receive a perfectly flat, clean 2D line drawing.
* **Use Case 2 (Manufacturing Prep):** A laser engraving machine's software only accepts simple polylines from a DXF file. You would create a scheme where the Curves tab is set to convert all splines to polylines. This ensures the file you send is 100% compatible.

### Other Information
This command is essential for any workflow that involves moving data from Rhino to AutoCAD. Creating multiple, named schemes for different tasks (e.g., a "2D for Laser" scheme, a "3D for Engineer" scheme) can save a significant amount of time.

---

## 5. AddNextU

### Short Info
Add the next control point in the u-direction to the selection.

### Detailed Description
The **AddNextU** command expands a selection of control points on a curve or surface by adding the next control point in the positive U direction. On a NURBS surface, control points are arranged in a grid; the U direction is one axis of this grid. This command is part of a family of tools used for structured, incremental selection of control points.

### Steps to use the command
1.  Turn on control points for a surface or curve (`PointsOn` or F10).
2.  Select at least one control point.
3.  Run the command `AddNextU`.
4.  The adjacent control point in the positive U direction will be added to the current selection.

### Command Options & Toggles
This command is a direct action and has no options or toggles.

### Note for better use
This command is most powerful when assigned to a keyboard shortcut. This allows you to "walk" your selection along a row of control points very quickly. To see which way the U and V directions are pointing on a surface, use the `Dir` command.

### Practical Use Cases
* **Use Case 1 (Walking a Selection):** You have selected a control point and want to select the next one in its row without deselecting the current one. Running `AddNextU` is faster than holding Shift and clicking the next point, especially if assigned to a keyboard shortcut.
* **Use Case 2 (Full Row Selection):** To select an entire row of control points, you can select one point in the middle, then repeatedly use `AddNextU` to select to one end, and `AddPrevU` to select to the other.

### Other Information
This command is almost always used in conjunction with its counterparts: `AddNextV`, `AddPrevU`, and `AddPrevV`.

---

## 6. AddNextV

### Short Info
Add the next control point in the v-direction to the selection.

### Detailed Description
The **AddNextV** command expands a selection of control points on a surface by adding the next control point in the positive V direction. On a NURBS surface, control points are arranged in a grid; the V direction is the second axis of this grid.

### Steps to use the command
1.  Turn on control points for a surface (`PointsOn` or F10).
2.  Select at least one control point.
3.  Run the command `AddNextV`.
4.  The adjacent control point in the positive V direction will be added to the current selection.

### Command Options & Toggles
This command is a direct action and has no options or toggles.

### Note for better use
To see which way the U and V directions are pointing on a surface, use the `Dir` command.

### Practical Use Cases
* **Use Case 1 (Expanding a Selection):** You have selected a row of control points using `AddNextU`/`AddPrevU` and now want to select the entire adjacent row as well. With the first row selected, running `AddNextV` will add the entire next row of control points to your selection.

### Other Information
This command is part of the control point selection family, along with `AddNextU`, `AddPrevU`, and `AddPrevV`.

---

## 7. AddPrevU

### Short Info
Add the previous control point in the u-direction to the selection.

### Detailed Description
The **AddPrevU** command expands a selection of control points on a curve or surface by adding the previous control point in the negative U direction.

### Steps to use the command
1.  Turn on control points for a surface or curve (`PointsOn` or F10).
2.  Select at least one control point.
3.  Run the command `AddPrevU`.
4.  The adjacent control point in the negative U direction will be added to the current selection.

### Command Options & Toggles
This command is a direct action and has no options or toggles.

### Note for better use
This command is most effective when used in combination with `AddNextU` to select an entire row of control points from a starting point in the middle.

### Practical Use Cases
* **Use Case 1 (Full Row Selection):** You want to adjust the dome height of a signet ring. To do this smoothly, you need to select an entire row of control points that runs across the top. Select a single control point in the middle of the row. Then, repeatedly use `AddNextU` until you reach one edge, and `AddPrevU` until you reach the other. This selects the entire row perfectly.

### Other Information
This command is part of the control point selection family.

---

## 8. AddPrevV

### Short Info
Add the previous control point in the v-direction to the selection.

### Detailed Description
The **AddPrevV** command expands a selection of control points on a surface by adding the previous control point in the negative V direction.

### Steps to use the command
1.  Turn on control points for a surface (`PointsOn` or F10).
2.  Select at least one control point.
3.  Run the command `AddPrevV`.
4.  The adjacent control point in the negative V direction will be added to the current selection.

### Command Options & Toggles
This command is a direct action and has no options or toggles.

### Note for better use
This command is part of the control point selection family.

### Practical Use Cases
* **Use Case 1 (Creating Deformations):** You need to create a gentle, concave dip in the surface of a pendant. Select a central control point. Use the `Add...U/V` family of commands to expand your selection to a small, square group of points. You can then move this group down to create a smooth depression.

### Other Information
This command is part of the control point selection family.

---

## 9. AddToGroup

### Short Info
Add an object to a selected group.

### Detailed Description
The **AddToGroup** command allows you to add one or more objects to a group that has already been created. A "group" is a collection of objects that can be selected and transformed together as a single unit, without permanently merging their geometry. This command modifies an existing group rather than creating a new one.

### Steps to use the command
1.  Run the command `AddToGroup`.
2.  You will be prompted: **"Select objects to add"**. Select the object(s) you want to add to a group and press Enter.
3.  You will be prompted: **"Select group to add to"**. Click on any object that is already a member of the target group.
4.  The objects selected in step 2 are now part of the target group.

### Command Options & Toggles
This command has no clickable options or toggles in the command line.

### Note for better use
Grouping is a non-destructive way to keep complex models organized. Unlike `BooleanUnion`, the parts remain separate objects. Unlike `Block`, editing one object in a group does not change the others. You can also add a group to another group, creating "nested" groups.

### Practical Use Cases
* **Use Case 1 (Assembly):** You have created a four-prong head and grouped the parts. Later, you decide to add two more prongs. Instead of ungrouping everything and starting over, you can create the two new prongs, run `AddToGroup`, select them, and then click on any of the original prongs to add them to the group.
* **Use Case 2 (Organization):** You have a large area of a ring covered in pavé stones, which you have grouped. You then add one more stone to fill a small gap. Run `AddToGroup`, select the new stone, and then click on any other stone in the main pavé group. The new stone is now included, keeping your pavé field organized.

### Other Information
This is a fundamental organizational tool for managing complex scenes.

---

## 10. Alerter

### Short Info
Open the Alerter options page.

### Detailed Description
The **Alerter** command is a system utility that opens the "Alerter" page within the main Rhino Options window. Its purpose is to control how Rhino notifies you when a time-consuming command has finished processing. This is a user-preference setting to manage workflow interruptions.

### Steps to use the command
1.  Run the command `Alerter`.
2.  The Rhino Options window will open to the "Alerter" page.
3.  Check "Enable command alerting" to turn the feature on.
4.  Set your preferences for when and how you want to be alerted.
5.  Click "OK" to save the settings.

### Command Options & Toggles
All options for this command are located within the dialog box:
* **Enable command alerting:** The master checkbox to turn the feature on or off.
* **Elapsed time in minutes:** The alert will only be triggered if the command takes longer than the number of minutes specified here.
* **Play a sound file:** When a command finishes, Rhino will play a sound.
* **Run Rhino commands:** When a command finishes, Rhino can automatically run another command or macro.

### Note for better use
Setting the "Elapsed time" too low (e.g., 0.1 minutes) can be annoying, as you will get alerts for many common commands. A setting of 1 or 2 minutes is usually more practical. The "Run Rhino commands" feature is a powerful way to automate a sequence. For example, after a long boolean operation, you could automatically run the `SelLast` and `ZoomSelected` commands to immediately inspect the new object.

### Practical Use Cases
* **Use Case 1 (Rendering):** You start a high-quality render that you know will take 15-20 minutes. Enable the alerter and check "Play a sound file." Now you can minimize the program and work on something else. When the render is complete, your computer will play a sound, notifying you that it's ready.
* **Use Case 2 (Complex Booleans):** You are performing a complex Boolean operation on two very detailed meshes, which might take several minutes. By enabling the alerter, you can step away from your computer and wait for the sound that tells you the operation is complete and you can continue working.

### Other Information
This is a utility for setting up notifications for commands that take a long time to complete.

---

## 11. Align

### Short Info
Line up bounding boxes of objects.

### Detailed Description
The **Align** command is a fundamental transformation tool used to precisely line up two or more objects. It works by moving selected objects to align the extents of their "bounding boxes" (the smallest imaginary box that can contain an object). You first select the objects to move, then a single target object that remains stationary. This is an essential command for creating symmetrical and precisely arranged models.

### Steps to use the command
1.  Select the object(s) to align.
2.  Run the command `Align`.
3.  At the **Select target object** prompt, click the object that will not move.
4.  At the **Alignment type...** prompt, click an option.

### Command Options & Toggles
* **Bottom:** Aligns the bottom edges of the objects' bounding boxes.
* **Concentric:** Aligns the centers of the objects' bounding boxes in all three axes (X, Y, and Z).
* **HCenter:** Aligns the horizontal centers.
* **Left:** Aligns the left edges of the bounding boxes.
* **Right:** Aligns the right edges of the bounding boxes.
* **Top:** Aligns the top edges of the bounding boxes.
* **VCenter:** Aligns the vertical centers.

### Note for better use
The effect of options like `Top`, `Bottom`, `Left`, `Right`, `HCenter`, and `VCenter` depends on the active viewport. For example, `Top` in the Top view aligns to the screen's top, while `Top` in the Front view aligns to the highest Z-coordinate. The `Concentric` option is the most powerful for jewelry, as it works in all three dimensions simultaneously.

### Practical Use Cases
* **Use Case 1 (Centering):** You have modeled a bezel and a gemstone and need to perfectly center the stone inside. Select the gemstone, run `Align`, select the bezel as the target, and click the **Concentric** option. The gemstone will instantly snap to the exact center of the bezel.
* **Use Case 2 (Arranging):** You have several small accent stones that need to be lined up perfectly along the top of a ring shank. In the Front view, select all the accent stones, run `Align`, select the shank as the target, and click **VCenter**. All stones will snap to the same height.

### Other Information
This command is a cornerstone of precise modeling, ensuring that components are perfectly centered or lined up, which is critical for both aesthetics and manufacturing.

---

## 12. AlignMeshVertices

### Short Info
Force mesh vertices to the same location.

### Detailed Description
The **AlignMeshVertices** command is a mesh editing tool that moves a selection of two or more mesh vertices to a single, averaged location. This command is used to flatten, straighten, or consolidate points on a mesh object. It essentially takes all the selected points and moves them to their collective center point, which is useful for cleaning up messy geometry.

### Steps to use the command
1.  Select two or more vertices on a mesh object.
2.  Run the command `AlignMeshVertices`.

### Command Options & Toggles
This command has no options in the standard version. It is an immediate action.

### Note for better use
To select individual mesh vertices (sub-objects), hold down **Ctrl + Shift** and click or drag a window over the vertices. This is a destructive editing tool; it can be very useful for cleaning up geometry, but it can also easily ruin the shape of a detailed mesh if used incorrectly.

### Practical Use Cases
* **Use Case 1 (Flattening):** You have an STL model of a bezel, but the top edge is slightly wavy and uneven. You need a perfectly flat top surface. Select all the vertices that make up the top edge of the bezel and run the command. All the selected vertices will be snapped to the same Z-height, instantly creating a perfectly flat top edge.
* **Use Case 2 (Cleaning Scans):** You have a 3D scan of a handmade organic shape, and there are some rough, "noisy" areas with jagged vertices that should be smoother. Select a small cluster of these jagged vertices and run the command. This will average their positions, effectively smoothing out the rough spot.

### Other Information
This is a low-level mesh repair tool, primarily used when preparing models for 3D printing or cleaning up imported mesh files.

---

## 13. AlignProfiles

### Short Info
Line up one curve to another.

### Detailed Description
The **AlignProfiles** command is a specialized tool used to orient and position open curves relative to each other, preparing them for surface creation commands like `Loft` or `Sweep`. The command is interactive, guiding you through a sequence of selections. It works by moving and rotating one curve to match the position and orientation of another, based on points you pick on each curve.

### Steps to use the command
1.  Run the command `AlignProfiles`.
2.  At the **Select curve to align** prompt, select the curve you want to move.
3.  At the **Point on curve to align from** prompt, click a point on that curve (e.g., its midpoint).
4.  At the **Select curve to align to** prompt, select the target curve that will not move.
5.  At the **Point on curve to align to** prompt, click a corresponding point on the target curve.
6.  The first curve will snap into position, aligned with the second curve.

### Command Options & Toggles
This command does not have clickable options in the command line when it starts. It is a sequential, interactive process.

### Note for better use
Use object snaps like `Mid` or `End` when picking the alignment points to ensure perfect accuracy. This command works best by aligning one curve to another. If you have multiple curves to align to a single target, repeat the command for each one.

### Practical Use Cases
* **Use Case 1 (Loft Prep):** You have drawn three different profile curves for a ring shank, but they are scattered. Before you can `Loft` them, they need to be positioned correctly. Use the command to align the midpoint of the second profile to the midpoint of the first. Then, repeat the command to align the midpoint of the third profile to the midpoint of the first. Now all three are perfectly aligned and ready for lofting.
* **Use Case 2 (Symmetry):** You are modeling a decorative element that will be mirrored. You have drawn the two profile curves that will define its shape. To ensure the resulting surface is perfectly symmetrical, the two profile curves must be perfectly aligned. By aligning the two profiles using their center points, you guarantee they are in the correct position before you create a surface between them.

### Other Information
This is a critical preparatory step for building clean, predictable surfaces, especially when the automated alignment in other commands doesn't produce the desired result.

---

## 14. Angle

### Short Info
Report the angle between two sets of locations.

### Detailed Description
The **Angle** command is an analysis tool that measures and reports the angle between two lines or two vectors defined by points. It does not create any permanent geometry; its sole purpose is to provide a measurement that is displayed in the command line.

### Steps to use the command
1.  Run the command `Angle`.
2.  Pick the start of the first line.
3.  Pick the end of the first line.
4.  Pick the start of the second line.
5.  Pick the end of the second line.
6.  The angle between the two defined lines is reported in the command history.

### Command Options & Toggles
This command is interactive and does not have clickable options.

### Note for better use
You can also measure the angle between two connected lines by picking three points: the end of the first line, the common corner point, and the end of the second line. `Angle` is for quick checks. If you need to create a permanent dimension that is visible on the model, use the `DimAngle` command instead.

### Practical Use Cases
* **Use Case 1 (Verification):** The inside wall of a bezel must have a specific draft angle (e.g., 5 degrees) for proper stone setting. In the Front view, use the `Angle` command to measure between a vertical construction line and the line representing the bezel's inner wall to confirm the angle.
* **Use Case 2 (Spacing):** You are creating a four-prong head and need to ensure the prongs are perfectly spaced at 90-degree intervals. In the Top view, use the command to measure the angle between a line from the center to the tip of one prong, and a line from the center to the tip of the next prong.

### Other Information
This is a pure measurement tool and does not create or modify any objects.

---

## 15. ApplyBoxMapping

### Short Info
Add a box texture mapping channel to an object.

### Detailed Description
The **ApplyBoxMapping** command is a texture mapping utility. It projects a texture onto an object as if it were being projected from the six sides of an imaginary box. This method is ideal for objects that are squarish or rectangular. When you run the command, it creates a "mapping widget" in the shape of a box that you can then move, scale, or rotate to control how the texture is applied.

### Steps to use the command
1.  Select the objects to map.
2.  Run the command `ApplyBoxMapping`.
3.  Pick the first corner of the mapping box or select an option.
4.  Pick the other corner of the mapping box.
5.  Pick the height of the mapping box.
6.  A box-shaped wireframe widget will appear around your object.

### Command Options & Toggles
* **BoundingBox:** Automatically creates a mapping widget that is the same size as the object's bounding box. This is the most common and quickest option.
* **CPlane:** Allows you to draw the base of the mapping box on the current construction plane.
* **Cap:** Controls how the texture is applied to the "capped" ends of the box projection.
* **World:** Uses the world axes for the initial orientation of the box.
* **Surface:** Allows you to align the mapping box to a specific surface.

### Note for better use
After applying the mapping, you may need to run the `MappingWidget` command to turn on the widget's visibility if you want to edit it later. For very precise control, you can use the `UVEditor` command after applying the box map to see how the texture is unwrapped.

### Practical Use Cases
* **Use Case 1 (Metal Finishes):** You have a signet ring with a flat, rectangular top and want to apply a brushed metal texture that flows correctly over the edges and down the sides. Select the ring, run the command, and choose the `BoundingBox` option. This will wrap the brushed texture realistically.
* **Use Case 2 (Gem Textures):** You are rendering a princess-cut or emerald-cut stone and want to apply a complex facet map or a custom texture. A box map is the perfect way to apply textures to rectilinear gemstone shapes, ensuring the texture is applied evenly to the top, sides, and bottom without distortion.

### Other Information
This command is one of the fundamental texture mapping types, essential for preparing models for rendering.

---

## 16. ApplyCrv

### Short Info
Wrap a curve onto a surface.

### Detailed Description
The **ApplyCrv** command is a powerful deformation tool that takes a flat, 2D curve and "wraps" or "maps" it onto a 3D surface. The command requires three inputs: the curve you want to apply, a "base surface" (which is often just the flat construction plane the curve is lying on), and the "target surface" where you want the curve to be wrapped. The result is a new 3D curve that follows the contour of the target surface.

### Steps to use the command
1.  Select the curve(s) to apply.
2.  Run the command `ApplyCrv`.
3.  At the **Select base surface** prompt, select a surface that the curve is on.
4.  At the **Select target surface** prompt, select the 3D surface you want to wrap the curve onto.

### Command Options & Toggles
This command is a sequential process and has no clickable options in the command line.

### Note for better use
Use the `CreateUVCrv` command to generate planar versions of the u and v curves of a surface so you can use them as a guide to orient your text. You must then also map the u and v curves along with the curves you are applying so they will act as a placeholder. The structure of the curve is refit with a tolerance of the value of the `Absolute tolerance` option in Document Properties > Units.

### Practical Use Cases
* **Use Case 1 (Surface Decoration):** You have drawn a complex, flat, 2D filigree pattern and you want to apply it to the curved surface of a wide wedding band. Select your 2D filigree curves, run the command, select the CPlane as the base, and select the ring shank as the target. A new set of 3D curves will be created, perfectly following the curvature of the ring.
* **Use Case 2 (Engraving):** You need to add a name or a date to the inside of a ring. Create the text using the `TextObject` command, which results in flat curves. Use `ApplyCrv` to wrap the flat text curves onto the inner surface of the ring. You can then use these new 3D curves to create an engraved effect with a boolean difference.

### Other Information
The position of the seam and the U/V directions of the target surface can affect how the curve is applied. If the curve appears in an unexpected location, try using the `SrfSeam` command to adjust the target surface's seam.

---

## 17. ApplyCurvePiping

### Short Info
Constructs a mesh pipe display around a curve.

### Detailed Description
The **ApplyCurvePiping** command creates a visual mesh pipe around a curve. This is a display feature, not a true geometric object. It makes a curve *look* like a solid pipe in rendered and shaded views, but it does not create a NURBS surface or polysurface that you can edit or use in boolean operations. Its main purpose is for quick visualization and rendering without the overhead of creating heavy geometry.

### Steps to use the command
1.  Select the curve(s) you want to apply piping to.
2.  Run the command `ApplyCurvePiping`.
3.  The "Curve Piping" properties panel will open.
4.  Adjust the settings (Radius, Segments, etc.).
5.  The curve will now appear as a pipe in shaded/rendered views.

### Command Options & Toggles
The options are controlled in the Properties panel:
* **On:** Turns the piping effect on or off for the selected curve.
* **Radius:** Sets the thickness of the pipe.
* **Segments:** Controls how many segments are used for the pipe's circumference (higher numbers are smoother).
* **Faceted:** Creates a faceted, low-poly look instead of a smooth round.
* **CapType:** Determines if the ends of the pipe are open, flat, or rounded.

### Note for better use
This is a display effect only. If you need to 3D print the pipe or perform a boolean operation with it, you must use the standard `Pipe` command to create real geometry. This command is much faster and uses less memory than creating thousands of real pipes, making it ideal for visualizing complex wireframe-style designs before committing to the final geometry.

### Practical Use Cases
* **Use Case 1 (Quick Visualization):** You have a complex filigree design made of hundreds of curves. You want to see what it will look like as a solid piece without running the slow `Pipe` command on every single curve. Select all the curves and apply curve piping. You can instantly visualize the design's thickness and form.
* **Use Case 2 (Render-Only Details):** You are creating a portfolio render and want to add some very fine, decorative wires to a piece that won't be part of the actual 3D printed model. Draw the curves and use `ApplyCurvePiping`. They will show up in the final render as solid pipes but won't add unnecessary weight or complexity to the manufacturing file.

### Other Information
To remove the effect, select the curve, go to its Properties panel, and uncheck the "On" box in the Curve Piping section.

---

## 18. ApplyCustomMapping

### Short Info
Add a custom texture mapping channel to an object.

### Detailed Description
The **ApplyCustomMapping** command is an advanced texture mapping utility. It wraps a texture onto a target object using another object's shape as the projection guide. This allows for complex, non-standard texture projections that follow specific forms, which is impossible with standard mapping types like box or planar.

### Steps to use the command
1.  Select the target object(s) that will receive the texture.
2.  Run the command `ApplyCustomMapping`.
3.  You will be prompted: **"Select a custom mapping object"**. Select the object that will act as the projector.
4.  A dialog box appears to configure the mapping.
5.  The texture is applied to the target object as if it were projected from the custom object.

### Command Options & Toggles
* **UV / UVW:** Chooses the mapping direction.
* **Mapping Primitive:** The type of object used for projection (plane, box, sphere, cylinder).

### Note for better use
This is the tool to use when standard mapping projections (box, spherical, cylindrical) don't work. For example, applying a texture that needs to follow a twisting, tapered shape. Unlike other mapping commands, this one requires a second, separate object to act as the mapping guide.

### Practical Use Cases
* **Use Case 1 (Advanced Texturing):** You have a ring shank that twists and changes shape, and you want to apply a repeating pattern that follows the twist perfectly. A standard planar or cylindrical map would stretch and distort. You could model a simplified, untwisted version of the shank to act as the "custom mapping object." By applying the texture using this simpler object as a guide, the texture will flow cleanly along the more complex, twisted shank.

### Other Information
The documentation confirms this command adds a custom texture mapping channel to an object.

---

## 19. ApplyCylindricalMapping

### Short Info
Add a cylindrical texture mapping channel to an object.

### Detailed Description
The **ApplyCylindricalMapping** command is a texture mapping utility that projects a texture onto an object as if it were wrapped around a cylinder. This method is ideal for objects that are round or cylindrical in shape, like a ring shank or a round bezel. It creates a cylindrical mapping widget that can be moved, scaled, and rotated to control the texture's application.

### Steps to use the command
1.  Select the object(s) to map.
2.  Run the command `ApplyCylindricalMapping`.
3.  You will be prompted to draw the base and height of the cylindrical widget. The `BoundingBox` option is often the easiest starting point.
4.  A cylindrical wireframe widget appears around the object.
5.  Press Enter to accept the mapping.

### Command Options & Toggles
* **BoundingBox:** Automatically creates a mapping cylinder that encloses the object.
* **Capped:** Toggles whether the texture is also projected onto the flat top and bottom ends of the cylinder.

### Note for better use
The cylindrical projection creates a "seam" where the two ends of the texture map meet. You can rotate the mapping widget to hide this seam in a less visible area of your model. This is the go-to mapping method for any object that is fundamentally cylindrical, such as shanks, bezels, and even the sides of a round gemstone.

### Practical Use Cases
* **Use Case 1 (Ring Patterns):** You want to apply a continuous, repeating pattern (like a floral or geometric design) around the outside of a wedding band. Select the ring, run `ApplyCylindricalMapping` and choose the `BoundingBox` option. This will wrap the pattern around the ring smoothly and evenly.
* **Use Case 2 (Brushed Finishes):** You want to render a round bezel with a brushed metal finish where the grain flows circularly around the bezel wall. `ApplyCylindricalMapping` is the perfect tool for this, as it will wrap the brushed texture around the bezel wall correctly.

### Other Information
The documentation confirms this command adds a cylindrical texture mapping channel to an object.

---

## 20. ApplyDisplacement

### Short Info
Constructs a displacement display mesh for surfaces, polysurfaces, or meshes.

### Detailed Description
The **ApplyDisplacement** command is a rendering and display feature that creates a "displacement mesh" on a surface or polysurface. This mesh deforms the object's appearance at render time, using the light and dark values of a texture map to create real, physical-looking bumps, grooves, and details. Unlike a bump map, which is a lighting trick, displacement actually modifies the object's silhouette.

### Steps to use the command
1.  Select the object you want to apply displacement to.
2.  In the Properties panel, go to the Displacement section.
3.  Click "On" and assign a texture map.
4.  Adjust the settings (Black point, White point).
5.  Run the command `ApplyDisplacement` to see a preview of the mesh in the viewport.

### Command Options & Toggles
The options are controlled in the Properties panel:
* **Texture:** The image map used to drive the displacement.
* **Black point:** The amount of inward displacement (indentation) caused by black areas of the texture.
* **White point:** The amount of outward displacement (height) caused by white areas of the texture.
* **Initial Quality:** Controls the density of the displacement mesh for the viewport preview.

### Note for better use
Displacement is a memory-intensive effect that is primarily calculated at render time. The viewport preview is a lower-quality approximation. For displacement to show fine details, the underlying object must have a dense render mesh. You can increase this in the Document Properties. After applying displacement, you can use the `ExtractRenderMesh` command to convert the visual displacement effect into a real, editable mesh object that can be 3D printed.

### Practical Use Cases
* **Use Case 1 (Realistic Textures):** You want to create a realistic, bumpy hammered texture on a ring for a client presentation, without having to manually sculpt every single dent. Find or create a black and white texture map of a hammered pattern. Apply this texture to the ring in the displacement slot. The white areas of the texture will create the raised bumps, giving a highly realistic result in the final render.
* **Use Case 2 (Complex Patterns):** You need to create a knurled (cross-hatch diamond) pattern on the edge of a bezel. Apply a knurled pattern texture map using displacement. Once you are happy with the look of the preview, use `ExtractRenderMesh` to turn the visual effect into a real, 3D printable mesh.

### Other Information
This is a powerful tool for adding surface detail that would be too difficult or time-consuming to model directly.

---

## 21. ApplyEdgeSoftening

### Short Info
Constructs an edge-softening display mesh for surfaces, polysurfaces, or meshes.

### Detailed Description
The **ApplyEdgeSoftening** command is a display feature that creates a "softening mesh" around the sharp edges of a surface or polysurface. This makes the edges appear rounded or filleted in rendered and shaded views without actually changing the underlying NURBS geometry. It is a visual trick, similar to `ApplyCurvePiping`, designed to create the appearance of a soft edge for quick visualization and rendering.

### Steps to use the command
1.  Select the object you want to apply edge softening to.
2.  In the Properties panel, go to the Edge Softening section.
3.  Click "On" and adjust the settings (Radius, etc.).
4.  Run the command `ApplyEdgeSoftening` to see a preview of the mesh in the viewport.

### Command Options & Toggles
The options are controlled in the Properties panel:
* **On:** Turns the edge softening effect on or off for the selected object.
* **Softening:** Sets the radius of the rounded edge effect.
* **Chamfer:** Toggles the effect between a rounded fillet and a flat chamfer.
* **Faceted:** Creates a faceted, low-poly look instead of a smooth round.

### Note for better use
This is a display effect only. If you need to 3D print the object with rounded edges, you must use the `FilletEdge` or `BlendEdge` command to create real geometric fillets. This command is much faster than creating dozens of complex fillets, making it ideal for quickly visualizing how a piece will look with soft edges before committing to the final, heavy geometry.

### Practical Use Cases
* **Use Case 1 (Render Prototyping):** You have a signet ring with many sharp edges. You want to show a client a quick render of what it would look like with soft, polished edges, but you don't want to spend time creating permanent fillets yet. Select the ring, turn on Edge Softening in the properties panel, and set a small radius. The ring will now render with beautiful, soft highlights on all its edges.
* **Use Case 2 (Comfort Fit Look):** You want to visualize how the inside edge of a wedding band will look with a soft, "comfort fit" rounding. Apply Edge Softening to the ring. This will give a good visual representation of the final polished piece without needing to model the complex comfort fit surface yet.

### Other Information
To convert this visual effect into a real, editable mesh object, you can use the `ExtractRenderMesh` command.

---

## 22. ApplyMesh

### Short Info
Fit a mesh that matches a source mesh onto a surface.

### Detailed Description
The **ApplyMesh** command deforms a mesh object to match the shape of a target NURBS surface. It is a specialized deformation tool used to wrap or fit an existing mesh onto a new curved form.

### Steps to use the command
1.  Select the mesh object you want to deform.
2.  Run the command `ApplyMesh`.
3.  At the **Select the surface to fit the mesh to** prompt, select the target NURBS surface.
4.  The mesh object will be deformed to match the surface's shape.

### Command Options & Toggles
This command has no clickable options in the command line.

### Note for better use
This command is the mesh equivalent of the `ApplyCrv` command. `ApplyCrv` is for curves, `ApplyMesh` is for meshes. This command works best when the mesh and the surface have a similar rectangular or square-like flow. Applying a complex mesh to a simple surface can produce unpredictable results.

### Practical Use Cases
* **Use Case 1 (Applying Mesh Patterns):** You have a flat, pre-made mesh pattern (for example, a complex filigree or grill that was modeled as a mesh) and you want to wrap it around a ring shank. Select the flat mesh pattern, run `ApplyMesh`, and select the ring shank surface as the target. The mesh pattern will bend and conform to the shape of the ring.
* **Use Case 2 (Conforming 3D Scans):** You have a 3D scan of a person's fingerprint (as a mesh) and you want to apply it to the curved surface of a signet ring. Use `ApplyMesh` to take the flat fingerprint mesh and deform it to the curved top of the ring, creating a custom, personalized piece.

### Other Information
This is a powerful tool for applying pre-existing mesh details to curved NURBS surfaces.

---

## 23. ApplyMeshUVN

### Short Info
Wrap meshes and points onto a surface.

### Detailed Description
The **ApplyMeshUVN** command is an advanced deformation tool that deforms meshes and points onto a surface with a high degree of control. It works by associating the X, Y, and Z coordinates of the source object with the U, V, and Normal directions of the target surface. This allows for complex transformations where an object can be wrapped and simultaneously raised or lowered from the target surface.

### Steps to use the command
1.  Select the mesh or point objects to deform.
2.  Run the command `ApplyMeshUVN`.
3.  At the **Select surface to apply objects to** prompt, select the target NURBS surface.
4.  A dialog box appears with options to control the U, V, and N (Normal) mapping.
5.  Click OK to apply the transformation.

### Command Options & Toggles
The options are in a dialog box:
* **U:** Maps the object's X coordinates to the surface's U direction.
* **V:** Maps the object's Y coordinates to the surface's V direction.
* **N:** Maps the object's Z coordinates to the surface's Normal direction (inward/outward).

### Note for better use
This is a highly technical command and is not used often in typical jewelry modeling. Its unique feature is the "N" (Normal) mapping, which means that the height (Z-axis) of your original flat mesh can be used to push the wrapped mesh in or out from the target surface.

### Practical Use Cases
* **Use Case 1 (Advanced Bas-Relief):** You have a flat mesh that was created from a heightmap image (like a 3D face or coin). You want to wrap this relief onto a curved pendant. Using `ApplyMeshUVN`, you can wrap the mesh onto the pendant (U and V mapping) while simultaneously using the original height of the mesh to create the raised relief effect (N mapping).

### Other Information
This command is more common in fields like texture baking and game development than in jewelry design.

---

## 24. ApplyPlanarMapping

### Short Info
Add a planar texture mapping channel.

### Detailed Description
The **ApplyPlanarMapping** command is a texture mapping utility that projects a texture onto an object from a single, flat plane. It works like a slide projector, casting the image in a straight line. This method is best for flat or nearly flat surfaces. It creates a rectangular mapping widget that you can move, scale, and rotate to control the projection.

### Steps to use the command
1.  Select the object(s) to map.
2.  Run the command `ApplyPlanarMapping`.
3.  You will be prompted to draw a rectangle in the viewport. This rectangle defines the mapping widget.
4.  A rectangular wireframe widget will appear.
5.  Press Enter to accept the mapping.

### Command Options & Toggles
* **BoundingBox:** Automatically creates a mapping widget that is the same size as the object's bounding box.
* **CPlane / World:** Aligns the widget to the active CPlane or the world axes.

### Note for better use
Be aware that planar mapping will cause severe stretching and distortion on any surfaces that are not parallel to the mapping widget (e.g., the sides of a box). This is the best and simplest mapping method for any object that is primarily flat, like the top of a signet ring, a coin, or a dog tag.

### Practical Use Cases
* **Use Case 1 (Applying Logos):** You have a logo image that you need to apply as a texture to the flat top surface of a signet ring for a render. Select the ring, in the Top view, run `ApplyPlanarMapping` and draw a rectangle that matches the size of the ring's top. The logo will be projected cleanly onto the flat surface.
* **Use Case 2 (Enamel Effects):** You have a 2D pattern that you want to render as enamel inside a recessed area of a flat pendant. `ApplyPlanarMapping` is the perfect way to place the enamel pattern texture precisely into the recessed area.

### Other Information
This is one of the most common and basic types of texture mapping.

---

## 25. ApplyShutLining

### Short Info
Constructs a shut-line display mesh for surfaces, polysurfaces, or meshes.

### Detailed Description
The **ApplyShutLining** command is a specialized display and rendering feature. It creates a visual effect of grooves, panel lines, or part lines on a surface or polysurface. It works by creating a mesh with rounded indentations wherever there is an edge on the original object. This is a visual effect only and does not change the underlying geometry.

### Steps to use the command
1.  Select the object.
2.  In the Properties panel, go to the Shut Lining section.
3.  Click "On" and adjust the settings (Radius, Profile, etc.).
4.  Run the command `ApplyShutLining` to see a preview of the mesh in the viewport.

### Command Options & Toggles
The options are controlled in the Properties panel:
* **On:** Turns the shut lining effect on or off.
* **Radius:** Controls the width of the groove.
* **Profile Curve:** Allows you to use a custom curve to define the cross-section shape of the groove.

### Note for better use
This command is primarily used in industrial and product design to simulate the gaps between panels on a car, phone, or other manufactured product. Like other display effects, you can use `ExtractRenderMesh` to convert the visual shut lines into a real, editable mesh object.

### Practical Use Cases
* **Use Case 1 (Non-Jewelry):** An industrial designer has modeled a phone case and wants to visualize the thin gap between the main body and a button. They would apply shut lining to the model. The command would automatically create a small, rounded groove along the edge where the button meets the body, creating a realistic render. This command has very limited use in traditional jewelry design.

### Other Information
This is a tool for creating visual details for rendering that are not intended to be part of the final manufactured geometry.

---

## 26. ApplySphericalMapping

### Short Info
Add a spherical texture mapping channel to an object.

### Detailed Description
The **ApplySphericalMapping** command is a texture mapping utility that projects a texture onto an object as if it were being projected from the inside of a sphere. This method is ideal for objects that are round or ball-shaped. It creates a spherical mapping widget that you can move, scale, and rotate to control the texture's application.

### Steps to use the command
1.  Select the object(s) to map.
2.  Run the command `ApplySphericalMapping`.
3.  You will be prompted to draw the center and radius of the spherical widget. The `BoundingBox` option is often easiest.
4.  A spherical wireframe widget appears around the object.
5.  Press Enter to accept the mapping.

### Command Options & Toggles
* **BoundingBox:** Automatically creates a mapping sphere that encloses the object.

### Note for better use
Spherical mapping will always cause some "pinching" or distortion at the top and bottom poles of the sphere. You can rotate the mapping widget to move these poles to a less visible area of your model. This mapping method works best with "seamless" or "tileable" textures that are designed to wrap without showing an obvious seam.

### Practical Use Cases
* **Use Case 1 (Pearls and Beads):** You are rendering a pearl necklace and want to apply a pearlescent, iridescent texture map to the spherical pearls. Select a pearl, run `ApplySphericalMapping`, and choose the `BoundingBox` option. This will wrap the texture around the pearl in the most natural way for a spherical object.
* **Use Case 2 (Globe Pendants):** You have modeled a spherical pendant and want to apply a texture map of the Earth to create a globe effect. `ApplySphericalMapping` is the only standard mapping type that will correctly wrap a world map onto a sphere.

### Other Information
This is a standard mapping primitive for round objects.

---

## 27. ApplySurfaceMapping

### Short Info
Add a surface texture mapping channel to an object.

### Detailed Description
The **ApplySurfaceMapping** command is a texture mapping utility that projects a texture onto an object based on the UV parameter space of a separate surface. This is similar to `ApplyCustomMapping` but is specifically for using a NURBS surface as the projection guide.

### Steps to use the command
1.  Select the object(s) that will receive the texture.
2.  Run the command `ApplySurfaceMapping`.
3.  At the **Select a mapping surface** prompt, select the NURBS surface that will act as the projector.
4.  The texture is applied.

### Command Options & Toggles
This command has no clickable options.

### Note for better use
This command essentially says "take the texture as it would appear on the flat, unwrapped UV space of the guide surface, and project it onto the target object." This is an advanced texturing tool used for very specific situations where other mapping types fail.

### Practical Use Cases
* **Use Case 1 (Irregular Gems):** You have a freeform, baroque-shaped gemstone and want to apply a texture (like stripes or spots) that flows cleanly across its irregular surface. You could create a simpler, smoother "proxy" surface that roughly matches the shape of the gemstone. Apply a clean planar map to this proxy surface. Then, use the proxy surface as the guide in the `ApplySurfaceMapping` command to project the texture onto the complex gemstone.

### Other Information
This command offers a high degree of control for projecting textures onto complex forms.

---

## 28. ApplyWatermark

### Short Info
Embed invisible watermarks in Rhino models.

### Detailed Description
The **ApplyWatermark** command is a utility that embeds an invisible, digital watermark into your Rhino 3DM model file. This watermark is a string of text that you provide. It is not visible in the model itself but can be detected by someone else using the `FindWatermark` command. Its purpose is to help prove ownership or authenticity of a file.

### Steps to use the command
1.  Run the command `ApplyWatermark`.
2.  A dialog box will appear.
3.  Type your desired watermark text (e.g., your name, company, or a unique ID) into the field.
4.  Click OK. The data is embedded in the file.

### Command Options & Toggles
The only option is the text you enter into the dialog box.

### Note for better use
This is not a visual watermark that appears on a render. It is hidden data inside the file itself. While it can help prove ownership, it is not a foolproof security measure, as someone with advanced knowledge could potentially try to remove the data.

### Practical Use Cases
* **Use Case 1 (Proving Ownership):** You are sending a preliminary design file to a new client and want a way to prove that the file originated from you if a dispute arises later. Before sending the file, use `ApplyWatermark` to embed your company name and the date. If you ever need to, you can ask for the file back and use the `FindWatermark` command to show that your hidden signature is present.
* **Use Case 2 (Tracking Versions):** You have multiple versions of a design and want a way to definitively identify which file is which, even if the filename is changed. You can embed a unique version number or code as a watermark in each file (e.g., "Project_Phoenix_V3_Final_Internal").

### Other Information
This is a file utility, not a modeling or design tool.

---

## 29. Arc

### Short Info
Arc by center, start, angle.

### Detailed Description
The **Arc** command is a fundamental 2D drawing tool used to create a circular arc. It provides several different methods for defining the arc's shape, size, and position, making it a very versatile command for creating curved geometry.

### Steps to use the command
1.  Run the command `Arc`.
2.  The command line will show several options for how to create the arc. Click on the desired method (e.g., `Center,Start,Angle` is a common default).
3.  Follow the prompts for that specific method. For `Center,Start,Angle`, you would:
    a. Pick the center point of the arc's circle.
    b. Pick the starting point of the arc.
    c. Pick the end point or type an angle.

### Command Options & Toggles
The options are different methods for creating the arc:
* **Center,Start,Angle:** Defines the arc by its center point, a starting radius point, and the angle it sweeps.
* **Start,End,Point:** Defines the arc by its start point, end point, and a third point that the arc must pass through.
* **Tangent:** Creates an arc that is tangent to one or more existing curves.
* **Deformable:** Creates a higher-degree NURBS curve that is shaped like an arc but has more control points for easier editing.

### Note for better use
The degree of the arc is 2. The `Deformable` option creates a degree 3 NURBS curve approximation of an arc. For creating rounded corners between two lines, the `Fillet` command is often faster than trying to draw a tangent arc manually.

### Practical Use Cases
* **Use Case 1 (Setting Components):** You need to create the curved lower wire (the gallery) of a four-prong setting. In the Top view, you can use the `Arc` command (with the Center, Start, Angle method) to draw a 90-degree arc between two prongs. This can then be copied or arrayed to form the complete gallery.
* **Use Case 2 (Overall Shape):** You want to design an earring in the shape of a crescent moon. You can create this shape by drawing two different arcs using the `Start,End,Point` method and then trimming them against each other.

### Other Information
This is one of the most basic and frequently used curve creation commands.

---

## 30. ArcBlend

### Short Info
Create an arc blend curve between two curves.

### Detailed Description
The **ArcBlend** command creates a special type of blend curve between two other curves. Unlike the standard `BlendCrv` command which creates a complex NURBS curve, `ArcBlend` specifically creates a true circular arc that is tangent to the two input curves. This is useful for situations where a precise, constant-radius connection is required.

### Steps to use the command
1.  Run the command `ArcBlend`.
2.  At the **Select first curve to blend** prompt, click near the end of the first curve.
3.  At the **Select second curve to blend** prompt, click near the end of the second curve.
4.  A preview of the arc blend will appear.
5.  The command completes.

### Command Options & Toggles
This command has no clickable options in the command line.

### Note for better use
The primary advantage of this command is that the resulting blend is a true arc, not a complex spline that approximates an arc. This can be important for manufacturing processes that require simple geometry. You have less control over the shape of the blend compared to `BlendCrv`, as the radius of the arc is determined automatically by the tangency conditions.

### Practical Use Cases
* **Use Case 1 (Smooth Transitions):** You have the top of a pendant and a separate loop for the bail. You need to connect them with a perfectly smooth, circular transition. You can use `ArcBlend` to create a tangent arc between the curve defining the pendant's top edge and the curve defining the bail. This arc can then be used as part of a sweep or network surface.
* **Use Case 2 (Filleting Separate Curves):** You have two curves that do not intersect, but you want to create a rounded corner between them as if they did. The standard `Fillet` command won't work in this case. `ArcBlend` can bridge the gap between the two curves with a tangent arc.

### Other Information
This is a niche command for situations where a true arc is required for blending.

---

## 31. Area

### Short Info
Report an object's area.

### Detailed Description
The **Area** command is an analysis tool that calculates the surface area of one or more objects. It can be used on closed curves, hatches, surfaces, polysurfaces, or meshes. The command reports the calculated area and the absolute error of the calculation in the command line.

### Steps to use the command
1.  Select the object(s) you want to measure.
2.  Run the command `Area`.
3.  The total surface area will be reported in the command history window.

### Command Options & Toggles
This command has no options. It is an immediate calculation.

### Note for better use
The area is reported in the current model's units (e.g., square millimeters, square inches). Make sure your units are set correctly before running the command. If you need to find the geometric center of the area in addition to the measurement, use the `AreaCentroid` command instead. If you select multiple objects, the command will report the cumulative (total) area of all selected objects.

### Practical Use Cases
* **Use Case 1 (Cost Estimation):** A client wants an estimate for a large, flat gold pendant. After modeling the pendant, you can use the `Area` command to find its total surface area. By multiplying this area by the thickness and the density of the gold, you can get a very accurate estimate of the final weight and material cost.
* **Use Case 2 (Enameling):** You are designing a piece that will have enamel applied to a specific recessed area. You need to know how much enamel to prepare. You can use `DupFaceBorder` to create a curve around the area to be enameled, and then use `Area` on that curve to calculate the precise surface area that needs to be covered.

### Other Information
This is a fundamental analysis tool for manufacturing and cost estimation.

---

## 32. AreaCentroid

### Short Info
Report and marks an object's area centroid.

### Detailed Description
The **AreaCentroid** command is an analysis tool that calculates the geometric center of a closed curve, surface, or polysurface. In addition to reporting the coordinates of this center point (the centroid) in the command line, it also places a point object at that location in the model.

### Steps to use the command
1.  Select the object(s) for which you want to find the area centroid.
2.  Run the command `AreaCentroid`.
3.  A point object will be created at the geometric center of the selected object(s).
4.  The coordinates of the centroid will be reported in the command history.

### Command Options & Toggles
This command has no options. It is an immediate action.

### Note for better use
The area centroid is the "center of gravity" of a 2D shape. For a simple circle or square, it's the exact center. For a complex, asymmetrical shape, it's the weighted average center. For finding the center of mass of a 3D solid object, use the `VolumeCentroid` command instead.

### Practical Use Cases
* **Use Case 1 (Finding Balance Point):** You have designed a complex, asymmetrical dangling earring and you need to find the perfect spot to place the bail loop so that it hangs straight. In the Front view, select the curve that outlines the earring's shape. Run `AreaCentroid`. The resulting point object shows you the earring's center of balance. Placing the bail directly above this point will ensure it hangs correctly.
* **Use Case 2 (Centering Elements):** You have a pendant with an organic, irregular outline and you want to place a monogram or a small gem perfectly in its visual center. Use `AreaCentroid` on the pendant's outline. The created point gives you the perfect reference location to begin placing your engraving or center stone.

### Other Information
This is a very useful tool for ensuring aesthetic balance in asymmetrical designs.

---

## 33. AreaMoments

### Short Info
Report an object's area moments of inertia.

### Detailed Description
The **AreaMoments** command is a high-level engineering analysis tool. It calculates the moments of inertia, radius of gyration, and other engineering properties related to the area of planar objects. This is a specialized command used for structural analysis and is not typically used in creative jewelry design.

### Steps to use the command
1.  Select a planar closed curve, surface, or polysurface face.
2.  Run the command `AreaMoments`.
3.  A detailed report of the area moments of inertia and other values is displayed in the command history.

### Command Options & Toggles
This command has no options.

### Note for better use
This command's outputs are primarily useful for engineers calculating how a flat shape might bend or resist twisting under load. The 3D equivalent for solid objects is the `VolumeMoments` command.

### Practical Use Cases
* **Use Case 1 (Non-Jewelry):** An engineer is designing a custom metal bracket and needs to calculate how it will perform under stress. They would run `AreaMoments` on the 2D cross-section of the bracket to get the data needed for their structural calculations. For jewelry design, this command has very limited practical application.

### Other Information
This is a purely technical engineering command.

---

## 34. Array

### Short Info
Copy and space objects in columns, rows, and levels.

### Detailed Description
The **Array** command is a powerful transformation tool that creates multiple copies of selected objects arranged in a three-dimensional grid. You specify the number of copies in the X, Y, and Z directions, and the spacing between them.

### Steps to use the command
1.  Select the object(s) to array.
2.  Run the command `Array`.
3.  You will be prompted for the **"Number in X direction"**. Type a number and press Enter.
4.  You will be prompted for the **"Number in Y direction"**. Type a number and press Enter.
5.  You will be prompted for the **"Number in Z direction"**. Type a number and press Enter.
6.  You will be prompted for **"X spacing or first reference point"**. You can either type a distance or click two points in the viewport to define the spacing and direction for the X-axis copies.
7.  You will then be prompted for Y spacing and Z spacing.
8.  A preview will appear. Press Enter to accept the array.

### Command Options & Toggles
The options are presented as prompts in the command line during the command's sequence.

### Note for better use
To create a simple 2D array (like on a flat surface), simply enter "1" for the Number in Z direction. If you only need to copy objects in a single straight line, the `ArrayLinear` command is faster.

### Practical Use Cases
* **Use Case 1 (Pavé Grids):** You need to create a perfectly spaced, rectangular grid of gemstones on the flat top of a signet ring. Place one gemstone in the corner position. Select it, run `Array`, and specify the number of stones you want in the X and Y directions (e.g., 5 in X, 4 in Y, 1 in Z). Then define the spacing to create the full grid of stones in one operation.
* **Use Case 2 (Chain Modeling):** You have modeled a single link of a box chain and need to create a full section of the chain. You can use `Array` to create a grid of the links. You would then need to manually delete the unnecessary links to form the final chain pattern, but the array command is the fastest way to generate the initial copies.

### Other Information
This is a fundamental tool for creating repeating patterns in a grid.

---

## 35. ArrayCrv

### Short Info
Copy and space objects along a curve.

### Detailed Description
The **ArrayCrv** command is a transformation tool that creates multiple copies of an object spaced evenly along a path defined by a curve. This is one of the most essential commands for jewelry design.

### Steps to use the command
1.  Select the object(s) to array.
2.  Run the command `ArrayCrv`.
3.  At the **Select path curve** prompt, click the curve you want the objects to follow.
4.  A dialog box or command line options will appear allowing you to specify either the **Number** of items or the **Distance** between items.
5.  The command will create the copies along the curve.

### Command Options & Toggles
* **Number:** You specify the exact number of copies you want. The command will space them evenly along the entire length of the curve.
* **Distance:** You specify the exact distance between the centers of each copy. The command will create as many copies as can fit along the curve with that spacing.
* **Orientation (Free/Roadlike):** This controls how the copied objects orient themselves as the curve bends. `Roadlike` is most common for jewelry, as it keeps the object's "up" direction consistent.

### Note for better use
The initial position of your object relative to the start of the path curve is important. It's often best to place the object directly on the start point of the curve before running the command. The direction of the path curve (which can be seen with the `Dir` command) determines the direction the array will be built.

### Practical Use Cases
* **Use Case 1 (Eternity Bands):** The most classic use. You have a ring rail curve and a single gemstone with its setting. You need to create copies of the gem and setting all the way around the ring. Select the gem and setting, run `ArrayCrv`, select the ring rail as the path, and enter the number of gems you want. The command will create a perfectly spaced eternity band.
* **Use Case 2 (Milgrain Edges):** You want to add a decorative milgrain (beaded) edge along the border of a pendant. Model a single tiny sphere (a bead). Select the sphere, run `ArrayCrv`, select the pendant's border curve as the path, and specify a small distance between copies. This will create a perfect milgrain texture.

### Other Information
This is a workhorse command for any design that involves repeating elements along a path.

---

## 36. ArrayCrvOnSrf

### Short Info
Copy and space objects along a curve on a surface.

### Detailed Description
The **ArrayCrvOnSrf** command creates multiple copies of an object and arranges them along a curve that lies on a surface. This is a combination of `ArrayCrv` and `ArraySrf`, ensuring the copied objects follow a specific path while also orienting themselves to be normal (perpendicular) to the underlying surface.

### Steps to use the command
1.  Select the object(s) to array.
2.  Run the command `ArrayCrvOnSrf`.
3.  At the **Select path curve on a surface** prompt, click the curve.
4.  At the **Select base surface** prompt, click the surface the curve is on.
5.  Options will appear to control the number of or distance between copies.
6.  The array will be created.

### Command Options & Toggles
* **Number:** Specify the exact number of copies.
* **Distance:** Specify the distance between copies.
* **Rotation:** Controls how the objects rotate as they follow the curve.

### Note for better use
For this command to work, the path curve must lie directly on the target surface. You can create such a curve with commands like `InterpCrvOnSrf` or by projecting a curve onto a surface (`Project`). When you need objects to follow a specific, non-linear path across a surface (not just a grid), this command is more suitable than `ArraySrf`.

### Practical Use Cases
* **Use Case 1 (Winding Channels):** You have a ring with a channel that winds and curves across its surface. You need to place gemstones inside this channel. Draw a curve down the center of the channel. Select a single gemstone, run `ArrayCrvOnSrf`, select the curve as the path and the ring as the surface. This will place the gems perfectly along the winding path.
* **Use Case 2 (Decorative Vines):** You want to create a vine with leaves that wraps around a curved bracelet. Model one leaf. Draw a curve on the bracelet where the vine's stem should be. Use `ArrayCrvOnSrf` to array the leaf along this curve, ensuring each leaf is attached flush to the bracelet's surface.

### Other Information
This command provides a high level of control for placing objects along a defined path on a 3D surface.

---

## 37. ArrayHole

### Short Info
Copy and space holes in rows and columns.

### Detailed Description
The **ArrayHole** command is a specialized utility that creates multiple copies of a hole on a single, planar surface. It arranges the copied holes in a rectangular grid pattern. This is much faster than manually copying and trimming each hole individually.

### Steps to use the command
1.  Create a planar surface with at least one hole in it.
2.  Run the command `ArrayHole`.
3.  At the **Select hole to array** prompt, click the edge of the hole you want to copy.
4.  You will be prompted for the number of copies in the X and Y directions.
5.  You will then be prompted to define the spacing for the grid.
6.  The new holes will be created on the surface.

### Command Options & Toggles
The options are presented as prompts in the command line, allowing you to specify the **Number** of rows and columns and the **Spacing** between them.

### Note for better use
This command is designed to work on flat surfaces. It will not work on curved surfaces. The hole and the arrayed copies must all be on the same single surface.

### Practical Use Cases
* **Use Case 1 (Grill Patterns):** You are designing a pair of earrings with a flat plate that needs to be perforated with a grid of decorative circular holes. Create a single hole in the plate using the `RoundHole` or `Trim` command. Then, select this hole and use `ArrayHole` to quickly create the entire grid of perforations.
* **Use Case 2 (Enamel Prep):** You are creating a piece that requires a fine mesh of holes for a specific enameling technique (plique-à-jour). `ArrayHole` is the perfect tool for quickly creating a large number of small, evenly spaced holes on the flat base plate before it is shaped.

### Other Information
This is a time-saving utility for creating repeating hole patterns on flat objects.

---

## 38. ArrayHolePolar

### Short Info
Copy and space holes around a central location.

### Detailed Description
The **ArrayHolePolar** command is a specialized utility that creates multiple copies of a hole on a single, planar surface, arranging them in a circular (polar) pattern around a center point.

### Steps to use the command
1.  Create a planar surface with at least one hole in it.
2.  Run the command `ArrayHolePolar`.
3.  At the **Select hole to array** prompt, click the edge of the hole.
4.  At the **Center of polar array** prompt, pick the center point for the circular pattern.
5.  You will be prompted for the number of items and the angle to fill.
6.  The new holes will be created.

### Command Options & Toggles
* **Number:** Specify the total number of holes in the circle (including the original).
* **AngleToFill:** Specify the angle for the array (e.g., 360 for a full circle).
* **Rotate:** If set to Yes, the holes themselves will be rotated as they are copied around the circle.

### Note for better use
Like `ArrayHole`, this command only works on flat surfaces. The accuracy of your array depends on the precise placement of the center point. Use object snaps like `Cen` if you are arranging holes around a central feature.

### Practical Use Cases
* **Use Case 1 (Watch Bezels):** You are designing a watch face and need to create 12 perfectly spaced holes for the hour markers around the dial. Create one hole at the 12 o'clock position. Run `ArrayHolePolar`, select the hole, pick the center of the watch face, and enter 12 for the number of items. This will create all 12 marker holes instantly.
* **Use Case 2 (Filigree Pendants):** You are creating a circular pendant with a repeating pattern of holes arranged like petals of a flower. Create the first hole. Use `ArrayHolePolar` to create the main circular pattern.

### Other Information
This is a time-saving utility for creating repeating circular hole patterns on flat objects.

---

## 39. ArrayLinear

### Short Info
Copy and space objects in a single direction.

### Detailed Description
The **ArrayLinear** command creates multiple copies of objects and spaces them along a single straight line. It is a simplified version of the main `Array` command, used when you only need one row or column of copies.

### Steps to use the command
1.  Select the object(s) to array.
2.  Run the command `ArrayLinear`.
3.  At the **Number of items** prompt, type the total number of copies you want.
4.  At the **First reference point** prompt, pick a starting point (often on the object itself).
5.  At the **Second reference point** prompt, pick a second point. The distance and direction between these two points will define the spacing for the array.
6.  The copies will be created.

### Command Options & Toggles
This command has no clickable options. The number of items and spacing are defined through the prompts.

### Note for better use
When you only need a single row of objects, this command is slightly faster to execute than the full `Array` command because it has fewer prompts. For precise spacing, snap the first and second reference points to existing geometry or use Ortho and enter a distance numerically.

### Practical Use Cases
* **Use Case 1 (Channel Setting):** You are designing a ring with a straight channel and need to place a single row of princess-cut stones side-by-side. Place the first stone at the beginning of the channel. Run `ArrayLinear`, enter the number of stones, and use the corners of the stone to define the spacing. This will create a perfectly spaced row.
* **Use Case 2 (Tennis Bracelets):** You have modeled a single link/setting for a tennis bracelet and need to create a straight section of the bracelet. Use `ArrayLinear` on the single link to quickly generate a straight line of identical links.

### Other Information
This is the simplest of the array commands.

---

## 40. ArrayPolar

### Short Info
Copy and space objects around a central location.

### Detailed Description
The **ArrayPolar** command creates multiple copies of objects arranged in a circular pattern around a center point. This is a fundamental tool for creating any kind of radial design.

### Steps to use the command
1.  Select the object(s) to array.
2.  Run the command `ArrayPolar`.
3.  At the **Center of polar array** prompt, pick the center point for the circular pattern.
4.  At the **Number of items** prompt, type the total number of copies.
5.  At the **Angle to fill** prompt, type an angle (e.g., 360 for a full circle) and press Enter.
6.  A preview will be shown. Press Enter again to accept.

### Command Options & Toggles
* **Items:** The total number of copies (including the original).
* **AngleToFill:** The angle the array will cover.
* **Rotate:** If Yes, the objects will rotate as they are copied around the center. If No, they will maintain their original orientation.
* **ZOffset:** Allows you to move each copy up or down in the Z-axis, creating a spiral or helical array.

### Note for better use
The `Rotate` option is critical. For prongs on a setting, you want `Rotate=Yes`. For gemstones in a halo where the table should always face up, you might want `Rotate=No`. Pay close attention to the preview before you press Enter the final time to ensure the settings are correct.

### Practical Use Cases
* **Use Case 1 (Prong Settings):** The most common use. You have modeled a single prong for a round stone setting and need to create the other three, five, or seven prongs. Select the prong, run `ArrayPolar`, snap to the center of the stone for the center point, enter the number of prongs (e.g., 4), and enter 360 for the angle. The prongs will be created in a perfect circle.
* **Use Case 2 (Halos):** You are creating a halo of small gems around a center stone. Place one small gem in the halo. Use `ArrayPolar` to create the other copies in a perfect circle around the center stone.

### Other Information
This is a workhorse command for any design that involves radial symmetry.

---

## 41. ArraySrf

### Short Info
Copy and space objects in rows and columns on a surface.

### Detailed Description
The **ArraySrf** command is a transformation tool that creates multiple copies of an object and arranges them in a grid pattern across the surface of a target object. The copies are oriented to be normal (perpendicular) to the target surface based on its U and V directions.

### Steps to use the command
1.  Select the object(s) to array.
2.  Run the command `ArraySrf`.
3.  At the **Select base surface** prompt, click the surface you want to arrange the objects on.
4.  You will be prompted for the number of copies in the surface's U and V directions, or the distance between them.
5.  The command will create the array.

### Command Options & Toggles
The options are presented as prompts in the command line, allowing you to specify the **Number** of rows in the U direction and the V direction, or the **Distance** between rows and columns.

### Note for better use
For more complex arrangements where the object needs to bend and deform to match the surface curvature, the `FlowAlongSrf` command is often a better choice. `ArraySrf` simply places copies; it doesn't deform them. The orientation of the copied objects is determined by the target surface's normal direction. Use the `Dir` command to check or flip the surface direction if the objects are pointing the wrong way.

### Practical Use Cases
* **Use Case 1 (Pavé Fields):** You need to cover a curved or domed surface, like the top of a signet ring, with a grid of gemstones. Place a single gemstone at the corner or center of the area. Select the gem, run `ArraySrf`, select the ring's top surface, and then specify the number of rows and columns of gems you want. The command will create the grid, with each gem pointing straight out from the curved surface.
* **Use Case 2 (Textured Patterns):** You want to create a repeating decorative pattern on a curved bracelet, for example, a grid of small pyramids. Model one pyramid. Use `ArraySrf` to copy it across the surface of the bracelet model, creating an instant, perfectly aligned texture.

### Other Information
This command is ideal for creating grid-like patterns on non-planar surfaces.

---

## 42. Arrowhead

### Short Info
Create or remove an arrowhead on a curve.

### Detailed Description
The **Arrowhead** command is a utility that adds or removes arrowhead line types to the end of a curve. This is a 2D drafting and annotation feature. It modifies the curve's properties to display an arrowhead without actually adding any new geometry.

### Steps to use the command
1.  Select the curve(s) you want to modify.
2.  Run the command `Arrowhead`.
3.  The command line will prompt: **"Add arrowhead to curve end? (Yes/No)"**.
4.  Choose Yes or No to add or remove the arrowhead.

### Command Options & Toggles
The options are a simple **Yes/No** choice presented in the command line.

### Note for better use
For creating proper annotation callouts with text, the `Leader` command is the correct tool. `Arrowhead` is for simply making a curve look like an arrow. The size and appearance of the arrowhead may depend on your Print Display settings.

### Practical Use Cases
* **Use Case 1 (Diagrams):** You are creating a quick diagram for a client or your notes to show the flow of a design feature, and you need simple arrows. Draw lines or curves, then use the `Arrowhead` command to turn them into arrows to indicate direction or point to specific features.
* **Use Case 2 (Checking Curve Direction):** You are trying to diagnose a problem with a `Sweep` or `Loft` command and you suspect the direction of one of your curves is wrong. You can temporarily add an arrowhead to the curve. The arrowhead always appears at the end of the curve, giving you a clear, instant visual confirmation of its direction.

### Other Information
This is a simple display property modifier for curves.

---

## 43. AssignBlankTexture

### Short Info
Assign texture names to objects.

### Detailed Description
The **AssignBlankTexture** command is a highly specialized utility for developers and advanced users. Its purpose is to assign a texture name to an object's texture channel *before* an actual material or texture bitmap has been assigned. This essentially creates an empty, named placeholder for a texture that can be referenced by scripts or specific rendering plugins.

### Steps to use the command
1.  Select the object(s).
2.  Run the command `AssignBlankTexture`.
3.  At the prompt, type a name for the texture and press Enter.

### Command Options & Toggles
This command has no clickable options. The only input is the texture name you provide.

### Note for better use
This is not a command used in typical day-to-day modeling. Its primary function is to set up objects so they can be manipulated by scripts or external programs that need to find and replace textures by name. Running this command will not produce any visible change on the object in the viewport.

### Practical Use Cases
* **Use Case 1 (Advanced Scripting):** A developer is writing a script that automatically applies specific materials to a model. The script needs to know which texture (e.g., "wood_grain," "metal_finish") goes on which part. The 3D modeler could use `AssignBlankTexture` to pre-name the texture slots on each part of the model. The script could then find the object with the "wood_grain" texture name and apply the corresponding wood material to it. This command has virtually no practical use in standard jewelry design.

### Other Information
This is a developer-level tool for managing texture data within a model.

---

## 44. AttachGHSData

### Short Info
Add GHS information to objects.

### Detailed Description
The **AttachGHSData** command is an extremely specialized command used exclusively for naval architecture (ship and boat design). GHS stands for "General HydroStatics." This command attaches specific data to surfaces in the model that is required by GHS software to perform calculations like buoyancy, stability, and fluid dynamics.

### Steps to use the command
1.  Run the command `AttachGHSData`.
2.  Follow the specific prompts related to GHS data types (e.g., defining hull sections, tanks, etc.).

### Command Options & Toggles
The command has various options related to naval architecture, such as defining the type of data being attached.

### Note for better use
This command has absolutely no application in jewelry design or any other field outside of naval architecture. It is a tool for a very specific industry workflow.

### Practical Use Cases
* **Use Case 1 (Ship Design):** A naval architect has modeled the hull of a ship in Rhino and needs to analyze its hydrostatic properties. They would use `AttachGHSData` to label the different parts of the hull surface with data that the GHS software can read and use for its calculations.

### Other Information
This is a third-party plug-in command for a specific engineering discipline.

---

## 45. Autosave

### Short Info
Save the current model to a backup file.

### Detailed Description
The **Autosave** command is a utility that saves the current model to a backup file. This command can be used to manually trigger an autosave, but it is more commonly used to set the options for Rhino's automatic saving feature. This feature helps prevent data loss in case of a crash or power outage by periodically saving a copy of your work in the background.

### Steps to use the command
1.  Run the command `Autosave`.
2.  The Rhino Options window will open to the "Files" page.
3.  Under the "Autosave" section, you can configure the settings.
4.  Click "OK" to save the settings.

### Command Options & Toggles
The options are located in the Options > Files dialog box:
* **Save every X minutes:** This checkbox enables or disables the autosave feature and lets you set the time interval between saves.
* **Autosave file:** This field shows the location where the autosave file will be stored. You can change this to a different folder.
* **Always save before:** This section has options to automatically save before running potentially unstable commands like rendering or meshing.

### Note for better use
Autosave is a safety net, not a replacement for manually saving your work (`Save` or Ctrl+S). Get in the habit of saving frequently. The autosave file is typically stored in a hidden AppData folder. When Rhino starts after a crash, it should automatically detect this file and ask if you want to recover it. Setting the autosave interval too low (e.g., 1 minute) on a very large file can cause noticeable pauses in your workflow.

### Practical Use Cases
* **Use Case 1 (Crash Recovery):** You have been working for an hour on a complex design and the program suddenly crashes. When you restart Rhino, it will detect the autosaved file and prompt you to recover it, potentially saving you from losing a significant amount of work.
* **Use Case 2 (Custom Folder):** You work on multiple computers or want your autosave files to be stored in a more accessible location, like a Dropbox folder. Use the `Autosave` command to open the options and change the "Autosave file" path to your desired folder.

### Other Information
Properly configuring your autosave settings is one of the most important things you can do to prevent data loss.

---

## 46. BackgroundBitmap

### Short Info
Manage a background image in a viewport.

### Detailed Description
The **BackgroundBitmap** command (also known as `Wallpaper` in some contexts) places an image in the background of a single viewport. This image does not move or scale with the view; it remains fixed like wallpaper. Its primary purpose is to serve as a 2D reference for tracing or modeling.

### Steps to use the command
1.  Make the desired viewport active (e.g., the Front view).
2.  Run the command `BackgroundBitmap`.
3.  The command line will present several options. Click **Place**.
4.  A file browser will open. Select your image file.
5.  You will be prompted to place the corners of the image in the viewport.
6.  The image will appear in the background of that viewport.

### Command Options & Toggles
* **Place:** Allows you to place a new image.
* **Remove:** Deletes the background image from the active viewport.
* **Align:** Provides tools to help you position the image.
* **Grayscale:** Toggles the image display between color and grayscale.
* **Visible:** Toggles the visibility of the image on or off.

### Note for better use
If you need an image that is an actual object in your scene (one that you can move, scale, and see in perspective), use the `PictureFrame` command instead. `BackgroundBitmap` is a 2D overlay only. Each viewport can have its own unique background bitmap.

### Practical Use Cases
* **Use Case 1 (Tracing):** A client has provided a hand-drawn sketch of a pendant that you need to model. In the Front viewport, use `BackgroundBitmap` to place the scanned sketch. You can then use the Curve tools to trace the outline and details directly over the image.
* **Use Case 2 (Side Profile Modeling):** You are modeling a ring and have a reference photo of its side profile. Place this image in the Right viewport. This allows you to model the ring's profile accurately, making sure the stone is at the correct height and the shank has the proper curvature.

### Other Information
This is an essential tool for modelers who work from existing sketches or reference images.

---

## 47. Bake

### Short Info
Combine an object's textures and decals into a single bitmap file and assigns that bitmap as the object's texture.

### Detailed Description
The **Bake** command is a rendering utility. Its purpose is to take an object that has complex materials, textures, and decals applied to it, and "bake" all of that visual information into a single, simple image file (a bitmap). It then creates a new material using that baked image and applies it to the object. This is a way of simplifying complex render setups into a single texture map.

### Steps to use the command
1.  Select an object with materials and textures applied.
2.  Run the command `Bake`.
3.  A dialog box will appear asking for the file name, location, and resolution of the new bitmap image to be created.
4.  Configure the settings and click OK.
5.  Rhino will render the object's appearance from all sides and save it as an image, then apply that image back to the object as a simple texture.

### Command Options & Toggles
The options are contained within the save file dialog box and subsequent settings windows, allowing you to control the **File Format** (JPG, PNG, TGA, etc.), **Image Resolution**, and other rendering parameters.

### Note for better use
This command is very common in game development and real-time rendering, where complex materials are too slow. By baking lighting and textures into a single map, performance is greatly improved. For the bake to work correctly on a complex object, the object must have a proper UV texture map (unwrapped). You can create this using the `Unwrap` command.

### Practical Use Cases
* **Use Case 1 (Real-Time Viewers):** You have designed a ring with complex procedural materials and you want to show it in a real-time web viewer or game engine that doesn't support those advanced materials. You would first `Unwrap` the ring to create a UV map. Then, use `Bake` to capture the appearance of the complex materials as a single image texture.
* **Use Case 2 (Sharing Models):** You have created a perfect material using multiple layers and procedural textures, and you want to share the model with someone without having to send them all the individual texture files. Baking the material consolidates everything into one image file that can be easily shared and applied to the model.

### Other Information
This is an advanced rendering technique used to optimize models for other applications.

---

## 48. Bend

### Short Info
Deform objects along an arc.

### Detailed Description
The **Bend** command is a deformation tool that deforms objects along an arc. It works by asking you to define a "spine" line and then an arc to bend the object to. The part of the object at the start of the spine will be bent the most, while the part at the end will be bent the least.

### Steps to use the command
1.  Select the object(s) to bend.
2.  Run the command `Bend`.
3.  At the **Start of spine** prompt, pick a point to start the axis around which the object will bend.
4.  At the **End of spine** prompt, pick a second point to define the length and orientation of the spine.
5.  At the **Point to bend through** prompt, click a third point to define the arc and amount of the bend. The object will deform in real-time as you move the mouse.

### Command Options & Toggles
* **Symmetric:** When this option is set to Yes, the bend is created symmetrically around the center of the spine.
* **Copy:** Creates a new, bent copy of the object instead of modifying the original.

### Note for better use
The `Bend` command works best on straight objects. Bending an object that is already curved can produce unpredictable results. Objects with more control points will deform more smoothly. If a bent object looks jagged, you may need to `Rebuild` it with more points before bending.

### Practical Use Cases
* **Use Case 1 (Ring Making):** You have designed a flat, straight strip with a detailed pattern on it. You now need to bend this strip into a circular ring. Select the flat pattern, run `Bend`, for the spine, pick the two endpoints of the straight strip, and for the "point to bend through," snap to the start point again and drag the object into a full circle.
* **Use Case 2 (Shank Shaping):** You have modeled two straight shanks that you want to curve and cross over each other in a bypass style. You can use the `Bend` command on each straight shank individually to give them the gentle curve needed to form the bypass shape.

### Other Information
This is a core deformation tool for turning flat patterns into curved objects.

---

## 49. Blend

### Short Info
Connect two curves maintaining continuity.

### Detailed Description
The **Blend** command creates a new curve that smoothly connects two existing curves. This is a simplified version of the more powerful `BlendCrv` command. It attempts to create a smooth, tangent connection between the endpoints of the two curves you select.

### Steps to use the command
1.  Run the command `Blend`.
2.  At the **Select curve to blend from** prompt, click near the end of the first curve.
3.  At the **Select curve to blend to** prompt, click near the end of the second curve.
4.  A new curve is created connecting the two.

### Command Options & Toggles
This command has no options in its basic form. For more control, you must use `BlendCrv`.

### Note for better use
For almost all design situations, the `BlendCrv` command is superior because it provides a dialog box with sliders to control the continuity (smoothness) of the blend. Use `Blend` only for very quick, non-critical connections. The direction of the input curves can affect the shape of the resulting blend.

### Practical Use Cases
* **Use Case 1 (Quick Connection):** You have two separate line segments that need to be connected with a smooth curve to form a single shape. `Blend` provides a one-click method to bridge the gap. You can then `Join` the three curves together.
* **Use Case 2 (Sketching):** In the early stages of a design, you are quickly sketching out ideas with curves and need to connect parts loosely. `Blend` is useful for this kind of rough concept modeling where precise continuity is not yet required.

### Other Information
This is a quick but imprecise tool. `BlendCrv` is the preferred professional tool.

---

## 50. BlendCrv

### Short Info
Connect two curves with continuity control.

### Detailed Description
The **BlendCrv** command is one of the most important curve creation tools in Rhino. It creates a smooth, continuous curve that connects the endpoints of two other curves. Unlike the simpler `Blend` command, `BlendCrv` opens a dialog box that gives you precise, interactive control over the shape and smoothness (continuity) of the connecting curve at each end.

### Steps to use the command
1.  Run the command `BlendCrv`.
2.  At the **Select first curve to blend** prompt, click near the end of the first curve.
3.  At the **Select second curve to blend** prompt, click near the end of the second curve.
4.  A dialog box will appear, and a preview of the blend curve will be shown.
5.  Adjust the sliders and options in the dialog box to change the shape of the blend.
6.  Click OK to create the curve.

### Command Options & Toggles
The options are in the dialog box:
* **Continuity Sliders (1 and 2):** These sliders control the smoothness of the connection at each end. The options are:
    * **Position (G0):** The curves just touch.
    * **Tangency (G1):** The curves touch and are pointing in the same direction (no sharp corner).
    * **Curvature (G2):** A very smooth transition where the curvature matches. This is the most common for high-quality surfaces.
* **Trim:** Trims the original curves back to the new blend curve.
* **Join:** Joins the original curves and the new blend curve into a single curve.

### Note for better use
Use the `ShowCurvatureGraph` command on the results to help visualize the smoothness of the curves. A smooth curvature graph indicates a good surface. For creating high-quality, seamless surfaces (a "Class A" surface), you should almost always aim for Curvature (G2) continuity on your blends.

### Practical Use Cases
* **Use Case 1 (Cathedral Rings):** You have the bottom part of a ring shank and the head/setting. You need to create the smooth, sweeping "cathedral" arms that connect the two. Use `BlendCrv` with Curvature (G2) continuity to create a perfectly smooth curve connecting the shank to the head. This curve can then be used as a rail for the `Sweep1` or `Sweep2` command.
* **Use Case 2 (Infinity Symbols):** You want to create a perfect infinity symbol shape from two circles. Place two circles next to each other, `Trim` away the inner halves, then use `BlendCrv` to create the smooth, twisting connections in the middle.

### Other Information
Mastering `BlendCrv` is essential for creating high-quality, organic shapes.

---

## 51. BlendEdge

### Short Info
Create a surface between polysurface edges maintaining continuity.

### Detailed Description
The **BlendEdge** command creates a smooth, transitional surface between two selected polysurface edges. It is similar to `FilletEdge` (which creates a constant-radius round) but offers much more control over the shape and continuity of the blend, similar to how `BlendCrv` is more advanced than `Fillet` for curves.

### Steps to use the command
1.  Run the command `BlendEdge`.
2.  At the **Select edges for first side** prompt, select one or more edges and press Enter.
3.  At the **Select edges for second side** prompt, select one or more edges and press Enter.
4.  A dialog box appears, allowing you to adjust the continuity and shape of the blend surface.
5.  Click OK to create the surface.

### Command Options & Toggles
The options are in a dialog box, similar to `BlendCrv`:
* **Continuity Sliders (1 and 2):** Control the smoothness (Position, Tangency, Curvature) of the blend where it meets each of the original surfaces.
* **Add Shapes:** Allows you to add cross-section curves to further control the shape of the blend along its length.

### Note for better use
This command is ideal for situations where a simple round fillet is not desired. It allows you to create more organic, flowing transitions between surfaces. The command works best on clean, un-trimmed, or simply-trimmed edges.

### Practical Use Cases
* **Use Case 1 (Soft Transitions):** You have a ring shank where the side profile meets the top surface, and you want a very soft, organic transition that is smoother than a standard fillet. Use `BlendEdge` and set both sides to Curvature (G2) continuity. This will create a visually seamless transition that will catch the light beautifully when polished.
* **Use Case 2 (Blending Sculpted Elements):** You have a sculpted leaf or flower that you have placed on top of a ring, and you want to blend it smoothly into the ring's surface. `BlendEdge` can create a beautiful, flowing transition between the base of the sculpted element and the main surface of the ring.

### Other Information
This is an advanced surfacing tool for creating high-quality transitions between connected edges of a single object.

---

## 52. BlendSrf

### Short Info
Create a blend surface between two surfaces with continuity control.

### Detailed Description
The **BlendSrf** command creates a smooth transitional surface between two existing surface edges. This is one of the most powerful and important surface creation tools for creating high-quality, organic models. It provides interactive control over the shape and continuity (smoothness) of the blend, ensuring a seamless connection between the two original surfaces.

### Steps to use the command
1.  Run the command `BlendSrf`.
2.  At the **Select first edge** prompt, click on the edge of the first surface.
3.  At the **Select second edge** prompt, click on the edge of the second surface.
4.  A dialog box will appear, and a preview of the blend surface will be shown.
5.  Adjust the sliders and options in the dialog box to change the shape of the blend.
6.  Click OK to create the surface.

### Command Options & Toggles
The options are in the dialog box:
* **Continuity Sliders (1 and 2):** Control the smoothness (Position, Tangency, Curvature) of the blend where it meets each of the original surface edges.
* **Add Shapes:** Allows you to add cross-section curves to further control the shape of the blend along its length.
* **Planar sections:** Forces the shape curves to be planar.

### Note for better use
Sometimes a blend surface can twist. This can be caused by the surface normals not pointing in the same general direction. Use the `Dir` command to see the normal direction. For the best results, the seam points of the two edges you are blending should be aligned. You can use the `SrfSeam` command to adjust them before running `BlendSrf`.

### Practical Use Cases
* **Use Case 1 (Cathedral Shanks):** This is a primary tool for this task. You have the bottom of the shank and the head/setting modeled as separate surfaces. You need to create the sweeping arms. Use `BlendSrf` to create a surface between the top edge of the shank and the bottom edge of the head. By adjusting the control points and setting the continuity to Curvature, you can create a perfect, flowing cathedral shank.
* **Use Case 2 (Closing Gaps):** You have modeled two parts of a complex, organic bracelet, and there is a gap between them that needs to be filled with a smooth, transitional surface. `BlendSrf` is the ideal tool to bridge the gap between the two surface edges, creating a single, seamless-looking object.

### Other Information
Mastering `BlendSrf` is essential for creating high-quality, freeform surfaces between separate objects.

---

## 53. Block

### Short Info
Define a block object.

### Detailed Description
The **Block** command is an organizational tool that lets you define a collection of objects as a single, reusable component called a "block definition." You can then insert multiple copies, called "block instances," of this definition throughout your model. The key feature is that if you edit the original block definition, all instances of that block in your model will update automatically.

### Steps to use the command
1.  Select the object(s) you want to include in the block.
2.  Run the command `Block`.
3.  A dialog box will appear.
4.  You will be prompted for a **"Base point"**. This is the insertion point for the block.
5.  Give the block a name.
6.  Click OK. The selected objects will be converted into a block instance.

### Command Options & Toggles
The options are in the dialog box:
* **Name:** The name for the block definition.
* **Description:** An optional text description.
* **Base point:** The point from which the block will be inserted.
* **Instance behavior (Hyperlink, etc.):** Advanced options for how the block can be linked.

### Note for better use
A Group is just a simple selection set. A Block is a powerful component definition. If you have 100 copies of a grouped object and need to change one, you have to change all 100 individually. If you have 100 instances of a block, you only need to edit the block definition once, and all 100 will update. Using blocks can also significantly reduce your file size.

### Practical Use Cases
* **Use Case 1 (Managing Gemstones):** You are designing a piece with dozens of 1.5mm round diamonds. Model one 1.5mm diamond and turn it into a block named "Diamond_1.5mm". Now, insert instances of this block wherever you need a stone. If you later decide to change the diamond's model, you only need to edit the one block definition, and all the diamonds in your piece will update instantly.
* **Use Case 2 (Reusable Components):** You have designed a custom 4-prong setting that you use frequently in your designs. Turn the entire setting into a block. You can then insert this block into any new design. This saves you from having to remodel it every time.

### Other Information
Blocks are a powerful tool for efficiency, organization, and file size management in complex models.

---

## 54. BlockEdit

### Short Info
Select a block instance to change the block geometry and update the block definition.

### Detailed Description
The **BlockEdit** command is the tool used to modify the geometry within a block definition. When you run this command and select a block instance, it temporarily opens a special editing session where only the objects inside that block are visible and editable. Any changes you make are saved to the block definition. When you exit the editing session, all instances of that block throughout your model will update to reflect your changes.

### Steps to use the command
1.  Run the command `BlockEdit`.
2.  At the **Select block instance to edit** prompt, click on one of the blocks in your model.
3.  A dialog box will appear listing the block name. Click OK.
4.  Your screen will change, hiding all other objects. You are now in the block editing mode.
5.  Make any desired changes to the geometry.
6.  When you are finished, run the `BlockEdit` command again or click the "OK" button in the small "Editing block" window that appears.
7.  All instances of the block will now be updated.

### Command Options & Toggles
The options are in the initial dialog box:
* **Block name list:** If the block you select is nested inside another block, this list allows you to choose which level of the block you want to edit.

### Note for better use
While in block edit mode, you can add new objects to the block or delete existing ones. You can also change the block's base point while in the editing session.

### Practical Use Cases
* **Use Case 1 (Changing Gem Proportions):** You have used a block for all the 1.5mm diamonds in your model. You now decide that the pavilion of the diamond model is too deep. Run `BlockEdit` on any one of the diamond instances. In the editing session, scale the pavilion to make it shallower. When you exit, all the diamonds in your entire piece will update.
* **Use Case 2 (Modifying a Setting):** You have used your custom 4-prong setting block in a new design, but for this particular ring, the prongs need to be slightly thicker. Use `BlockEdit` to open the setting's block definition. Thicken the prongs. When you exit, the setting in your current design will be updated.

### Other Information
This is the only way to edit the contents of a block definition after it has been created.

---

## 55. BlockManager

### Short Info
Manage the block definitions in the model.

### Detailed Description
The **BlockManager** command opens a dialog box that lists all of the block definitions in your current model. It is the central hub for managing, viewing, and modifying your blocks. It allows you to see how many instances of each block exist, update blocks that are linked to external files, and perform other maintenance tasks.

### Steps to use the command
1.  Run the command `BlockManager`.
2.  The Block Manager dialog box will appear, listing all block definitions in the file.
3.  Select a block from the list to see its properties and a preview.
4.  Use the buttons on the right to manage the selected block.

### Command Options & Toggles
The options are the buttons within the dialog box:
* **Properties:** Shows details about the selected block definition.
* **Update:** If a block is linked to an external file that has changed, this button will update the block to the newer version.
* **Export:** Saves the selected block definition as a separate .3dm file.
* **Delete:** Deletes a block definition (only works if there are no instances of it in the model).
* **Count:** Reports how many instances of the selected block are in the model.

### Note for better use
You can create blocks that are linked to an external Rhino file. This is very powerful for team collaboration. If one person updates the external file (e.g., changes the design of a standard clasp), everyone else using that linked block will be notified in the `BlockManager` that an update is available. If you have deleted all instances of a block, its definition still exists in the file. You can use the `Purge` command or the `Delete` button in the `BlockManager` to remove these unused definitions.

### Practical Use Cases
* **Use Case 1 (Stone Counting):** You are preparing a file for a client and want to see how many of each size of gemstone are used in the design. Open `BlockManager`. It will list all of your gemstone blocks (e.g., "Diamond_1.5mm", "Sapphire_3mm"). By selecting each one and clicking "Count," you can quickly generate an accurate stone count for the entire piece.
* **Use Case 2 (Updating Components):** Your company uses a standard logo that is inserted as a linked block on all signet rings. The logo has recently been redesigned. You would update the external logo file. Then, in each ring file, you would open `BlockManager`, select the linked logo block (it will be marked as "out of date"), and click "Update." The new logo will automatically replace the old one.

### Other Information
This is the main interface for managing all block-related data in a file.

---

## 56. Boolean2Objects

### Short Info
Cycle through Boolean operations for two objects.

### Detailed Description
The **Boolean2Objects** command is an interactive utility that helps you visualize the results of all possible boolean operations between two objects. When you run the command, it cycles through the four possible outcomes—Union, Difference A-B, Difference B-A, and Intersection—allowing you to see a preview of each one before committing. This is very useful when you are unsure which specific boolean command will give you the result you need.

### Steps to use the command
1.  Select two objects that overlap.
2.  Run the command `Boolean2Objects`.
3.  The command line will show the first result (e.g., Union).
4.  Keep clicking the mouse or pressing Enter to cycle through the other possible results.
5.  When you see the result you want, stop clicking. The command will time out and create that geometry.

### Command Options & Toggles
This command has no clickable options. The "options" are the different results that you cycle through by pressing Enter.

### Note for better use
This is an excellent command for beginners who are still learning the difference between the various boolean operations. It can also be useful for complex shapes where it's not immediately obvious what the intersection or difference will look like.

### Practical Use Cases
* **Use Case 1 (Figuring Out Cuts):** You have a complex, sculptural ring shank and an equally complex cutter for a gallery opening. You are not sure if you need to subtract the cutter from the shank, or the shank from the cutter, or find their intersection. Select both objects and run `Boolean2Objects`. You can cycle through all the possibilities and visually identify the correct operation.
* **Use Case 2 (Design Exploration):** You have two intersecting organic shapes and are exploring different ways they could be combined to create a pendant. `Boolean2Objects` lets you quickly see if the merged shape (Union), the interlocking shape (Intersection), or one shape carved out of the other (Difference) produces the most aesthetically pleasing design.

### Other Information
This is a helpful utility that combines four commands into one interactive sequence.

---

## 57. BooleanDifference

### Short Info
Subtract the volume of one set of objects from another.

### Detailed Description
The **BooleanDifference** command is a fundamental solid modeling tool that subtracts the volume of one set of objects from another. It is the primary command used for creating holes, engravings, and cuts in 3D models.

### Steps to use the command
1.  Run the command `BooleanDifference`.
2.  At the **Select surfaces or polysurfaces to subtract from** prompt, select the main object that you want to cut into, and press Enter.
3.  At the **Select surfaces or polysurfaces to subtract with** prompt, select the cutting object(s), and press Enter.
4.  The volume of the second set of objects will be removed from the first object.

### Command Options & Toggles
* **DeleteInput:**
    * **Yes:** The original cutting object is deleted after the operation. This is the default.
    * **No:** The original cutting object is kept. This is useful if you need to use the same cutter multiple times.

### Note for better use
For boolean operations to work reliably, both objects must be "closed solids" (also called watertight or manifold). Use the `ShowEdges` command to check for any naked edges before running the command. Booleans can sometimes fail if the two objects have perfectly overlapping (co-planar) faces. It's often helpful to make your cutting object slightly larger than the area you want to cut to ensure a clean intersection.

### Practical Use Cases
* **Use Case 1 (Cutting Gem Seats):** The most common use in jewelry CAD. You have a ring and a "gem cutter" (a solid object representing the shape of the gem's pavilion). You need to create the seat for the stone. Run `BooleanDifference`. Select the ring as the object to subtract from. Select the gem cutter as the object to subtract with. The result is a perfectly shaped seat inside the ring.
* **Use Case 2 (Engraving):** You have created raised, solid letters or a pattern that you want to engrave into the surface of a ring. Run `BooleanDifference`, select the ring, and then select the letters. The letters will be subtracted from the ring, leaving an engraved impression.

### Other Information
This is one of the most frequently used commands in solid modeling.

---

## 58. BooleanIntersection

### Short Info
Create a new solid from solids' intersected volumes.

### Detailed Description
The **BooleanIntersection** command is a solid modeling tool that calculates the shared, overlapping volume between two or more solid objects and creates a new solid object from only that volume. All parts of the original objects that do not overlap are discarded.

### Steps to use the command
1.  Run the command `BooleanIntersection`.
2.  At the **Select first set of surfaces or polysurfaces** prompt, select the first object(s) and press Enter.
3.  At the **Select second set of surfaces or polysurfaces** prompt, select the second object(s) and press Enter.
4.  A new solid object is created from the volume where all the selected objects overlapped.

### Command Options & Toggles
* **DeleteInput:** Determines whether the original objects are deleted after the operation.

### Note for better use
Like all booleans, this command works best when all input objects are closed solids. It can sometimes be difficult to predict what the intersection of two complex objects will look like. It's often helpful to use a transparent display mode to see where the objects overlap before running the command.

### Practical Use Cases
* **Use Case 1 (Custom Gems):** You want to create a gemstone that is shaped like a heart, but also has a standard brilliant-cut pavilion. Model a heart-shaped solid and a standard round brilliant cone-shaped solid. Place them so they overlap. Run `BooleanIntersection`. The result will be a new solid that has the outline of the heart and the faceting of the cone.
* **Use Case 2 (Finding Bezel Seats):** You have a complex, organic-shaped ring and a gemstone, and you need to create a bezel that perfectly matches the shape of the ring where the stone sits. Create a simple solid that represents the bezel (e.g., a `Pipe` around the stone). Intersect this bezel solid with the main ring solid. The result of the `BooleanIntersection` is the exact volume of the bezel that is "inside" the ring, which can then be used to create a perfect seat.

### Other Information
This command is useful for creating complex shapes that would be difficult to model directly.

---

## 59. BooleanSplit

### Short Info
Split and close solids at intersections.

### Detailed Description
The **BooleanSplit** command is a solid modeling tool that splits one set of objects where they are intersected by another set of objects. Unlike `BooleanDifference`, which deletes the cutter and the cut-out portion, `BooleanSplit` keeps all the resulting pieces.

### Steps to use the command
1.  Run the command `BooleanSplit`.
2.  At the **Select objects to split** prompt, select the object(s) you want to cut and press Enter.
3.  At the **Select cutting objects** prompt, select the object(s) that will act as the cutters and press Enter.
4.  The first object will be split into multiple, separate solid pieces. The cutting object will remain.

### Command Options & Toggles
* **DeleteInput:** In this command, this option is typically not available as the cutter is kept by default.

### Note for better use
The key difference between this and `BooleanDifference` is that `BooleanSplit` does not delete anything. It simply splits the target object into separate pieces that you can then move, edit, or delete manually. This command is often used when a standard `BooleanDifference` fails or when you need more control over the cutting process.

### Practical Use Cases
* **Use Case 1 (Two-Tone Rings):** You have a single, solid ring model and you want to split it into a yellow gold part and a white gold part along a curved seam. Create a surface that passes through the ring where you want the split to occur. Use this surface as the "cutting object" in the `BooleanSplit` command. The ring will be split into two separate, perfectly fitting solids that can be assigned different materials.
* **Use Case 2 (Hollowing Lockets):** You have a solid locket shape and you want to hollow it out, creating the main body and the lid as two separate pieces. Create a plane or surface that cuts through the locket where the lid should separate. Use this plane to `BooleanSplit` the locket. This will result in two perfectly matching halves.

### Other Information
This is a more controlled and less destructive alternative to `BooleanDifference`.

---

## 60. BooleanUnion

### Short Info
Combine the volumes of one or more objects.

### Detailed Description
The **BooleanUnion** command is a fundamental solid modeling tool that merges two or more overlapping solid objects into a single, continuous solid. It removes the interior, overlapping surfaces, resulting in one clean, manifold object.

### Steps to use the command
1.  Select two or more overlapping solid objects.
2.  Run the command `BooleanUnion`.
3.  The objects will be merged into a single polysurface.

### Command Options & Toggles
* **DeleteInput:** This is not an option, as the input objects are consumed to create the new, single object.

### Note for better use
For the union to work correctly, all input objects must be closed solids. The objects must physically intersect each other. If they are only touching at an edge or a point, the command will fail. Boolean Union is often one of the final steps in creating a model for 3D printing, as it ensures the entire piece is a single, continuous mesh.

### Practical Use Cases
* **Use Case 1 (Attaching Prongs):** You have modeled a ring shank and four separate prongs for a setting. To make it a single, manufacturable piece, they must be joined. Move the prongs so that they are intersecting the ring shank. Select the shank and all four prongs. Run `BooleanUnion`. The result is a single, solid ring with the prongs seamlessly attached.
* **Use Case 2 (Combining Elements):** You have a base ring and have added several decorative elements like leaves, scrolls, or beads that are currently separate, overlapping objects. Select the base ring and all the decorative elements and run `BooleanUnion`. This will fuse everything together into one solid piece, ready for casting.

### Other Information
This is a critical command for ensuring a model is a single, solid piece for manufacturing.

---

## 61. Boss

### Short Info
Extrude closed planar curves normal to the curve plane toward a boundary surface.

### Detailed Description
The **Boss** command is a specialized solid creation tool. It extrudes a closed, planar curve perpendicular to its plane until it meets a boundary surface. It then automatically trims the boundary surface and joins the extruded shape to it, creating a raised "boss" feature. This command combines several steps (`ExtrudeCrv`, `Trim`, `Join`) into a single, efficient operation.

### Steps to use the command
1.  Run the command `Boss`.
2.  At the **Select planar closed curves for boss base** prompt, select the curve and press Enter.
3.  At the **Select boundary surface** prompt, select the surface.
4.  The curve will be extruded and joined to the surface.

### Command Options & Toggles
This command has no clickable options in the command line.

### Note for better use
The extrusion always happens in the direction normal (perpendicular) to the curve's plane. This command is most effective when the boundary surface completely covers the area above the profile curve.

### Practical Use Cases
* **Use Case 1 (Raised Bezels):** You have the curved surface of a signet ring and you have drawn a circle on the CPlane below it where you want to add a raised bezel. Run `Boss`, select the circle as the curve, and the ring surface as the boundary. The command will extrude the circle straight up until it meets the curved surface, trimming the top of the extrusion to match the curve and joining it to the ring seamlessly.
* **Use Case 2 (Adding Feet):** You have modeled the curved bottom surface of a decorative box and have drawn the 2D profiles of the feet on the CPlane. The `Boss` command can be used to extrude these profiles up to meet the curved bottom, creating perfectly fitting feet that are already joined.

### Other Information
This is a powerful tool for adding features to curved surfaces without complex trimming and joining operations.

---

## 62. Bounce

### Short Info
Shoot a ray at a collection of surfaces to create a polyline path.

### Detailed Description
The **Bounce** command is a specialized analysis tool that traces the path of a bouncing ray. You define a starting point and direction for a ray, and the command calculates its path as it bounces off a collection of surfaces, creating a polyline that represents this path.

### Steps to use the command
1.  Run the command `Bounce`.
2.  At the **Select surfaces for bounce** prompt, select the surfaces the ray will bounce off and press Enter.
3.  At the **Start of ray** prompt, pick a point.
4.  At the **Direction of ray** prompt, pick a second point to define the direction.
5.  A polyline representing the bounce path will be created.

### Command Options & Toggles
* **MaxBounces:** Sets the maximum number of times the ray is allowed to bounce before the command stops.

### Note for better use
This command simulates a very simplified version of ray tracing and can be used to understand how light might reflect inside a geometric shape. This is a geometric analysis tool, not a rendering tool. It does not calculate light color or intensity.

### Practical Use Cases
* **Use Case 1 (Gemstone Optics):** You have modeled a custom-cut gemstone and want to visualize how a ray of light might travel and reflect off the internal facets. You can use `Bounce` to trace a path starting from the top of the stone, helping you to understand its light performance and identify any areas where light might be "leaking" out the bottom instead of reflecting back to the top.

### Other Information
This is a highly specialized analysis tool with niche applications.

---

## 63. BoundingBox

### Short Info
Create a polyline or solid that encloses objects.

### Detailed Description
The **BoundingBox** command creates a box that represents the extents of an object or group of objects. It calculates the smallest possible rectangular box, aligned with the active CPlane or the world axes, that can completely enclose the selected geometry.

### Steps to use the command
1.  Select the object(s) you want to enclose.
2.  Run the command `BoundingBox`.
3.  A dialog box or command line options will appear.
4.  Choose your options and press Enter. A box will be created.

### Command Options & Toggles
* **Output (Curves/Surfaces/Mesh):** You can choose whether the resulting box is made of wireframe curves, a solid polysurface, or a mesh.
* **CoordinateSystem (CPlane/World):** You can choose whether the box is aligned to the active construction plane's axes or the world's X, Y, and Z axes.

### Note for better use
This is the fastest way to get the overall length, width, and height of a complex or rotated object. Bounding boxes are useful for seeing the space an object occupies, which can help when arranging multiple items for 3D printing.

### Practical Use Cases
* **Use Case 1 (Dimensions):** You have imported a complex, faceted gemstone model and need to know its exact length, width, and depth to build a setting for it. Select the gemstone, run `BoundingBox` (with the output set to Curves), and the resulting box will give you a simple frame from which you can easily pull dimensions.
* **Use Case 2 (Creating a Base):** You have a complex, organic sculpture and you want to create a simple, rectangular base that is perfectly sized to fit it. Run `BoundingBox` on the sculpture with the output set to Surfaces. This will instantly create a perfectly sized solid box that you can then use as a starting point for designing the base.

### Other Information
This command is very useful for measurement and for creating reference geometry.

---

## 64. Box

### Short Info
Draw a solid box.

### Detailed Description
The **Box** command is a fundamental solid creation tool used to draw a solid rectangular box. It offers several different methods for defining the box's size and position.

### Steps to use the command
1.  Run the command `Box`.
2.  Follow the prompts for the chosen creation method. For the default method (defining the base and then the height):
    a. **"First corner of base"**: Pick a point.
    b. **"Other corner of base or length"**: Pick a second point to define the length and width of the box's base.
    c. **"Height"**: Drag the mouse up or down and click to define the height, or type a value.

### Command Options & Toggles
The options are different methods for creating the box:
* **3Point:** Defines the box by picking three points that define its length, width, and height vectors.
* **Vertical:** Creates a box with vertical sides relative to the active CPlane.
* **Center:** Defines the box by picking its center point first.

### Note for better use
The box is a "primitive" shape. It's a simple building block that is often used as a starting point for more complex models, or as a cutter in boolean operations.

### Practical Use Cases
* **Use Case 1 (Signet Rings):** You are starting to model a basic square-top signet ring. The `Box` command is the fastest way to create the basic solid shape for the top of the ring. You can then use other tools like `FilletEdge` to round the corners and `MoveFace` to taper the sides.
* **Use Case 2 (Cutters):** You need to create a rectangular slot or hole in another object. Draw a box that represents the shape and size of the hole you need. Position it so it intersects the main object, and then use `BooleanDifference` to subtract it.

### Other Information
This is one of the most basic solid modeling commands.

---

## 65. BoxEdit

### Short Info
Size, scale, position, and rotate objects numerically.

### Detailed Description
The **BoxEdit** command opens a persistent, floating dialog box that allows you to numerically and precisely control the size, scale, position, and rotation of selected objects. It works by manipulating the object's bounding box. This is an extremely powerful tool for making exact, data-driven adjustments to your model.

### Steps to use the command
1.  Run the command `BoxEdit`.
2.  A floating panel will appear.
3.  Select one or more objects in your scene.
4.  The panel will populate with the size, position, and rotation values for the selected object(s).
5.  You can type new values into the fields and click "Apply" to transform the object.

### Command Options & Toggles
The options are the sections within the panel:
* **Size:** Displays and allows you to edit the object's dimensions along the X, Y, and Z axes.
* **Scale:** Allows you to scale the object by a specific factor.
* **Position:** Displays and allows you to edit the location of the object's bounding box center or pivot point.
* **Rotation:** Allows you to rotate the object by a precise angle around the X, Y, or Z axis.
* **Gumball Pivot:** Controls whether transforms are applied from the bounding box center or the Gumball pivot.

### Note for better use
Many experienced users keep the `BoxEdit` panel open on a second monitor or docked to the side of their screen at all times, as it provides constant access to precise transformations. If you select multiple objects, `BoxEdit` will show the dimensions of the bounding box that contains all of them, and any transform you apply will affect all selected objects as a single unit.

### Practical Use Cases
* **Use Case 1 (Exact Sizing):** You have a model of a gemstone that is currently 7.53mm long, but it needs to be exactly 7.50mm to fit a calibrated setting. Select the gemstone. In the `BoxEdit` panel's "Size" section, type "7.50" into the appropriate axis field and click "Apply." The stone will be scaled perfectly.
* **Use Case 2 (Precise Positioning):** You need to move a prong so that its center is exactly at the coordinate X=10, Y=5, Z=2. Select the prong. In the `BoxEdit` panel's "Position" section, type the exact coordinates into the X, Y, and Z fields and click "Apply."

### Other Information
This tool is indispensable for any work that requires high precision and numeric input.

---

## 66. BringForward

### Short Info
Bring curves forward in the draw order.

### Detailed Description
The **BringForward** command is a 2D utility that changes the drawing order of curves. It moves the selected curve one level forward in the stacking order, making it appear "on top" of the curve it was previously behind. This only affects the display order in wireframe and 2D views; it has no effect on 3D geometry or rendering.

### Steps to use the command
1.  Select the curve(s) you want to bring forward.
2.  Run the command `BringForward`.
3.  The selected curve will move one step forward in the draw order.

### Command Options & Toggles
This command has no options.

### Note for better use
To move a curve all the way to the front of all other curves in one step, use the `BringToFront` command. To reset the draw order for all curves back to the default, use the `ClearDrawOrder` command.

### Practical Use Cases
* **Use Case 1 (Cleaning Up Drawings):** You have a very complex 2D pattern for a filigree design with many overlapping curves. A key curve that defines the main border is hidden behind other, smaller curves, making it difficult to see and select. Select the border curve and run `BringForward`. This will make it draw on top of the other curves, making the 2D design much easier to read.

### Other Information
This is purely a visual aid for working with complex 2D line drawings.

---

## 67. BringToFront

### Short Info
Bring curves to the front in the draw order.

### Detailed Description
The **BringToFront** command is a 2D utility that changes the drawing order of curves. It moves the selected curve(s) to the very front of the stacking order, making them appear "on top" of all other curves in the view. Like `BringForward`, this only affects the display order and has no effect on 3D geometry.

### Steps to use the command
1.  Select the curve(s) you want to bring to the front.
2.  Run the command `BringToFront`.
3.  The selected curve(s) will move to the front of the draw order.

### Command Options & Toggles
This command has no options.

### Note for better use
The opposite of this command is `SendToBack`, which moves selected curves behind all others.

### Practical Use Cases
* **Use Case 1 (Emphasizing a Centerline):** You have a complex 2D drawing for a ring profile and have drawn a centerline for reference. The centerline is getting lost among all the other construction lines. Select the centerline, run `BringToFront`, and perhaps change its color. It will now draw on top of everything else, making it clearly visible as a primary guide.

### Other Information
This is a simple but useful tool for organizing complex 2D layouts.

---

## 68. BringViewportToTop

### Short Info
Bring a viewport to the front.

### Detailed Description
The **BringViewportToTop** command is a viewport management utility used with floating viewports. If you have multiple floating viewports that are overlapping, this command will bring the currently active floating viewport to the front of the stack, making it fully visible.

### Steps to use the command
1.  Create one or more floating viewports (`NewFloatingViewport`).
2.  Make one of the floating viewports active by clicking in it.
3.  Run the command `BringViewportToTop`.
4.  The active floating viewport will move in front of any other floating viewports.

### Command Options & Toggles
This command has no options.

### Note for better use
This command has no effect on the standard, docked viewports. It is only for managing overlapping floating windows.

### Practical Use Cases
* **Use Case 1 (Managing Detail Views):** You are working on a complex model and have a floating viewport that is zoomed in on a specific detail, like a single prong. This floating window is partially covered by another floating window or panel. Click in the detail viewport to make it active and run `BringViewportToTop`. The detail view will pop to the front so you can see it clearly.

### Other Information
This is a window management tool, not a modeling tool.

---

## 69. Cage

### Short Info
Create a control cage object used by the CageEdit command to deform other objects.

### Detailed Description
The **Cage** command is the first step in a powerful two-part free-form modeling process. Its purpose is to create a "control object" or "cage" that surrounds the geometry you intend to deform. This cage is a simpler object (like a box, sphere, or even a custom shape) with its own set of control points. This cage does not become part of your final model; it acts only as a deformation tool. Once the cage is created, you use the `CageEdit` command to link it to your target geometry.

### Steps to use the command
1.  Run the command `Cage`.
2.  The command line will show several options for the shape of the cage.
3.  Select an option (e.g., `BoundingBox`).
4.  Follow the prompts to define the cage object. For the `BoundingBox` option, you will be prompted to select the objects you want to deform.
5.  After defining the cage, you will be prompted to define the number of control points and the degree for the X, Y, and Z directions.
6.  A new cage object with its own control points will be created around your selected geometry.

### Command Options & Toggles
* **BoundingBox:** Creates a cage that is the same size as the bounding box of the object(s) you select.
* **Line:** Creates a cage from a line.
* **Rectangle:** Creates a planar rectangular cage.
* **Box:** Allows you to draw a box-shaped cage by defining its corners and height.
* **Sphere:** Creates a spherical cage.
* **Cylinder:** Creates a cylindrical cage.
* **Deformable:** Creates a NURBS cage instead of a simple cage object, offering more editing flexibility.
* **PointCount:** (Appears after defining the cage shape) Sets the number of control points in the U, V, and W (or X, Y, Z) directions.
* **Degree:** (Appears after defining the cage shape) Sets the mathematical degree for the cage in the U, V, and W directions.

### Note for better use
The number of control points and the degree you choose for the cage are very important. Fewer points and a lower degree will result in a smoother, more global deformation. More points and a higher degree will allow for more detailed, localized changes to the captive object. `Cage` only creates the control object; the actual deformation is done with the `CageEdit` command.

### Practical Use Cases
* **Use Case 1 (Preparing to Deform):** You have a finished, complex ring model and want to make it slightly wider in the middle. Before you can use `CageEdit`, you must first create the cage. You would run `Cage`, select the `BoundingBox` option, select your ring, and then define the number of control points for the cage (e.g., 4 in each direction) to create the deformation tool.

### Other Information
This command is always the first step. You cannot use `CageEdit` without first creating a control object with `Cage`.

---

## 70. CageEdit

### Short Info
Deform objects smoothly using control cage objects.

### Detailed Description
The **CageEdit** command is the second, active part of the cage editing process. It establishes a link between a "captive" object (the geometry you want to deform) and a "control" object (the cage you created with the `Cage` command). Once this association is made, you can turn on the control points for the cage and manipulate them. As you move, scale, or rotate the cage's control points, the captive geometry inside will be smoothly and organically deformed, following the influence of the cage.

### Steps to use the command
1.  Select the captive object (object to edit).
2.  Select or create a control object.
3.  Define the region to edit.

### Command Options & Toggles
* **Options for control object:** (These are available when prompted to "Select control object")
    * **BoundingBox:** Uses the captive objects' bounding box to create the cage.
        * **CoordinateSystem:** (Sub-option) Defines the orientation of the bounding box (CPlane or World coordinates).
    * **Line:** Allows you to draw a line to be used as the control object.
    * **Rectangle:** Allows you to draw a plane to be used as a control object.
    * **Box:** Allows you to draw a box to be used as a control object.

* **Deformation Options:**
    * **Accurate:** Slower to update but may result in denser, more accurate surfaces when deformed objects are refit.
    * **Fast:** Creates surfaces with fewer control points, which is faster but less accurate.
    * **PreserveStructure (Yes/No):**
        * **Yes:** Preserves the control point structure of the surface. Deformation may be less accurate if there are too few control points on the object.
        * **No:** Objects are refit as needed with more control points to allow accurate deformation.

* **Region options:**
    * **Global:** Objects are deformed throughout 3-D space. The influence of the control object is not limited.
    * **Local:** Allows you to specify a **Falloff** distance from the control object where the deformation effect fades to zero.
    * **Other:** Allows you to define a box, sphere, or cylinder that limits the influence of the control object.

* **Cage points:** (Appears after defining a new cage shape within the command)
    * **XPointCount / YPointCount / ZPointCount:** Sets the number of control points in each direction.
    * **XDegree / YDegree / ZDegree:** Sets the mathematical degree in each direction.

### Note for better use
Cage editing allows smooth deformation of surfaces with dense control points. Polysurfaces are not broken apart at the seams by CageEdit deformation. When you are finished deforming an object, you can use the `ReleaseFromCage` command to break the link.

### Practical Use Cases
* **Use Case 1 (Tapering a Bezel):** You have a straight-walled bezel. Run `CageEdit`, select the bezel as captive, then choose the `BoundingBox` option to create the control cage. Once the link is made, turn on the cage's control points, select the entire top row of points, and use the 2D scale command to shrink them slightly. The bezel will deform into a perfect, smooth taper.
* **Use Case 2 (Asymmetrical Shapes):** You have a perfectly symmetrical pendant and want to give it a more handmade, asymmetrical look. Use `CageEdit` with a `BoundingBox` control. Select one side of the cage's control points and rotate them slightly. The pendant inside will twist and deform in a very smooth, organic way.

### Other Information
The `CageEdit` command has a built-in `History` connection, regardless of the global History setting. This means that if you edit the control object (the cage) after the initial deformation, the captive object will continue to update.

---

## 71. CageEdit

### Short Info
Deform objects smoothly using control cage objects.

### Detailed Description
(This is a duplicate entry in the source documentation list, pointing to the same command as #70). The **CageEdit** command is a powerful free-form deformation tool that allows you to modify complex objects ("captives") by manipulating the control points of a simpler "control" object. The control object, or cage, can be an existing curve or surface, or it can be a primitive shape like a box, sphere, or line that you create within the command itself. Once the captive object is associated with the control cage, moving the cage's control points will smoothly and organically deform the captive geometry inside.

### Steps to use the command
1.  Select the captive object (object to edit).
2.  Select or create a control object.
3.  Define the region to edit.

### Command Options & Toggles
* **Options for control object:** (These are available when prompted to "Select control object")
    * **BoundingBox:** Uses the captive objects' bounding box to create the cage.
        * **CoordinateSystem:** (Sub-option) Defines the orientation of the bounding box (CPlane or World coordinates).
    * **Line:** Allows you to draw a line to be used as the control object.
    * **Rectangle:** Allows you to draw a plane to be used as a control object.
    * **Box:** Allows you to draw a box to be used as a control object.

* **Deformation Options:**
    * **Accurate:** Slower to update but may result in denser, more accurate surfaces when deformed objects are refit.
    * **Fast:** Creates surfaces with fewer control points, which is faster but less accurate.
    * **PreserveStructure (Yes/No):**
        * **Yes:** Preserves the control point structure of the surface. Deformation may be less accurate if there are too few control points on the object.
        * **No:** Objects are refit as needed with more control points to allow accurate deformation.

* **Region options:**
    * **Global:** Objects are deformed throughout 3-D space.
    * **Local:** Allows you to specify a **Falloff** distance.
    * **Other:** Allows you to define a box, sphere, or cylinder that limits the influence.

* **Cage points:** (Appears after defining a new cage shape within the command)
    * **XPointCount / YPointCount / ZPointCount:** Sets the number of control points in each direction.
    * **XDegree / YDegree / ZDegree:** Sets the mathematical degree in each direction.

### Note for better use
When you are finished deforming an object, you can use the `ReleaseFromCage` command to break the link.

### Practical Use Cases
* **Use Case 1 (Adding Organic Swell):** You have a flat signet ring top and want to make it swell out in the middle, like it was inflated. Use `CageEdit` with a `Box` control cage. After linking them, pull the control points on the top of the cage upward. The flat top will deform into a smooth, domed shape.

### Other Information
This entry is a duplicate of command #70.

---

## 72. Calc

### Short Info
Open the on-screen calculator.

### Detailed Description
The **Calc** command opens a simple, floating calculator window inside Rhino. It can be used for basic arithmetic.

### Steps to use the command
1.  Run the command `Calc`.
2.  The calculator window appears.

### Command Options & Toggles
This command has no options.

### Note for better use
You can type calculations directly into any command prompt that is asking for a number. For example, at a "Radius" prompt, you can type "10/2" and press Enter, and Rhino will use the value 5. This is often faster than opening the calculator.

### Practical Use Cases
* **Use Case 1 (Quick Math):** You are calculating the spacing for an array and need to do some quick division or multiplication without leaving the Rhino window.

### Other Information
This is a simple convenience utility.

---

## 73. CalcRPN

### Short Info
Open the on-screen Reverse Polish Notation calculator.

### Detailed Description
The **CalcRPN** command opens a Reverse Polish Notation (RPN) calculator. RPN is a different system for entering calculations where the operators (`+`, `-`, `*`, `/`) are entered *after* the numbers. It is favored by some for its efficiency in complex, multi-step calculations.

### Steps to use the command
1.  Run the command `CalcRPN`.
2.  The RPN calculator window appears.

### Command Options & Toggles
This command has no options.

### Note for better use
This calculator is for users who are specifically familiar with and prefer RPN. For most users, the standard `Calc` command or entering formulas directly in the command line is more intuitive.

### Practical Use Cases
* **Use Case 1 (Engineering Calculations):** An engineer or technical user who is accustomed to RPN calculators (like many classic HP models) can use this for complex calculations without having to mentally translate their workflow to a standard algebraic calculator.

### Other Information
This is a specialized utility for a specific type of user.

---

## 74. Camera

### Short Info
Show, hide, and toggle the visibility of the viewport camera.

### Detailed Description
The **Camera** command controls the visibility of the camera widget in the active viewport. The camera widget is an icon that represents the position and orientation of the "camera" for that viewport. Turning it on allows you to see a viewport's camera from other viewports and manipulate it directly as an object.

### Steps to use the command
1.  Make a viewport active (e.g., Perspective).
2.  Run the command `Camera`.
3.  The command line will prompt with options.
4.  Choose **Show**. A camera object will appear in the other viewports, representing the Perspective view's camera.
5.  You can now select this camera object and use commands like `Move` or `Rotate` on it, which will change the view in the Perspective viewport.

### Command Options & Toggles
* **Show:** Makes the camera for the active viewport visible.
* **Hide:** Hides the camera for the active viewport.
* **Toggle:** Toggles the camera's visibility on and off.

### Note for better use
Manipulating the camera object directly is a powerful way to achieve very precise camera angles and positions that can be difficult to get by just tumbling the view with the mouse.

### Practical Use Cases
* **Use Case 1 (Product Rendering):** You need to set up a very specific, repeatable camera angle for a product render. You can turn the camera on, position it exactly using numeric input with the `Move` command, and then save that view using the `NamedView` command for future use.
* **Use Case 2 (Walkthrough Animation):** You are setting up an animation where the camera needs to fly through a piece of jewelry. You can attach the camera object to a path curve, allowing it to move smoothly along a pre-defined path.

### Other Information
This is a key tool for advanced camera control, animations, and setting up precise rendered shots.

---

## 75. Cancel

### Short Info
Cancel the current command and deselects objects.

### Detailed Description
The **Cancel** command is a utility command that stops any currently running command and deselects all selected objects, curves, and control points. It is equivalent to pressing the **Escape (Esc)** key.

### Steps to use the command
1.  While a command is active (e.g., you are in the middle of drawing a line), run the command `Cancel`.
2.  The active command will be terminated.

### Command Options & Toggles
This command has no options.

### Note for better use
Pressing the **Esc** key is the universal and much faster way to perform this action. The `Cancel` command is primarily useful when writing scripts or macros, where you need a command name to stop a process.

### Practical Use Cases
* **Use Case 1 (Scripting):** You are writing a complex macro and need to ensure that any previously running command is stopped and nothing is selected before the macro proceeds. You would put `Cancel` at the beginning of your script.

### Other Information
For daily interactive use, always use the Esc key instead of typing this command.

---

## 76. Cap

### Short Info
Fill planar openings with a surface joined to the hole edge.

### Detailed Description
The **Cap** command creates a planar surface to close a flat, open hole in a polysurface or joined curve. If the hole is planar, this command will create a trimmed surface that perfectly fits the opening and join it to the object, turning an open object into a closed solid.

### Steps to use the command
1.  Select an object with one or more planar holes.
2.  Run the command `Cap`.
3.  The planar holes will be filled, and the object will become a closed polysurface.

### Command Options & Toggles
This command has no options.

### Note for better use
The `Cap` command will only work on holes that have a perfectly flat (planar) edge loop. If the edge of the hole is curved in 3D space, the command will fail. In that case, you would need to use other tools like `Patch` or `EdgeSrf` to close the hole.

### Practical Use Cases
* **Use Case 1 (Closing Extrusions):** You have created a ring shank by extruding a profile curve (`ExtrudeCrv`), which results in an open tube-like object. Running `Cap` on this object will close the two flat ends, instantly turning it into a solid.
* **Use Case 2 (Creating a Signet Top):** You have created the body of a signet ring by lofting profiles, but the top is still open. If the top edge is planar, `Cap` will create the flat top surface and join it to the body in one step.

### Other Information
This is a very fast and efficient way to close simple, flat openings in objects.

---

## 77. Chamfer

### Short Info
Create a line segment between two curves.

### Detailed Description
The **Chamfer** command creates a straight line segment (a chamfer) between two intersecting curves. It trims the original curves back to the new line segment and joins them together. This is the straight-edged equivalent of the `Fillet` command, which creates a rounded corner.

### Steps to use the command
1.  Run the command `Chamfer`.
2.  You will be prompted: **"Select first curve to chamfer"**.
3.  You will be prompted: **"Select second curve to chamfer"**.
4.  A chamfered corner is created.

### Command Options & Toggles
* **Distances:** Allows you to set the distance from the corner where each curve will be trimmed. You can set two different distances for an asymmetrical chamfer.
* **Join:** Toggles whether the resulting curves are joined together.
* **Trim:** Toggles whether the original curves are trimmed back to the chamfer.

### Note for better use
The `Chamfer` command is for 2D curves. For creating a beveled edge on a 3D solid, use the `ChamferEdge` command.

### Practical Use Cases
* **Use Case 1 (Creating a Beveled Profile):** You are drawing the 2D cross-section profile for a ring shank. Instead of a sharp 90-degree corner, you want a 45-degree beveled corner. Use `Chamfer` on the two lines to create the bevel before you extrude or sweep the profile.
* **Use Case 2 (Octagonal Shapes):** You can quickly turn a square into an octagon by applying the same chamfer distance to all four corners.

### Other Information
This is a basic 2D drawing tool for creating beveled corners.

---

## 78. ChamferEdge

### Short Info
Create a ruled surface at polysurface edges.

### Detailed Description
The **ChamferEdge** command creates a flat, beveled surface between selected edges of a solid polysurface. It is the 3D equivalent of the `Chamfer` command and is used to remove sharp edges from a model, replacing them with angled faces.

### Steps to use the command
1.  Run the command `ChamferEdge`.
2.  At the **Select edges to chamfer** prompt, click on the edges of your solid model.
3.  A preview will appear. You can click on the handles to dynamically change the chamfer distance.
4.  Press Enter to create the chamfered surfaces.

### Command Options & Toggles
* **NextRadius:** Allows you to set different chamfer distances for different edges within the same command run.
* **FaceEdges:** A selection filter that helps you select all the edges of a single face at once.
* **Preview:** Toggles the dynamic preview on or off.

### Note for better use
Unlike `FilletEdge`, which can sometimes fail on complex corner conditions, `ChamferEdge` is generally more robust and less likely to fail because it is creating simple, flat surfaces.

### Practical Use Cases
* **Use Case 1 (Stylistic Edges):** You are designing a modern, geometric piece of jewelry and want to give it a crisp, beveled-edge look instead of soft, rounded fillets. `ChamferEdge` is the perfect tool for this aesthetic.
* **Use Case 2 (Preparing for a Bezel):** Before cutting a seat for a princess-cut (square) gemstone, you can add a very small chamfer to the top inside edge of the bezel. This helps the stone to slide into place more easily during setting.

### Other Information
This is a fundamental tool for detailing and finishing solid models.

---

## 79. ChamferSrf

### Short Info
Create a chamfer surface between two surfaces.

### Detailed Description
The **ChamferSrf** command creates a flat, ruled surface (a chamfer) between two separate surfaces that intersect. It trims the original surfaces back to the new chamfer surface. This is similar to `ChamferEdge`, but it works on two independent surfaces rather than the connected edges of a single polysurface.

### Steps to use the command
1.  Run the command `ChamferSrf`.
2.  At the **Select first surface to chamfer** prompt, select a surface near the intersection.
3.  At the **Select second surface to chamfer** prompt, select the other surface.
4.  A preview will appear, and you can adjust the chamfer distances.
5.  Press Enter to create the chamfer.

### Command Options & Toggles
* **Distances:** Allows you to set the chamfer distances from the intersection.
* **Trim:** Toggles whether the original surfaces are trimmed.
* **Join:** Toggles whether the resulting surfaces are joined.

### Note for better use
This command is useful when you are building a model piece by piece from separate surfaces and want to create beveled transitions before joining everything into a solid.

### Practical Use Cases
* **Use Case 1 (Assembling a Model):** You have modeled the top of a signet ring and the shank as two separate, intersecting surfaces. You want to create a beveled transition where they meet before joining them. `ChamferSrf` can create this transition surface.
* **Use Case 2 (Architectural Modeling):** This command is more common in architectural or product design for creating beveled joints between separate wall or panel surfaces.

### Other Information
For most jewelry modeling where you are working with a single solid, `ChamferEdge` is the more commonly used command.

---

## 80. ChangeDegree

### Short Info
Change the degree of a curve or surface.

### Detailed Description
The **ChangeDegree** command rebuilds a NURBS curve or surface to a different mathematical degree. The "degree" of a curve is a whole number that determines its smoothness. A degree 1 curve is a polyline (sharp corners), a degree 2 curve can be a circle or arc, and a degree 3 curve is the standard, smooth "Bézier" style curve. Increasing the degree can make a curve smoother and more "global" (moving one control point affects a larger portion of the curve), while decreasing it can simplify the curve.

### Steps to use the command
1.  Select the curve or surface.
2.  Run the command `ChangeDegree`.
3.  At the **New degree** prompt, enter a new whole number and press Enter.
4.  The curve's structure will be changed.

### Command Options & Toggles
* **Deformable:** When changing a simple curve (like a line or arc) to a higher degree, this option ensures the new curve has enough control points to be edited freely.

### Note for better use
Changing the degree of an object is a significant modification to its underlying mathematical structure. This will change the number and location of its control points. This is an advanced tool and should be used with a clear understanding of what you are trying to achieve. For general smoothing or simplifying, the `Rebuild` command is often more intuitive.

### Practical Use Cases
* **Use Case 1 (Matching Degrees for Lofting):** You are trying to `Loft` several profile curves, but one of them is a degree 1 polyline and the others are degree 3 curves. This can sometimes cause problems or undesirable surface flow. You can use `ChangeDegree` to change the degree 1 curve to degree 3 to match the others before lofting.
* **Use Case 2 (Increasing Editability):** You have a perfect circle (a degree 2 curve) but you want to pull a small section of it out to create an organic bump. A degree 2 circle has very few control points. By changing its degree to 3 or 5, you add more control points, which allows for more localized and detailed editing.

### Other Information
This is an advanced tool for users who need precise control over the mathematical properties of their curves and surfaces.

---

## 81. ChangeLayer

### Short Info
Change an object's layer.

### Detailed Description
The **ChangeLayer** command moves one or more selected objects to a different layer. Layers are the primary method for organizing a Rhino model, allowing you to control the visibility, color, and other properties of groups of objects. This command opens a dialog box that lists all the layers in your model, allowing you to choose the destination layer for the selected objects.

### Steps to use the command
1.  Select the object(s) you want to move.
2.  Run the command `ChangeLayer`.
3.  The "Change Object Layer" dialog box will appear.
4.  Select the desired destination layer from the list.
5.  Click OK.

### Command Options & Toggles
The options are the buttons within the dialog box, allowing you to select a layer or create a new one.

### Note for better use
There are several ways to change an object's layer. You can also right-click on the layer in the Layer panel and choose "Change Object Layer," or use the pie menu in Matrix. The `ChangeLayer` command is simply the typed-command method for users who prefer it.

### Practical Use Cases
* **Use Case 1 (Organization):** You have just created a set of prongs for a ring. To keep your model organized, you select the new prongs, run `ChangeLayer`, and move them to your "Prongs" layer. This allows you to hide or show all prongs at once.
* **Use Case 2 (Correcting Mistakes):** You realize you accidentally created a gemstone on your "Metal" layer. You select the gemstone, run `ChangeLayer`, and move it to the correct "Gems" layer to ensure it has the right appearance and properties.

### Other Information
Proper layer management is one of the most important habits for efficient and professional CAD modeling.

---

## 82. ChangeToCurrentLayer

### Short Info
Change an object's layer to the current layer.

### Detailed Description
The **ChangeToCurrentLayer** command is a faster alternative to `ChangeLayer`. It moves the selected object(s) directly to whichever layer is currently active (the one with the checkmark next to it in the Layer panel) without opening a dialog box.

### Steps to use the command
1.  Ensure the desired destination layer is set as the "current" layer in the Layer panel.
2.  Select the object(s) you want to move.
3.  Run the command `ChangeToCurrentLayer`.
4.  The objects will immediately move to the current layer.

### Command Options & Toggles
This command has no options. It is an immediate action.

### Note for better use
This command is very efficient and is often assigned to a custom toolbar button or keyboard shortcut for rapid layer organization. It streamlines the process of layer management by removing the need to select a layer from a list.

### Practical Use Cases
* **Use Case 1 (Fast Workflow):** You are modeling a ring and are currently working on the "Shank" layer. You create a new curve that will be part of the shank. Since the "Shank" layer is already active, you can simply select the curve, run this command, and it will be moved instantly without any extra clicks.

### Other Information
This is a simple but very effective command for speeding up your organizational workflow.

---

## 83. Check

### Short Info
Inspect an object for errors.

### Detailed Description
The **Check** command is a diagnostic tool that examines the data structure of a selected object for any internal errors, corruption, or invalid geometry. If it finds a problem, it will report it in the command history. This is an important tool for troubleshooting problematic objects that are failing in other commands, especially boolean operations.

### Steps to use the command
1.  Select the object you want to check.
2.  Run the command `Check`.
3.  Read the command history. It will report "This is a valid polysurface" or will describe any errors it finds.

### Command Options & Toggles
This command has no options.

### Note for better use
If `Check` reports an error, it's a sign that the object's geometry is bad and needs to be repaired. Commands like `RebuildEdges`, `Explode`/`Rejoin`, or sometimes completely remodeling the object may be necessary.

### Practical Use Cases
* **Use Case 1 (Troubleshooting Booleans):** You are trying to perform a `BooleanUnion` on two objects, but it keeps failing. You can run `Check` on each object individually. If one of them reports an error, you know that object is the source of the problem and needs to be fixed before the boolean will work.
* **Use Case 2 (Validating Imported Files):** You have just imported a file from another CAD program (like an IGES or STEP file). Before you start working with the imported geometry, it's a good practice to run `Check` on it to ensure that the data was translated correctly and that there are no underlying errors.

### Other Information
This is a key diagnostic tool for maintaining a healthy and error-free model.

---

## 84. CheckInLicense

### Short Info
Return a license to the Zoo.

### Detailed Description
The **CheckInLicense** command is a license management utility used in environments that use the "Zoo" network license manager. When a user "checks out" a license, they can use Rhino on their computer even when it's disconnected from the network. The `CheckInLicense` command returns that checked-out license to the Zoo server so that it becomes available for other users on the network.

### Steps to use the command
1.  Ensure your computer is connected to the network where the Zoo server is running.
2.  Run the command `CheckInLicense`.
3.  The license will be returned to the server pool.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is only relevant for users with a network license managed by the Zoo. It has no function for standalone licenses.

### Practical Use Cases
* **Use Case 1 (Sharing a License):** You have checked out a Rhino license to work on your laptop over the weekend. When you return to the office on Monday, you run `CheckInLicense` to make the license available again for your colleagues to use from the shared network pool.

### Other Information
This is purely a license administration command.

---

## 85. CheckNewObjects

### Short Info
Turn on checking of new objects.

### Detailed Description
The **CheckNewObjects** command is a toggle that turns on an automatic validation mode. When this mode is active, Rhino will automatically run the equivalent of the `Check` command on every single object that is created or imported into your model. If an object is created with bad geometry, a warning dialog box will appear immediately.

### Steps to use the command
1.  Run the command `CheckNewObjects`.
2.  The command line will show the current state (Enabled or Disabled).
3.  Click on the state to toggle it.

### Command Options & Toggles
This command is a simple toggle between **Enabled** and **Disabled**.

### Note for better use
While this can be useful for catching errors early, leaving this feature on all the time can slightly slow down your workflow, as every object creation has to go through a validation check. It's often used as a temporary diagnostic tool rather than a permanent setting.

### Practical Use Cases
* **Use Case 1 (Troubleshooting Imports):** You are importing a complex IGES file that is known to have some problematic surfaces. Before importing, you can enable `CheckNewObjects`. As Rhino imports the file, it will alert you to each individual bad surface as it is created, making it much easier to find and fix them.
* **Use Case 2 (Diagnosing Failing Commands):** You are using a complex command that is creating bad objects. You can turn on `CheckNewObjects` to get an immediate warning the moment the bad geometry is created, helping you to diagnose the problem with the command's inputs or settings.

### Other Information
This is an advanced diagnostic tool for pinpointing the source of bad geometry.

---

## 86. CheckOutLicense

### Short Info
Check out a license from the Zoo.

### Detailed Description
The **CheckOutLicense** command is a license management utility used with the "Zoo" network license manager. It allows a user to "check out" a license from the network pool and store it on their local machine. This allows them to use Rhino on that computer even when it is disconnected from the network (e.g., on a laptop at home or on the road).

### Steps to use the command
1.  Ensure your computer is connected to the network where the Zoo server is running.
2.  Run the command `CheckOutLicense`.
3.  The license will be borrowed from the server and stored locally.

### Command Options & Toggles
This command has no options.

### Note for better use
A checked-out license is removed from the available pool on the server, so other users cannot use it until you return it with the `CheckInLicense` command.

### Practical Use Cases
* **Use Case 1 (Working Remotely):** You need to work on a project on your laptop over the weekend, away from the office network. Before you leave the office, you run `CheckOutLicense`. You can now use Rhino on your laptop all weekend. When you return to the office, you use `CheckInLicense` to return it to the pool.

### Other Information
This is purely a license administration command for network license users.

---

## 87. Circle

### Short Info
Draw a circle from center and radius.

### Detailed Description
The **Circle** command is a fundamental 2D drawing tool used to create a perfect circular curve. It offers many different methods for defining the circle's position and size based on different geometric inputs (center, diameter, points, tangency).

### Steps to use the command
1.  Run the command `Circle`.
2.  Follow the prompts for the chosen creation method. For the default method:
    a. At the **Center of circle** prompt, pick a point.
    b. At the **Radius** prompt, drag the mouse and click, or type a radius value and press Enter.

### Command Options & Toggles
The options are different methods for creating the circle:
* **3Point:** Creates a circle that passes through three selected points.
* **Tangent:** Creates a circle that is tangent to one or more existing curves.
* **Vertical:** Creates a circle that is perpendicular to the active construction plane.
* **Diameter:** Allows you to define the circle by its diameter instead of its radius.

### Note for better use
A circle in Rhino is a degree 2 NURBS curve. This means it has a simple structure that is mathematically perfect.

### Practical Use Cases
* **Use Case 1 (Drawing Gemstones):** The most common use in jewelry. To model a round gemstone, you start by drawing a circle with its exact diameter (e.g., 5mm). This circle becomes the basis for the gem's girdle, from which you can build the rest of the stone.
* **Use Case 2 (Creating Ring Rails):** The foundation of every ring is a circle representing the finger size. You would use the `Circle` command with the `Diameter` option to draw a circle with the precise inner diameter required for the ring.

### Other Information
This is one of the most frequently used commands in any form of CAD design.

---

## 88. ClearAllMeshes

### Short Info
Clear all analysis and display meshes.

### Detailed Description
The **ClearAllMeshes** command deletes all the temporary "render meshes" and "analysis meshes" from the model. These meshes are the polygons that Rhino creates automatically in the background to display your smooth NURBS surfaces in shaded and rendered viewports. While they are usually hidden, they are saved with the file and can sometimes increase the file size. This command clears them from the file to save space.

### Steps to use the command
1.  Run the command `ClearAllMeshes`.
2.  The meshes are deleted. The command line will report how many meshes were removed.

### Command Options & Toggles
This command has no options.

### Note for better use
The meshes will be automatically regenerated the next time you shade or render a viewport, so this is not a destructive command for your NURBS geometry. It is a temporary cleanup. The `SaveSmall` command performs this action automatically when you save a file.

### Practical Use Cases
* **Use Case 1 (Reducing File Size):** You have a very large and complex model with many smooth surfaces. The file size has become very large, making it slow to save or email. Running `ClearAllMeshes` and then saving can sometimes reduce the file size by removing this cached display data.

### Other Information
This is a file maintenance utility, not a modeling command.

---

## 89. ClearDrawOrder

### Short Info
Return the curve draw order to the default.

### Detailed Description
The **ClearDrawOrder** command resets the 2D drawing order for all curves back to the default state. If you have used commands like `BringToFront` or `SendToBack` to manually control which curves draw on top of others, this command will undo all of that custom sorting.

### Steps to use the command
1.  Run the command `ClearDrawOrder`.
2.  The draw order for all curves in the model is immediately reset.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a global command that affects all curves. There is no way to reset the draw order for only selected curves.

### Practical Use Cases
* **Use Case 1 (Cleaning a 2D Drawing):** You have been working on a complex 2D pattern and have used the draw order commands extensively to help you see what you're doing. Now that you are finished, you want to return to a neutral state. Running `ClearDrawOrder` will reset everything.

### Other Information
This is a utility for managing the 2D display of curves.

---

## 90. ClearUndo

### Short Info
Clear the undo buffer.

### Detailed Description
The **ClearUndo** command completely deletes the undo history for the current session. The `Undo` command works by storing your previous actions in the computer's memory (RAM). On very large files, this undo buffer can sometimes consume a significant amount of memory. This command clears that buffer, freeing up the RAM, but at the cost of losing the ability to undo your previous actions.

### Steps to use the command
1.  Run the command `ClearUndo`.
2.  A dialog box will appear asking you to confirm.
3.  Click Yes to proceed. The undo buffer will be cleared.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a permanent action for the current session. Once you clear the undo buffer, you cannot get it back. This command should be used with extreme caution and only when you are experiencing performance issues on a very large file and are certain you will not need to undo your recent work.

### Practical Use Cases
* **Use Case 1 (Performance on Large Files):** You are working on an extremely large and complex model that is using almost all of your computer's available RAM, and the program is becoming slow and unresponsive. If you are at a safe point in your project, you can run `ClearUndo` to free up memory and potentially improve performance.

### Other Information
This is a system utility for managing memory usage in extreme situations.

---

## 91. ClippingPlane

### Short Info
Create a clipping plane object that represents a plane for visibly clipping away geometry in a viewport.

### Detailed Description
The **ClippingPlane** command creates a special planar object that acts as a visual cutting plane. In any viewport, all geometry that is *behind* the clipping plane will be hidden, creating a cross-section view of your 3D models. This is a non-destructive display feature; it only affects the visibility of objects and does not actually cut or change the geometry itself.

### Steps to use the command
1.  Run the command `ClippingPlane`.
2.  Draw a rectangle in the viewport to define the size and location of the clipping plane object.
3.  The clipping effect will become active in the appropriate viewports.

### Command Options & Toggles
The options are different methods for creating the plane:
* **3Point:** Defines the plane by three points.
* **Vertical:** Creates a plane that is vertical to the current CPlane.
* **Center:** Defines the plane by its center and corners.

### Note for better use
You can move, copy, and rotate the clipping plane object like any other piece of geometry to change the position and angle of the cut. The clipping effect can be enabled or disabled for specific viewports in the object's properties panel.

### Practical Use Cases
* **Use Case 1 (Viewing a Cross-Section):** You have modeled a complex bezel setting and want to see the cross-section to check the thickness of the metal and the shape of the gemstone seat inside. Create a clipping plane and move it through the setting to get a live, interactive cross-section view.
* **Use Case 2 (Client Presentations):** You want to show a client the inside of a locket or the internal structure of a complex piece. A clipping plane provides a clean and easy-to-understand way to create a cutaway view for a screenshot or render.

### Other Information
This is a powerful visualization tool for inspecting and presenting the internal structure of solid models.

---

## 92. CloseCrv

### Short Info
Close an open curve.

### Detailed Description
The **CloseCrv** command closes an open curve by creating a straight line segment between its start and end points. This is a fundamental command for turning an open profile into a closed, continuous loop, which is often a requirement for creating solid objects.

### Steps to use the command
1.  Select one or more open curves.
2.  Run the command `CloseCrv`.
3.  A straight line segment will be added connecting the start and end of each selected curve.

### Command Options & Toggles
This command has no options. It is an immediate action.

### Note for better use
This command always adds a straight line. If you need a smooth, curved connection to close a curve, you should use the `BlendCrv` command and then `Join` the result. `CloseCrv` will create a sharp corner (a kink) at the new segment if the start and end tangents are not aligned.

### Practical Use Cases
* **Use Case 1 (Preparing for Extrusion):** You have drawn the profile of a ring shank, but you left a small gap between the start and end points. Before you can `ExtrudeCrv` to create a solid, the curve must be closed. `CloseCrv` will quickly bridge that gap, making the profile ready for extrusion.
* **Use Case 2 (Creating Planar Surfaces):** You have traced an outline for a flat pendant, and you want to turn it into a surface using `PlanarSrf`. The `PlanarSrf` command requires a closed, planar curve. If your trace is open, `CloseCrv` is the first step to making it a valid boundary for the surface.

### Other Information
This is a simple but essential command for preparing 2D geometry for 3D modeling operations.

---

## 93. CloseRenderWindow

### Short Info
Close the render window.

### Detailed Description
The **CloseRenderWindow** command closes the window that displays the results of a render. This is a simple utility command for managing the windows on your screen.

### Steps to use the command
1.  Run the command `CloseRenderWindow`.
2.  The render window, if open, will be closed.

### Command Options & Toggles
This command has no options.

### Note for better use
This is equivalent to clicking the "X" button on the render window's title bar. It is most useful when included in scripts or macros.

### Practical Use Cases
* **Use Case 1 (Scripting):** You are writing a macro that creates a render, saves the image, and then cleans up the workspace. You would include `CloseRenderWindow` at the end of the macro to automatically close the render window after the image has been saved.

### Other Information
This is purely a window management command.

---

## 94. ClosestPt

### Short Info
Create a point object on an object at the closest location to a picked point.

### Detailed Description
The **ClosestPt** command is an analysis and object creation tool. It finds the point on a curve, surface, or mesh that is geometrically closest to a specified location in space, and it places a new point object at that location. It also reports the coordinates of this closest point in the command history.

### Steps to use the command
1.  Run the command `ClosestPt`.
2.  At the **Select object for closest point** prompt, select the curve or surface.
3.  At the **Point to test for** prompt, click a location in space.
4.  A new point object will be created on the selected object.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is very useful for finding the exact point of perpendicularity from a location to an object, as the closest point will always lie along a line that is normal (perpendicular) to the curve or surface at that spot.

### Practical Use Cases
* **Use Case 1 (Positioning a Prong):** You have a curved ring shank and a prong that you need to place on the surface, directly underneath a gemstone. You can run `ClosestPt`, select the ring shank as the object, and then snap to the center of the gemstone for the "point to test for." The command will create a point on the shank's surface that is the precise location for the base of your prong.
* **Use Case 2 (Measuring Clearance):** You have two complex, non-parallel surfaces and need to find the minimum distance between them. You can create a point on one surface, then use `ClosestPt` to find the corresponding closest point on the second surface. The distance between these two new points is the minimum clearance.

### Other Information
This is a powerful tool for precision modeling and analysis.

---

## 95. CloseViewport

### Short Info
Close the active viewport.

### Detailed Description
The **CloseViewport** command closes the currently active viewport. This is a viewport management utility.

### Steps to use the command
1.  Make the viewport you want to close active by clicking in it.
2.  Run the command `CloseViewport`.
3.  The active viewport will be closed, and the remaining viewports will resize to fill the space.

### Command Options & Toggles
This command has no options.

### Note for better use
You can restore the default layout at any time by using the `4View` command.

### Practical Use Cases
* **Use Case 1 (Customizing Workspace):** You are working on a 2D pattern and have no need for the Perspective or Right viewports. You can close them to create a larger workspace for the Top and Front views.

### Other Information
This is a simple workspace customization tool.

---

## 96. CollapseMeshEdge

### Short Info
Merge the two vertices of a mesh edge.

### Detailed Description
The **CollapseMeshEdge** command is a low-level mesh editing tool that merges the two vertices at the ends of a selected mesh edge into a single vertex at the edge's midpoint. This action also removes any mesh faces that rely on that edge, effectively simplifying the mesh topology.

### Steps to use the command
1.  Run the command `CollapseMeshEdge`.
2.  At the **Select a mesh edge to collapse** prompt, click on a mesh edge.
3.  The edge will collapse to its midpoint.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a destructive editing tool that permanently alters the structure of the mesh. It is often used as part of a manual "polygon reduction" workflow to simplify a mesh.

### Practical Use Cases
* **Use Case 1 (Manual Mesh Retopology):** You have a very dense mesh from a 3D scan and you are manually cleaning it up to reduce the polygon count. `CollapseMeshEdge` can be used to strategically remove edges in flat areas to simplify the geometry without significantly changing the overall shape.

### Other Information
This is an advanced tool for users who are doing detailed mesh editing.

---

## 97. CollapseMeshFace

### Short Info
Merge the vertices of a mesh face to a single vertex.

### Detailed Description
The **CollapseMeshFace** command is a low-level mesh editing tool that takes a single selected mesh face and merges all of its vertices into a single new vertex located at the face's center. This effectively deletes the original face and any adjacent faces that share all of its vertices.

### Steps to use the command
1.  Run the command `CollapseMeshFace`.
2.  At the **Select a mesh face to collapse** prompt, click on a mesh face.
3.  The face will collapse to a single point.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a more aggressive simplification tool than `CollapseMeshEdge`. It is useful for quickly removing small, problematic faces or for terminating edge loops in complex meshes.

### Practical Use Cases
* **Use Case 1 (Removing Small Artifacts):** After a boolean operation on a mesh, you are sometimes left with tiny, sliver-like triangular faces. `CollapseMeshFace` can be used to select one of these tiny faces and instantly collapse it, cleaning up the area.

### Other Information
This is an advanced tool for users who are doing detailed mesh editing.

---

## 98. CollapseMeshFacesByArea

### Short Info
Collapse small mesh faces.

### Detailed Description
The **CollapseMeshFacesByArea** command is an automated mesh simplification tool. It finds all mesh faces that have an area smaller than a value you specify and collapses them. This is a way to automatically clean up a mesh by removing tiny, unnecessary polygons.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `CollapseMeshFacesByArea`.
3.  At the **Area less than** prompt, type a small number and press Enter.
4.  All faces with an area smaller than that value will be collapsed.

### Command Options & Toggles
The only option is the area value you enter.

### Note for better use
Start with a very small number and gradually increase it. If you enter too large a value, you can accidentally delete important details from your mesh. Always work on a copy of your mesh when using automated clean-up tools.

### Practical Use Cases
* **Use Case 1 (Automated Mesh Cleanup):** You have a complex mesh that resulted from a messy boolean operation or a 3D scan. It is likely full of thousands of tiny, invisible faces that add to the file size but not to the detail. Running this command with a small tolerance can automatically remove this "mesh noise."

### Other Information
This is a powerful but potentially destructive automated tool for mesh simplification.

---

## 99. CollapseMeshFacesByAspectRatio

### Short Info
Collapse long skinny mesh faces.

### Detailed Description
The **CollapseMeshFacesByAspectRatio** command is an automated mesh simplification tool that finds and collapses mesh faces that are long and skinny. The "aspect ratio" is a measure of how elongated a shape is. This command is useful for cleaning up meshes that have long, thin, sliver-like polygons, which can sometimes cause problems in 3D printing or other applications.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `CollapseMeshFacesByAspectRatio`.
3.  At the **Aspect ratio greater than** prompt, type a number (e.g., 10 for faces that are 10 times longer than they are wide) and press Enter.
4.  All faces with an aspect ratio greater than that value will be collapsed.

### Command Options & Toggles
The only option is the aspect ratio value you enter.

### Note for better use
Like `CollapseMeshFacesByArea`, start with a high number and work your way down. A value between 5 and 10 is often a good starting point for cleaning up typical sliver faces.

### Practical Use Cases
* **Use Case 1 (Fixing Bad Triangulation):** When a NURBS surface is converted to a mesh, sometimes long, thin triangles are created, especially in areas where trimmed edges are close together. This command can automatically find and remove these problematic sliver faces.

### Other Information
This is another automated tool for cleaning and simplifying complex meshes.

---

## 100. CollapseMeshFacesByEdgeLength

### Short Info
Collapse mesh faces with short edges.

### Detailed Description
The **CollapseMeshFacesByEdgeLength** command is an automated mesh simplification tool. It finds all mesh faces that have edges shorter than a value you specify and collapses them. This is another method for automatically cleaning up a mesh by removing polygons that are too small to contribute meaningful detail.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `CollapseMeshFacesByEdgeLength`.
3.  At the **Edge length less than** prompt, type a small number (in your current model units) and press Enter.
4.  All faces with edges shorter than that value will be collapsed.

### Command Options & Toggles
The only option is the edge length value you enter.

### Note for better use
This command is very useful for removing "mesh dust" - tiny, disconnected mesh fragments that have very short edges. Be careful not to set the length too high, or you will start to lose important details in your model.

### Practical Use Cases
* **Use Case 1 (Post-Boolean Cleanup):** After a complex boolean operation, small slivers and fragments can be left behind. This command can quickly find and remove any fragments whose edges are smaller than a certain tolerance (e.g., 0.01mm).

### Other Information
This is a powerful automated tool for mesh simplification and repair.


---

## 101. CollapseMeshVertex

### Short Info
Merge a mesh vertex into a neighboring vertex.

### Detailed Description
The **CollapseMeshVertex** command is a low-level mesh editing tool that merges a selected mesh vertex with one of its adjacent, connected vertices. This is a manual way to reduce the polygon count and simplify the mesh in a very precise, controlled way, by effectively deleting a vertex and re-triangulating the surrounding faces.

### Steps to use the command
1.  Run the command `CollapseMeshVertex`.
2.  At the **Vertex to collapse from** prompt, select a mesh vertex.
3.  At the **Vertex to collapse to** prompt, select an adjacent vertex that is connected to the first one by an edge.
4.  The first vertex will be merged into the second vertex.

### Command Options & Toggles
This command has no options.

### Note for better use
This gives you more control than `CollapseMeshEdge`, as you can choose the final location of the merged vertex. It's a useful tool for precision retopology where you need to carefully manage the flow of mesh edges.

### Practical Use Cases
* **Use Case 1 (Precision Retopology):** You are manually simplifying a mesh and need to remove a vertex, but you want to control exactly where the surrounding geometry moves to. `CollapseMeshVertex` allows you to pick which neighboring vertex will become the new corner point for the surrounding faces, maintaining the mesh flow.

### Other Information
This is an advanced tool for users who are doing detailed, manual mesh editing and simplification.

---

## 102. CommandHelp

### Short Info
Open the Command Help window.

### Detailed Description
The **CommandHelp** command is a utility that opens a dedicated help panel inside the Rhino interface. When you run another command, this panel automatically displays the content of the help file for that specific command, including its description, steps, and options.

### Steps to use the command
1.  Run the command `CommandHelp`.
2.  The Command Help panel will open.
3.  Now, run any other command (e.g., `Line`).
4.  The help information for the `Line` command will automatically appear in the panel.

### Command Options & Toggles
This command has no options.

### Note for better use
Keeping the Command Help window open on a second monitor or docked to the side of your screen is an excellent way to learn new commands or to remind yourself of the specific options for a command you don't use often.

### Practical Use Cases
* **Use Case 1 (Learning Rhino):** A new user is learning the software. By keeping the Command Help panel open, they can get instant, context-sensitive information about every tool they try, which greatly accelerates the learning process.
* **Use Case 2 (Exploring Options):** An experienced user is about to use a complex command like `Sweep2` and wants to be reminded of all the available sub-options for controlling the surface. The Command Help panel provides a quick reference without having to open the main help file.

### Other Information
This is a core part of the Rhino user interface designed to make the software easier to learn and use.

---

## 103. CommandHistory

### Short Info
Open the command history window.

### Detailed Description
The **CommandHistory** command opens a floating window that displays a complete, scrollable record of all the commands you have run and the output that was generated in the command line during your current Rhino session. This is useful for reviewing your steps, copying previous command outputs, or debugging scripts.

### Steps to use the command
1.  Run the command `CommandHistory`.
2.  The command history window appears.

### Command Options & Toggles
This command has no options.

### Note for better use
You can also open this window by pressing the F2 key. You can select and copy text from this window just like any other text editor.

### Practical Use Cases
* **Use Case 1 (Checking a Measurement):** You used the `Distance` command a few minutes ago to measure a critical part of your model but have since run other commands. You can open the `CommandHistory` window to scroll back and find the exact measurement that was reported.
* **Use Case 2 (Debugging a Macro):** You are testing a long macro, and it fails. The `CommandHistory` window will show you every step the macro took and at which command the error occurred, making it much easier to find and fix the problem.

### Other Information
This is an essential utility for reviewing your actions and for scripting.

---

## 104. CommandList

### Short Info
Open the command list window.

### Detailed Description
The **CommandList** command is a utility that opens a window displaying a simple, searchable list of all available commands in Rhino. This is useful for finding commands when you can't remember the exact name.

### Steps to use the command
1.  Run the command `CommandList`.
2.  The Command List window appears.
3.  You can scroll through the list or type in the search box to filter the commands.

### Command Options & Toggles
This command has no options.

### Note for better use
The list shows both the command name and a very brief description of what it does. Double-clicking a command in the list will run it.

### Practical Use Cases
* **Use Case 1 (Finding a Command):** You remember there is a command for creating a surface from a network of curves, but you can't remember its name. You can open the `CommandList` and type "network" or "surface" in the search box to quickly find the `NetworkSrf` command.

### Other Information
This is a simple help utility for discovering and launching commands.

---

## 105. CommandPrompt

### Short Info
Manage the command prompt window.

### Detailed Description
The **CommandPrompt** command is a utility that controls the visibility and position of the command prompt window within the Rhino interface.

### Steps to use the command
1.  Run the command `CommandPrompt`.
2.  The command line will present several options for controlling the window.

### Command Options & Toggles
* **Show (Yes/No):** Toggles the visibility of the command prompt window.
* **Position:** Allows you to change the location of the window (e.g., Top, Bottom, Floating).

### Note for better use
If you ever accidentally close the command prompt, typing `CommandPrompt` and choosing "Show" is the way to get it back.

### Practical Use Cases
* **Use Case 1 (Customizing UI):** A user prefers to have the command prompt floating in a separate window on a second monitor instead of docked at the top of the screen. They can use this command to change its position.

### Other Information
This is purely an interface customization command.

---

## 106. Commands

### Short Info
Open the Commands help topic.

### Detailed Description
The **Commands** command is a simple utility that opens the main Rhino help file directly to the "Commands" section, which contains an alphabetical list of all commands.

### Steps to use the command
1.  Run the command `Commands`.
2.  The Rhino help window will open.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (General Help):** You want to browse the main help file to learn about commands. This is a direct shortcut to that section of the documentation.

### Other Information
This is a simple help access command.

---

## 107. ComputeVertexColors

### Short Info
Apply vertex colors to a mesh.

### Detailed Description
The **ComputeVertexColors** command is a specialized mesh utility. It calculates colors for the vertices of a mesh object based on either the colors of a texture map or the colors of another mesh, and then "bakes" those colors into the mesh itself. This vertex color data can then be used by certain rendering engines or exported for use in applications that support vertex coloring (like 3D printing with color).

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `ComputeVertexColors`.
3.  The mesh's vertices will be colored based on the active texture or other source.

### Command Options & Toggles
This command has no options in the command line; it relies on the material and texture applied to the object.

### Note for better use
This is an advanced command, primarily for workflows that involve exporting data to other specialized applications. The vertex colors may not be visible in all of Rhino's display modes.

### Practical Use Cases
* **Use Case 1 (Color 3D Printing):** You have designed a ring and applied a complex, multi-colored texture map to it for a render. You want to 3D print the ring on a machine that supports full-color printing (like a Z-Corp printer). You would use `ComputeVertexColors` to transfer the texture's color information to the mesh's vertices, which is the format the 3D printer's software requires.

### Other Information
This command is a data-conversion tool for specific export workflows.

---

## 108. Cone

### Short Info
Draw a solid cone.

### Detailed Description
The **Cone** command is a fundamental solid creation tool used to draw a solid cone. It can create both pointed cones and truncated cones (cones with the top cut off).

### Steps to use the command
1.  Run the command `Cone`.
2.  Follow the prompts. For a basic cone:
    a. At the **Base of cone** prompt, pick a center point.
    b. At the **Radius** prompt, drag the mouse and click, or type a value.
    c. At the **End of cone** prompt, drag the mouse up or down for the height and click.

### Command Options & Toggles
* **3Point:** Defines the base circle by three points.
* **Vertical:** Creates a cone that is vertical to the active CPlane.
* **AroundCurve:** Creates a cone that is normal to a curve at a specified point.

### Note for better use
To create a truncated cone, simply click a point for the height and then, at the final prompt, specify a radius for the top surface instead of bringing it to a point.

### Practical Use Cases
* **Use Case 1 (Gemstone Pavilions):** The pavilion (bottom part) of a standard round brilliant gemstone is essentially a cone. The `Cone` command is the fastest way to model this basic form, which can then be trimmed or faceted.
* **Use Case 2 (Ring Shanks):** A cone can be used as a cutting object in a boolean operation to create a tapered opening or feature in a ring shank.

### Other Information
This is one of the basic solid modeling primitives.

---

## 109. Conic

### Short Info
Draw a conic section curve.

### Detailed Description
The **Conic** command draws a conic section curve, which can be a parabola, hyperbola, or ellipse, depending on the points you pick. This is an advanced curve creation tool used for creating very specific and smooth shapes that are mathematically defined.

### Steps to use the command
1.  Run the command `Conic`.
2.  Follow the prompts to define the curve by picking its start, end, apex, and a curve-through point.

### Command Options & Toggles
This command has no clickable options.

### Note for better use
The shape of the conic is determined by the "rho" value, which is controlled by the fourth point you pick. A rho value of 0.5 creates a parabola, less than 0.5 creates an ellipse, and greater than 0.5 creates a hyperbola.

### Practical Use Cases
* **Use Case 1 (Smooth Transitions):** You need to create a very smooth, flowing curve to define the profile of a shank or the edge of a pendant. A conic curve can provide a more aesthetically pleasing and mathematically pure transition than a standard NURBS curve in some situations.

### Other Information
This is an advanced curve tool for users who need precise mathematical shapes.

---

## 110. Connect

### Short Info
Extend and trim curves to meet.

### Detailed Description
The **Connect** command extends and/or trims two curves so that their endpoints meet precisely. This is a quick utility for cleaning up 2D line work where curves have small gaps or overlaps.

### Steps to use the command
1.  Run the command `Connect`.
2.  At the **Select first curve to connect** prompt, click near the end of the first curve.
3.  At the **Select second curve to connect** prompt, click near the end of the second curve.
4.  The curves will be extended or trimmed to meet.

### Command Options & Toggles
* **Join:** Toggles whether the two curves are joined into a single curve after the operation.
* **SubCrv:** Allows you to connect a segment of a polycurve instead of the entire curve.

### Note for better use
This command is for 2D curves. The 3D equivalent for surfaces is `ConnectSrf`.

### Practical Use Cases
* **Use Case 1 (Closing Gaps):** You have drawn two lines that are supposed to form a corner, but there is a small gap between their endpoints. `Connect` will extend them so they meet perfectly.
* **Use Case 2 (Cleaning Up Traces):** You have traced a sketch, resulting in several curves that slightly overlap or don't quite touch. `Connect` is a fast way to go through and clean up all these intersections before joining the curves into a clean outline.

### Other Information
This is a fundamental 2D cleanup and editing tool.

---

## 111. ConnectSrf

### Short Info
Extend surfaces to meet and trims.

### Detailed Description
The **ConnectSrf** command is a surface editing tool that extends two surfaces until they meet, and then trims them to each other. This is the 3D equivalent of the `Connect` command for curves.

### Steps to use the command
1.  Run the command `ConnectSrf`.
2.  At the **Select first surface to connect** prompt, select the first surface.
3.  At the **Select second surface to connect** prompt, select the second surface.
4.  The surfaces will be extended and trimmed.

### Command Options & Toggles
* **Join:** Toggles whether the two surfaces are joined into a single polysurface after the operation.

### Note for better use
This command works best on simple, untrimmed surfaces. The surfaces are extended in a straight, tangential direction from their edges.

### Practical Use Cases
* **Use Case 1 (Joining Shank Halves):** You have modeled the two halves of a ring shank as separate surfaces, and there is a small gap between them at the bottom. `ConnectSrf` can extend both surfaces until they meet, creating a clean seam.

### Other Information
This is a useful tool for joining surfaces that don't quite meet.

---

## 112. ContentFilter

### Short Info
Open the Content Filter panel.

### Detailed Description
The **ContentFilter** command opens a panel that allows you to search for and filter content like materials, environments, and textures that are stored in your Rhino libraries. This is an organizational tool for managing your rendering assets.

### Steps to use the command
1.  Run the command `ContentFilter`.
2.  The Content Filter panel appears.
3.  You can type search terms to find specific materials or textures.

### Command Options & Toggles
The options are the search and filter controls within the panel itself.

### Note for better use
This tool is most useful when you have a large library of rendering materials and need a quick way to find a specific one (e.g., "18k yellow gold").

### Practical Use Cases
* **Use Case 1 (Finding Materials):** You are preparing a model for rendering and need to find the specific "brushed platinum" material you saved last week. Instead of browsing through folders, you can open the `ContentFilter`, type "platinum," and it will show you all matching materials in your library.

### Other Information
This is an interface panel for managing rendering assets.

---

## 113. ContinueCurve

### Short Info
Continue to draw the selected curve using control points.

### Detailed Description
The **ContinueCurve** command allows you to resume drawing a curve that you previously stopped. It picks up from the end point of the selected curve and allows you to add more segments by placing new control points, maintaining the same degree and structure as the original curve.

### Steps to use the command
1.  Select a curve.
2.  Run the command `ContinueCurve`.
3.  You can now click in the viewport to add new control points to the end of the curve.
4.  Press Enter when you are finished.

### Command Options & Toggles
This command has no options.

### Note for better use
This command continues the curve using control points. If you want to continue a curve by picking points that the curve must pass *through*, use the `ContinueInterpCrv` command instead.

### Practical Use Cases
* **Use Case 1 (Extending a Design):** You have drawn a flowing scrollwork curve but realize it needs to be longer to cover more of the ring shank. You can select the curve and use `ContinueCurve` to add more control points and extend the scroll in a smooth, continuous way.

### Other Information
This is a simple curve editing utility.

---

## 114. ContinueInterpCrv

### Short Info
Continue to draw the selected curve by picking points on the curve.

### Detailed Description
The **ContinueInterpCrv** command allows you to resume drawing an interpolated curve that you previously stopped. An interpolated curve is one that passes directly through the points you pick. This command picks up from the end point of the selected curve and allows you to add more segments by picking new points for the curve to pass through.

### Steps to use the command
1.  Select an interpolated curve.
2.  Run the command `ContinueInterpCrv`.
3.  You can now click in the viewport to add new points for the curve to pass through.
4.  Press Enter when you are finished.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is the counterpart to `ContinueCurve`. Use `ContinueCurve` to add control points, and `ContinueInterpCrv` to add curve-through points.

### Practical Use Cases
* **Use Case 1 (Continuing a Trace):** You were tracing a complex sketch with an interpolated curve and had to stop. `ContinueInterpCrv` allows you to select the curve and pick up tracing exactly where you left off.

### Other Information
This is a simple curve editing utility.

---

## 115. Contour

### Short Info
Create a spaced series of planar curves and points through objects.

### Detailed Description
The **Contour** command creates a series of evenly spaced, parallel cross-section curves by slicing through one or more objects. You define a start point, an end point (which sets the direction of the cuts), and the distance between each cut.

### Steps to use the command
1.  Select the object(s) to contour.
2.  Run the command `Contour`.
3.  At the **Contour plane base point** prompt, pick a point to start the contours.
4.  At the **Direction perpendicular to contour planes** prompt, pick a second point to define the direction of the cuts.
5.  At the **Distance between contours** prompt, type a value and press Enter.
6.  A series of cross-section curves will be created.

### Command Options & Toggles
* **JoinCurves:** Allows you to join curves from separate objects at each contour level.
* **GroupObjectsBy:** Groups the resulting curves by contour level.

### Note for better use
This command is incredibly powerful for analyzing a 3D shape or for creating the profile curves needed for a `Loft` or `NetworkSrf`.

### Practical Use Cases
* **Use Case 1 (Analyzing a Shank):** You have a complex, organic ring shank and want to understand how its cross-section changes along its length. You can run `Contour` along the shank to generate a series of profile curves. This is excellent for checking for undercuts or areas that are too thin.
* **Use Case 2 (Reverse Engineering):** You have a 3D scan of a ring (as a mesh) and need to remodel it as a clean NURBS surface. You can use `Contour` on the mesh to generate a series of cross-section curves. You can then use these curves as the input for a `Loft` to rebuild the surface.

### Other Information
This is a key tool for both analysis and reverse engineering workflows.

---

## 116. Convert

### Short Info
Change a complex curve to a simpler curve.

### Detailed Description
The **Convert** command rebuilds a NURBS curve into a simpler representation made up of only straight line segments and circular arcs. This is useful for exporting to older machines or software that cannot handle complex splines.

### Steps to use the command
1.  Select the curve(s) to convert.
2.  Run the command `Convert`.
3.  A dialog box appears where you can set the tolerance for the conversion.
4.  Click OK. The curve will be rebuilt into lines and arcs.

### Command Options & Toggles
The options are in the dialog box and control the accuracy of the conversion:
* **Tolerance:** How far the new curve is allowed to deviate from the original.
* **AngleTolerance:** Sets the tolerance for angles.
* **MinLength / MaxLength:** Sets the minimum and maximum length for the resulting segments.

### Note for better use
This is a destructive command that changes the curve's structure. The `SimplifyCrv` command is a similar but often more intuitive tool for this purpose.

### Practical Use Cases
* **Use Case 1 (CNC Machining):** You are sending a 2D pattern to be cut on an older CNC machine that can only read lines and arcs, not complex NURBS curves. You would use `Convert` on your curves before exporting the file to ensure compatibility.

### Other Information
This is a specialized tool for converting modern curve types to a legacy format.

---

## 117. ConvertDots

### Short Info
Change annotation dots to points or text.

### Detailed Description
The **ConvertDots** command is a utility that changes annotation dot objects into either point objects or text objects.

### Steps to use the command
1.  Run the command `ConvertDots`.
2.  A dialog box appears.
3.  Choose whether to convert the dots to points or text.
4.  Choose whether to delete the original dots.
5.  Click OK.

### Command Options & Toggles
* **Output (Points/Text):** The type of object to create.
* **DeleteInput (Yes/No):** Deletes the original dot objects.

### Note for better use
This can be useful if you have used dots to mark locations and now need actual point objects at those locations for modeling or analysis.

### Practical Use Cases
* **Use Case 1 (Marking Gem Locations):** You have used the `Dot` command to place markers on a ring where you plan to set gemstones. To use a command like `OrientOnSrf`, you need real point objects. `ConvertDots` can quickly change all your visual markers into usable point geometry.

### Other Information
This is a simple utility for converting between annotation and geometry types.

---

## 118. Dot

### Short Info
Create an annotation dot.

### Detailed Description
The **Dot** command creates a small, text-based annotation object that is used to mark a location and display a short piece of text. The dot is always parallel to the view and scales with the view, so it remains readable even when you zoom in and out.

### Steps to use the command
1.  Run the command `Dot`.
2.  At the **Location of annotation dot** prompt, pick a point.
3.  The text from the previous dot is displayed. Press Enter to accept it, or type new text and press Enter.

### Command Options & Toggles
This command has no options.

### Note for better use
The appearance of the dot (font, size) is controlled by the current Annotation Style settings in your Document Properties.

### Practical Use Cases
* **Use Case 1 (Leaving Notes):** You are working on a design and need to leave a note for yourself or a colleague about a specific area, for example, "Check thickness here." You can use the `Dot` command to place a marker with that text directly on the model.
* **Use Case 2 (Labeling Parts):** You have a complex assembly and want to label the different parts. You can use dots to label the "shank," "head," "gallery," etc.

### Other Information
This is a fundamental annotation tool for communication and note-taking within a model.

---

## 119. ConvertExtrusion

### Short Info
Change extrusion objects to surfaces and polysurfaces.

### Detailed Description
The **ConvertExtrusion** command changes a special "lightweight" extrusion object into a standard NURBS surface or polysurface. In Rhino 5, simple extruded shapes (like from `Box` or `ExtrudeCrv`) are sometimes created as a special, memory-efficient object type. While these are good for performance, they cannot be edited in advanced ways (like moving individual control points). This command converts them to standard geometry so they can be fully edited.

### Steps to use the command
1.  Select one or more extrusion objects.
2.  Run the command `ConvertExtrusion`.
3.  The objects will be converted to standard polysurfaces.

### Command Options & Toggles
This command has no options.

### Note for better use
You can control whether Rhino creates lightweight extrusions in the first place by using the `UseExtrusions` command.

### Practical Use Cases
* **Use Case 1 (Enabling Advanced Editing):** You have created a ring shank with `ExtrudeCrv`. You now want to use `CageEdit` to deform it, but `CageEdit` works best on standard NURBS surfaces. You would first run `ConvertExtrusion` on the shank to turn it into a polysurface, and then proceed with the cage editing.

### Other Information
This is a utility command for converting between different internal object types in Rhino.

---

## 120. ConvertToBeziers

### Short Info
Change a NURBS object to a series of Bézier curves.

### Detailed Description
The **ConvertToBeziers** command converts a NURBS curve or surface into an equivalent object composed of multiple, joined Bézier curve segments. Bézier curves are a specific type of curve commonly used in graphic design programs like Adobe Illustrator. This command is used for exporting geometry to software that has better support for Béziers than for general NURBS.

### Steps to use the command
1.  Select the NURBS object(s).
2.  Run the command `ConvertToBeziers`.
3.  The object will be converted.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a highly specialized command for workflows that involve moving data to and from graphic design software. For most 3D modeling within Rhino, there is no need to convert objects to Béziers.

### Practical Use Cases
* **Use Case 1 (Exporting to Illustrator):** You have created a complex logo shape in Rhino using NURBS curves and need to export it to Adobe Illustrator for a graphic designer to use. Running `ConvertToBeziers` before exporting can sometimes result in a cleaner, more editable file in Illustrator.

### Other Information
This is a specialized data conversion tool for specific export workflows.


---

## 121. Copy

### Short Info
Duplicate objects.

### Detailed Description
The **Copy** command is a fundamental transformation tool that creates one or more duplicates of selected objects. It works by prompting you to pick a base point and then one or more destination points. This allows for precise placement of copies relative to the original object or other geometry in the scene.

### Steps to use the command
1.  Select the object(s) to copy.
2.  Run the command `Copy`.
3.  At the **Point to copy from** prompt, pick a base point.
4.  At the **Point to copy to** prompt, pick one or more locations to place the copies.
5.  Press Enter to end the command.

### Command Options & Toggles
* **InPlace:** The **InPlace** option makes a copy of an object in the exact same location as the original. This is useful for creating a duplicate on which to perform an action while keeping the original as a backup.
* **Vertical:** The **Vertical** option constrains the movement of the copy to the Z-axis of the current construction plane. This is useful for copying objects straight up or down.

### Note for better use
Using object snaps when picking the "point to copy from" and "point to copy to" is essential for precision. For example, to copy a prong from one side of a bezel to the other, you would snap the base point to the quadrant of the bezel and the destination point to the opposite quadrant.

### Practical Use Cases
* **Use Case 1 (Duplicating Settings):** You have created a single prong for a gemstone setting. You can use the `Copy` command with the `Cen` (center) object snap to precisely copy the prong from its current location to the other required locations around the center of the stone.
* **Use Case 2 (Creating Layers):** You are about to perform a complex or destructive operation on a part of your model, like a `BooleanUnion`. Before doing so, you can use the `Copy` command with the `InPlace` option to create a duplicate of the objects on a separate, hidden layer as a backup in case the operation fails or you need to revert to the original.

### Other Information
The `Copy` command is one of the most frequently used commands in all of CAD. Mastering its use with object snaps is a fundamental skill.

---

## 122. CopyCPlaneSettingsToAll

### Short Info
Copy grid and snap settings from one viewport to all viewports.

### Detailed Description
The **CopyCPlaneSettingsToAll** command is a viewport management utility. It takes the construction plane settings—specifically the grid spacing, snap spacing, and grid extents—from the currently active viewport and applies them to all other viewports in the model.

### Steps to use the command
1.  Configure the grid and snap settings in one viewport exactly as you want them.
2.  Make that viewport active.
3.  Run the command `CopyCPlaneSettingsToAll`.
4.  The settings from the active viewport will be copied to all other viewports.

### Command Options & Toggles
This command has no options.

### Note for better use
This command only copies the settings related to the grid and snaps. It does not copy the orientation or origin of the construction plane itself. For that, you would use the `CopyCPlaneToAll` command.

### Practical Use Cases
* **Use Case 1 (Standardizing a Workspace):** You are working on a project that requires a very specific grid spacing (e.g., 0.5mm) for precise layout work. After setting this up in your Top view, you can use `CopyCPlaneSettingsToAll` to instantly ensure that your Front and Right views have the exact same grid setup, maintaining consistency across your workspace.

### Other Information
This is a simple utility for quickly standardizing your modeling environment.

---

## 123. CopyCPlaneToAll

### Short Info
Copy the construction plane from one viewport to all viewports.

### Detailed Description
The **CopyCPlaneToAll** command is a viewport management utility. It takes the entire construction plane—its origin point and orientation—from the currently active viewport and applies it to all other viewports.

### Steps to use the command
1.  Set up a custom construction plane in one viewport using the `CPlane` command.
2.  Make that viewport active.
3.  Run the command `CopyCPlaneToAll`.
4.  The custom CPlane from the active viewport will be copied to all other viewports.

### Command Options & Toggles
This command has no options.

### Note for better use
This command can be disorienting if used improperly, as it can result in all viewports having a non-standard orientation (e.g., all viewports showing a tilted plane). It is most useful in specific, controlled situations. To restore the default viewports, use the `4View` command twice.

### Practical Use Cases
* **Use Case 1 (Working on an Angled Surface):** You are setting pavé stones on a surface that is tilted at a 37-degree angle. You use the `CPlane > Surface` option to set the construction plane in your Perspective view to be aligned with this tilted surface. To make it easier to work, you can then use `CopyCPlaneToAll` to make the Top, Front, and Right views also use this same tilted plane, so that your 2D drawing actions are perfectly aligned with the 3D surface.

### Other Information
This is an advanced viewport setup tool for working on non-standard planes.

---

## 124. CopyDetailToViewport

### Short Info
Copy a Layout detail view to a modeling viewport.

### Detailed Description
The **CopyDetailToViewport** command is a utility used within the Layout space (paper space). It takes the camera view (the position, projection, and zoom level) from a selected detail view window on a layout page and applies it to a standard modeling viewport.

### Steps to use the command
1.  Go to a Layout page.
2.  Run the command `CopyDetailToViewport`.
3.  At the **Select detail to copy** prompt, select a detail view window.
4.  At the **Select viewport to copy to** prompt, click inside the modeling viewport you want to change.
5.  The modeling viewport will update to match the detail view's camera.

### Command Options & Toggles
This command has no options.

### Note for better use
This is useful if you have set up a perfect camera angle for a drawing in a detail view and want to return to that exact view in your main modeling space to continue working.

### Practical Use Cases
* **Use Case 1 (Matching Drawing Views):** You have carefully arranged a perspective view in a detail window for a client presentation sheet. You notice a small modeling error. You can use `CopyDetailToViewport` to instantly set your main Perspective viewport to the exact same camera angle, make the correction, and be confident that the updated model will look correct in the layout.

### Other Information
This is a tool for synchronizing views between the modeling space and the paper layout space.

---

## 125. CopyLayout

### Short Info
Copy a layout.

### Detailed Description
The **CopyLayout** command creates a duplicate of an entire layout page. This includes the page size, all detail views, and any dimensions or annotations that have been placed on the layout.

### Steps to use the command
1.  Make the layout page you want to copy active by clicking its tab.
2.  Run the command `CopyLayout`.
3.  A new layout tab will appear with a copy of the original.

### Command Options & Toggles
This command has no options.

### Note for better use
This is much faster than creating a new layout from scratch and manually copying all the detail views and annotations.

### Practical Use Cases
* **Use Case 1 (Creating Drawing Variations):** You have created a complete technical drawing of a ring on a layout page. You now want to create a second page that is identical but shows a different version of the ring. You can use `CopyLayout` to duplicate the entire page, then simply change the model view within the detail windows on the new page.
* **Use Case 2 (Templating):** You have a standard title block and layout format that you use for all your client presentations. You can create one perfect layout page and then use `CopyLayout` to quickly create new pages that already have your title block and company information in place.

### Other Information
This is a time-saving utility for managing multi-page drawing sets.

---

## 126. CopyRenderWindowToClipboard

### Short Info
Copy the image in the render window to the Clipboard.

### Detailed Description
The **CopyRenderWindowToClipboard** command takes the image currently displayed in the Rhino Render window and copies it to the computer's clipboard. This allows you to quickly paste the rendered image into another application like an email, a Word document, or an image editor like Photoshop.

### Steps to use the command
1.  Create a render using the `Render` command.
2.  When the render is finished and displayed in the render window, run the command `CopyRenderWindowToClipboard`.
3.  The image is now on your clipboard.
4.  Go to another application and use the Paste command (Ctrl+V).

### Command Options & Toggles
This command has no options.

### Note for better use
This is a quick way to share a render without having to first save it as a file (e.g., a JPG or PNG) and then insert that file into the other application.

### Practical Use Cases
* **Use Case 1 (Quick Client Updates):** You have just finished a quick render of a design modification for a client. You can use `CopyRenderWindowToClipboard` and then paste the image directly into an email to send to them for immediate feedback.
* **Use Case 2 (Creating Reports):** You are creating a project report in Microsoft Word and need to include several renders. You can create each render, use this command to copy it, and paste it directly into your document without creating a folder full of temporary image files.

### Other Information
This is a simple but very useful workflow efficiency tool.

---

## 127. CopyToClipboard

### Short Info
Copy selected objects to the Clipboard.

### Detailed Description
The **CopyToClipboard** command copies the selected Rhino geometry (curves, surfaces, solids, etc.) to the Windows clipboard. This allows you to paste the geometry into another Rhino window or, in some cases, into other programs that can accept 3D geometry from the clipboard.

### Steps to use the command
1.  Select the object(s) you want to copy.
2.  Run the command `CopyToClipboard`.
3.  The objects are now on the clipboard.
4.  Use the `Paste` command in the destination window.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the equivalent of the standard Windows shortcut Ctrl+C. Using the shortcut is much faster than typing the command.

### Practical Use Cases
* **Use Case 1 (Moving Objects Between Files):** You have designed a custom clasp in one Rhino file and want to use it in your current ring project. You can open the clasp file, select the clasp, use `CopyToClipboard` (or Ctrl+C), switch to your ring file, and use `Paste` (or Ctrl+V) to bring it in.
* **Use Case 2 (Creating Variations):** You want to try a different design idea on a copy of your ring. You can select the entire ring, copy it to the clipboard, and then paste it to the side to create a duplicate to work on.

### Other Information
This is a fundamental command for managing objects within and between files.

---

## 128. CopyToLayer

### Short Info
Copy objects to a different layer.

### Detailed Description
The **CopyToLayer** command creates a duplicate of the selected object(s) and places the copy on a different layer that you specify. The original object remains on its original layer.

### Steps to use the command
1.  Select the object(s) to copy.
2.  Run the command `CopyToLayer`.
3.  The "Copy to Layer" dialog box will appear.
4.  Select the destination layer from the list.
5.  Click OK. A copy of the object will be created on the chosen layer.

### Command Options & Toggles
The options are the layers available in the dialog box.

### Note for better use
This is useful for creating backup or construction geometry. You can copy a key surface to a new layer before you trim or modify it, preserving the original.

### Practical Use Cases
* **Use Case 1 (Creating Construction Geometry):** You have a final, clean model of a ring shank. You need to create some temporary construction curves that are based on the shank's edges. You can use `DupEdge` to create the curves, and then immediately use `CopyToLayer` to place a copy of them onto a "Construction" layer, keeping your main "Curves" layer clean.
* **Use Case 2 (Design Variations):** You have a ring on your "Version 1" layer. You want to create a second version. You can select all the objects, use `CopyToLayer` to place a duplicate on a new "Version 2" layer, and then hide the "Version 1" layer to work on the new design.

### Other Information
This is a key organizational command for managing complex projects and design iterations.

---

## 129. CopyViewportToDetail

### Short Info
Copy a modeling viewport view to a Layout detail.

### Detailed Description
The **CopyViewportToDetail** command is a utility used within the Layout space (paper space). It takes the camera view (the position, projection, and zoom level) from a standard modeling viewport and applies it to a selected detail view window on a layout page.

### Steps to use the command
1.  Go to a Layout page.
2.  Run the command `CopyViewportToDetail`.
3.  At the **Select detail to change** prompt, select a detail view window.
4.  At the **Viewport to copy view from** prompt, click inside the modeling viewport that has the view you want to copy.
5.  The detail view will update to match the modeling viewport's camera.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the opposite of the `CopyDetailToViewport` command. It is useful for setting up your drawing sheets. You can navigate and compose your shot perfectly in the main modeling viewport, and then use this command to transfer that exact view to your detail window.

### Practical Use Cases
* **Use Case 1 (Setting Up a Drawing):** You are creating a presentation sheet for a client. In your main Perspective viewport, you tumble and zoom the model to get the perfect, dramatic "hero shot." You then switch to your Layout, run `CopyViewportToDetail`, select your main detail view, and then select the Perspective viewport. The detail view now shows the exact hero shot you framed.

### Other Information
This is a tool for synchronizing views between the modeling space and the paper layout space.

---

## 130. CPlane

### Short Info
Set the construction plane in the active viewport.

### Detailed Description
The **CPlane** command is a fundamental tool that sets the orientation and origin of the construction plane in the active viewport. The construction plane is the imaginary 2D grid (the "floor") on which you are currently working. By default, the Top view's CPlane is the world XY plane, the Front view's is the XZ, and the Right view's is the YZ. This command allows you to create custom construction planes aligned to objects, angles, or specific views.

### Steps to use the command
1.  Run the command `CPlane`.
2.  The command line will show many options for how to define the new plane.
3.  Select an option (e.g., `Surface`).
4.  Follow the prompts for that option. For `Surface`, you would select a surface, and the CPlane would align to it.

### Command Options & Toggles
* **3Point:** Sets the CPlane by picking an origin, an X-axis point, and a Y-axis point.
* **Object:** Sets the CPlane to match a selected object's orientation.
* **Surface:** Aligns the CPlane to be tangent to a point on a surface.
* **View:** Sets the CPlane to be parallel to the current view.
* **World:** Resets the CPlane to one of the default Top, Front, or Right orientations.
* **Undo/Redo:** Cycles through previous CPlane orientations.

### Note for better use
Custom CPlanes are temporary. You can always return to the default world planes by running `CPlane` and choosing the `World` option. You can save and restore custom CPlanes using the `NamedCPlane` command.

### Practical Use Cases
* **Use Case 1 (Working on Angled Surfaces):** You need to set pavé stones on a surface that is tilted at a 37-degree angle. Running `CPlane` and using the `Surface` option will align the grid to that tilted surface. Now, when you draw circles for your cutters, they will be perfectly aligned and perpendicular to the surface you are working on.
* **Use Case 2 (Creating Angled Prongs):** You need to model prongs that stick out from a bezel at a specific angle. You can create a new CPlane that is rotated to that angle, making it easy to draw the prong profiles in the correct orientation.

### Other Information
Mastering the use of custom construction planes is an essential skill for advanced 3D modeling.

---

## 131. CreaseSplitting

### Short Info
Control whether commands split surfaces at creases.

### Detailed Description
The **CreaseSplitting** command is a system setting that controls how Rhino handles surfaces with sharp corners or "creases." When CreaseSplitting is ON, commands like `Loft`, `Sweep`, and `Extrude` will automatically split a surface with a crease into a polysurface made of separate, simpler faces. When it is OFF, the command will create a single, more complex surface that has a crease running through it.

### Steps to use the command
1.  Run the command `CreaseSplitting`.
2.  The command line will show the current state (Yes or No).
3.  Click the option to toggle it.

### Command Options & Toggles
* **SplitAlongCreases (Yes/No):** The main toggle for the feature.

### Note for better use
For most jewelry modeling, leaving this setting ON (the default) is recommended. It creates simpler, cleaner polysurfaces that are generally easier to work with. Turning it OFF is an advanced technique used for creating single surfaces for specific types of surface analysis or deformation where a single surface is required.

### Practical Use Cases
* **Use Case 1 (Standard Modeling - ON):** You extrude a rectangular curve with sharp corners. With CreaseSplitting ON, Rhino creates a polysurface with four distinct side faces, which is easy to edit with commands like `MoveFace`.
* **Use Case 2 (Advanced Surfacing - OFF):** You are modeling a car body and need to create a single, flowing surface for a door panel that has a sharp character line creased into it. By turning CreaseSplitting OFF before running a command like `NetworkSrf`, you can create a single surface with a crease, which can be better for certain types of analysis and editing.

### Other Information
This is a global setting that affects the output of many surface creation commands.

---

## 132. CreateRegions

### Short Info
Create planar surfaces from curve regions.

### Detailed Description
The **CreateRegions** command is a specialized tool for fixing complex, non-manifold polysurfaces. A non-manifold object is one that has errors, such as edges that are shared by more than two faces. This command attempts to break down the problematic object into a collection of separate, valid, closed (solid) regions.

### Steps to use the command
1.  Select a non-manifold polysurface.
2.  Run the command `CreateRegions`.
3.  The command will analyze the object and, if successful, will output one or more valid, closed polysurfaces.

### Command Options & Toggles
This command has no options.

### Note for better use
This is an advanced repair tool. It is used when a complex boolean operation or imported file results in a single, messy object that cannot be used for further modeling or 3D printing.

### Practical Use Cases
* **Use Case 1 (Repairing a Failed Boolean):** You perform a `BooleanUnion` on several complex, overlapping parts of a ring, and the result is a single, non-manifold polysurface with internal errors. `CreateRegions` can sometimes analyze this messy object and successfully separate it back into the intended solid parts.

### Other Information
This is a "last resort" repair tool for very specific types of geometric problems.

---

## 133. CreateSolid

### Short Info
Create a closed solid from a set of surfaces.

### Detailed Description
The **CreateSolid** command takes a collection of surfaces or polysurfaces that form a closed "watertight" volume and joins them into a single, closed polysurface (a solid). It is essentially a combination of the `Join` command and a check to see if the result is a valid solid.

### Steps to use the command
1.  Select all the surfaces that form the boundary of your intended solid.
2.  Run the command `CreateSolid`.
3.  If the surfaces form a closed volume, they will be joined into a single solid.

### Command Options & Toggles
This command has no options.

### Note for better use
All of the selected surfaces must meet at their edges with no gaps (naked edges) for this command to be successful. You can use the `ShowEdges` command beforehand to check for any open gaps.

### Practical Use Cases
* **Use Case 1 (Assembling from Parts):** You have modeled the top, bottom, and side surfaces of a bezel as separate pieces. You select all of these surfaces and run `CreateSolid`. If they are all perfectly aligned, the command will join them into a single, solid bezel ready for further operations.

### Other Information
This command is very similar to `Join`, but it provides more feedback in the command line about whether a valid solid was created.

---

## 134. CreateUVCrv

### Short Info
Project a surface boundary and trim curves to the world x-y plane.

### Detailed Description
The **CreateUVCrv** command takes a surface or polysurface and "unrolls" its trim and border curves into a flat, 2D pattern on the world XY construction plane. The "UV" refers to the U and V directions that define a surface's parameter space. This command is essential for creating flat 2D patterns from 3D shapes, especially for preparing designs that will be applied back onto the surface.

### Steps to use the command
1.  Select one or more surfaces.
2.  Run the command `CreateUVCrv`.
3.  Flat 2D curves representing the edges and trim boundaries of the selected surfaces will be created at the origin of the world XY plane.

### Command Options & Toggles
This command has no options.

### Note for better use
The resulting 2D curves represent the "flattened" texture space of the 3D surface. Any curves you draw within this 2D boundary can be accurately mapped back onto the original 3D surface using the `ApplyCrv` command.

### Practical Use Cases
* **Use Case 1 (Pattern Layout):** You want to apply a complex filigree pattern to a curved ring shank. First, use `CreateUVCrv` on the ring shank to get its flattened 2D outline. Now you can draw or arrange your filigree pattern perfectly within this 2D boundary. Finally, use `ApplyCrv` to wrap the new 2D pattern back onto the 3D ring shank.
* **Use Case 2 (Texture Mapping Prep):** This command is invaluable for creating guides for texture maps. By creating the UV curves, you can export them to a program like Photoshop or Illustrator, create your texture around them, and be confident that the texture will align perfectly when applied back to the 3D model.

### Other Information
This is a fundamental command for any workflow that involves creating flat patterns from 3D surfaces.

---

## 135. Crv2View

### Short Info
Create a curve by averaging two curves.

### Detailed Description
The **Crv2View** (Curve Two Views) command is a specialized curve creation tool. It takes two 2D curves drawn in two different orthographic viewports (e.g., a profile in the Top view and a profile in the Front view) and creates a single 3D curve that is the spatial average of the two inputs.

### Steps to use the command
1.  Draw a curve in one viewport (e.g., Top).
2.  Draw a second curve in another viewport (e.g., Front).
3.  Run the command `Crv2View`.
4.  At the **Select first curve** prompt, select one of the curves.
5.  At the **Select second curve** prompt, select the other curve.
6.  A new 3D curve will be created.

### Command Options & Toggles
This command has no options.

### Note for better use
For this command to work predictably, the two input curves should have the same structure (e.g., the same number of control points). You can use the `Rebuild` command to ensure this.

### Practical Use Cases
* **Use Case 1 (Creating Complex Shank Rails):** This is the primary use case. You can draw the top-down shape of a ring shank in the Top view, and the side-profile shape in the Front view. `Crv2View` will combine these to create a single, complex 3D curve that can be used as a rail for a `Sweep1` command, creating a shank that is shaped correctly from both views at once.

### Other Information
This is a powerful technique for creating complex 3D curves from simple 2D inputs.

---

## 136. CrvDeviation

### Short Info
Report the distance between two curves.

### Detailed Description
The **CrvDeviation** (Curve Deviation) command is an analysis tool that measures and reports the maximum and minimum distance between two selected curves. It places point objects on the curves at the locations of maximum and minimum deviation and draws lines connecting them.

### Steps to use the command
1.  Run the command `CrvDeviation`.
2.  At the **Select first curve** prompt, select a curve.
3.  At the **Select second curve** prompt, select another curve.
4.  The command history will report the distances, and markers will appear on the objects.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is useful for quality control and for comparing a simplified or rebuilt curve to its original to ensure it is still within an acceptable tolerance.

### Practical Use Cases
* **Use Case 1 (Checking a Rebuilt Curve):** You have used the `Rebuild` command to simplify a complex curve. To ensure the new, simpler curve is still accurate enough, you can use `CrvDeviation` to measure the maximum distance between it and the original curve. If the distance is within your manufacturing tolerance, the rebuilt curve is acceptable.

### Other Information
This is a precision analysis tool for quality control.

---

## 137. CrvEnd

### Short Info
Place a point object at the end of a curve.

### Detailed Description
The **CrvEnd** command is a simple utility that places a point object at the exact end point of a selected curve.

### Steps to use the command
1.  Select one or more curves.
2.  Run the command `CrvEnd`.
3.  A point object will be created at the end of each selected curve.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a shortcut for the `End` object snap. You could achieve the same result by running the `Point` command and using the `End` snap on the curve.

### Practical Use Cases
* **Use Case 1 (Marking a Location):** You need to place a permanent marker at the end of a specific curve to use as a reference point for other operations, like the start of a `Sweep` or the location for a `Transform`.

### Other Information
This is a simple utility command. Its counterpart is `CrvStart`.

---

## 138. CrvSeam

### Short Info
Change the seam of a closed curve.

### Detailed Description
The **CrvSeam** (Curve Seam) command allows you to change the location of the start/end point (the "seam") on a closed curve. The seam is the point where a closed curve begins and ends. Its location can affect how other commands, especially surface creation commands, interact with the curve.

### Steps to use the command
1.  Run the command `CrvSeam`.
2.  At the **Select curve to change seam** prompt, select a closed curve.
3.  A point will appear on the curve, showing the current seam. You can drag this point along the curve to a new location.
4.  Click to place the new seam.

### Command Options & Toggles
This command has no options.

### Note for better use
The location of a curve's seam is often very important for the `Loft` and `Sweep` commands. If you are creating a surface and it has an unexpected twist, it is often because the seams of your profile curves are not aligned. Use `CrvSeam` to line them all up before creating the surface.

### Practical Use Cases
* **Use Case 1 (Fixing a Twisted Loft):** You are trying to `Loft` three circular profile curves to create a simple ring shank, but the resulting surface is twisted. This is likely because the seams on the three circles are not aligned. You can use `CrvSeam` on each circle and snap the seam to the same quadrant (e.g., the top quadrant) on all three curves. Now, the `Loft` will produce a clean, untwisted surface.

### Other Information
The 3D equivalent for surfaces is the `SrfSeam` command.

---

## 139. CrvStart

### Short Info
Place a point object at the start of a curve.

### Detailed Description
The **CrvStart** command is a simple utility that places a point object at the exact start point of a selected curve.

### Steps to use the command
1.  Select one or more curves.
2.  Run the command `CrvStart`.
3.  A point object will be created at the start of each selected curve.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a shortcut for the `Start` object snap. You could achieve the same result by running the `Point` command and using the `Start` snap on the curve.

### Practical Use Cases
* **Use Case 1 (Marking a Path):** You are about to use a curve as a path for an `ArrayCrv` or `Sweep` command and want to be certain which end is the start. Running `CrvStart` will place a point there, giving you a clear visual confirmation.

### Other Information
This is a simple utility command. Its counterpart is `CrvEnd`.

---

## 140. CSec

### Short Info
Create cross-sections through profile curves.

### Detailed Description
The **CSec** (Cross Section) command creates a new curve from the cross-section of a series of profile curves. You draw a line that cuts through the profiles, and the command creates a new curve by placing a control point on each profile where the cutting line intersects it.

### Steps to use the command
1.  Arrange a series of profile curves in space.
2.  Run the command `CSec`.
3.  At the **Select profile curves** prompt, select the profiles in order and press Enter.
4.  You will then be prompted to draw the cross-section line(s) that cut through the profiles.
5.  A new curve will be created for each cross-section line.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is a manual way to create the curves that would be used in a command like `NetworkSrf`. It gives you a high degree of control over the shape of the resulting surface.

### Practical Use Cases
* **Use Case 1 (Manual Surface Creation):** You are modeling a very complex, organic shape, like the body of a custom ring. You have created several profile curves that define its shape at different points. You can use `CSec` to create the longitudinal curves that connect these profiles. You can then use all of these curves together in a `NetworkSrf` to create a very precise and controlled surface.

### Other Information
This is an advanced curve creation tool used for complex surface modeling.


---

## 141. CullControlPolygon

### Short Info
Do not draw control points and mesh vertices on the back side of objects.

### Detailed Description
The **CullControlPolygon** command is a display toggle that affects the visibility of control points and mesh vertices. When enabled, it "culls" or hides any control points or vertices that are on the back side of a surface or mesh, relative to the current view. This helps to de-clutter the display, making it much easier to see and select the points on the front side of an object without accidentally selecting points on the back.

### Steps to use the command
1.  Run the command `CullControlPolygon`.
2.  The command line will show the current state (On or Off).
3.  Click the option to toggle it.

### Command Options & Toggles
This command is a simple toggle between **On** and **Off**.

### Note for better use
This is a global display setting that affects all objects in all viewports. It is an essential tool to turn on when you are doing detailed control point editing on complex, closed 3D objects.

### Practical Use Cases
* **Use Case 1 (Editing a Gemstone):** You have turned on the control points for a complex faceted gemstone model. With `CullControlPolygon` turned off, you see a confusing jumble of points from both the front and back of the stone. By turning it on, the view instantly cleans up, showing you only the control points for the facets facing you, making them easy to select and adjust.
* **Use Case 2 (Sculpting an Organic Shape):** You are editing the surface of a complex, organic ring shank. You want to select a group of control points on the top surface to pull them up. With this command enabled, you can safely drag a selection window around the points on top, confident that you will not accidentally select and move any points on the underside of the shank.

### Other Information
This command only affects the display of control points and mesh vertices; it does not affect the geometry itself.

---

## 142. CullDegenerateMeshFaces

### Short Info
Delete mesh faces with zero area.

### Detailed Description
The **CullDegenerateMeshFaces** command is a mesh cleanup and repair tool. It searches a mesh object for any "degenerate" faces—polygons whose vertices are all co-linear (in a straight line) or co-incident (in the same location), resulting in a face with zero area. These zero-area faces are errors in the mesh structure and can cause problems for 3D printing, rendering, and other mesh operations. This command automatically finds and deletes them.

### Steps to use the command
1.  Select one or more mesh objects.
2.  Run the command `CullDegenerateMeshFaces`.
3.  The command will report how many degenerate faces were found and deleted.

### Command Options & Toggles
This command has no options. It is an immediate action.

### Note for better use
This is a safe and useful command to run as part of a standard mesh cleanup workflow, along with commands like `Weld` and checking for naked edges. It is a good practice to run this on any mesh you import from another program or after performing complex boolean operations.

### Practical Use Cases
* **Use Case 1 (Preparing for 3D Printing):** Before exporting a model as an STL file for 3D printing, you should run a series of cleanup commands. Running `CullDegenerateMeshFaces` ensures that the file you send to the printer does not contain these small errors, which can sometimes cause slicing failures.
* **Use Case 2 (Fixing Imported Meshes):** You have imported an OBJ or STL file from an online source, and it is behaving strangely. Running this command can often fix hidden problems by removing invalid faces that are not immediately visible.

### Other Information
This is a key command in any professional mesh repair workflow.

---

## 143. Curvature

### Short Info
Evaluate the curvature of a curve or surface.

### Detailed Description
The **Curvature** command is an analysis tool that allows you to evaluate the curvature at a specific point on a curve or surface. When you run the command and click on a point, it displays the circle that matches the curve's "tightness" at that exact spot. It also reports the radius of that circle and the curvature value (which is 1/radius) in the command line. This is used to analyze the smoothness and consistency of a curve.

### Steps to use the command
1.  Run the command `Curvature`.
2.  At the **Select curve or surface for curvature measurement** prompt, select an object.
3.  Move your mouse along the object. A circle representing the curvature at the cursor's location will be displayed dynamically.
4.  Click a point to place a permanent curvature circle and report the values in the command history.

### Command Options & Toggles
* **MarkCurvature (Yes/No):** If Yes, the command will create a permanent circle object and a point at the location you click. If No, it will only report the value.

### Note for better use
A smaller circle means higher curvature (a tighter bend), while a larger circle means lower curvature (a flatter section). For a perfectly smooth curve, the transition between the curvature circles as you move along it should be smooth and gradual.

### Practical Use Cases
* **Use Case 1 (Fairing a Curve):** You are designing a flowing, organic piece and want to ensure the main design lines are perfectly smooth, without any small kinks or flat spots. You can use the `Curvature` command to move along the curve and visually check that the curvature circle changes size smoothly and consistently.
* **Use Case 2 (Checking for Kinks):** You have a curve that looks smooth but is causing a problem in a `Sweep` command. You can use `Curvature` to check the point where the sweep fails. If the curvature circle suddenly jumps in size or disappears, it indicates a hidden kink or problem at that point on the curve.

### Other Information
This is a more precise, point-by-point analysis tool compared to the more visual `CurvatureGraph` or `CurvatureAnalysis` commands.

---

## 144. CurvatureAnalysis

### Short Info
Visually evaluate surface curvature using a false-color map.

### Detailed Description
The **CurvatureAnalysis** command is a powerful surface analysis tool. It applies a false-color map to a surface that visually represents its curvature. This allows you to instantly see the shape and smoothness of a surface, identify any unwanted flat spots or wrinkles, and check for smooth transitions between joined surfaces.

### Steps to use the command
1.  Select the surface(s) to analyze.
2.  Run the command `CurvatureAnalysis`.
3.  A dialog box will appear with options to control the color map and the type of curvature being displayed.
4.  The selected surfaces will be colored in the viewport.

### Command Options & Toggles
The options are in a dialog box:
* **Gaussian:** This is the most common type. It shows flat areas as green, convex areas (domes) in one color range (e.g., red), and concave areas (bowls) in another (e.g., blue).
* **Mean:** Shows the average curvature.
* **Min Radius / Max Radius:** Shows the minimum or maximum amount of curve at any point.
* **Auto Range:** Automatically adjusts the color map to fit the curvature range of the selected object.

### Note for better use
For a high-quality, "Class-A" surface, the color transitions in the curvature map should be very smooth and gradual. Any sudden, sharp changes in color indicate a problem area, like a kink or a point where tangency is not smooth.

### Practical Use Cases
* **Use Case 1 (Checking Surface Quality):** You have just created a complex, flowing surface for a ring using `NetworkSrf`. To ensure it is perfectly smooth before proceeding, you can run `CurvatureAnalysis`. If you see smooth, blended color transitions, the surface is good. If you see sharp lines or splotches of color, you know the surface needs to be rebuilt or repaired.
* **Use Case 2 (Verifying Blends):** You have used `BlendSrf` to connect two surfaces. To verify that you have achieved true G2 (curvature) continuity, you can turn on `CurvatureAnalysis` for all three surfaces. If the color stripes flow seamlessly from one surface, across the blend, and onto the next surface, the blend is perfect.

### Other Information
This is an essential tool for any designer creating high-quality, free-form surfaces.

---

## 145. CurvatureAnalysisOff

### Short Info
Turn off curvature analysis.

### Detailed Description
The **CurvatureAnalysisOff** command is a simple utility that turns off the false-color curvature map created by the `CurvatureAnalysis` command and returns the objects to their normal display color.

### Steps to use the command
1.  Run the command `CurvatureAnalysisOff`.
2.  The curvature analysis display will be turned off for all objects.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Ending Analysis):** You have finished inspecting your surfaces with `CurvatureAnalysis` and now want to continue modeling. You run `CurvatureAnalysisOff` to remove the color map and return to a standard shaded view.

### Other Information
This is the companion command to `CurvatureAnalysis`.

---

## 146. CurvatureGraph

### Short Info
Display a graph of the curvature on a curve or surface.

### Detailed Description
The **CurvatureGraph** command is an analysis tool that displays a visual "graph" on a curve or surface to represent its curvature. The graph consists of small lines (often called "hairs") that stick out from the object. The length of these lines corresponds to the amount of curvature at that point—longer lines mean higher curvature (tighter bends), and shorter lines mean lower curvature (flatter sections).

### Steps to use the command
1.  Select the curve(s) or surface(s) to analyze.
2.  Run the command `CurvatureGraph`.
3.  A dialog box will appear with options to control the appearance of the graph.
4.  The curvature graph will be displayed on the selected objects.

### Command Options & Toggles
The options are in a dialog box:
* **Display Scale:** Controls the length of the "hairs" to make the graph more or less exaggerated and easier to see.
* **Hair Density:** Controls how many lines are displayed along the curve or surface.
* **U / V:** On surfaces, allows you to display the graph in the U direction, V direction, or both.

### Note for better use
For a curve to be considered smooth and "fair," its curvature graph should be smooth and have no sudden jumps or breaks. A perfect circle will have a graph where all the hairs are the same length. A straight line will have no graph at all (zero curvature).

### Practical Use Cases
* **Use Case 1 (Fairing a Curve):** You are designing a key profile curve for a ring shank. To ensure it is perfectly smooth and has no imperfections, you turn on the `CurvatureGraph`. You can then edit the curve's control points and watch the graph update in real-time, aiming to make the graph as smooth and flowing as possible.
* **Use Case 2 (Checking for Kinks):** If a curve has a hidden sharp point or kink, the curvature graph will show a sudden spike or break at that exact location, making it very easy to find and fix the problem.

### Other Information
This is an indispensable tool for anyone creating high-quality curves that will be used to generate surfaces.

---

## 147. CurvatureGraphOff

### Short Info
Turn off the curvature graph display.

### Detailed Description
The **CurvatureGraphOff** command is a simple utility that turns off the curvature graph created by the `CurvatureGraph` command.

### Steps to use the command
1.  Run the command `CurvatureGraphOff`.
2.  The curvature graph display will be turned off for all objects.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Ending Analysis):** You have finished inspecting and fairing your curves with `CurvatureGraph` and now want to continue modeling. You run `CurvatureGraphOff` to remove the graph display.

### Other Information
This is the companion command to `CurvatureGraph`.

---

## 148. Curve

### Short Info
Draw a curve from control point locations.

### Detailed Description
The **Curve** command is one of the most fundamental 2D drawing tools. It creates a smooth, free-form NURBS curve by allowing you to place its control points. The curve does not pass through the control points (except for the start and end); instead, the points act like "magnets," pulling the curve towards them. This allows for the creation of smooth, flowing shapes.

### Steps to use the command
1.  Run the command `Curve`.
2.  At the **Start of curve** prompt, click to place the first control point.
3.  Continue clicking to place additional control points. A preview of the curve will update with each click.
4.  Press Enter when you are finished.

### Command Options & Toggles
* **Degree:** Sets the mathematical degree of the curve. The default of 3 is standard for most free-form curves.
* **Close:** Closes the curve by creating a segment from the last point back to the first.
* **Undo:** Removes the last control point placed.

### Note for better use
For curves that must pass through specific points, use the `InterpCrv` (Interpolate Curve) command instead. Understanding the difference between control-point curves (`Curve`) and interpolated curves (`InterpCrv`) is a fundamental concept in NURBS modeling.

### Practical Use Cases
* **Use Case 1 (Drawing Organic Shapes):** You are drawing the flowing outline of a leaf or a scroll for a piece of filigree. The `Curve` command allows you to create a smooth, organic shape with a minimal number of control points, making it easy to edit later.
* **Use Case 2 (Creating Profile Curves):** You are drawing the cross-section profile for a comfort-fit wedding band. The `Curve` command is ideal for creating the smooth, gentle arcs of the profile.

### Other Information
This is a workhorse command and one of the first that new users learn for 2D drawing.

---

## 149. CurveBoolean

### Short Info
Trim, split, and join curves based on their overlapping regions.

### Detailed Description
The **CurveBoolean** command is a powerful 2D editing tool. It takes two or more overlapping, closed, planar curves and allows you to create new curves based on their combined regions. You can create the union (the total outline), the intersection (only the shared area), or the difference (subtracting one area from another). It is the 2D equivalent of the 3D boolean commands.

### Steps to use the command
1.  Select two or more overlapping, closed, planar curves.
2.  Run the command `CurveBoolean`.
3.  The command line will present several options.
4.  Click inside the regions you want to keep. A preview of the resulting curve will appear.
5.  Press Enter to create the new curve(s).

### Command Options & Toggles
* **CombineRegions:** Toggles between creating a single outline (Union) or separate curves for each region.
* **DeleteInput:** Deletes the original curves.
* **AllRegions:** Automatically generates curves for every possible region.

### Note for better use
All input curves must be closed and they must all lie on the same plane for this command to work correctly.

### Practical Use Cases
* **Use Case 1 (Creating a Crescent Shape):** You want to create a perfect crescent moon shape. Draw two overlapping circles. Select both and run `CurveBoolean`. Click in the area of one circle that is *not* overlapping the other. Press Enter. The result is a single, clean crescent-shaped curve.
* **Use Case 2 (Creating Complex Patterns):** You have created a complex pattern by overlapping many different shapes (circles, squares, etc.). `CurveBoolean` is the perfect tool to combine all of these into a single, clean outer boundary and/or to cut out the interior negative spaces.

### Other Information
This is an essential tool for creating complex 2D shapes from simpler components.

---

## 150. CurveThroughPolyline

### Short Info
Create a curve that passes through the vertices of a polyline.

### Detailed Description
The **CurveThroughPolyline** command takes a polyline (a curve made of straight line segments) and creates a new, smooth NURBS curve that passes through the vertices (corners) of that polyline. It is essentially a one-step way to smooth out a jagged polyline.

### Steps to use the command
1.  Select a polyline.
2.  Run the command `CurveThroughPolyline`.
3.  A new smooth curve is created.

### Command Options & Toggles
* **Degree:** Sets the degree of the resulting curve.
* **DeleteInput:** Deletes the original polyline.

### Note for better use
This command is very similar to `CurveThroughPt`, but it uses the vertices of an existing polyline as its input instead of separate point objects.

### Practical Use Cases
* **Use Case 1 (Smoothing a Rough Trace):** You have quickly traced a design using the `Polyline` command, resulting in a shape with sharp corners. To get a smooth, organic version of your trace, you can run `CurveThroughPolyline`.

### Other Information
This is a simple utility for converting one curve type to another.

---

## 151. CurveThroughPt

### Short Info
Create a curve that passes through a selection of point objects.

### Detailed Description
The **CurveThroughPt** command creates a smooth NURBS curve that passes through a set of pre-existing point objects. This is different from the `InterpCrv` command, where you pick the points interactively. This command uses point objects that are already in your model.

### Steps to use the command
1.  Place two or more point objects in your model.
2.  Run the command `CurveThroughPt`.
3.  Select the point objects in the order you want the curve to pass through them.
4.  Press Enter. A new curve is created.

### Command Options & Toggles
* **Degree:** Sets the degree of the resulting curve.
* **Close:** Closes the curve.

### Note for better use
The order in which you select the points is critical, as it determines the path of the curve.

### Practical Use Cases
* **Use Case 1 (Reverse Engineering):** You have used a digitizing arm or another method to capture a series of specific data points from a physical object. You can use `CurveThroughPt` to generate a smooth curve that accurately represents the shape defined by those points.
* **Use Case 2 (Plotting Data):** You have a set of X, Y, Z coordinates from a spreadsheet that you have imported as point objects. `CurveThroughPt` can be used to draw a smooth graph or path through this data.

### Other Information
This command is essential for workflows that involve creating geometry from pre-defined data points.

---

## 152. CurveThroughSrfControlPt

### Short Info
Create curves through surface control points.

### Detailed Description
The **CurveThroughSrfControlPt** command is a specialized tool that creates curves that pass through the control points of a selected surface. It essentially traces the rows of control points on a surface, creating a wireframe of curves that represents the surface's underlying structure.

### Steps to use the command
1.  Select a surface.
2.  Run the command `CurveThroughSrfControlPt`.
3.  Curves will be created along the U and V directions of the surface's control point grid.

### Command Options & Toggles
* **Direction (U/V/Both):** Allows you to choose whether to create curves in the U direction, the V direction, or both.

### Note for better use
The resulting curves are separate from the surface and can be edited or used for other modeling operations. This is a way to "extract" the structural lines of a surface.

### Practical Use Cases
* **Use Case 1 (Rebuilding a Surface):** You have a complex surface and you want to rebuild it using `NetworkSrf`. You can use `CurveThroughSrfControlPt` to extract the main "flow lines" of the surface. You can then edit or simplify these curves and use them as the input for a new, cleaner surface.

### Other Information
This is an advanced tool for surface analysis and reconstruction.

---

## 153. Cut

### Short Info
Delete objects and place them on the Clipboard.

### Detailed Description
The **Cut** command removes the selected objects from the model and places them on the Windows clipboard. This allows you to then use the `Paste` command to move them to a different location, a different Rhino file, or in some cases, to another application.

### Steps to use the command
1.  Select the object(s) you want to cut.
2.  Run the command `Cut`.
3.  The objects will disappear from the model and be placed on the clipboard.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the equivalent of the standard Windows shortcut Ctrl+X. Using the shortcut is much faster than typing the command.

### Practical Use Cases
* **Use Case 1 (Moving Objects Between Files):** You have designed a custom clasp in one Rhino file and want to move it into your current ring project (not just copy it). You can open the clasp file, select the clasp, use `Cut` (or Ctrl+X), switch to your ring file, and use `Paste` (or Ctrl+V) to move it.

### Other Information
This is a fundamental command for managing objects within and between files.

---

## 154. CutPlane

### Short Info
Create a planar surface that cuts through objects.

### Detailed Description
The **CutPlane** command creates one or more planar surfaces that pass through selected objects. Unlike the `ClippingPlane` command, which is a visual-only effect, `CutPlane` creates real NURBS surfaces. These surfaces can then be used as cutting objects for commands like `Trim`, `Split`, or `BooleanSplit`.

### Steps to use the command
1.  Select the object(s) you want to create cutting planes through.
2.  Run the command `CutPlane`.
3.  You will be prompted to draw a line in a viewport. This line defines the orientation and location of the cutting plane.
4.  A new planar surface will be created.

### Command Options & Toggles
* **3Point:** Allows you to define the cutting plane by picking three points.

### Note for better use
This command is a very fast way to create a cutting object that is perfectly sized to pass through your entire model.

### Practical Use Cases
* **Use Case 1 (Creating a Cross-Section):** You want to split a ring in half to see its cross-section. Select the ring, run `CutPlane`, and draw a vertical line through the middle of the ring in the Top view. This creates a planar surface that you can then use with the `Split` command to cut the ring into two pieces.
* **Use Case 2 (Flattening a Shank):** You need to flatten the bottom of a ring shank. Use `CutPlane` to create a horizontal plane that cuts through the bottom of the shank. You can then use this plane to `Trim` away the rounded bottom, leaving a flat surface.

### Other Information
This is a quick and efficient tool for creating cutting geometry.

---

## 155. CutVolume

### Short Info
Report the volume of the intersection between a solid and a box.

### Detailed Description
The **CutVolume** command is a specialized analysis tool. It calculates and reports the volume of the intersection between a selected solid object and a box volume that you define.

### Steps to use the command
1.  Select a closed polysurface.
2.  Run the command `CutVolume`.
3.  You will be prompted to define the corners of a cutting box.
4.  The command history will report the volume of the portion of the original solid that was inside the cutting box.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a measurement tool only. It does not create or modify any geometry.

### Practical Use Cases
* **Use Case 1 (Material Estimation):** You have a model of a ring that is made of two different materials (e.g., a platinum shank with a gold inlay). You can use `CutVolume` to draw a box around just the inlay portion to calculate its specific volume, which is needed for accurate weight and cost estimation.

### Other Information
This is a niche analysis tool for calculating the volume of a sub-region of a solid.

---

## 156. Cylinder

### Short Info
Draw a solid cylinder.

### Detailed Description
The **Cylinder** command is a fundamental solid creation tool used to draw a solid cylinder.

### Steps to use the command
1.  Run the command `Cylinder`.
2.  Follow the prompts. For a basic cylinder:
    a. At the **Base of cylinder** prompt, pick a center point.
    b. At the **Radius** prompt, drag the mouse and click, or type a value.
    c. At the **End of cylinder** prompt, drag the mouse up or down for the height and click.

### Command Options & Toggles
* **3Point:** Defines the base circle by three points.
* **Vertical:** Creates a cylinder that is vertical to the active CPlane.
* **AroundCurve:** Creates a cylinder that is normal to a curve at a specified point.

### Note for better use
The cylinder is a "primitive" shape that is often used as a starting point for more complex models or as a cutting object.

### Practical Use Cases
* **Use Case 1 (Creating a Bezel):** The fastest way to start a simple round bezel is to draw a cylinder with the outer diameter of the bezel. You can then use the `Shell` command to hollow it out, or use a second, smaller cylinder and `BooleanDifference` to cut out the inside.
* **Use Case 2 (Creating Cutters):** Cylinders are the most common type of cutter in jewelry. They are used with `BooleanDifference` to create holes for setting round gemstones, to create drill holes for stringing pearls, or to hollow out parts of a model.

### Other Information
This is one of the most basic and frequently used solid modeling commands.

---

## 157. Delete

### Short Info
Erase objects.

### Detailed Description
The **Delete** command permanently erases the selected objects from the model.

### Steps to use the command
1.  Select the object(s) you want to delete.
2.  Run the command `Delete`.
3.  The objects will be erased.

### Command Options & Toggles
This command has no options.

### Note for better use
Pressing the **Delete** key on your keyboard is the universal and much faster way to perform this action. The `Delete` command is primarily useful when writing scripts or macros.

### Practical Use Cases
* **Use Case 1 (Cleaning a Model):** You have many temporary construction curves that you no longer need. You can select them all (`SelCrv`) and press the Delete key to remove them.
* **Use Case 2 (Scripting):** You are writing a macro that creates temporary geometry, uses it for a calculation, and then needs to clean up after itself. You would include the `Delete` command in your script to remove the temporary objects.

### Other Information
For daily interactive use, always use the Delete key instead of typing this command.

---

## 158. DeleteHole

### Short Info
Remove a hole from a polysurface.

### Detailed Description
The **DeleteHole** command is a surface editing tool that removes a hole from a planar surface and repairs the surface. It is a very fast way to patch or fill circular or simple holes on flat faces.

### Steps to use the command
1.  Run the command `DeleteHole`.
2.  At the **Select hole edge(s) to remove** prompt, click on the edge of the hole you want to remove.
3.  Press Enter.
4.  The hole will be filled.

### Command Options & Toggles
This command has no options.

### Note for better use
This command works best on holes in flat (planar) surfaces. While it can sometimes work on gently curved surfaces, it may fail or produce undesirable results on complex, doubly-curved surfaces. For those, you would need to use a tool like `Untrim` or `Patch`.

### Practical Use Cases
* **Use Case 1 (Removing a Drill Hole):** You have created a hole through a flat pendant for a chain, but you decide to use a bail instead. You can use `DeleteHole` to quickly select the edge of the hole and fill it in, making the surface solid again.
* **Use Case 2 (Editing a Signet Top):** You have cut several holes in the top of a signet ring for stone settings but need to change the layout. `DeleteHole` allows you to quickly fill in the old holes before you create the new ones.

### Other Information
This is a powerful and time-saving tool for editing holes on flat surfaces.

---

## 159. DeleteMeshFaces

### Short Info
Remove selected faces from a mesh.

### Detailed Description
The **DeleteMeshFaces** command is a low-level mesh editing tool that removes selected faces from a mesh object, creating a hole. This is the primary way to open up a closed mesh or to remove unwanted parts of a mesh's surface.

### Steps to use the command
1.  Run the command `DeleteMeshFaces`.
2.  At the **Select mesh faces to delete** prompt, select one or more faces.
3.  Press Enter.
4.  The selected faces will be deleted.

### Command Options & Toggles
This command has no options.

### Note for better use
To select individual mesh faces (sub-objects), you may need to hold down **Ctrl + Shift** while clicking. Deleting faces will create "naked edges" and make a mesh "open" or "non-watertight," which is generally undesirable for 3D printing unless you intend to patch the hole with new faces.

### Practical Use Cases
* **Use Case 1 (Manual Mesh Repair):** You have an imported STL file with some overlapping or intersecting faces that are causing errors. You can use `DeleteMeshFaces` to remove the problematic faces, and then use `3DFace` or `FillMeshHole` to rebuild the area correctly.
* **Use Case 2 (Creating an Opening):** You have a solid, closed mesh model of a locket and you want to create an opening for the hinge. You can use `DeleteMeshFaces` to remove the faces where the hinge will be attached.

### Other Information
This is a fundamental command for any detailed mesh editing or repair work.

---

## 160. DeleteSubCrv

### Short Info
Delete a segment of a curve.

### Detailed Description
The **DeleteSubCrv** (Delete Sub-Curve) command removes a segment of a curve that lies between two points that you pick on that curve.

### Steps to use the command
1.  Run the command `DeleteSubCrv`.
2.  At the **Select a curve to shorten** prompt, select the curve.
3.  At the **Pick first point on curve** prompt, click a location on the curve.
4.  At the **Pick second point on curve** prompt, click another location on the curve.
5.  The segment of the curve between the two points will be deleted.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is similar to using the `Split` command with the "Point" option and then deleting the middle segment, but it combines those actions into a single command.

### Practical Use Cases
* **Use Case 1 (Creating a Gap for a Hinge):** You have drawn a complete, closed curve that represents the outline of a bezel. You now need to remove a small segment to make space for a hinge. You can use `DeleteSubCrv` to click on either side of the hinge area and remove that piece of the curve.
* **Use Case 2 (Shortening a Design Element):** You have a long, flowing scrollwork curve and you decide it is too long. You can use `DeleteSubCrv` to remove the end portion of the curve back to a specific point.

### Other Information
This is a simple but useful curve editing utility for making precise cuts.


---

## 161. Detail

### Short Info
Manage detail views on a layout.

### Detailed Description
The **Detail** command is a viewport management tool used exclusively within the Layout (paper space) environment. A "detail view" is a window on your layout page that looks into your 3D model space. The `Detail` command allows you to activate, deactivate, and control the properties of these windows, such as their scale and locked status.

### Steps to use the command
1.  Go to a Layout page that contains detail views.
2.  Run the command `Detail`.
3.  The command line will show several options for managing the detail views.
4.  Select an option (e.g., `Activate`).
5.  Follow the prompts for that option.

### Command Options & Toggles
* **Activate:** Activates a selected detail view, allowing you to pan, zoom, and rotate the 3D model inside it, just like a regular viewport.
* **Deactivate:** Deactivates the active detail view, returning you to editing the 2D layout page.
* **Enable:** Turns on a disabled detail view.
* **Disable:** Turns off a detail view, making the model inside it invisible.
* **Lock:** Locks a detail view, preventing its camera from being panned or zoomed. This is crucial for maintaining a set scale.
* **Unlock:** Unlocks a locked detail view.

### Note for better use
The most common workflow is to double-click inside a detail view to activate it, and double-click outside of it to deactivate it. The `Detail` command's main advantage is its `Lock` and `Unlock` options, which are essential for creating accurate, to-scale technical drawings.

### Practical Use Cases
* **Use Case 1 (Setting a Scale):** You are creating a technical drawing that requires a precise 1:1 scale view of a ring. You would activate the detail view, set the camera and zoom level, and then use `Detail > Lock` to lock the view. This prevents you from accidentally changing the scale while you add dimensions.
* **Use Case 2 (Multi-View Layouts):** You are creating a presentation sheet with multiple views of a single piece of jewelry. Each view (Top, Front, Perspective) is in its own detail window. The `Detail` command allows you to activate each window individually to arrange the camera angle perfectly for that specific view.

### Other Information
This command is fundamental to creating 2D drawings and layouts from your 3D models.

---

## 162. Diameter

### Short Info
Report the diameter of a curve.

### Detailed Description
The **Diameter** command is an analysis tool that measures the diameter of a curve at a specified point. It is typically used on circles and arcs to verify their size.

### Steps to use the command
1.  Run the command `Diameter`.
2.  At the **Select curve for diameter measurement** prompt, select a curve.
3.  The command will report the diameter in the command history. For arcs and circles, it will also place temporary markers showing the diameter.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a quick measurement tool. To create a permanent, visible dimension on your model, use the `DimDiameter` command instead.

### Practical Use Cases
* **Use Case 1 (Verifying Gem Size):** You have drawn a circle that will represent a 5mm round gemstone. To quickly double-check that you created it correctly, you can run `Diameter` and select the circle. The command line should report a diameter of 5.00mm.
* **Use Case 2 (Checking a Ring Rail):** You have created a ring rail for a size 7 ring and want to confirm its inner diameter. `Diameter` will give you an instant measurement.

### Other Information
This is a simple analysis command for quick verification of circular objects.

---

## 163. DigBeep

### Short Info
Turn the digitizer beep on and off.

### Detailed Description
The **DigBeep** command is a utility for users with a hardware digitizing arm connected to Rhino. It controls whether the computer makes a beeping sound each time a point is captured by the digitizer.

### Steps to use the command
1.  Run the command `DigBeep`.
2.  The command line will show the current state (On or Off).
3.  Click the option to toggle it.

### Command Options & Toggles
This command is a simple toggle between **On** and **Off**.

### Note for better use
This is a user-preference setting and has no effect on the geometry or the digitizing process itself.

### Practical Use Cases
* **Use Case 1 (User Feedback):** A user is digitizing a physical model in a noisy workshop. They turn `DigBeep` on to get audible confirmation that each point they press with the digitizer's stylus has been successfully registered by the computer.

### Other Information
This command is only relevant for users with a hardware digitizing arm.

---

## 164. DigCalibrate

### Short Info
Calibrate a digitizer.

### Detailed Description
The **DigCalibrate** command is a utility for users with a hardware digitizing arm. It initiates a calibration process to ensure that the physical movements of the digitizer arm are accurately translated into the digital coordinates within the Rhino model space. This involves touching the digitizer's stylus to a series of known reference points.

### Steps to use the command
1.  Run the command `DigCalibrate`.
2.  Follow the prompts in the command line, which will guide you through picking a series of points on your physical setup and the corresponding points in your Rhino model.

### Command Options & Toggles
The options are presented as a sequence of prompts during the calibration process.

### Note for better use
Calibration is a critical first step whenever you set up a digitizing arm for the first time or if you notice that the captured points are not aligning correctly with your model.

### Practical Use Cases
* **Use Case 1 (Initial Setup):** You have just connected a new digitizing arm to your computer. Before you can use it to trace a model, you must run `DigCalibrate` to establish the relationship between the physical space of the digitizer and the virtual space of your Rhino file.

### Other Information
This is a hardware setup and calibration tool, only used with digitizing arms.

---

## 165. DigCamera

### Short Info
Align the view to the digitizer.

### Detailed Description
The **DigCamera** command is a utility for users with a hardware digitizing arm. It synchronizes the viewport camera with the digitizer's stylus. When activated, the viewport camera will point in the same direction as the stylus, and the camera's target will be at the stylus's tip.

### Steps to use the command
1.  Run the command `DigCamera`.
2.  The active viewport will update to match the digitizer's orientation.

### Command Options & Toggles
This command has no options.

### Note for better use
This can be a useful way to navigate a 3D model by physically moving the digitizer arm, providing a more tactile way to inspect a digital object.

### Practical Use Cases
* **Use Case 1 (Model Inspection):** A designer is comparing a physical prototype on their desk to the 3D model. They can use `DigCamera` to point the physical digitizer stylus at a feature on the prototype, and the viewport camera will instantly pan and rotate to show the same feature on the digital model.

### Other Information
This is a hardware interface command, only used with digitizing arms.

---

## 166. DigClick

### Short Info
Simulate a mouse click at the digitizer's location.

### Detailed Description
The **DigClick** command is a utility for users with a hardware digitizing arm. It simulates a left mouse button click at the current location of the digitizer's stylus.

### Steps to use the command
1.  Run the command `DigClick`.
2.  A mouse click is registered at the current stylus location.

### Command Options & Toggles
* **Auto (Yes/No):** When set to Yes, a click is automatically registered every time the digitizer pedal is pressed.

### Note for better use
This command allows for hands-free operation, where the user can trigger commands and select points using only the digitizer and its foot pedal.

### Practical Use Cases
* **Use Case 1 (Hands-Free Digitizing):** A user is tracing a delicate physical object and needs both hands to hold it steady. They can use the digitizer's foot pedal, linked to `DigClick`, to register points without having to touch the mouse or keyboard.

### Other Information
This is a hardware interface command, only used with digitizing arms.

---

## 167. DigDisconnect

### Short Info
Disconnect the digitizer.

### Detailed Description
The **DigDisconnect** command is a utility for users with a hardware digitizing arm. It closes the connection between Rhino and the digitizer.

### Steps to use the command
1.  Run the command `DigDisconnect`.
2.  The connection to the digitizer is terminated.

### Command Options & Toggles
This command has no options.

### Note for better use
It is good practice to disconnect the digitizer when you are finished using it to free up the COM port on your computer.

### Practical Use Cases
* **Use Case 1 (Ending a Session):** You have finished tracing a physical object with your digitizer. You run `DigDisconnect` to properly close the software connection to the hardware.

### Other Information
This is a hardware interface command, only used with digitizing arms.

---

## 168. Digitize

### Short Info
Calibrate and connect a digitizer.

### Detailed Description
The **Digitize** command is the main utility for connecting and managing a hardware digitizing arm. It opens a dialog box that allows you to select the digitizer model, configure its connection settings (like the COM port), and initiate the calibration process.

### Steps to use the command
1.  Run the command `Digitize`.
2.  The "Digitizer" dialog box appears.
3.  Select your digitizer from the list and configure the port settings.
4.  Click "Connect" to establish a connection.
5.  Click "Calibrate" to run the `DigCalibrate` command.

### Command Options & Toggles
The options are all contained within the dialog box for connecting, disconnecting, and calibrating the hardware.

### Note for better use
This is the central control panel for setting up and managing your digitizer.

### Practical Use Cases
* **Use Case 1 (Setup):** This is the first command you would run when you want to start a new digitizing session to connect and prepare the hardware for use.

### Other Information
This is a hardware interface command, only used with digitizing arms.

---

## 169. DigLine

### Short Info
Draw a line normal to a surface with a digitizer.

### Detailed Description
The **DigLine** command is a specialized drawing tool for users with a hardware digitizing arm. It allows you to draw a line that is perpendicular (normal) to a surface at the point where you touch the digitizer's stylus to a corresponding physical object.

### Steps to use the command
1.  Run the command `DigLine`.
2.  Follow the prompts to digitize points on the physical object.
3.  A line normal to the corresponding digital surface will be created.

### Command Options & Toggles
This command has no options.

### Note for better use
This tool is useful for reverse-engineering tasks where you need to determine the surface normal at specific locations on a physical model.

### Practical Use Cases
* **Use Case 1 (Reverse Engineering):** You are digitizing a complex, physical model of a ring. You need to place prongs on the digital surface that are perfectly perpendicular to it. You can use `DigLine` to touch the physical model at the desired prong locations, which will create normal lines on your digital surface, providing a perfect axis for building the prongs.

### Other Information
This is a hardware interface command, only used with digitizing arms.

---

## 170. DigPause

### Short Info
Pause the digitizer.

### Detailed Description
The **DigPause** command is a utility for users with a hardware digitizing arm. It temporarily pauses the input from the digitizer, allowing you to move the stylus without sending any data to Rhino.

### Steps to use the command
1.  Run the command `DigPause`.
2.  The digitizer input will be paused.
3.  Run the command again to resume.

### Command Options & Toggles
This command is a toggle.

### Note for better use
This is useful when you need to reposition the digitizer arm to a new section of your physical model without creating unwanted points or lines in your digital model.

### Practical Use Cases
* **Use Case 1 (Repositioning):** You are tracing the outline of a large object. After tracing one side, you need to move the object and the digitizer to get access to the other side. You would use `DigPause` before moving everything to prevent stray points from being created, and then resume once you are in the new position.

### Other Information
This is a hardware interface command, only used with digitizing arms.

---

## 171. DigScale

### Short Info
Set the digitizer scale factor.

### Detailed Description
The **DigScale** command is a utility for users with a hardware digitizing arm. It allows you to set a scaling factor for the points being captured. This is useful if the physical model you are tracing is not at a 1:1 scale with the digital model you want to create.

### Steps to use the command
1.  Run the command `DigScale`.
2.  You will be prompted to enter a scaling factor.

### Command Options & Toggles
The only option is the numerical scale factor you provide.

### Note for better use
You can also define the scale factor by picking reference points on the physical model and in the digital model.

### Practical Use Cases
* **Use Case 1 (Scaling Up):** You are digitizing a small, hand-carved wax model of a ring, but you want the final digital model to be 10% larger. You can set the `DigScale` factor to 1.1. Now, every point you capture from the small wax model will be created 10% larger in the Rhino file.

### Other Information
This is a hardware interface command, only used with digitizing arms.

---

## 172. DigSection

### Short Info
Create cross-sections through objects with a digitizer.

### Detailed Description
The **DigSection** command is a specialized drawing tool for users with a hardware digitizing arm. It allows you to create cross-section curves of a digital object by defining a cutting plane with the digitizer.

### Steps to use the command
1.  Run the command `DigSection`.
2.  You will be prompted to digitize three points with the stylus. These three points define the cutting plane.
3.  A cross-section curve will be created where that plane intersects the selected digital object.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a powerful reverse-engineering tool that allows you to capture the cross-sectional shape of a physical object by defining the section plane with the digitizer.

### Practical Use Cases
* **Use Case 1 (Capturing Profiles):** You have a physical model of a ring shank and need to capture its cross-sectional profile at various points. You can use `DigSection` to define cutting planes along the shank, which will generate the exact profile curves needed to remodel the shank digitally.

### Other Information
This is a hardware interface command, only used with digitizing arms.

---

## 173. DigSketch

### Short Info
Sketch a curve with a digitizer.

### Detailed Description
The **DigSketch** command is a drawing tool for users with a hardware digitizing arm. It allows you to "sketch" a curve by moving the digitizer's stylus across the surface of a physical object. Rhino captures a series of points as you move and creates a smooth curve from them.

### Steps to use the command
1.  Run the command `DigSketch`.
2.  Press and hold the digitizer's foot pedal (or button).
3.  Move the stylus across the physical object.
4.  Release the pedal to stop sketching.
5.  A curve will be created in the digital model.

### Command Options & Toggles
This command has no options.

### Note for better use
This is useful for quickly tracing organic outlines or surface details from a physical model. The accuracy of the curve depends on the smoothness of your hand movement.

### Practical Use Cases
* **Use Case 1 (Tracing a Pattern):** You have a pendant with a hand-engraved scrollwork pattern on it. You can use `DigSketch` to trace over the engraved lines on the physical object, which will create corresponding curves in your digital model that you can then use to recreate the pattern.

### Other Information
This is a hardware interface command, only used with digitizing arms.

---

## 174. Dim

### Short Info
Create a horizontal or vertical linear dimension.

### Detailed Description
The **Dim** (Dimension) command is a fundamental annotation tool. It creates a linear dimension that measures the distance between two points, constrained to be either horizontal or vertical relative to the active construction plane.

### Steps to use the command
1.  Run the command `Dim`.
2.  Pick the first point.
3.  Pick the second point.
4.  Pick the location for the dimension line.

### Command Options & Toggles
* **Horizontal:** Forces the dimension to be horizontal.
* **Vertical:** Forces the dimension to be vertical.
* **Rotated:** Allows you to create a dimension at a specific angle.

### Note for better use
The appearance of the dimension (arrowheads, text size, font) is controlled by the current Annotation Style, which can be edited in the Document Properties.

### Practical Use Cases
* **Use Case 1 (Technical Drawings):** You are creating a 2D technical drawing of a ring for a manufacturer. You need to specify the overall width and height of the ring. The `Dim` command is used to create these clear, standard horizontal and vertical measurements.

### Other Information
This is one of the primary tools for creating 2D documentation.

---

## 175. DimAligned

### Short Info
Create a linear dimension aligned with two points.

### Detailed Description
The **DimAligned** command is an annotation tool that creates a linear dimension whose measurement line is parallel to the line between the two points being measured. Unlike the `Dim` command, it is not constrained to be horizontal or vertical.

### Steps to use the command
1.  Run the command `DimAligned`.
2.  Pick the first point.
3.  Pick the second point.
4.  Pick the location for the dimension line.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Measuring Angled Features):** You are creating a technical drawing of a bezel setting with tapered walls. To specify the length of the angled wall itself, you would use `DimAligned` and click on the top and bottom points of the wall.
* **Use Case 2 (Diagonal Measurements):** You need to specify the corner-to-corner distance of a square gemstone. `DimAligned` will create a dimension that is aligned with the diagonal.

### Other Information
This is the tool to use for any linear dimension that is not perfectly horizontal or vertical.

---

## 176. DimAngle

### Short Info
Dimension the angle between two lines.

### Detailed Description
The **DimAngle** command is an annotation tool that creates an angular dimension to show the angle between two lines.

### Steps to use the command
1.  Run the command `DimAngle`.
2.  Select the first line.
3.  Select the second line.
4.  Pick the location for the dimension arc.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Specifying Prong Angles):** You are creating a technical drawing for a multi-prong setting and need to specify the exact angle between the prongs. `DimAngle` is used to create a clear, visible dimension showing this angle.
* **Use Case 2 (Taper Angles):** You need to show the draft angle on a bezel wall. `DimAngle` can be used between the bezel wall and a vertical construction line to create this dimension.

### Other Information
This is a standard tool for technical drafting and annotation.

---

## 177. DimArea

### Short Info
Dimension the area of a closed curve, hatch, surface, or mesh.

### Detailed Description
The **DimArea** command is an annotation tool that calculates the area of a closed object and creates a text field displaying that area, often with a leader line pointing to the object.

### Steps to use the command
1.  Run the command `DimArea`.
2.  Select a closed curve, hatch, surface, or mesh.
3.  The area will be displayed at the cursor. Click to place the text.

### Command Options & Toggles
This command has no options.

### Note for better use
The text created is a "Text Field," which means if you scale or change the object, the area value in the dimension can be updated automatically using the `UpdateText` command.

### Practical Use Cases
* **Use Case 1 (Material Callouts):** You are creating a drawing for a piece that will be enameled. You can use `DimArea` to create a label that points to the enameled section and displays its exact surface area, which is useful information for the enameler.

### Other Information
This is a specialized annotation tool for displaying area measurements directly on a drawing.

---

## 178. DimCreaseAngle

### Short Info
Dimension the angle between two surfaces.

### Detailed Description
The **DimCreaseAngle** command is an annotation tool that measures and creates a dimension for the angle between two adjacent faces of a polysurface.

### Steps to use the command
1.  Run the command `DimCreaseAngle`.
2.  At the **Select a surface** prompt, select the first face.
3.  At the **Select a second surface** prompt, select an adjacent face.
4.  Pick a location for the dimension.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Facet Angles):** You have modeled a custom-cut gemstone and need to create a diagram for the gem cutter that specifies the exact angle between the table facet and the star facets. `DimCreaseAngle` is the tool used to create these dimensions.

### Other Information
This is a specialized 3D dimensioning tool.

---

## 179. DimCurveLength

### Short Info
Dimension the length of a curve.

### Detailed Description
The **DimCurveLength** command is an annotation tool that calculates the length of a curve and creates a text field displaying that length, with a leader line pointing to the curve.

### Steps to use the command
1.  Run the command `DimCurveLength`.
2.  Select a curve.
3.  The length will be displayed at the cursor. Click to place the text.

### Command Options & Toggles
This command has no options.

### Note for better use
Like `DimArea`, this creates a Text Field that can be updated if the curve's length changes.

### Practical Use Cases
* **Use Case 1 (Chain Length):** You have drawn a curve representing the path of a necklace chain and need to label its total length on a drawing. `DimCurveLength` will create this label automatically.

### Other Information
This is a specialized annotation tool for displaying curve length measurements.

---

## 180. DimDiameter

### Short Info
Dimension the diameter of a curve.

### Detailed Description
The **DimDiameter** command is a fundamental annotation tool used to create a diameter dimension for a circle or arc.

### Steps to use the command
1.  Run the command `DimDiameter`.
2.  Select the circle or arc to dimension.
3.  Pick the location for the dimension line.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Specifying Gem Sizes):** You are creating a technical drawing for a ring. You must use `DimDiameter` to create a clear dimension showing the exact diameter of the center stone and any accent stones. This is critical information for the stone setter.
* **Use Case 2 (Ring Size):** On a drawing, you can use `DimDiameter` to specify the inner diameter of the ring shank, which corresponds to the finger size.

### Other Information
This is one of the most frequently used dimensioning tools in jewelry design.


---

## 181. DimOrdinate

### Short Info
Create ordinate dimensions.

### Detailed Description
The **DimOrdinate** command is a specialized annotation tool used in technical drafting to create ordinate dimensions. Unlike linear dimensions that measure the distance between two points, ordinate dimensions measure the X or Y distance of a feature from a single, fixed base point (the origin). All dimensions in a set share this common origin, which keeps drawings clean and avoids tolerance buildup.

### Steps to use the command
1.  Run the command `DimOrdinate`.
2.  At the **Select point to dimension** prompt, pick the location of the feature you want to dimension.
3.  At the **Leader end point** prompt, drag the leader line to a clear location and click.
4.  The dimension text, showing the X or Y coordinate relative to the origin, will be placed.

### Command Options & Toggles
* **Direction (X_datum/Y_datum):** Specifies whether you are creating a dimension for the X-coordinate or the Y-coordinate.
* **UseCPlaneCoordinates:** Measures the coordinates relative to the current construction plane's origin, rather than the world origin.

### Note for better use
Ordinate dimensioning is a standard practice in mechanical engineering and manufacturing drawings. It ensures that all features are measured from a single reference point, which is critical for precision machining.

### Practical Use Cases
* **Use Case 1 (Technical Plate Drawing):** You are creating a 2D manufacturing drawing for a flat metal plate that will have several holes drilled in it. Instead of creating a complex web of linear dimensions between each hole, you would establish a base point at one corner of the plate. Then, use `DimOrdinate` to create clean X and Y dimensions for the center of each hole, all referencing that single corner.

### Other Information
This is a formal drafting tool and is less commonly used in artistic jewelry design but is essential for creating precise manufacturing schematics.

---

## 182. DimRadius

### Short Info
Dimension the radius of a curve.

### Detailed Description
The **DimRadius** command is a fundamental annotation tool used to create a radius dimension for a circle or an arc. It displays the radius value with a leader line pointing from the text to the curve.

### Steps to use the command
1.  Run the command `DimRadius`.
2.  At the **Select curve for radius dimension** prompt, select a circle or arc.
3.  At the **Pick dimension line location** prompt, click to place the dimension text and leader line.

### Command Options & Toggles
This command has no options.

### Note for better use
The appearance of the dimension (arrowheads, text size, font) is controlled by the current Annotation Style. This command is the counterpart to `DimDiameter`.

### Practical Use Cases
* **Use Case 1 (Specifying Fillets):** You have created a ring with rounded edges using the `FilletEdge` command. In your technical drawing, you must specify the radius of these fillets. `DimRadius` is the correct tool to create a clear label showing the fillet radius.
* **Use Case 2 (Defining Corners):** You are creating a drawing for a custom-shaped bezel with rounded corners. You would use `DimRadius` to specify the exact radius of each corner for the manufacturer.

### Other Information
This is one of the most frequently used dimensioning tools.

---

## 183. DimRecenterText

### Short Info
Return dimension text to its default location.

### Detailed Description
The **DimRecenterText** command is a utility for cleaning up dimensions. If you have manually moved the text of a dimension to a custom location, this command will instantly snap it back to its original, default position as defined by the current annotation style.

### Steps to use the command
1.  Select one or more dimension objects whose text has been moved.
2.  Run the command `DimRecenterText`.
3.  The text on the selected dimensions will move back to its default location.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Cleaning Up Drawings):** You have been moving dimension text around to fit in a crowded area of your drawing. Now, after rearranging the drawing, you want to restore the text to its proper, standardized position. `DimRecenterText` does this for all selected dimensions in one step.

### Other Information
This is a simple but useful utility for maintaining consistency and standards in your technical drawings.

---

## 184. DimRotated

### Short Info
Create a rotated linear dimension.

### Detailed Description
The **DimRotated** command is an annotation tool that creates a linear dimension, but allows you to specify a rotation angle for the dimension line itself. This is useful for measuring the distance between two points along a specific direction that is not necessarily aligned with the points or the main axes.

### Steps to use the command
1.  Run the command `DimRotated`.
2.  At the **First dimension point** prompt, pick a point.
3.  At the **Second dimension point** prompt, pick a second point.
4.  At the **Rotation angle** prompt, define the angle for the dimension line.
5.  Pick the location for the dimension line.

### Command Options & Toggles
This command has no options; the angle is set interactively.

### Note for better use
This command is different from `DimAligned`. `DimAligned` creates a dimension line that is *parallel* to the two points. `DimRotated` creates a dimension line at *any angle you specify* and measures the distance between the two points along that direction.

### Practical Use Cases
* **Use Case 1 (Measuring Part Width at an Angle):** You have a tapered ring shank and you need to specify its width at a location that is 30 degrees from the top. You can use `DimRotated` to create a dimension that measures the width specifically along that 30-degree line.

### Other Information
This is a specialized dimensioning tool for measuring objects along a specific, non-axial direction.

---

## 185. Dir

### Short Info
Display and edit an object's normal direction.

### Detailed Description
The **Dir** (Direction) command is a powerful analysis and editing tool that allows you to see and change the "direction" of curves, surfaces, and meshes. For a curve, this is its start and end. For a surface, this is its U, V, and Normal (outward) direction. The direction of an object is a critical property that affects how many other commands, especially boolean and surfacing commands, work.

### Steps to use the command
1.  Select an object.
2.  Run the command `Dir`.
3.  White arrows will appear on the object indicating its current direction(s).
4.  The command line will show options for changing the direction. Click on the object to flip the direction.
5.  Press Enter when you are finished.

### Command Options & Toggles
* **Flip:** Reverses the object's direction.
* **SwapUV:** (Surfaces only) Swaps the U and V directions.
* **ReverseU/ReverseV:** (Surfaces only) Reverses the U or V direction individually.

### Note for better use
If a boolean operation gives you the opposite result of what you expected (e.g., it cuts the wrong piece away), the most likely cause is that the normal direction of one of your surfaces is flipped inward. Use `Dir` to check and flip it so it points outward. Similarly, if a `Loft` or `Sweep` is twisted, it's often because the directions of the input curves do not match.

### Practical Use Cases
* **Use Case 1 (Fixing Booleans):** You are trying to subtract a cutter from a ring (`BooleanDifference`), but instead, the ring is subtracted from the cutter. Select the ring, run `Dir`, and you will likely see the normal arrows pointing *into* the object. Click it to flip the normals outward, and the boolean will now work correctly.
* **Use Case 2 (Fixing a Sweep):** You are creating a `Sweep2` for a ring shank, but the profile curves are flipping upside down along the path. This is because the direction of your two rail curves are not pointing the same way. Use `Dir` on each rail curve to ensure their direction arrows are pointing in the same direction.

### Other Information
Understanding and checking object direction with `Dir` is one of the most important troubleshooting skills in Rhino.

---

## 186. DirectionalLight

### Short Info
Insert a directional light.

### Detailed Description
The **DirectionalLight** command adds a directional light source to the model. A directional light simulates a very distant light source, like the sun. It emits parallel rays in a single direction, so its position in the scene does not matter, only its rotation. The objects in the scene are illuminated as if the light is infinitely far away.

### Steps to use the command
1.  Run the command `DirectionalLight`.
2.  You will be prompted to pick two points in the viewport. The line between these two points will define the direction vector of the light.
3.  A light object will be created in your model.

### Command Options & Toggles
This command has no options in the command line. The light's properties (color, intensity) are edited in the Properties panel.

### Note for better use
The default Rhino sun is a type of directional light. Adding your own directional lights is useful for creating specific lighting schemes for rendering, such as a three-point lighting setup (key, fill, and back lights).

### Practical Use Cases
* **Use Case 1 (Studio Lighting):** You are setting up a scene to render a piece of jewelry. You can use `DirectionalLight` to create your main "key" light that defines the primary shadows, and another one with lower intensity to act as a "fill" light to soften the shadows.
* **Use Case 2 (Simulating Sunlight):** You want to render a piece to show how it would look in direct afternoon sunlight. You can create a `DirectionalLight`, aim it at an appropriate angle, and give it a warm, yellowish color to simulate the sun.

### Other Information
This is one of the fundamental light types used in 3D rendering.

---

## 187. DisableClippingPlane

### Short Info
Turn off selected clipping planes in the active viewport.

### Detailed Description
The **DisableClippingPlane** command deactivates the effect of a selected `ClippingPlane` object in the currently active viewport. The clipping plane object remains in the model, but it will no longer visually clip away geometry in that specific view.

### Steps to use the command
1.  Make the viewport where you want to disable the effect active.
2.  Run the command `DisableClippingPlane`.
3.  At the **Select clipping planes to disable** prompt, select the clipping plane object(s).
4.  The clipping effect will be turned off in the active viewport.

### Command Options & Toggles
This command has no options.

### Note for better use
You can also control which viewports a clipping plane is active in by selecting the clipping plane and going to its Properties panel. The `DisableClippingPlane` command is a faster way to do this for the active view. The opposite command is `EnableClippingPlane`.

### Practical Use Cases
* **Use Case 1 (Controlling Views):** You have a clipping plane that cuts through your model to show a cross-section in the Perspective view. However, you want your Top and Front views to remain un-clipped so you can take measurements. You would make the Top view active and use `DisableClippingPlane` to turn off the effect there, and then do the same for the Front view.

### Other Information
This command provides viewport-specific control over the display of clipping planes.

---

## 188. DisableOsnap

### Short Info
Turn off persistent object snaps.

### Detailed Description
The **DisableOsnap** command is a toggle that temporarily turns off all persistent object snaps (the ones that are checked in the Osnap panel). This is useful when you are working in a very dense area and the object snaps are making it difficult to select a point freely.

### Steps to use the command
1.  Run the command `DisableOsnap`.
2.  The "Disabled" text will appear in the Osnap panel in the status bar, and all persistent snaps will be temporarily deactivated.
3.  Run the command again to re-enable them.

### Command Options & Toggles
This command is a toggle.

### Note for better use
Clicking the "Disable" text in the status bar has the same effect and is much faster. You can also hold down the **Alt** key while picking a point to temporarily suspend all Osnaps for that single pick.

### Practical Use Cases
* **Use Case 1 (Working in Crowded Areas):** You are trying to place a control point in a very precise location near a complex object with many edges and corners. The object snaps keep trying to snap to an endpoint or midpoint, preventing you from placing the point exactly where you want it. You can use `DisableOsnap` to turn them all off, place your point freely, and then turn them back on.

### Other Information
This is a workflow utility for managing object snaps.

---

## 189. DisplayCommandPrompt

### Short Info
Show, hide, and move the command prompt window.

### Detailed Description
The **DisplayCommandPrompt** command is a utility that controls the visibility and position of the command prompt window within the Rhino interface. This is the same as the `CommandPrompt` command.

### Steps to use the command
1.  Run the command `DisplayCommandPrompt`.
2.  The command line will present several options for controlling the window.

### Command Options & Toggles
* **Show (Yes/No):** Toggles the visibility of the command prompt window.
* **Position:** Allows you to change the location of the window (e.g., Top, Bottom, Floating).

### Note for better use
If you ever accidentally close the command prompt, typing this command and choosing "Show" is the way to get it back.

### Practical Use Cases
* **Use Case 1 (UI Customization):** A user prefers to have the command prompt floating in a separate window on a second monitor instead of docked at the top of the screen. They can use this command to change its position.

### Other Information
This is purely an interface customization command.

---

## 190. DisplayProperties

### Short Info
Open the Display panel.

### Detailed Description
The **DisplayProperties** command opens the "Display" panel. This panel allows you to override the display mode settings for specific, selected objects. This means you can have one object appear in wireframe while all other objects are in shaded mode within the same viewport.

### Steps to use the command
1.  Run the command `DisplayProperties`.
2.  The Display panel will open (often docked with other panels like Layers and Properties).
3.  Select an object.
4.  In the Display panel, you can assign a specific display mode to that object that is different from the viewport's overall display mode.

### Command Options & Toggles
The options are all contained within the panel, allowing you to assign any available display mode (Wireframe, Shaded, Rendered, etc.) to the selected object.

### Note for better use
This is a powerful tool for visualization and for working with complex models. To remove the override, select the object and choose the "Use View" option in the Display panel.

### Practical Use Cases
* **Use Case 1 (Reference Geometry):** You have a complex ring model and have also created a set of construction curves on its surface. To make the curves easier to see against the solid model, you can select the main ring, open the Display panel, and set its mode to "Shaded" while keeping the viewport in "Wireframe." Now the ring will be solid, but the rest of the scene, including your curves, will be in wireframe.
* **Use Case 2 (X-Ray Vision):** You have a bezel setting with a gemstone inside. You want to see both the solid metal and the gemstone, even though the gem is inside. You can select the bezel and set its display mode to "Ghosted" or "X-Ray." This will make the bezel transparent, allowing you to see the gemstone clearly inside it.

### Other Information
This command provides per-object control over display modes, which is very useful for advanced visualization.

---

## 191. Distance

### Short Info
Report the distance between two locations.

### Detailed Description
The **Distance** command is a fundamental analysis tool that measures and reports the distance between two points that you pick in the viewport. It provides a detailed breakdown in the command line, including the straight-line distance, the delta (distance) in the X, Y, and Z axes, and the angle in the CPlane.

### Steps to use the command
1.  Run the command `Distance`.
2.  At the **First point** prompt, pick a location.
3.  At the **Second point** prompt, pick another location.
4.  The distance measurements will be reported in the command history.

### Command Options & Toggles
This command has no options.

### Note for better use
Use object snaps to ensure you are measuring between the exact points you intend (e.g., from the `End` of one line to the `Midpoint` of another).

### Practical Use Cases
* **Use Case 1 (Checking Clearances):** You are designing a channel setting and need to ensure the distance between the two channel walls is exactly 3mm. You can use the `Distance` command with the `Near` or `Perp` snaps to measure the gap and verify its size.
* **Use Case 2 (Verifying Shank Thickness):** You need to check that the bottom of your ring shank is at least 1.5mm thick. You can use the `Distance` command in the Front or Right view to measure from the inside surface to the outside surface.

### Other Information
This is one of the most frequently used analysis commands for verifying a model's dimensions.

---

## 192. Divide

### Short Info
Create point objects along a curve.

### Detailed Description
The **Divide** command is a point creation tool that places a specified number of evenly spaced point objects along a curve.

### Steps to use the command
1.  Select the curve you want to divide.
2.  Run the command `Divide`.
3.  At the **Number of segments** prompt, type the number of sections you want to divide the curve into and press Enter.
4.  Point objects will be created at the end of each segment.

### Command Options & Toggles
* **Length:** Allows you to divide the curve into segments of a specified length instead of a specified number.
* **Split:** If set to Yes, this option will split the curve into separate segments at the division points instead of just placing point objects.

### Note for better use
The command asks for the "Number of segments." If you enter 10 segments, you will get 11 point objects (one at the start, one at the end, and 9 in between).

### Practical Use Cases
* **Use Case 1 (Placing Prongs):** You need to place 5 prongs evenly spaced around the top edge of a bezel. You can select the top edge curve, run `Divide`, and enter 5 for the number of segments. This will create 5 evenly spaced points on the edge, which are the perfect locations to place your prongs.
* **Use Case 2 (Arranging Decorative Elements):** You want to place small decorative spheres along a curved line on a pendant. The `Divide` command can create the precise, evenly spaced points you need to snap the center of each sphere to.

### Other Information
This is a fundamental tool for layout and for creating guide geometry.

---

## 193. DivideAlongCreases

### Short Info
Split a surface at creases.

### Detailed Description
The **DivideAlongCreases** command is a surface editing tool that takes a single surface that has sharp corners or "creases" and splits it into a polysurface made of separate, simpler faces. This is useful for breaking down complex surfaces into more manageable parts.

### Steps to use the command
1.  Select a surface that has one or more creases.
2.  Run the command `DivideAlongCreases`.
3.  The surface will be split into a polysurface.

### Command Options & Toggles
* **SplitAtTangents:** If set to Yes, this option will also split the surface at locations where the curve is tangent, not just at sharp corners.

### Note for better use
This command is essentially the opposite of what happens when you create a surface with the `CreaseSplitting` option turned OFF. This command allows you to retroactively split a creased surface that was created as a single entity.

### Practical Use Cases
* **Use Case 1 (Preparing for Editing):** You have imported a surface from another program that has sharp corners but is still a single surface. This can make it difficult to edit with commands like `MoveFace`. By running `DivideAlongCreases`, you can break it down into a standard polysurface with separate faces that are easier to select and manipulate.

### Other Information
This is a specialized tool for converting single creased surfaces into standard polysurfaces.

---

## 194. DocumentProperties

### Short Info
Manage settings for the current model.

### Detailed Description
The **DocumentProperties** command (more commonly accessed by running the `Options` command) opens the main settings dialog box for the current Rhino file. This is the central location for managing all file-specific settings, including units, tolerances, annotation styles, render settings, and much more.

### Steps to use the command
1.  Run the command `DocumentProperties` or `Options`.
2.  The Rhino Options dialog box will appear.
3.  Navigate through the different pages on the left to access and change the settings for your file.

### Command Options & Toggles
The options are the vast array of settings contained within the dialog box, organized into pages like:
* **Units:** Sets the model units (millimeters, inches) and tolerances.
* **Grid:** Controls the appearance and behavior of the construction plane grid.
* **Annotation Styles:** Where you define the font, size, and appearance of all dimensions and text.
* **Mesh:** Controls the quality of the render meshes used for shaded and rendered views.

### Note for better use
The settings in Document Properties are saved *with the file*. They are different from the main Rhino Options, which are global settings for the application. It is a good idea to create a template file with all of your preferred document properties (like units set to millimeters and your custom dimension style) and use that template to start all your new jewelry projects.

### Practical Use Cases
* **Use Case 1 (Setting Up a New Project):** Before you begin any new jewelry model, the first step should be to open `DocumentProperties` and ensure your Units are set to Millimeters and your Absolute tolerance is set to an appropriate value (e.g., 0.001).
* **Use Case 2 (Customizing Dimensions):** You want all the dimensions in your technical drawings to use a specific font and have a certain text size. You would go to `DocumentProperties > Annotation Styles`, edit your style, and set the font and text height. All dimensions using that style will update.

### Other Information
Understanding and properly configuring the Document Properties is essential for professional and accurate modeling.

---

## 195. DocumentPropertiesPage

### Short Info
Open a specific page in the Document Properties dialog.

### Detailed Description
The **DocumentPropertiesPage** command is a utility that opens the Document Properties dialog box directly to a specific page that you name. This is a shortcut to avoid having to open the main dialog and then navigate to the page you want.

### Steps to use the command
1.  Run the command `DocumentPropertiesPage`.
2.  At the **Page name** prompt, type the name of the page you want to open (e.g., "Units", "Grid").
3.  The Document Properties dialog box will open with that page already selected.

### Command Options & Toggles
This command has no options other than the page name you provide.

### Note for better use
This command is most useful when creating custom toolbar buttons or macros for quick access to a settings page you use frequently.

### Practical Use Cases
* **Use Case 1 (Custom Toolbar):** You frequently need to adjust the render mesh settings for your models. You could create a custom button on your toolbar with the macro `! _DocumentPropertiesPage Mesh` to instantly open the mesh settings without any extra clicks.

### Other Information
This is a simple workflow efficiency command for power users.

---

## 196. DollyZoom

### Short Info
Move the camera location and change the lens length simultaneously.

### Detailed Description
The **DollyZoom** command is a camera manipulation tool that creates a cinematic effect known as a "dolly zoom" or "Vertigo effect." It works by moving the camera toward or away from the target while simultaneously changing the camera's lens length. This results in the main subject staying the same size in the frame, while the background appears to either expand and become more distorted, or compress and become flatter.

### Steps to use the command
1.  Make a perspective viewport active.
2.  Run the command `DollyZoom`.
3.  Drag the mouse up or down in the viewport to perform the dolly zoom.
4.  Click to end the command.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a purely visual, cinematic effect and has no practical application for the geometric modeling of jewelry. It is used for creating dramatic camera movements for animations or presentations.

### Practical Use Cases
* **Use Case 1 (Animation):** You are creating an animation to present a ring and want to create a dramatic shot where the ring stays in focus but the background seems to warp around it. `DollyZoom` is the tool used to create this specific camera effect.

### Other Information
This is a specialized camera tool for creating a specific visual effect.

---

## 197. Domain

### Short Info
Report the domain of a curve or surface.

### Detailed Description
The **Domain** command is a technical analysis tool that reports the "domain" of a curve or surface. The domain is the range of numbers (from a minimum to a maximum) that Rhino uses internally to describe the parameter space of an object. For a curve, this is a single range (e.g., from 0 to 12.5). For a surface, it has two ranges, one for the U direction and one for the V direction.

### Steps to use the command
1.  Select a curve or surface.
2.  Run the command `Domain`.
3.  The domain range(s) will be reported in the command history.

### Command Options & Toggles
This command has no options.

### Note for better use
Understanding the domain is an advanced concept, but it can be important for certain scripting and surfacing workflows. For example, some commands work best on objects that have a simple domain (like 0 to 1). The `Rebuild` command can be used to simplify an object's domain.

### Practical Use Cases
* **Use Case 1 (Scripting):** A script writer is creating a tool that needs to place an object at the exact midpoint of a curve. They can use the `Domain` command to find the start and end values of the curve's parameter space, and then calculate the midpoint value to use in their script.

### Other Information
This is an advanced, technical command primarily used by scripters and power users.

---

## 198. Dot

### Short Info
Create an annotation dot.

### Detailed Description
The **Dot** command creates a small, text-based annotation object that is used to mark a location and display a short piece of text. The dot is always parallel to the view and scales with the view, so it remains readable even when you zoom in and out.

### Steps to use the command
1.  Run the command `Dot`.
2.  At the **Location of annotation dot** prompt, pick a point.
3.  The text from the previous dot is displayed. Press Enter to accept it, or type new text and press Enter.

### Command Options & Toggles
This command has no options.

### Note for better use
The appearance of the dot (font, size) is controlled by the current Annotation Style settings in your Document Properties.

### Practical Use Cases
* **Use Case 1 (Leaving Notes):** You are working on a design and need to leave a note for yourself or a colleague about a specific area, for example, "Check thickness here." You can use the `Dot` command to place a marker with that text directly on the model.
* **Use Case 2 (Labeling Parts):** You have a complex assembly and want to label the different parts. You can use dots to label the "shank," "head," "gallery," etc.

### Other Information
This is a fundamental annotation tool for communication and note-taking within a model.

---

## 199. DraftAngleAnalysis

### Short Info
Visually evaluate surface draft angle.

### Detailed Description
The **DraftAngleAnalysis** command is a powerful manufacturing analysis tool. It applies a false-color map to a surface that visually represents its "draft angle" relative to the construction plane. The draft angle is the amount of taper on a vertical surface, which is critical for ensuring that a part can be easily removed from a mold.

### Steps to use the command
1.  Select the object(s) to analyze.
2.  Run the command `DraftAngleAnalysis`.
3.  A dialog box appears where you can set the minimum and maximum angles for the color display.
4.  The object will be colored in the viewport. Areas with sufficient draft will be one color (e.g., green), and areas with insufficient or negative draft will be another color (e.g., red).

### Command Options & Toggles
The options are in the dialog box:
* **Min angle / Max angle:** Sets the angle range for the color display.
* **Auto Range:** Automatically sets the range based on the object.

### Note for better use
This command is essential for anyone designing parts that will be cast using a rubber or metal mold. It instantly shows you any "undercuts" or vertical walls that would prevent the part from being removed from the mold.

### Practical Use Cases
* **Use Case 1 (Checking a Signet Ring for Molding):** You have designed a signet ring that will be mass-produced via casting in a rubber mold. Before sending the file, you must run `DraftAngleAnalysis`. This will highlight any surfaces on the side of the ring that are perfectly vertical (90 degrees) or undercut, which would tear the mold. You can then add a slight taper to these surfaces until the analysis shows all green.
* **Use Case 2 (Analyzing a Bezel):** You want to ensure the inside wall of a bezel has a consistent taper to allow for easy stone setting. `DraftAngleAnalysis` can provide a clear visual confirmation of this taper.

### Other Information
This is a critical pre-manufacturing analysis tool.

---

## 200. DraftAngleAnalysisOff

### Short Info
Turn off draft angle analysis.

### Detailed Description
The **DraftAngleAnalysisOff** command is a simple utility that turns off the false-color draft angle map created by the `DraftAngleAnalysis` command and returns the objects to their normal display color.

### Steps to use the command
1.  Run the command `DraftAngleAnalysisOff`.
2.  The draft angle analysis display will be turned off for all objects.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Ending Analysis):** You have finished inspecting your model with `DraftAngleAnalysis` and have fixed all the problem areas. You now want to continue modeling. You run `DraftAngleAnalysisOff` to remove the color map and return to a standard shaded view.

### Other Information
This is the companion command to `DraftAngleAnalysis`.


---

## 201. DraftAnglePoint

### Short Info
Place a point object on a surface at a specified draft angle.

### Detailed Description
The **DraftAnglePoint** command is a specialized analysis tool used to find and mark specific points on a surface that correspond to a certain draft angle. The "draft angle" is the angle of a surface relative to a construction plane, which is critical for manufacturing parts in a mold. This command places point objects at the locations where the surface's angle matches the angle you specify.

### Steps to use the command
1.  Select a surface.
2.  Run the command `DraftAnglePoint`.
3.  At the **Draft angle** prompt, enter an angle value.
4.  At the **Pick point to start searching from** prompt, click a location on the surface.
5.  Point objects will be created on the surface at all locations that match the specified draft angle.

### Command Options & Toggles
This command has no clickable options. The angle is set via a numerical prompt.

### Note for better use
This command is a companion to the `DraftAngleAnalysis` command. While `DraftAngleAnalysis` gives you a visual color map of all angles, `DraftAnglePoint` allows you to find the exact location of a specific angle. The points are created on the active layer.

### Practical Use Cases
* **Use Case 1 (Finding the Parting Line):** In mold making, the "parting line" is often at the point of zero draft angle. You can run `DraftAnglePoint` and enter an angle of 0 to create a series of points that define the parting line of your model. You can then draw a curve through these points.
* **Use Case 2 (Verifying Taper):** You have designed a bezel and want to confirm that the inside wall has a consistent 3-degree taper. You can use this command with an angle of 3 to see if points are generated along the entire inner surface, confirming the taper is correct.

### Other Information
This is a technical tool primarily used for preparing models for molding and casting.

---

## 202. DragMode

### Short Info
Set the object drag mode.

### Detailed Description
The **DragMode** command controls how objects are moved relative to the construction plane or the camera when you click and drag them with the mouse. It allows you to switch between different modes for more intuitive control depending on the task.

### Steps to use the command
1.  Run the command `DragMode`.
2.  The command line will show the available modes.
3.  Click on the desired option (e.g., `CPlane`).

### Command Options & Toggles
* **CPlane:** When you drag an object, it will move parallel to the active construction plane.
* **View:** When you drag an object, it will move parallel to the view plane (the computer screen).
* **UVN:** (For single surfaces) Moves the object along the surface's U, V, or Normal directions.

### Note for better use
The `UVN` mode is particularly powerful for making fine adjustments to objects that are already on a curved surface, as it allows you to slide them along the surface's natural flow.

### Practical Use Cases
* **Use Case 1 (Standard Dragging - CPlane):** This is the default mode. When you are in the Top view and drag an object, it moves along the world XY plane.
* **Use Case 2 (Screen-Based Adjustments - View):** You are arranging objects in a perspective view for a render and want to nudge an object slightly to the left on your screen. Setting the `DragMode` to `View` allows you to do this without worrying about which 3D axis it's moving on.

### Other Information
This is a user-preference command that changes the behavior of a core interface action.

---

## 203. Drape

### Short Info
Create a surface through the intersections of objects and points projected toward the construction plane.

### Detailed Description
The **Drape** command creates a new, flexible NURBS surface over the top of selected objects. It works by creating a grid of points and projecting them "downward" onto the objects in the active viewport. A new surface is then created by fitting it through these projected points. It's like dropping a digital cloth over your models.

### Steps to use the command
1.  Arrange the objects you want to drape over in a viewport (e.g., the Top view).
2.  Run the command `Drape`.
3.  You will be prompted: **"Drag a window to drape"**. Draw a rectangle that covers all the objects.
4.  A new surface that conforms to the top contours of the objects will be created.

### Command Options & Toggles
* **Spacing:** Controls the density of the grid used to create the surface. A smaller spacing value creates a more detailed but heavier surface.

### Note for better use
The `Drape` command is view-dependent. It projects the grid from your current camera angle. For most predictable results, run the command from one of the standard orthographic views (Top, Front, or Right).

### Practical Use Cases
* **Use Case 1 (Creating a Pave Surface):** You have arranged dozens of gemstones in a complex, multi-level layout and now need to create a single, smooth surface that flows over the top of them, which will become the metal for a pavé setting. `Drape` is the perfect tool for this.
* **Use Case 2 (Creating Terrain):** You have a series of contour curves representing a landscape. You can use `Drape` in the Top view to create a single, smooth terrain surface that passes through all these curves.

### Other Information
This is a powerful tool for creating organic surfaces from complex arrangements of other objects.

---

## 204. DrapePt

### Short Info
Create a grid of points over objects.

### Detailed Description
The **DrapePt** (Drape Points) command works just like the `Drape` command, but instead of creating a surface, it creates a grid of point objects that lie on the surface of the underlying geometry.

### Steps to use the command
1.  Arrange the objects you want to drape over in a viewport.
2.  Run the command `DrapePt`.
3.  You will be prompted: **"Drag a window to drape"**. Draw a rectangle that covers all the objects.
4.  A grid of point objects will be created on the surfaces of the underlying geometry.

### Command Options & Toggles
* **Spacing:** Controls the density of the point grid.

### Note for better use
This command is useful when you need the reference points for another operation but don't need the full surface created by the `Drape` command.

### Practical Use Cases
* **Use Case 1 (Reference for Stone Setting):** You want to manually place gemstones on a complex organic surface. You can use `DrapePt` to create a regular grid of points on the surface, which you can then use as snap points to precisely place your stones.

### Other Information
This is the point-cloud equivalent of the `Drape` command.

---

## 205. DupBorder

### Short Info
Create a curve that duplicates a surface or polysurface border.

### Detailed Description
The **DupBorder** (Duplicate Border) command creates a new curve or curves that are an exact duplicate of the outer boundary of a selected surface or polysurface. If the object has holes, it will also create curves duplicating the borders of the holes.

### Steps to use the command
1.  Select one or more surfaces or polysurfaces.
2.  Run the command `DupBorder`.
3.  New curves will be created along all outer borders and hole borders of the selected objects.

### Command Options & Toggles
This command has no options.

### Note for better use
The resulting curves will often be joined into a single polycurve for each continuous border. If you only need to duplicate a single edge of a surface, use the `DupEdge` command instead.

### Practical Use Cases
* **Use Case 1 (Creating a Bezel Lip):** You have modeled a solid bezel. To create the lip that will hold the stone, you can use `DupBorder` on the top surface of the bezel. This will create two curves: one for the outer edge and one for the inner edge. You can then use these curves to `Loft` or `Sweep` the lip.
* **Use Case 2 (Offsetting a Shank):** You want to create a raised edge on a ring shank. Use `DupBorder` on the shank's main surface to get its outline curve. You can then `Offset` this curve inward and use the two curves to create the raised detail.

### Other Information
This is a fundamental command for extracting key curves from existing surfaces.

---

## 206. DupDimStyle

### Short Info
Create new dimension styles by copying existing styles.

### Detailed Description
The **DupDimStyle** (Duplicate Dimension Style) command is a utility for managing annotation styles. It allows you to create a new dimension style by making a copy of an existing one. This is much faster than creating a new style from scratch, as you can simply duplicate a style that is close to what you need and then make minor modifications.

### Steps to use the command
1.  Run the command `DupDimStyle`.
2.  At the **Name of dimension style to copy** prompt, enter the name of an existing style.
3.  At the **New dimension style name** prompt, enter a name for the new style.
4.  A new dimension style will be created with the same settings as the original.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Creating Drawing Variations):** You have a standard dimension style for your 1:1 drawings. You need to create a new style for 2:1 drawings where the text and arrowheads are half the size. You can use `DupDimStyle` to copy your standard style, and then simply edit the copy to change the size values.

### Other Information
This is a time-saving utility for managing your annotation standards.

---

## 207. DupEdge

### Short Info
Create a curve that duplicates a surface edge.

### Detailed Description
The **DupEdge** (Duplicate Edge) command creates new, independent curve objects that are exact duplicates of selected surface or polysurface edges. This is one of the most common and essential commands for extracting specific pieces of geometry from a 3D model to use for new construction.

### Steps to use the command
1.  Run the command `DupEdge`.
2.  At the **Select edges to duplicate** prompt, click on the individual edges you want to copy.
3.  Press Enter when you are finished selecting edges.
4.  New curves will be created in the exact location of the selected edges.

### Command Options & Toggles
This command has no options.

### Note for better use
The new curves are created on the current layer. It's good practice to set your "Curves" layer as current before running this command to keep your model organized. If you need to duplicate the entire border of a surface at once, use `DupBorder`.

### Practical Use Cases
* **Use Case 1 (Creating Rails for a Sweep):** This is a primary use case. You have modeled the main body of a ring and now want to add a channel setting on the side. You can use `DupEdge` to duplicate the top and bottom edges of the shank's side. These two new curves are the perfect rails to use for a `Sweep2` command to create the channel walls.
* **Use Case 2 (Creating a Ring Rail from a Shank):** You have a finished ring model and need to get the exact curve representing the inner finger hole. Use `DupEdge` to select the inner edges of the shank, and then `Join` the resulting arcs into a single circular curve.

### Other Information
This is a workhorse command used constantly in advanced modeling workflows.

---

## 208. DupFaceBorder

### Short Info
Create a curve that duplicates a polysurface face border.

### Detailed Description
The **DupFaceBorder** (Duplicate Face Border) command is a combination of `DupBorder` and sub-object selection. It creates a new curve that is an exact duplicate of the border of a single, selected face on a polysurface.

### Steps to use the command
1.  Run the command `DupFaceBorder`.
2.  At the **Select a polysurface face** prompt, click on the face you want to duplicate the border of.
3.  A new curve will be created along the border of that specific face.

### Command Options & Toggles
This command has no options.

### Note for better use
This is faster than using `DupBorder` on a whole object and then deleting the unwanted curves. It allows you to extract the outline of a single face in one step.

### Practical Use Cases
* **Use Case 1 (Creating an Inlay):** You have a signet ring and want to create a shallow pocket on top for an inlay. You can use `DupFaceBorder` to get the exact curve of the top face. You can then `Offset` this curve inward and use the result to trim the pocket into the ring.
* **Use Case 2 (Placing Gems on a Face):** You want to set a pattern of gemstones that is perfectly contained within a single facet of a complex model. Use `DupFaceBorder` to get the outline of that facet, which you can then use as a boundary for your gem layout.

### Other Information
This is a very efficient command for extracting the boundary of a specific part of a larger object.

---

## 209. DupLayer

### Short Info
Copy a layer including all of its objects.

### Detailed Description
The **DupLayer** (Duplicate Layer) command creates a complete duplicate of a selected layer. This includes copying the layer's name (with a "Copy" suffix), color, and all of its settings, as well as creating copies of all the geometry that resides on that layer.

### Steps to use the command
1.  Run the command `DupLayer`.
2.  At the **Select layer to duplicate** prompt, select a layer in the Layer panel.
3.  A new layer will be created with copies of all the original objects.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a very fast way to create a complete backup or a new version of a specific part of your model that is organized on its own layer.

### Practical Use Cases
* **Use Case 1 (Design Iteration):** You have a complete ring design, and all its parts (shank, head, prongs) are on a layer named "Ring Version 1." You want to create a new version with thicker prongs. You can run `DupLayer` on the "Ring Version 1" layer. This will create a new layer named "Ring Version 1 Copy" with a complete, independent copy of the ring. You can then rename the new layer to "Ring Version 2" and make your edits without affecting the original.

### Other Information
This is a powerful organizational tool for managing design variations.

---

## 210. DupMeshHoleBoundary

### Short Info
Create a polyline that duplicates the boundary of a hole in a mesh.

### Detailed Description
The **DupMeshHoleBoundary** (Duplicate Mesh Hole Boundary) command is a mesh repair tool. It creates a closed polyline curve that is an exact duplicate of the edge of a hole in a mesh object.

### Steps to use the command
1.  Select a mesh that has one or more holes.
2.  Run the command `DupMeshHoleBoundary`.
3.  Closed polyline curves will be created around each hole in the mesh.

### Command Options & Toggles
This command has no options.

### Note for better use
The resulting polyline can be used as a guide for rebuilding the missing section of the mesh. For example, you could use the curve with the `Patch` command to create a NURBS surface to fill the hole, and then mesh that new surface.

### Practical Use Cases
* **Use Case 1 (Patching Complex Holes):** You have an imported STL file with a large, irregular hole. The `FillMeshHole` command is failing to close it correctly. You can use `DupMeshHoleBoundary` to create a clean curve around the hole. This curve gives you a much better starting point for manually rebuilding the patch with other surfacing tools.

### Other Information
This is a useful utility in an advanced mesh repair workflow.

---

## 211. EarthAnchorPoint

### Short Info
Add geographic location data to a model.

### Detailed Description
The **EarthAnchorPoint** command is a specialized tool used in architecture, civil engineering, and GIS (Geographic Information System) workflows. It allows you to embed real-world geographic location data (latitude, longitude, elevation) into your Rhino model. This anchors the model to a specific spot on the Earth.

### Steps to use the command
1.  Run the command `EarthAnchorPoint`.
2.  A dialog box appears.
3.  You can manually enter the latitude and longitude, or use the map to find a location.
4.  You also specify a corresponding point in your model that will be linked to that geographic location.

### Command Options & Toggles
All options are contained within the dialog box for setting the location and model reference point.

### Note for better use
This command has no practical application in standard jewelry design. It is for large-scale projects that need to be geo-located.

### Practical Use Cases
* **Use Case 1 (Architecture):** An architect has designed a building in Rhino. They use the `EarthAnchorPoint` to set the exact real-world location of the building's corner. This allows them to perform accurate sun studies and to correctly position the model in mapping software like Google Earth.

### Other Information
This is a tool for a completely different design discipline.

---

## 212. Echo

### Short Info
Display script commands in the history window.

### Detailed Description
The **Echo** command is a utility used in scripting. It controls whether the commands being run by a script are displayed (echoed) in the command history window.

### Steps to use the command
1.  This command is typically used inside a script file.
2.  The line `Rhino.Echo` in a script will turn on the display of subsequent commands.

### Command Options & Toggles
This command is a toggle within a script.

### Note for better use
The opposite command is `NoEcho`, which turns off the display of commands. By default, commands in a script are echoed.

### Practical Use Cases
* **Use Case 1 (Script Debugging):** You are writing a complex script, and you want to see each command as it is executed to make sure the script is running correctly. You would ensure that `Echo` is active. If you want the script to run silently and faster, you would add `NoEcho` at the beginning.

### Other Information
This is a utility for script developers.

---

## 213. EdgeSrf

### Short Info
Create a surface from two, three, or four curves.

### Detailed Description
The **EdgeSrf** (Edge Surface) command is a fundamental surface creation tool. It creates a simple NURBS surface from a network of two, three, or four curves that form a closed boundary. The curves must touch at their endpoints.

### Steps to use the command
1.  Run the command `EdgeSrf`.
2.  At the **Select 2, 3, or 4 open curves** prompt, select the boundary curves.
3.  A new surface will be created that fills the area between the curves.

### Command Options & Toggles
This command has no options.

### Note for better use
This command creates the simplest possible surface that will fit the input curves. It does not offer any control over the interior shape of the surface. For more control, you should use commands like `Loft`, `Sweep2`, or `NetworkSrf`.

### Practical Use Cases
* **Use Case 1 (Filling a Simple Opening):** You have created the four edge curves that define a single facet on a gemstone model. `EdgeSrf` is the perfect tool to create the simple, flat surface that fills that four-sided boundary.
* **Use Case 2 (Creating a Basic Shank Surface):** You have two rail curves for the edges of a ring shank, and two profile curves for the ends. If these four curves are joined into a closed loop, `EdgeSrf` can create the basic surface for the shank.

### Other Information
This is a basic but very reliable tool for creating simple surfaces from a closed loop of edge curves.

---

## 214. EditLightByLooking

### Short Info
Aim a spotlight to match the view.

### Detailed Description
The **EditLightByLooking** command is a utility for adjusting spotlights. It allows you to interactively aim a spotlight by simply manipulating a viewport, as if you were looking through the light itself.

### Steps to use the command
1.  Select a spotlight object.
2.  Run the command `EditLightByLooking`.
3.  The active viewport will change to look from the spotlight's point of view.
4.  You can now tumble, pan, and zoom this view to aim the light.
5.  Press Enter when you are finished.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a very intuitive way to aim a light, as it gives you a "light's-eye view" of the scene.

### Practical Use Cases
* **Use Case 1 (Highlighting a Gem):** You are setting up a render and have created a spotlight to create a bright highlight on the main gemstone. To aim it perfectly, you can use `EditLightByLooking` to look "through" the spotlight and position the highlight exactly where you want it on the stone's facets.

### Other Information
This is a useful tool for interactive lighting setup for rendering.

---

## 215. EditPtOn

### Short Info
Display edit points on a curve.

### Detailed Description
The **EditPtOn** (Edit Points On) command displays a special type of point on a curve called an "edit point." Unlike control points (which are off the curve), edit points lie directly *on* the curve. Moving an edit point will change the shape of the curve while ensuring the curve continues to pass through that specific point's new location.

### Steps to use the command
1.  Select one or more curves.
2.  Run the command `EditPtOn`.
3.  Edit points will appear on the curves.

### Command Options & Toggles
This command has no options.

### Note for better use
Edit points are a result of the curve's knot structure. They are different from control points (`PointsOn` or F10). Editing a curve via its edit points can be less intuitive than using control points, but it is useful in specific situations where you need the curve to pass through an exact location. To turn them off, use the `PointsOff` command (F11).

### Practical Use Cases
* **Use Case 1 (Precision Adjustments):** You have a curve that must pass through a very specific coordinate in space. You can turn on its edit points and move the relevant point to that exact coordinate, guaranteeing the curve passes through it.

### Other Information
For most free-form, organic modeling, editing with control points (`PointsOn`) is more common and intuitive.

---

## 216. EditPythonScript

### Short Info
Open the Python script editor.

### Detailed Description
The **EditPythonScript** command opens Rhino's built-in editor for writing and running scripts using the Python programming language. This is an advanced tool for automating tasks and creating custom tools.

### Steps to use the command
1.  Run the command `EditPythonScript`.
2.  The Python script editor window will open.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Automation):** A designer performs the same sequence of 20 commands every time they start a new ring project. A script writer could use the Python editor to write a script that runs all 20 of those commands automatically with a single click.

### Other Information
This is a tool for developers and advanced users who want to extend Rhino's functionality.

---

## 217. EditScript

### Short Info
Open the RhinoScript editor.

### Detailed Description
The **EditScript** command opens Rhino's built-in editor for writing and running scripts using the RhinoScript language, which is based on VBScript. This is the older scripting tool in Rhino, largely superseded by the Python editor, but still functional.

### Steps to use the command
1.  Run the command `EditScript`.
2.  The RhinoScript editor window will open.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Legacy Scripts):** A user needs to run or modify an older custom tool that was written in RhinoScript. They would use this editor to do so.

### Other Information
For new scripting projects, it is highly recommended to use the `EditPythonScript` editor instead, as Python is a more modern and powerful language.

---

## 218. EditText

### Short Info
Open a text edit window.

### Detailed Description
The **EditText** command opens an edit window that allows you to change the text content of an existing annotation dot or text object.

### Steps to use the command
1.  Select one or more text or dot objects.
2.  Run the command `EditText`.
3.  An edit box will appear, allowing you to type new text.
4.  Click OK to apply the changes.

### Command Options & Toggles
This command has no options.

### Note for better use
Double-clicking on a text or dot object is a much faster way to open the text edit window.

### Practical Use Cases
* **Use Case 1 (Correcting a Note):** You have placed an annotation dot on your model with the text "Check thickness," but you meant to write "Check width." You can select the dot, run `EditText`, and correct the text.

### Other Information
This is a basic annotation editing tool.

---

## 219. Ellipse

### Short Info
Draw a closed elliptical curve.

### Detailed Description
The **Ellipse** command is a 2D drawing tool used to create a closed elliptical curve. It offers several methods for defining the ellipse's shape and orientation.

### Steps to use the command
1.  Run the command `Ellipse`.
2.  Follow the prompts for the chosen creation method. For the default method (Center, Axis, Axis):
    a. At the **Center of ellipse** prompt, pick a point.
    b. At the **End of first axis** prompt, pick a point to define the length and direction of the first axis.
    c. At the **End of second axis** prompt, pick a point to define the length of the second axis.

### Command Options & Toggles
* **Diameter:** Allows you to define the axes by their diameter instead of their radius.
* **FromFoci:** Creates the ellipse by defining its two focal points.
* **Deformable:** Creates a higher-degree, more easily editable NURBS approximation of an ellipse.

### Note for better use
An ellipse is a degree 2 curve.

### Practical Use Cases
* **Use Case 1 (Drawing Oval Gems):** The `Ellipse` command is the primary tool for drawing the outline of an oval-shaped gemstone. You would typically use the default method, defining the center, the length, and then the width of the stone.
* **Use Case 2 (Creating an Oval Bezel):** To create a bezel for an oval stone, you would first draw the main ellipse, then use the `Offset` command to create a second, larger ellipse for the outer wall.

### Other Information
This is a fundamental tool for creating non-circular, rounded shapes.

---

## 220. Ellipsoid

### Short Info
Draw a solid ellipsoid.

### Detailed Description
The **Ellipsoid** command is a solid creation tool that creates a 3D solid ellipsoid, which is like a sphere that has been stretched or squashed along its axes.

### Steps to use the command
1.  Run the command `Ellipsoid`.
2.  Follow the prompts. For the default method (Center, Axis, Axis, Axis):
    a. At the **Center of ellipsoid** prompt, pick a point.
    b. At the **End of first axis** prompt, pick a point.
    c. At the **End of second axis** prompt, pick a point.
    d. At the **End of third axis** prompt, pick a point.

### Command Options & Toggles
* **FromFoci:** Creates the ellipsoid by defining its focal points.

### Note for better use
This is the 3D equivalent of the `Ellipse` command.

### Practical Use Cases
* **Use Case 1 (Modeling a Cabochon):** You need to model a smooth, dome-shaped cabochon gemstone. You can create an ellipsoid and then use a cutting plane to `Trim` away the bottom half, leaving a perfect cabochon shape.
* **Use Case 2 (Organic Forms):** An ellipsoid is a great starting point for sculpting organic shapes. You can create a basic ellipsoid and then use tools like `CageEdit` or control point editing to push and pull it into a more complex, free-form shape.

### Other Information
This is one of the basic solid modeling primitives.

---

## 221. EMap

### Short Info
Visually evaluate surface smoothness using an environment map.

### Detailed Description
The **EMap** (Environment Map) command is a surface analysis tool that temporarily applies a reflective image map onto selected objects. This allows you to visually inspect the quality and smoothness of a surface by looking at how the reflections flow across it. Smooth, flowing reflections indicate a high-quality surface, while wavy, broken, or jagged reflections reveal flaws.

### Steps to use the command
1.  Select the object(s) to analyze.
2.  Run the command `EMap`.
3.  A file browser will open. Select an image to use for the reflection map (often a striped or high-contrast image).
4.  The selected objects will appear to be highly reflective in the viewport.

### Command Options & Toggles
* **BlendWithObjectColor:** Blends the reflection map with the object's original display color.
* **Browse:** Allows you to select a different image file for the map.

### Note for better use
This is a temporary display mode for analysis. It does not actually apply a material to the object. To turn it off, use the `EMapOff` command. This tool is very similar in purpose to the `Zebra` command but provides a different kind of visual feedback.

### Practical Use Cases
* **Use Case 1 (Checking for Surface Continuity):** You have joined two surfaces together with `BlendSrf` and want to check if the connection is perfectly smooth. Applying an `EMap` will show you how reflections flow across the seam. If the reflection lines are smooth and unbroken, the connection is good (G2 continuity). If the lines have a sharp kink, the connection is only tangent (G1).
* **Use Case 2 (Finding Surface Flaws):** You have a large, flowing surface on a bracelet that looks smooth, but you suspect there might be small wrinkles or imperfections. An `EMap` will make these flaws highly visible, as the reflection lines will become wavy or distorted in the problem areas.

### Other Information
This is an essential tool for any designer creating high-quality, "Class-A" surfaces that need to be perfectly smooth.

---

## 222. EMapOff

### Short Info
Turn off environment map display.

### Detailed Description
The **EMapOff** command is a simple utility that turns off the environment map display created by the `EMap` command and returns the objects to their normal display color.

### Steps to use the command
1.  Run the command `EMapOff`.
2.  The environment map display will be turned off.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Ending Analysis):** You have finished inspecting your surfaces with `EMap` and now want to continue modeling. You run `EMapOff` to remove the reflective display.

### Other Information
This is the companion command to `EMap`.

---

## 223. EnableClippingPlane

### Short Info
Turn on selected clipping planes in the active viewport.

### Detailed Description
The **EnableClippingPlane** command activates the effect of a selected `ClippingPlane` object that has been previously disabled in the currently active viewport.

### Steps to use the command
1.  Make the viewport where you want to enable the effect active.
2.  Run the command `EnableClippingPlane`.
3.  At the **Select clipping planes to enable** prompt, select the clipping plane object(s).
4.  The clipping effect will be turned on in the active viewport.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the opposite of the `DisableClippingPlane` command.

### Practical Use Cases
* **Use Case 1 (Toggling a Section View):** You have disabled a clipping plane in your Top view to take some measurements. Now you want to see the cross-section in that view again. You make the Top view active and use `EnableClippingPlane` to turn the effect back on.

### Other Information
This command provides viewport-specific control over the display of clipping planes.

---

## 224. EndBulge

### Short Info
Adjust the shape of a curve near its end.

### Detailed Description
The **EndBulge** command is a curve and surface editing tool that allows you to adjust the "fullness" or "bulge" of a curve or surface near its endpoint. It works by moving the second-to-last control point along a line connecting it to the two adjacent control points, which makes the shape fuller or flatter without changing the endpoint's location or tangency.

### Steps to use the command
1.  Run the command `EndBulge`.
2.  At the **Select curve or surface edge for bulging** prompt, select an object near its end.
3.  The command will highlight the second-to-last control point.
4.  Drag this point with the mouse to interactively adjust the bulge.
5.  Click to set the new shape.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a very intuitive tool for making subtle adjustments to the shape of a curve's end without having to manually select and move individual control points.

### Practical Use Cases
* **Use Case 1 (Fine-Tuning a Shank Profile):** You have created a profile curve for a ring shank, but the transition where it meets the top of the ring is a little too sharp. You can use `EndBulge` to subtly "fatten up" the curve just before the endpoint, creating a fuller and more graceful transition.

### Other Information
This is a specialized tool for fine-tuning the shape of curves and surfaces.

---

## 225. Enter

### Short Info
Simulate pressing Enter in a script.

### Detailed Description
The **Enter** command is a utility used in scripts and macros to simulate the action of a user pressing the Enter key. This is used to accept the default option in a command, to complete a command, or to move to the next prompt.

### Steps to use the command
1.  This command is used inside a macro or script file.
2.  Typing `_Enter` in a macro is the same as a user pressing the Enter key.

### Command Options & Toggles
This command has no options.

### Note for better use
The underscore `_` in front of the command (`_Enter`) is important in scripting as it ensures the command will run on any language version of Rhino.

### Practical Use Cases
* **Use Case 1 (Scripting a Circle):** You are writing a macro to create a circle of a specific size at the origin. The macro would look like this: `! _Circle 0,0,0 5 _Enter`. The `_Enter` at the end completes the command after the radius of 5 has been entered.

### Other Information
This is a fundamental component of scripting in Rhino.

---

## 226. EnterEnd

### Short Info
Simulate pressing Enter to end a command in a script.

### Detailed Description
The **EnterEnd** command is a utility used in scripts and macros. It is similar to the `Enter` command but is specifically used to signal the completion of a command that can accept a variable number of inputs, like `Polyline` or `Loft`.

### Steps to use the command
1.  This command is used inside a macro or script file.
2.  It is placed at the point in the script where a user would press Enter to finish the command.

### Command Options & Toggles
This command has no options.

### Note for better use
In many cases, a simple `Enter` will work, but `EnterEnd` can be more robust in certain situations, especially when dealing with commands that might have multiple "Enter" presses during their sequence.

### Practical Use Cases
* **Use Case 1 (Scripting a Loft):** You are writing a script that selects three specific curves and then lofts them. The macro might look like: `! _SelName "Profile1" _SelName "Profile2" _SelName "Profile3" _Loft _EnterEnd`. The `_EnterEnd` tells the `Loft` command that you are finished selecting curves and it should now create the surface.

### Other Information
This is a scripting utility for controlling command flow.

---

## 227. EnvironmentEditor

### Short Info
Open the Environment Editor panel.

### Detailed Description
The **EnvironmentEditor** command opens a panel that allows you to create and manage rendering environments. An "environment" is what the reflective and refractive objects in your scene will "see." It can be a simple color, a gradient, or an image (like an HDRI file) that simulates a realistic surrounding like a photo studio or an outdoor scene.

### Steps to use the command
1.  Run the command `EnvironmentEditor`.
2.  The Environment Editor panel will open.
3.  You can create new environments, assign images to them, and set them as the background or reflection environment for your render.

### Command Options & Toggles
All options are contained within the panel for creating and editing environments.

### Note for better use
Using a high-quality HDRI (High Dynamic Range Image) as your reflection environment is one of the most important steps in creating realistic metal and gemstone renders.

### Practical Use Cases
* **Use Case 1 (Studio Lighting):** You want to render your jewelry in a clean, white "photo studio" environment. You would use the `EnvironmentEditor` to create a new environment and assign a studio HDRI image to it for reflections.
* **Use Case 2 (Realistic Background):** You want your ring render to look like it is sitting on a wooden table. You would set the background environment to be a simple color, but set the reflection environment to be an HDRI of an indoor room to get realistic reflections in the metal.

### Other Information
This is a fundamental panel for controlling the lighting and reflections in your renders.

---

## 228. EvaluatePt

### Short Info
Report the world and construction plane coordinates of a selected point.

### Detailed Description
The **EvaluatePt** (Evaluate Point) command is an analysis tool that reports the X, Y, and Z coordinates of a specific location. The location can be a point object, a control point, or any point you snap to on an object.

### Steps to use the command
1.  Run the command `EvaluatePt`.
2.  At the **Point to evaluate** prompt, select a point object or snap to a location.
3.  The command history will report the World coordinates and the active Construction Plane coordinates of that point.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a quick way to get the exact coordinates of any point on your model without having to create any new geometry.

### Practical Use Cases
* **Use Case 1 (Verifying Symmetry):** You have a ring that should be symmetrical. You can use `EvaluatePt` and snap to a control point on the left side of the shank and note its X-coordinate. Then, check the corresponding control point on the right side. Its X-coordinate should be the exact negative of the first point's.
* **Use Case 2 (Checking Height):** You need to confirm that the top of a prong is at a specific Z-height. Use `EvaluatePt` and snap to the prong tip to get its exact Z-coordinate.

### Other Information
This is a simple but very useful analysis and verification tool.

---

## 229. EvaluateUVPt

### Short Info
Report the UV coordinates of a point on a surface.

### Detailed Description
The **EvaluateUVPt** (Evaluate UV Point) command is a technical analysis tool for surfaces. It reports the U and V coordinates of a point that you pick on a surface. The U and V coordinates are the parameters that define a point's location within the surface's internal parameter space, which is used for things like texture mapping.

### Steps to use the command
1.  Select a surface.
2.  Run the command `EvaluateUVPt`.
3.  At the **Point to evaluate** prompt, click a location on the surface.
4.  The command history will report the U and V coordinates, as well as the 3D world coordinates, of that point.

### Command Options & Toggles
This command has no options.

### Note for better use
This is an advanced tool, primarily used by script writers or users who are doing very complex surfacing or texture mapping that requires an understanding of a surface's internal parameterization.

### Practical Use Cases
* **Use Case 1 (Scripting):** A script needs to place an object at a specific parametric location on a surface (e.g., halfway along the U direction and a quarter of the way along the V direction). A developer could use `EvaluateUVPt` to understand the surface's UV space while writing the script.

### Other Information
For most designers, this command is not part of a typical workflow.

---

## 230. Exit

### Short Info
Close Rhino.

### Detailed Description
The **Exit** command closes the Rhinoceros application. If the current file has unsaved changes, it will prompt you to save them before closing.

### Steps to use the command
1.  Run the command `Exit`.
2.  If your file is unsaved, a "Save changes" dialog will appear.
3.  The Rhino application will close.

### Command Options & Toggles
This command has no options.

### Note for better use
This is equivalent to clicking the "X" in the top-right corner of the Rhino window. The `Exit` command is primarily used in scripts.

### Practical Use Cases
* **Use Case 1 (Batch Processing Script):** You have a script that opens a file, performs a series of actions (like exporting an image), and then needs to close the program. The `Exit` command would be the last line in the script.

### Other Information
This is a simple application control command.


---

## 231. Explode

### Short Info
Break objects down into components.

### Detailed Description
The **Explode** command is a fundamental editing tool that breaks a complex object into its constituent, simpler parts. For example, it will break a polysurface into its individual surfaces, a polyline into separate line and arc segments, or a block instance into its component objects. This is a primary method for deconstructing objects to edit their individual pieces.

### Steps to use the command
1.  Select the object(s) to explode.
2.  Run the command `Explode`.
3.  The object will be broken down into its component parts.

### Command Options & Toggles
This command has no options.

### Note for better use
The opposite of `Explode` is `Join`, which connects separate curves or surfaces into a single object. Exploding a block instance is a one-way operation; you cannot easily re-assemble it back into a block. For editing blocks, it is always better to use the `BlockEdit` command.

### Practical Use Cases
* **Use Case 1 (Editing a Polysurface):** You have created a ring shank as a single closed polysurface, but you need to modify only one of the surfaces. You can `Explode` the ring, select and edit the single surface, and then `Join` all the surfaces back together into a solid.
* **Use Case 2 (Modifying a Curve):** You have a closed polyline that represents the outline of a pendant, and you want to change the shape of just one segment. You can `Explode` the polyline, delete or edit the single segment, and then `Join` the curves back together.

### Other Information
This is one of the most basic and essential editing commands in Rhino.

---

## 232. ExplodeBlock

### Short Info
Explode a block instance into its component objects.

### Detailed Description
The **ExplodeBlock** command is a specific version of the `Explode` command that works only on block instances. It breaks a selected block instance down into its individual component objects, severing the link to the block definition.

### Steps to use the command
1.  Select one or more block instances.
2.  Run the command `ExplodeBlock`.
3.  The block instances will be replaced by regular, independent geometry.

### Command Options & Toggles
This command has no options.

### Note for better use
Once a block is exploded, the resulting geometry is no longer linked to the block definition. This means that if you later edit the block definition using `BlockEdit`, the exploded geometry will **not** update. For this reason, it is almost always better to use `BlockEdit` to modify blocks rather than exploding them.

### Practical Use Cases
* **Use Case 1 (Making a Unique Variation):** You have placed 10 instances of a "prong" block in your model. You want to make one of those prongs slightly different from the others. You can select that single instance, run `ExplodeBlock`, and then edit the resulting geometry. The other 9 prong blocks will remain unchanged.

### Other Information
This is a destructive command that should be used with caution, as it breaks the powerful link between a block instance and its definition.

---

## 233. Export

### Short Info
Save selected objects to a new file.

### Detailed Description
The **Export** command saves the currently selected objects into a new file. Unlike the `Save` command, which saves the entire model, `Export` only saves the objects you have selected. It also allows you to save the new file in a wide variety of different file formats (e.g., .STL, .OBJ, .STEP, .AI) for use in other software.

### Steps to use the command
1.  Select the object(s) you want to export.
2.  Run the command `Export`.
3.  A file save dialog box will appear.
4.  Choose a location, enter a filename, and select the desired file type from the "Save as type" dropdown menu.
5.  Click "Save."

### Command Options & Toggles
The options are contained within the save dialog box and subsequent format-specific settings windows.

### Note for better use
Pay close attention to the options dialog that appears after you click "Save," as this is where you control the quality and settings for the exported file (e.g., the polygon density for an STL file, or the export scheme for a DWG file).

### Practical Use Cases
* **Use Case 1 (Creating an STL for 3D Printing):** You have finished modeling a ring. You select the final, solid polysurface of the ring, run `Export`, and choose ".STL (Stereolithography)" as the file type. This creates the file you will send to the 3D printer.
* **Use Case 2 (Sending Curves to Illustrator):** You have created a 2D pattern of curves that you want to use in a graphic design. You select the curves, run `Export`, and choose ".AI (Adobe Illustrator)" as the file type to create a file that can be opened and edited in Illustrator.

### Other Information
This is the primary command for sending your geometry to other applications.

---

## 234. ExportBitmaps

### Short Info
Save texture bitmaps to a folder.

### Detailed Description
The **ExportBitmaps** command is a utility that finds all the texture images (bitmaps) that are used by the materials in your current model and saves copies of them to a folder that you specify.

### Steps to use the command
1.  Run the command `ExportBitmaps`.
2.  A folder browser dialog will appear.
3.  Select a folder where you want to save the texture images.
4.  Click OK. Copies of all bitmap files will be saved to that folder.

### Command Options & Toggles
This command has no options.

### Note for better use
This is very useful for packaging a project to send to someone else for rendering. It ensures that you have gathered all the necessary texture files (like wood grains, metal finishes, etc.) into one place so they don't go missing.

### Practical Use Cases
* **Use Case 1 (Archiving a Project):** You have just finished a major project that uses many different textures from various locations on your computer. To archive the project neatly, you can use `ExportBitmaps` to save a copy of all the used textures into the main project folder, keeping everything together.

### Other Information
This is a file management and project organization utility.

---

## 235. ExportWithOrigin

### Short Info
Save objects to a new file with a specified origin and construction plane.

### Detailed Description
The **ExportWithOrigin** command is a more advanced version of the `Export` command. It allows you to select objects and save them to a new file, but it also lets you define a new origin (0,0,0 point) and construction plane for that new file.

### Steps to use the command
1.  Select the object(s) to export.
2.  Run the command `ExportWithOrigin`.
3.  You will be prompted to pick a new origin point.
4.  You will then be prompted to define the orientation of the new construction plane.
5.  A file save dialog box will appear. Choose a location, name, and file type.

### Command Options & Toggles
The options are presented as prompts for defining the new CPlane.

### Note for better use
This is very useful when exporting a part that needs to be inserted into another model at a specific location and orientation. By setting the origin at a key snap point (like the center of a gemstone), you can ensure that the exported part can be easily and precisely placed in the other file.

### Practical Use Cases
* **Use Case 1 (Creating a Component Library):** You have designed a custom 4-prong setting. You want to save it as a separate file in your component library. You would select the setting, run `ExportWithOrigin`, and pick the exact center of the setting as the new origin. Now, whenever you insert this file into a new design, it will import with its insertion point already at its center, making it easy to snap to a ring rail.

### Other Information
This is a powerful tool for creating modular, reusable components.

---

## 236. Extend

### Short Info
Lengthen a curve.

### Detailed Description
The **Extend** command is a 2D editing tool that lengthens a curve until it intersects with a selected boundary object.

### Steps to use the command
1.  Run the command `Extend`.
2.  At the **Select boundary objects** prompt, select one or more objects that will act as the boundary and press Enter.
3.  At the **Select curve to extend** prompt, click on the end of the curve that you want to lengthen.
4.  The curve will be extended until it meets the boundary.

### Command Options & Toggles
* **Type (Arc/Line):** You can choose to extend the curve with a natural arc or with a straight line.

### Note for better use
The opposite of this command is `Trim`. If a curve is already past the boundary object, the `Extend` command can also be used to trim it back.

### Practical Use Cases
* **Use Case 1 (Closing Gaps):** You have drawn the profile of a bezel, but one of the lines is slightly too short and does not touch the other side. You can use `Extend`, select the other side as the boundary, and click on the short line to close the gap perfectly.
* **Use Case 2 (Creating Construction Lines):** You need a line that goes from the end of an existing curve and extends all the way to the edge of your ring shank. `Extend` is the perfect tool for this.

### Other Information
This is a fundamental 2D editing and cleanup tool.

---

## 237. ExtendCrvOnSrf

### Short Info
Lengthen a curve on a surface.

### Detailed Description
The **ExtendCrvOnSrf** (Extend Curve On Surface) command lengthens a curve that lies on a surface until it meets the edge of that surface.

### Steps to use the command
1.  Run the command `ExtendCrvOnSrf`.
2.  At the **Select boundary edges** prompt, select the edge of the surface that you want to extend to and press Enter.
3.  At the **Select curve on surface to extend** prompt, click on the end of the curve that you want to lengthen.
4.  The curve will be extended along the surface until it meets the selected edge.

### Command Options & Toggles
This command has no options.

### Note for better use
The curve must lie on the surface for this command to work.

### Practical Use Cases
* **Use Case 1 (Creating Trim Objects):** You have drawn a decorative curve on the surface of a ring shank that you intend to use for a `Split` or `Trim` operation. The curve doesn't quite reach the edge of the shank. `ExtendCrvOnSrf` will lengthen the curve so that it fully crosses the surface, ensuring a clean split.

### Other Information
This is a specialized curve editing tool for working with curves that are on surfaces.

---

## 238. ExtendSrf

### Short Info
Lengthen a surface.

### Detailed Description
The **ExtendSrf** (Extend Surface) command lengthens a surface by a specified distance. It extends the surface by continuing the shape of the selected edge in a smooth, tangential direction.

### Steps to use the command
1.  Run the command `ExtendSrf`.
2.  At the **Select edge of surface to extend** prompt, click the edge you want to lengthen.
3.  At the **Extend distance** prompt, type a value and press Enter.
4.  The surface will be extended.

### Command Options & Toggles
* **Type (Smooth/Linear):**
    * **Smooth:** Extends the surface while maintaining its curvature.
    * **Linear:** Extends the surface with a straight, ruled section.

### Note for better use
This command works best on un-trimmed edges. Extending a trimmed edge can sometimes produce unpredictable results.

### Practical Use Cases
* **Use Case 1 (Making a Shank Longer):** You have modeled a ring shank, but you realize it needs to be slightly wider. You can use `ExtendSrf` on the side edges of the shank surface to lengthen it before performing other operations.
* **Use Case 2 (Creating Overlap for Booleans):** You have two surfaces that are supposed to intersect for a boolean operation, but they don't quite overlap. You can use `ExtendSrf` on one of the surfaces to make it slightly larger, ensuring a clean intersection.

### Other Information
This is a useful surface editing tool for making small size adjustments.

---

## 239. ExtractAnalysisMesh

### Short Info
Duplicate an analysis mesh.

### Detailed Description
The **ExtractAnalysisMesh** command is a utility that takes a temporary analysis mesh (like the one created by `Zebra` or `CurvatureAnalysis`) and creates a permanent, independent mesh object from it.

### Steps to use the command
1.  Run an analysis command like `Zebra` or `CurvatureAnalysis` on an object.
2.  Run the command `ExtractAnalysisMesh`.
3.  At the **Select objects with analysis meshes to extract** prompt, select the object.
4.  A new mesh object, with the analysis colors baked into its vertices, will be created.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Saving an Analysis):** You have performed a `CurvatureAnalysis` on a surface and want to save the result as part of a presentation to a client to show the quality of the surface. `ExtractAnalysisMesh` will create a permanent mesh object with the analysis colors that you can save, export, or render.

### Other Information
This is a specialized utility for capturing the results of visual analysis commands.

---

## 240. ExtractBadSrf

### Short Info
Separate invalid surfaces from a polysurface.

### Detailed Description
The **ExtractBadSrf** command is a diagnostic and repair tool. It inspects a polysurface and, if it finds any "bad" or corrupted individual surfaces within the object, it separates them from the main polysurface. This helps you to isolate and identify problematic geometry.

### Steps to use the command
1.  Select a polysurface that you suspect has errors.
2.  Run the command `ExtractBadSrf`.
3.  If any bad surfaces are found, they will be extracted as separate objects.

### Command Options & Toggles
This command has no options.

### Note for better use
A "bad" surface is one that has an invalid data structure, which can cause other commands to fail. After extracting a bad surface, you will typically need to delete it and remodel that section of the object.

### Practical Use Cases
* **Use Case 1 (Repairing an Import):** You have imported a STEP file from another CAD program, and the resulting object is causing errors. Running `ExtractBadSrf` can help you find which specific face of the polysurface was corrupted during the import process.

### Other Information
This is an important tool in an advanced model repair workflow.

---

## 241. ExtractConnectedMeshFaces

### Short Info
Separate mesh faces from a mesh.

### Detailed Description
The **ExtractConnectedMeshFaces** command is a mesh editing tool. It takes a selection of faces on a mesh and separates them from the main mesh, creating a new, independent mesh object from the selected faces.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `ExtractConnectedMeshFaces`.
3.  At the **Select mesh faces to extract** prompt, select one or more faces.
4.  Press Enter. A new mesh object will be created from the faces you selected.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is useful for breaking a single mesh object into multiple parts.

### Practical Use Cases
* **Use Case 1 (Separating a Scanned Model):** You have a 3D scan of a ring with the stone still in it, all as a single mesh. You can use this command to carefully select all the faces that make up the stone and extract them, separating the stone from the metal setting.

### Other Information
This is a fundamental tool for editing and deconstructing mesh objects.

---

## 242. ExtractControlPolygon

### Short Info
Create a polyline or mesh through the control points of a curve or surface.

### Detailed Description
The **ExtractControlPolygon** command is an analysis and construction tool. It creates a new object (a polyline for a curve, or a mesh for a surface) that represents the "control polygon" or "control net" of the selected object. This new object is a visual representation of the underlying structure that defines the shape of the smooth NURBS object.

### Steps to use the command
1.  Select a curve or surface.
2.  Run the command `ExtractControlPolygon`.
3.  A new polyline or mesh object will be created.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Visualizing Structure):** You are trying to understand why a surface has a particular shape. By extracting its control polygon, you can see the simple, faceted cage that is generating the complex, smooth surface.
* **Use Case 2 (Rebuilding):** You can extract the control polygon mesh of a surface, modify that simpler mesh, and then use the vertices of the modified mesh as the input for a new `SrfPtGrid` command to create a new, altered surface.

### Other Information
This is a useful tool for understanding and working with the underlying structure of NURBS geometry.

---

## 243. ExtractCurvatureGraph

### Short Info
Create a curve from a curvature graph.

### Detailed Description
The **ExtractCurvatureGraph** command is a utility that takes a temporary curvature graph (created by the `CurvatureGraph` command) and creates a permanent, independent curve object from it.

### Steps to use the command
1.  Run the `CurvatureGraph` command on a curve.
2.  Run the command `ExtractCurvatureGraph`.
3.  At the **Select objects with curvature graphs to extract** prompt, select the curve.
4.  A new curve object, shaped like the curvature graph, will be created.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Analysis and Documentation):** You are preparing a report on the quality of a curve and want to include an image of its curvature graph in a 2D drawing. `ExtractCurvatureGraph` allows you to create a real curve from the graph that you can then place and dimension in your layout.

### Other Information
This is a specialized utility for capturing the results of the `CurvatureGraph` analysis command.

---

## 244. ExtractDuplicateMeshFaces

### Short Info
Find and separate duplicate mesh faces.

### Detailed Description
The **ExtractDuplicateMeshFaces** command is a mesh cleanup and repair tool. It searches a mesh object for any faces that are perfect duplicates of each other (i.e., they occupy the exact same space and have the same vertices). It then extracts these duplicate faces as a separate object, allowing you to delete them.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `ExtractDuplicateMeshFaces`.
3.  If any duplicate faces are found, they will be separated, and the command line will report how many were found.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Repairing Imported Meshes):** Sometimes when importing mesh files from other programs, errors in translation can result in duplicated faces. These can cause problems for 3D printing and boolean operations. This command is a one-step way to find and remove them.

### Other Information
This is an important command in a professional mesh repair workflow.

---

## 245. ExtractIsocurve

### Short Info
Create a curve that duplicates a surface isoparametric curve.

### Detailed Description
The **ExtractIsocurve** command is a fundamental curve-from-object tool. It allows you to create a new, independent curve that is an exact duplicate of a surface's "isocurve." Isocurves are the lines that are displayed on a NURBS surface in the viewport, representing the lines of constant U or V parameters.

### Steps to use the command
1.  Run the command `ExtractIsocurve`.
2.  At the **Select surface to extract isocurves from** prompt, select a surface.
3.  Move your mouse over the surface. A preview of the isocurve at your cursor's location will be shown.
4.  Click to create the curve. You can continue clicking to create multiple curves.

### Command Options & Toggles
* **Direction (U/V/Both):** Toggles whether you are extracting a U-direction isocurve, a V-direction isocurve, or both at once.
* **Toggle:** Switches between the U and V directions.

### Note for better use
This is one of the most common ways to create curves that perfectly follow the contour of an existing surface.

### Practical Use Cases
* **Use Case 1 (Creating Profile Curves):** You have a complex, curved ring shank and you need to get the cross-section profile at a specific location. You can run `ExtractIsocurve` and click on the shank to pull off a perfect profile curve at that exact spot.
* **Use Case 2 (Creating Paths for Gems):** You want to set a row of gems that follows the flow of a surface. You can extract an isocurve from the surface and then use that new curve as the path for the `ArrayCrv` or `GemsOnCurve` command.

### Other Information
This is a workhorse command for creating construction geometry from existing surfaces.

---

## 246. ExtractMeshEdges

### Short Info
Separate mesh faces from a mesh by their edge angles.

### Detailed Description
The **ExtractMeshEdges** command is a mesh editing tool that separates mesh faces based on the angle between them or whether their shared edges are welded or unwelded. It allows you to break a mesh apart based on its sharp corners or existing seams.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `ExtractMeshEdges`.
3.  A dialog box will appear with options.
4.  Set your options (e.g., `Unwelded` or `ByAngle`) and click OK.
5.  The mesh will be split into multiple separate mesh objects.

### Command Options & Toggles
* **Unwelded:** Splits the mesh only at unwelded ("naked") edges.
* **ByAngle:** Splits the mesh at any edge where the angle between the adjacent faces is greater than the specified value.

### Note for better use
This is a fast way to break a complex mesh object, like a faceted gemstone, into its individual faces or sections.

### Practical Use Cases
* **Use Case 1 (Separating Facets):** You have an STL model of a gemstone and you want to separate each facet into its own object. You can run `ExtractMeshEdges` with the `ByAngle` option set to a small value (e.g., 1 degree). This will split the mesh at every sharp edge between the facets.

### Other Information
This is a useful tool for deconstructing complex mesh objects.

---

## 247. ExtractMeshFaces

### Short Info
Separate selected faces from a mesh.

### Detailed Description
The **ExtractMeshFaces** command is a mesh editing tool. It takes a selection of faces on a mesh and separates them from the main mesh, creating a new, independent mesh object from the selected faces.

### Steps to use the command
1.  Run the command `ExtractMeshFaces`.
2.  At the **Select mesh faces to extract** prompt, select one or more faces and press Enter.
3.  A new mesh object will be created from the faces you selected.

### Command Options & Toggles
* **Copy:** Creates a copy of the faces instead of removing them from the original mesh.

### Note for better use
This is the mesh equivalent of the `ExtractSrf` command. To select individual mesh faces, you may need to hold down Ctrl+Shift.

### Practical Use Cases
* **Use Case 1 (Separating Parts of a Scan):** You have a 3D scan of a ring with the stone still in it, all as a single mesh. You can use this command to carefully select all the faces that make up the stone and extract them, separating the stone from the metal setting.

### Other Information
This is a fundamental tool for editing and deconstructing mesh objects.

---

## 248. ExtractMeshFacesByArea

### Short Info
Separate mesh faces from a mesh by area.

### Detailed Description
The **ExtractMeshFacesByArea** command is a mesh selection and editing tool. It finds all mesh faces that have an area larger or smaller than a value you specify and separates them from the original mesh.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `ExtractMeshFacesByArea`.
3.  At the prompt, choose whether you want to extract faces that are **LessThan** or **GreaterThan** a certain area.
4.  Enter an area value.
5.  The matching faces will be extracted as a new mesh object.

### Command Options & Toggles
* **LessThan/GreaterThan:** Sets the selection criteria.

### Practical Use Cases
* **Use Case 1 (Isolating Small Artifacts):** You have a mesh with many small, problematic artifact faces. You can use this command with the `LessThan` option and a small area value to select and extract all of these tiny faces at once so you can inspect or delete them.

### Other Information
This is a selection and editing tool for working with complex meshes.

---

## 249. ExtractMeshFacesByAspectRatio

### Short Info
Separate mesh faces from a mesh by aspect ratio.

### Detailed Description
The **ExtractMeshFacesByAspectRatio** command is a mesh selection and editing tool that finds and separates mesh faces that are long and skinny. The "aspect ratio" is a measure of how elongated a shape is.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `ExtractMeshFacesByAspectRatio`.
3.  At the prompt, choose whether you want to extract faces that are **LessThan** or **GreaterThan** a certain aspect ratio.
4.  Enter an aspect ratio value (e.g., 10 for faces that are 10 times longer than they are wide).
5.  The matching faces will be extracted as a new mesh object.

### Command Options & Toggles
* **LessThan/GreaterThan:** Sets the selection criteria.

### Practical Use Cases
* **Use Case 1 (Finding Sliver Faces):** You want to find and fix all the long, thin "sliver" faces in a mesh that was created from a trimmed NURBS surface. You can use this command with the `GreaterThan` option and a high aspect ratio value to select and extract all these problematic faces for repair.

### Other Information
This is a selection and editing tool for working with complex meshes.

---

## 250. ExtractMeshFacesByDraftAngle

### Short Info
Separate mesh faces from a mesh by draft angle.

### Detailed Description
The **ExtractMeshFacesByDraftAngle** command is a mesh selection and editing tool. It finds and separates mesh faces based on their draft angle relative to the construction plane.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `ExtractMeshFacesByDraftAngle`.
3.  Follow the prompts to define the draft angle range you want to extract.
4.  The matching faces will be extracted as a new mesh object.

### Command Options & Toggles
The options are presented as prompts to define the angle range.

### Practical Use Cases
* **Use Case 1 (Analyzing for Molds):** You have an STL file of a ring and need to analyze it for molding. You can use this command to extract all the faces that have a draft angle of less than 3 degrees, which would be problematic for a mold. This allows you to isolate and inspect only the problem areas.

### Other Information
This is a mesh-based companion to the `DraftAngleAnalysis` command.

---

## 251. ExtractMeshFacesByEdgeLength

### Short Info
Separate mesh faces from a mesh by edge length.

### Detailed Description
The **ExtractMeshFacesByEdgeLength** command is a mesh selection and editing tool. It finds and separates mesh faces that have edges that are shorter or longer than a value you specify.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `ExtractMeshFacesByEdgeLength`.
3.  At the prompt, choose whether you want to extract faces with edges that are **LessThan** or **GreaterThan** a certain length.
4.  Enter a length value.
5.  The matching faces will be extracted as a new mesh object.

### Command Options & Toggles
* **LessThan/GreaterThan:** Sets the selection criteria.

### Practical Use Cases
* **Use Case 1 (Finding Small Edges):** You are preparing a mesh for 3D printing, and the printer has a minimum feature size. You can use this command with the `LessThan` option to find and inspect any faces that have edges smaller than your printer's tolerance.

### Other Information
This is a selection and editing tool for working with complex meshes.

---

## 252. ExtractMeshPart

### Short Info
Separate disjoint pieces of a mesh.

### Detailed Description
The **ExtractMeshPart** command is a mesh repair tool. If you have a single mesh object that is actually composed of multiple, separate, disconnected pieces (disjoint pieces), this command will separate them into independent mesh objects.

### Steps to use the command
1.  Select a mesh object that contains disjoint pieces.
2.  Run the command `ExtractMeshPart`.
3.  At the **Select a mesh face for part to extract** prompt, click on one of the separate pieces.
4.  That piece will be extracted as a new mesh object.

### Command Options & Toggles
This command has no options.

### Note for better use
The command `SplitDisjointMesh` is often faster, as it separates all the disjoint pieces at once, whereas `ExtractMeshPart` requires you to select each piece individually.

### Practical Use Cases
* **Use Case 1 (Cleaning Up Scans):** A 3D scan often includes the main object as well as small, floating "islands" of mesh noise. `ExtractMeshPart` allows you to click on the main object to separate it from all the floating noise, which you can then easily delete.

### Other Information
This is a fundamental tool for cleaning up messy mesh files.

---

## 253. ExtractNonManifoldMeshEdges

### Short Info
Separate non-manifold mesh edges.

### Detailed Description
The **ExtractNonManifoldMeshEdges** command is a mesh repair tool. It finds any "non-manifold" edges in a mesh and splits the mesh at those locations. A non-manifold edge is an error where more than two faces are connected to a single edge. This is a common problem in meshes that can prevent them from being 3D printed.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `ExtractNonManifoldMeshEdges`.
3.  If non-manifold edges are found, the mesh will be split at those locations.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Repairing for Printing):** You run the `ShowEdges` command on your ring model and it highlights some non-manifold edges. This means the mesh is not valid for printing. Running `ExtractNonManifoldMeshEdges` can often separate the problematic areas, allowing you to delete the bad faces and repair the hole manually.

### Other Information
This is an important command in a professional mesh repair workflow.

---

## 254. ExtractPipedCurve

### Short Info
Create a mesh from a curve's pipe display.

### Detailed Description
The **ExtractPipedCurve** command is a utility that takes a curve that has a visual pipe display (created with `ApplyCurvePiping`) and converts that visual effect into a real, permanent mesh object.

### Steps to use the command
1.  Use `ApplyCurvePiping` on a curve to create the visual pipe.
2.  Select the curve.
3.  Run the command `ExtractPipedCurve`.
4.  A new, independent mesh object, shaped like the pipe, will be created.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the bridge between the lightweight `ApplyCurvePiping` display and a real piece of geometry. If you like the look of your curve piping and decide you need it to be a real object for 3D printing, this is the command you use.

### Practical Use Cases
* **Use Case 1 (Finalizing a Design):** You have used `ApplyCurvePiping` to quickly visualize a complex filigree pattern. Once you are happy with the design and the pipe radius, you can run `ExtractPipedCurve` on all the curves to convert the entire visual design into solid mesh geometry that can be exported for 3D printing.

### Other Information
This command is the final step in the `ApplyCurvePiping` workflow if you need to create physical geometry.

---

## 255. ExtractPt

### Short Info
Create point objects at the locations of curve and surface control points, edit points, and vertices.

### Detailed Description
The **ExtractPt** command is a utility that creates point objects at the locations of an object's structural points, such as its control points, edit points, or vertices.

### Steps to use the command
1.  Select one or more objects (curves, surfaces, meshes).
2.  Run the command `ExtractPt`.
3.  Point objects will be created at all of the structural points of the selected objects.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a fast way to get a point cloud that represents the underlying structure of a NURBS object.

### Practical Use Cases
* **Use Case 1 (Rebuilding a Surface):** You have a surface that you want to rebuild. You can use `ExtractPt` to create point objects at all of its control points. You can then delete some of these points or move them, and then use the modified set of points to create a new, cleaner surface with the `SrfPtGrid` command.

### Other Information
This is a useful tool for reverse-engineering and surface reconstruction workflows.

---

## 256. ExtractRenderMesh

### Short Info
Duplicate the render mesh.

### Detailed Description
The **ExtractRenderMesh** command is a utility that takes the invisible "render mesh" of a NURBS surface or polysurface and creates a permanent, independent mesh object from it. The render mesh is the polygon mesh that Rhino creates in the background to display smooth objects in shaded and rendered views.

### Steps to use the command
1.  Select one or more NURBS surfaces or polysurfaces.
2.  Run the command `ExtractRenderMesh`.
3.  A new mesh object, which is a faceted approximation of your original smooth object, will be created.

### Command Options & Toggles
This command has no options.

### Note for better use
The density and quality of the extracted mesh are controlled by the render mesh settings in your Document Properties. If you need a high-quality mesh for 3D printing, you should increase these settings before running the command.

### Practical Use Cases
* **Use Case 1 (Exporting for 3D Printing):** While you can export a NURBS object directly to STL (and Rhino will convert it automatically), some workflows require you to have the mesh object first for inspection or modification. `ExtractRenderMesh` is the command you use to perform this conversion manually before exporting.
* **Use Case 2 (Capturing a Display Effect):** You have used a display effect like `ApplyDisplacement` or `ApplyEdgeSoftening`. These effects are only visual. To convert them into real, 3D printable geometry, you must run `ExtractRenderMesh` on the object. The resulting mesh will have the displacement or softened edges "baked" into its geometry.

### Other Information
This is the primary command used to convert your final NURBS models into meshes for manufacturing.

---

## 257. ExtractSrf

### Short Info
Separate or copy polysurface faces.

### Detailed Description
The **ExtractSrf** (Extract Surface) command is a fundamental polysurface editing tool. It allows you to select one or more faces of a polysurface and either separate them from the original object or create independent copies of them.

### Steps to use the command
1.  Run the command `ExtractSrf`.
2.  At the **Select surfaces to extract** prompt, select one or more faces of a polysurface.
3.  Press Enter.
4.  The selected faces will become new, independent surface objects.

### Command Options & Toggles
* **Copy:** If set to Yes, this option will create copies of the faces, leaving the original polysurface intact. If set to No (the default), it will remove the faces from the original object, creating holes.

### Note for better use
To select individual faces of a polysurface, you may need to hold down Ctrl+Shift while clicking.

### Practical Use Cases
* **Use Case 1 (Creating a Two-Tone Ring):** You have a solid ring model and you want the top surface to be a different material. You can use `ExtractSrf` with the `Copy=Yes` option to create a duplicate of the top surface. You can then place this new surface on a different layer and assign a different material to it for rendering.
* **Use Case 2 (Deconstructing a Model):** You need to modify a single surface within a complex, closed solid. You can use `ExtractSrf` (with `Copy=No`) to remove the surface, which opens up the model. You can then edit or replace the surface and `Join` everything back together.

### Other Information
This is a workhorse command for any workflow that involves editing parts of a complex solid object.

---

## 258. ExtractSubCrv

### Short Info
Separate a polycurve segment.

### Detailed Description
The **ExtractSubCrv** (Extract Sub-Curve) command is a curve editing tool that separates a segment of a polycurve into a new, independent curve object.

### Steps to use the command
1.  Run the command `ExtractSubCrv`.
2.  At the **Select polycurve to extract from** prompt, select a polycurve.
3.  At the **Select curve segment to extract** prompt, click on the segment you want to separate.
4.  A new, independent curve object will be created from that segment.

### Command Options & Toggles
* **Copy:** If set to Yes, this option will create a copy of the segment, leaving the original polycurve intact. If No, it will remove the segment from the original.

### Note for better use
This is similar to using `Explode` on a polycurve, but it allows you to extract only the specific segments you need without breaking the entire curve apart.

### Practical Use Cases
* **Use Case 1 (Using Part of an Outline):** You have drawn the complete outline of a complex pendant as a single closed polycurve. Now you need to use just the bottom edge of that outline as a rail for a `Sweep`. You can use `ExtractSubCrv` with the `Copy=Yes` option to create a duplicate of just that bottom segment to use as your rail.

### Other Information
This is a useful utility for working with complex polycurves.

---

## 259. ExtractUVMesh

### Short Info
Extract the texture coordinates of an object as a mesh.

### Detailed Description
The **ExtractUVMesh** command is a highly specialized utility used in advanced texture mapping workflows. It takes an object that has texture coordinates (a UV map) and creates a new mesh object that represents that flattened, 2D UV map.

### Steps to use the command
1.  Select an object that has texture mapping applied.
2.  Run the command `ExtractUVMesh`.
3.  A new, flat mesh object will be created that represents the unwrapped texture layout.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is the reverse of `UVEditor`. The `UVEditor` lets you edit the UV mesh; this command extracts that mesh as a physical object in your scene.

### Practical Use Cases
* **Use Case 1 (Creating a Texture Template):** You have created a complex UV map for a ring using the `Unwrap` command. You want to create a precise texture in Photoshop. You can use `ExtractUVMesh` to create a mesh of your UV layout. You can then use `Make2D` on this mesh and export the resulting curves to Photoshop to use as a perfect template for painting your texture.

### Other Information
This is a very advanced tool for users who are deeply involved in custom texture creation.

---

## 260. ExtractWireframe

### Short Info
Create curves from a surface's isocurves.

### Detailed Description
The **ExtractWireframe** command creates new, independent curve objects that are duplicates of all the isocurves of a selected surface or polysurface. This essentially creates a "wireframe" copy of your object made of actual curves.

### Steps to use the command
1.  Select one or more surfaces or polysurfaces.
2.  Run the command `ExtractWireframe`.
3.  New curves will be created along every isocurve of the selected objects.

### Command Options & Toggles
This command has no options.

### Note for better use
This can create a very large number of curves on a dense object. It is often more precise to use `ExtractIsocurve` to get only the specific curves you need.

### Practical Use Cases
* **Use Case 1 (Creating a Cage-like Structure):** You want to create a piece of jewelry that looks like a wireframe cage in the shape of a complex surface. You can model the smooth surface, then use `ExtractWireframe` to generate all the curves. You can then use the `Pipe` command on these curves to create the physical wires.
* **Use Case 2 (Analysis):** You want to export the structural lines of a surface to another program. `ExtractWireframe` provides a quick way to generate all of these curves at once.

### Other Information
This command can be memory-intensive on complex objects.

---

## 261. ExtrudeCrv

### Short Info
Drive closed planar curves in a straight line.

### Detailed Description
The **ExtrudeCrv** (Extrude Curve) command is a fundamental solid creation tool. It takes a flat, closed curve and extends it in a straight line to create a 3D object. If the input curve is closed, the result will be a solid. If the input curve is open, the result will be a surface.

### Steps to use the command
1.  Select the curve(s) to extrude.
2.  Run the command `ExtrudeCrv`.
3.  Drag the mouse to define the extrusion distance and direction, and click. Or, type a distance and press Enter.

### Command Options & Toggles
* **BothSides:** Extrudes the curve in both directions from the starting plane.
* **Solid (Yes/No):** If Yes, the command will automatically `Cap` the result to create a closed solid.
* **DeleteInput:** Deletes the original curve.
* **Direction:** Allows you to specify the extrusion direction by picking two points.

### Note for better use
The input curve must be planar (completely flat) for this command to work correctly.

### Practical Use Cases
* **Use Case 1 (Creating a Bezel):** You have drawn a circle representing the outer wall of a bezel. `ExtrudeCrv` is the command you use to pull that circle up, giving it height and turning it into a solid cylinder.
* **Use Case 2 (Creating a Ring Shank):** You have drawn the 2D cross-section profile of a ring shank. `ExtrudeCrv` is used to extend that profile sideways to create the main body of the ring.

### Other Information
This is one of the most basic and frequently used commands for creating 3D geometry from 2D profiles.

---

## 262. ExtrudeCrvAlongCrv

### Short Info
Drive closed planar curves along a path curve.

### Detailed Description
The **ExtrudeCrvAlongCrv** (Extrude Curve Along Curve) command creates a 3D object by sweeping a flat profile curve along a path curve. It is similar to the `Sweep1` command but is simpler and less flexible.

### Steps to use the command
1.  Run the command `ExtrudeCrvAlongCrv`.
2.  At the **Select profile curves** prompt, select the flat curve(s) and press Enter.
3.  At the **Select path curve** prompt, select the curve to extrude along.
4.  The object will be created.

### Command Options & Toggles
* **SubCrv:** Allows you to select a segment of a curve as the path.

### Note for better use
For most jewelry design, the `Sweep1` command is superior to this one because it offers much more control over the orientation of the profile curve as it travels along the path. `ExtrudeCrvAlongCrv` keeps the profile parallel to its original orientation, which can cause self-intersection on tight curves.

### Practical Use Cases
* **Use Case 1 (Creating a Simple Tube):** You have a circle and a curved path, and you want to create a simple tube that follows the path. This command can do this quickly, but the `Pipe` command is often a better tool for this specific task.

### Other Information
While it exists, this command is often superseded by the more powerful `Sweep1` command for most practical applications.

---

## 263. ExtrudeCrvTapered

### Short Info
Drive closed planar curves tapered in a straight line.

### Detailed Description
The **ExtrudeCrvTapered** (Extrude Curve Tapered) command is a variation of `ExtrudeCrv`. It takes a flat curve and extends it in a straight line while also tapering the shape in or out at a specified angle.

### Steps to use the command
1.  Select the curve(s) to extrude.
2.  Run the command `ExtrudeCrvTapered`.
3.  At the **Extrusion distance** prompt, define the height of the extrusion.
4.  At the **Draft angle** prompt, enter an angle value for the taper.

### Command Options & Toggles
* **Direction:** Allows you to specify the extrusion direction.
* **DeleteInput:** Deletes the original curve.

### Note for better use
A positive draft angle will make the shape wider at the top, while a negative angle will make it narrower.

### Practical Use Cases
* **Use Case 1 (Creating a Tapered Bezel):** You have drawn a circle for the base of a bezel. You can use `ExtrudeCrvTapered` with a negative angle to extrude the circle upwards and inwards at the same time, creating a tapered bezel wall in a single operation.
* **Use Case 2 (Creating a Prong):** You can draw the square or round base of a prong and use this command with a negative angle to create a tapered prong shape.

### Other Information
This is a very efficient command for creating simple, drafted shapes.

---

## 264. ExtrudeCrvToPoint

### Short Info
Drive closed planar curves to a point.

### Detailed Description
The **ExtrudeCrvToPoint** (Extrude Curve To Point) command takes a flat curve and extrudes it towards a single point, creating a conical or pyramidal shape.

### Steps to use the command
1.  Select the curve(s) to extrude.
2.  Run the command `ExtrudeCrvToPoint`.
3.  At the **Extrusion point** prompt, pick a location in space.
4.  A solid object will be created.

### Command Options & Toggles
* **DeleteInput:** Deletes the original curve.

### Note for better use
This is a fast way to create simple pointed shapes.

### Practical Use Cases
* **Use Case 1 (Modeling a Gem Pavilion):** You have drawn the circular girdle outline of a round gemstone. You can use `ExtrudeCrvToPoint` to extrude this circle down to a single point, instantly creating the basic cone shape for the gem's pavilion.
* **Use Case 2 (Creating a Spike):** You are designing a piece of punk-style jewelry and need to create a pointed spike. You can draw the circular base of the spike and use this command to extrude it to a sharp point.

### Other Information
This is a simple but useful primitive creation tool.

---

## 265. ExtrudeSrf

### Short Info
Drive surface edges in a straight line to create a solid.

### Detailed Description
The **ExtrudeSrf** (Extrude Surface) command takes a surface and extends its boundary edges in a straight line to create a solid object. It is often used to give thickness to a flat or curved surface.

### Steps to use the command
1.  Select the surface(s) to extrude.
2.  Run the command `ExtrudeSrf`.
3.  Drag the mouse to define the extrusion distance and direction, and click.

### Command Options & Toggles
* **BothSides:** Extrudes the surface in both directions.
* **Solid (Yes/No):** If Yes, the command will close the result to create a solid.
* **DeleteInput:** Deletes the original surface.
* **Direction:** Allows you to specify the extrusion direction.

### Note for better use
This command is very similar to `OffsetSrf`, but it extrudes the edges straight, whereas `OffsetSrf` creates a new surface that is parallel to the original at all points. For giving thickness to a curved surface, `OffsetSrf` often produces a better result.

### Practical Use Cases
* **Use Case 1 (Giving Thickness to a Plate):** You have modeled a flat, decorative pendant as a single surface. To make it a solid object for 3D printing, you can use `ExtrudeSrf` to give it the desired thickness.
* **Use Case 2 (Creating a Ring Band):** You have created the outer surface of a ring band. You can use `ExtrudeSrf` to extend the edges inward to create the inner surface and the side walls, forming a solid ring.

### Other Information
This is a fundamental tool for turning surfaces into solid objects.

---

## 266. ExtrudeSrfAlongCrv

### Short Info
Drive surface edges along a path curve to create a solid.

### Detailed Description
The **ExtrudeSrfAlongCrv** (Extrude Surface Along Curve) command creates a 3D object by sweeping a surface along a path curve.

### Steps to use the command
1.  Select the surface(s) to extrude.
2.  Run the command `ExtrudeSrfAlongCrv`.
3.  At the **Select path curve** prompt, select the curve to extrude along.
4.  The object will be created.

### Command Options & Toggles
* **SubCrv:** Allows you to select a segment of a curve as the path.

### Note for better use
This is a very specialized command. For most design situations where you need to sweep a profile along a path, the `Sweep1` or `Sweep2` commands are more appropriate and flexible.

### Practical Use Cases
* **Use Case 1 (Advanced Forms):** This command could be used to create complex, ribbon-like forms where an entire surface shape needs to be extruded along a path.

### Other Information
This is a less commonly used extrusion command.

---

## 267. ExtrudeSrfTapered

### Short Info
Drive surface edges tapered in a straight line to create a solid.

### Detailed Description
The **ExtrudeSrfTapered** (Extrude Surface Tapered) command takes a surface and extends its boundary edges in a straight line while also tapering the shape in or out at a specified angle.

### Steps to use the command
1.  Select the surface(s) to extrude.
2.  Run the command `ExtrudeSrfTapered`.
3.  At the **Extrusion distance** prompt, define the height of the extrusion.
4.  At the **Draft angle** prompt, enter an angle value for the taper.

### Command Options & Toggles
* **Direction:** Allows you to specify the extrusion direction.
* **DeleteInput:** Deletes the original surface.

### Note for better use
This is very useful for creating drafted parts for molding directly from a single surface.

### Practical Use Cases
* **Use Case 1 (Creating a Tapered Ring):** You have modeled the curved top surface of a ring. You can use `ExtrudeSrfTapered` to extrude the edges of this surface downward and inward at the same time, creating the tapered body of the ring in a single operation.

### Other Information
This is a powerful and efficient command for creating drafted solids.

---

## 268. ExtrudeSrfToPoint

### Short Info
Drive surface edges to a point to create a solid.

### Detailed Description
The **ExtrudeSrfToPoint** (Extrude Surface To Point) command takes a surface and extrudes its boundary edges towards a single point, creating a solid object.

### Steps to use the command
1.  Select the surface(s) to extrude.
2.  Run the command `ExtrudeSrfToPoint`.
3.  At the **Extrusion point** prompt, pick a location in space.
4.  A solid object will be created.

### Command Options & Toggles
* **DeleteInput:** Deletes the original surface.

### Practical Use Cases
* **Use Case 1 (Creating a Custom Pavilion):** You have modeled a complex, non-circular top surface for a custom gemstone. You can use `ExtrudeSrfToPoint` to extrude the edges of this surface down to a single point, creating a perfectly matching custom pavilion.

### Other Information
This is a useful tool for creating custom conical and pyramidal shapes from any surface base.

---

## 269. Fair

### Short Info
Smooth a curve.

### Detailed Description
The **Fair** command is a curve editing tool that smooths a curve by averaging the locations of its control points, helping to remove unwanted ripples, kinks, or unevenness.

### Steps to use the command
1.  Select a curve.
2.  Run the command `Fair`.
3.  A dialog box appears where you can set the tolerance.
4.  Click OK. The curve will be smoothed.

### Command Options & Toggles
* **Tolerance:** Controls how much the new, smoothed curve is allowed to deviate from the original.

### Note for better use
This is a quick, automated smoothing tool. For more precise control over the smoothness of a curve, it is often better to use the `CurvatureGraph` command as a visual guide and manually adjust the control points.

### Practical Use Cases
* **Use Case 1 (Cleaning a Traced Curve):** You have traced a sketch by hand, and the resulting curve is slightly wobbly. The `Fair` command can quickly smooth out these small imperfections to create a more flowing line.

### Other Information
This is a useful command for quick clean-up of messy curves.

---

## 270. Fillet

### Short Info
Create an arc between two curves.

### Detailed Description
The **Fillet** command is a fundamental 2D editing tool that creates a circular arc of a specified radius between two intersecting curves, trimming the original curves back to the new arc. It is used to create rounded corners.

### Steps to use the command
1.  Run the command `Fillet`.
2.  At the **Select first curve to fillet** prompt, select a curve.
3.  At the **Select second curve to fillet** prompt, select another curve.
4.  A rounded corner will be created.

### Command Options & Toggles
* **Radius:** Allows you to set the radius of the fillet arc. This is the most important option.
* **Join:** Toggles whether the resulting curves are joined.
* **Trim:** Toggles whether the original curves are trimmed.

### Note for better use
The `Fillet` command is for 2D curves. For creating a rounded edge on a 3D solid, use the `FilletEdge` command.

### Practical Use Cases
* **Use Case 1 (Rounding a Bezel Profile):** You are drawing the 2D cross-section of a bezel. To create a soft, rounded top edge, you can use `Fillet` on the sharp corner where the top and side lines meet.
* **Use Case 2 (Creating a Cushion Shape):** You can start with a square (`Rectangle` command) and then use `Fillet` on all four corners to quickly create a soft, cushion-shaped outline.

### Other Information
This is one of the most frequently used 2D editing commands.

---

## 271. FilletCorners

### Short Info
Round the corners of a polyline.

### Detailed Description
The **FilletCorners** command is a specialized version of `Fillet` that is designed to round all of the corners of a polycurve or polyline at once.

### Steps to use the command
1.  Run the command `FilletCorners`.
2.  At the **Select polycurve to fillet corners** prompt, select a polycurve.
3.  All corners of the polycurve will be filleted with the current radius.

### Command Options & Toggles
The radius is set by the last-used `Fillet` command's radius setting.

### Note for better use
This is much faster than running the `Fillet` command on each corner individually.

### Practical Use Cases
* **Use Case 1 (Softening a Rectangle):** You have drawn a rectangle and want to give all four corners a smooth, rounded appearance. `FilletCorners` will do this in a single click.

### Other Information
This is a time-saving utility for working with polylines.

---

## 272. FilletEdge

### Short Info
Create a tangent surface between polysurface edges.

### Detailed Description
The **FilletEdge** command is a fundamental solid modeling tool that creates a rounded, tangent surface (a fillet) along the selected edges of a polysurface. This is used to remove sharp edges from a model, which is critical for both aesthetic appeal and for the manufacturability of a piece of jewelry.

### Steps to use the command
1.  Run the command `FilletEdge`.
2.  At the **Select edges to fillet** prompt, click on the edges of your solid model.
3.  A preview will appear. You can click on the handles to dynamically change the fillet radius.
4.  Press Enter to create the filleted surfaces.

### Command Options & Toggles
* **NextRadius:** Allows you to set the fillet radius. You can set different radii for different edges within the same command run.
* **FaceEdges:** A selection filter that helps you select all the edges of a single face at once.
* **Preview:** Toggles the dynamic preview on or off.

### Note for better use
Filleting can be a complex operation. It works best when you fillet larger radii before smaller radii. If a fillet fails at a complex corner, you may need to fillet the edges individually and then use other surfacing tools like `Patch` or `BlendSrf` to manually build the corner.

### Practical Use Cases
* **Use Case 1 (Softening a Ring):** This is a primary use. After you have created the basic solid shape of a ring, you use `FilletEdge` on all the sharp edges to give it a smooth, polished, and comfortable feel.
* **Use Case 2 (Creating a Comfort Fit):** You can use `FilletEdge` with a large radius on the inside edges of a ring shank to create a basic comfort-fit profile.

### Other Information
This is one of the most important and frequently used commands for finishing a 3D model.

---

## 273. FilletSrf

### Short Info
Create a fillet surface between two surfaces.

### Detailed Description
The **FilletSrf** (Fillet Surface) command creates a constant-radius, rounded surface (a fillet) between two separate surfaces that intersect. It trims the original surfaces back to the new fillet surface. This is similar to `FilletEdge`, but it works on two independent surfaces rather than the connected edges of a single polysurface.

### Steps to use the command
1.  Run the command `FilletSrf`.
2.  At the **Select first surface to fillet** prompt, select a surface near the intersection.
3.  At the **Select second surface to fillet** prompt, select the other surface.
4.  A preview will appear, and you can adjust the radius.
5.  Press Enter to create the fillet.

### Command Options & Toggles
* **Radius:** Sets the radius of the fillet.
* **Trim:** Toggles whether the original surfaces are trimmed.
* **Join:** Toggles whether the resulting surfaces are joined.

### Note for better use
This command is useful when you are building a model piece by piece from separate surfaces and want to create rounded transitions before joining everything into a solid.

### Practical Use Cases
* **Use Case 1 (Assembling a Model):** You have modeled the top of a signet ring and the shank as two separate, intersecting surfaces. You want to create a rounded transition where they meet before joining them. `FilletSrf` can create this transition surface.

### Other Information
For most jewelry modeling where you are working with a single solid, `FilletEdge` is the more commonly used command.

---

## 274. FillMeshHole

### Short Info
Fill a hole in a mesh.

### Detailed Description
The **FillMeshHole** command is a mesh repair tool that attempts to fill a single hole in a mesh by creating new faces.

### Steps to use the command
1.  Run the command `FillMeshHole`.
2.  At the **Select mesh boundary edges** prompt, select the edges of a single hole in your mesh.
3.  Press Enter. The command will attempt to create new faces to close the hole.

### Command Options & Toggles
This command has no options.

### Note for better use
This command works best on relatively simple, clean holes. For very complex or irregular holes, it may fail or produce a messy result. In those cases, it is often better to patch the hole manually using `3DFace`.

### Practical Use Cases
* **Use Case 1 (Quick Mesh Repair):** You have an STL file with a few small, simple holes. `FillMeshHole` is the fastest way to select each hole and close it, making the mesh watertight.

### Other Information
The companion command, `FillMeshHoles`, attempts to fill all holes in a mesh at once.

---

## 275. FillMeshHoles

### Short Info
Fill all holes in a mesh.

### Detailed Description
The **FillMeshHoles** command is an automated mesh repair tool that finds and attempts to fill all of the holes (naked edge boundaries) in a selected mesh object.

### Steps to use the command
1.  Select a mesh object that has holes.
2.  Run the command `FillMeshHoles`.
3.  The command will automatically create new faces to close all detected holes.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a very fast, "brute force" method for making a mesh watertight. However, it can sometimes create undesirable flat caps over openings that were intended to be there. It's best used when you know the object is supposed to be a single, closed solid.

### Practical Use Cases
* **Use Case 1 (Finalizing a Scan):** You have a 3D scan of an object that has many small holes and gaps due to scanning errors. `FillMeshHoles` can often close all of these small imperfections in a single step, making the scan a solid object.

### Other Information
This is a powerful but potentially blunt tool for mesh repair.

---

## 276. Fin

### Short Info
Create a surface that extends from a curve on a surface.

### Detailed Description
The **Fin** command creates a small surface that extends perpendicularly from a curve that lies on another surface. The height of the "fin" is determined by the curvature of the base surface.

### Steps to use the command
1.  Create a curve on a surface.
2.  Run the command `Fin`.
3.  Select the curve.
4.  A fin-like surface will be created.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a very specialized command. The shape of the fin is not directly controllable but is instead derived from the geometry of the base surface.

### Practical Use Cases
* **Use Case 1 (Aerodynamic Analysis):** This command is more common in industrial design or engineering. For example, an engineer could use it to quickly generate small fins on an airplane wing surface to analyze airflow. It has very limited application in jewelry design.

### Other Information
This is a niche surfacing command.

---

## 277. FindText

### Short Info
Search for text.

### Detailed Description
The **FindText** command is a utility that searches the model for specific text content within text objects or annotation dots.

### Steps to use the command
1.  Run the command `FindText`.
2.  A dialog box appears.
3.  Type the text you want to search for in the "Find" field.
4.  Click "Find Next." The command will zoom to and select the first object containing that text.

### Command Options & Toggles
The options are contained within the dialog box:
* **Match case:** Makes the search case-sensitive.
* **Wrap:** Continues the search from the beginning after reaching the end of the object list.

### Practical Use Cases
* **Use Case 1 (Finding a Note):** You have left an important note for yourself somewhere in a complex model using an annotation dot, but you can't find it. You can use `FindText` to search for a keyword that you remember from the note.

### Other Information
This is a simple search utility for annotation objects.

---

## 278. FindWatermark

### Short Info
Find a watermark in a model.

### Detailed Description
The **FindWatermark** command is a utility that scans the current model file to find any invisible, digital watermarks that were embedded using the `ApplyWatermark` command.

### Steps to use the command
1.  Run the command `FindWatermark`.
2.  The command history will report "Watermark found" and display the watermark text, or it will report "No watermark found."

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Verifying Ownership):** A client claims that a 3D model is their original work, but you suspect it is a copy of a file you sent them. You can ask for the file and run `FindWatermark` to see if your hidden signature is present.

### Other Information
This is the companion command to `ApplyWatermark`.

---

## 279. ApplyWatermark

### Short Info
Embed invisible watermarks in Rhino models.

### Detailed Description
(This is a duplicate entry in the source documentation list, pointing to the same command as #28). The **ApplyWatermark** command is a utility that embeds an invisible, digital watermark into your Rhino 3DM model file. This watermark is a string of text that you provide. It is not visible in the model itself but can be detected by someone else using the `FindWatermark` command. Its purpose is to help prove ownership or authenticity of a file.

### Steps to use the command
1.  Run the command `ApplyWatermark`.
2.  A dialog box will appear.
3.  Type your desired watermark text (e.g., your name, company, or a unique ID) into the field.
4.  Click OK. The data is embedded in the file.

### Command Options & Toggles
The only option is the text you enter into the dialog box.

### Note for better use
This is not a visual watermark that appears on a render. It is hidden data inside the file itself.

### Practical Use Cases
* **Use Case 1 (Proving Ownership):** You are sending a preliminary design file to a new client and want a way to prove that the file originated from you if a dispute arises later. Before sending the file, use `ApplyWatermark` to embed your company name and the date.

### Other Information
This entry is a duplicate of command #28.

---

## 280. FitCrv

### Short Info
Refit a curve to a tolerance.

### Detailed Description
The **FitCrv** (Fit Curve) command rebuilds a curve to have fewer control points while staying within a specified tolerance of the original shape. It is a tool for simplifying complex curves.

### Steps to use the command
1.  Select the curve(s) to refit.
2.  Run the command `FitCrv`.
3.  At the **Tolerance** prompt, enter a value and press Enter.
4.  A new, simpler curve will be created.

### Command Options & Toggles
* **Degree:** Allows you to specify the degree of the resulting curve.
* **DeleteInput:** Deletes the original curve.

### Note for better use
This command is useful for simplifying curves that have been created by intersecting surfaces or by tracing, as these can often have an unnecessarily high number of control points. A smaller tolerance will result in a curve that is more accurate to the original but has more points. A larger tolerance will create a simpler curve that may deviate more from the original.

### Practical Use Cases
* **Use Case 1 (Simplifying an Intersection Curve):** You have used the `Intersect` command on two complex surfaces, and the resulting curve has hundreds of control points, making it difficult to edit. `FitCrv` can be used to rebuild this curve into a much simpler, smoother curve with fewer points that is easier to use for a `Sweep` or `Pipe` operation.

### Other Information
This is an important tool for cleaning up and simplifying complex curves.

---

## 281. FitSrf

### Short Info
Refit a surface to a tolerance.

### Detailed Description
The **FitSrf** (Fit Surface) command rebuilds a surface to a new tolerance. It is a tool for simplifying complex surfaces by reducing the number of control points.

### Steps to use the command
1.  Select a surface.
2.  Run the command `FitSrf`.
3.  At the **Tolerance** prompt, enter a value and press Enter.
4.  The surface will be rebuilt with a simpler control point structure.

### Command Options & Toggles
* **Tolerance:** Controls how much the new surface is allowed to deviate from the original.
* **DegreeU / DegreeV:** Allows you to specify the degree of the new surface in the U and V directions.

### Note for better use
This is an advanced surfacing tool. For most general simplification, the `Rebuild` command is often more intuitive.

### Practical Use Cases
* **Use Case 1 (Simplifying an Imported Surface):** You have imported a surface from another program that has a very dense and uneven control point structure. `FitSrf` can be used to refit the surface into a cleaner, lighter NURBS surface that is easier to work with in Rhino.

### Other Information
This is a specialized tool for advanced surface editing and reconstruction.

---

## 282. FixedLengthCrvEdit

### Short Info
Edit a curve without changing its length.

### Detailed Description
The **FixedLengthCrvEdit** (Fixed Length Curve Edit) command is a specialized curve editing tool that allows you to change the shape of a curve by editing its control points, while ensuring that the overall length of the curve remains exactly the same.

### Steps to use the command
1.  Select a curve.
2.  Run the command `FixedLengthCrvEdit`.
3.  The curve's control points will be displayed.
4.  Drag the control points to change the curve's shape. The command will automatically adjust the rest of the curve to maintain the original length.
5.  Press Enter to accept the changes.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a very useful tool for design situations where the length of a curve is a critical parameter that must not be changed.

### Practical Use Cases
* **Use Case 1 (Designing a Necklace Chain):** You have designed a necklace and have drawn a curve representing the chain, which must be exactly 18 inches long. You need to adjust the shape of how the chain hangs (its catenary curve), but you cannot change its length. `FixedLengthCrvEdit` is the perfect tool for this, as it allows you to change the curve's shape while guaranteeing the length remains exactly 18 inches.

### Other Information
This is a unique and powerful tool for length-constrained design problems.

---

## 283. FlatShade

### Short Info
Temporarily shade the current viewport with flat shading.

### Detailed Description
The **FlatShade** command is a temporary display command. It sets the active viewport to a shaded mode where each polygon of the render mesh is displayed as a flat face, without any smoothing between faces. This gives the object a faceted, low-poly appearance.

### Steps to use the command
1.  Make a viewport active.
2.  Run the command `FlatShade`.
3.  The viewport will switch to flat shaded mode.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a temporary override. As soon as you pan or rotate the view, the display will revert to the viewport's original display mode. To make this effect permanent for a viewport, you need to go into the Display Mode options and turn off "smooth shading."

### Practical Use Cases
* **Use Case 1 (Visualizing Mesh Structure):** You want to quickly see the underlying polygon structure of your smooth NURBS models. `FlatShade` instantly reveals the render mesh, which can be useful for diagnosing mesh-related issues or for appreciating the faceted form.

### Other Information
This is a simple display utility.

---

## 284. FlattenSrf

### Short Info
Create flat curves from a 3-D developable surface.

### Detailed Description
The **FlattenSrf** (Flatten Surface) command is a utility that creates flat 2D curves from the edges of a 3D surface. This command is an older, less powerful predecessor to the `UnrollSrf` and `Smash` commands. It is intended for "developable" surfaces, which are surfaces that can be unrolled onto a flat plane without any stretching or tearing (like a cylinder or a cone, but not a sphere).

### Steps to use the command
1.  Select a developable surface.
2.  Run the command `FlattenSrf`.
3.  2D curves representing the flattened border of the surface will be created on the construction plane.

### Command Options & Toggles
This command has no options.

### Note for better use
For nearly all situations, the `UnrollSrf` command is a superior and more modern tool for unrolling developable surfaces. For surfaces that are not developable (curved in two directions), the `Smash` or `Squish` commands should be used.

### Practical Use Cases
* **Use Case 1 (Legacy Workflows):** This command's primary use is in maintaining compatibility with older versions of Rhino or older workflows that were built around it. For new projects, `UnrollSrf` is the recommended command.

### Other Information
This is largely a legacy command.

---

## 285. Flip

### Short Info
Reverse the normal direction of a curve, surface, or mesh object.

### Detailed Description
The **Flip** command is a fundamental editing tool that reverses the "normal" direction of an object. For a curve, this swaps its start and end points. For a surface or a mesh face, this flips its "front" and "back" sides. This is the same action as clicking on the arrows in the `Dir` command.

### Steps to use the command
1.  Select the object(s) to flip.
2.  Run the command `Flip`.
3.  The direction of the object(s) will be reversed.

### Command Options & Toggles
This command has no options.

### Note for better use
The normal direction of a surface is critical for boolean operations. All surfaces of a solid object should have their normals pointing "outward" for booleans to work predictably. If a boolean operation gives you the opposite result of what you expect, it's almost always because one of the object's normals is flipped.

### Practical Use Cases
* **Use Case 1 (Fixing Booleans):** You are trying to subtract a cutter from a ring, but instead, the ring is subtracted from the cutter. This is a classic sign of flipped normals. Select the ring, run `Flip`, and then try the `BooleanDifference` again. It will now work correctly.
* **Use Case 2 (Correcting a Sweep):** You are using `Sweep1` to create a ring shank, but the profile curve is flipping upside down. This means the direction of your rail curve is not what you intended. You can use `Flip` on the rail curve to reverse its direction, which will fix the sweep.

### Other Information
This is an essential troubleshooting command. It is a faster alternative to using the `Dir` command when you already know you just need to flip the direction.

---

## 286. Flow

### Short Info
Re-align objects from a base curve to a target curve.

### Detailed Description
The **Flow** command is a powerful deformation tool that deforms an object by remapping it from a straight "base" line to a curved "target" curve. This allows you to bend and shape objects along a specific path.

### Steps to use the command
1.  Select the object(s) to flow.
2.  Run the command `Flow`.
3.  You will be prompted: **"Base curve - select near one end"**. Draw a straight line that represents the "un-bent" state of your object.
4.  You will be prompted: **"Target curve - select near matching end"**. Select the curved path you want the object to follow.
5.  The object will be deformed to match the shape of the target curve.

### Command Options & Toggles
* **Copy:** Creates a new, deformed copy of the object.
* **Stretch:** Stretches or compresses the object so that its length perfectly matches the length of the target curve.

### Practical Use Cases
* **Use Case 1 (Bending a Pattern into a Ring):** You have designed a flat, straight panel with a detailed pattern on it. You want to bend this into a ring shape. Draw a straight line the same length as your flat panel (the base curve). Draw a circle with the correct finger size (the target curve). Use `Flow` with the `Stretch=Yes` option to wrap the flat panel perfectly into a circle.
* **Use Case 2 (Creating a Wavy Shank):** You have modeled a standard, straight ring shank. You want to give it a gentle, wavy shape. You can draw a straight line along the shank (base) and then draw a wavy curve (target). `Flow` will deform the straight shank to follow the wavy path.

### Other Information
This is a fundamental command for creating curved objects from flat patterns. For deforming objects onto a 3D surface, use the `FlowAlongSrf` command.

---

## 287. FlowAlongSrf

### Short Info
Re-align objects from a source surface to a target surface.

### Detailed Description
The **FlowAlongSrf** (Flow Along Surface) command is one of the most powerful and essential deformation tools in Rhino, especially for jewelry design. It deforms an object by remapping it from a flat "source" plane to a curved "target" surface. This allows you to take flat, 2D patterns and wrap them perfectly onto complex 3D shapes like ring shanks and pendants.

### Steps to use the command
1.  Select the object(s) to flow (your flat pattern).
2.  Run the command `FlowAlongSrf`.
3.  At the **Base surface - select near a corner** prompt, select a flat plane that your pattern is sitting on.
4.  At the **Target surface - select near a matching corner** prompt, select the 3D surface you want to wrap the pattern onto.
5.  The flat pattern will be deformed to match the curvature of the target surface.

### Command Options & Toggles
* **Copy:** Creates a new, deformed copy of the object.
* **Rigid:** Prevents the object from deforming, simply placing it on the surface.
* **PreserveStructure:** Maintains the control point structure of the object, which can result in a less accurate but cleaner deformation.

### Note for better use
The success of this command depends heavily on the structure of your base and target surfaces. For best results, they should have a similar flow and structure. It is common practice to create a custom, clean base surface for your flat pattern rather than just using the CPlane.

### Practical Use Cases
* **Use Case 1 (Applying Pavé):** This is the primary professional method for setting pavé. You create your entire pavé layout (stones, cutters, and prongs) on a flat plane. Then, you use `FlowAlongSrf` to wrap the entire flat layout onto the curved top surface of your ring model. This is far more precise and efficient than trying to place each stone individually on the curved surface.
* **Use Case 2 (Applying Filigree):** You have created a complex, flat filigree pattern made of piped curves. `FlowAlongSrf` is the command you use to take this flat pattern and wrap it perfectly onto the 3D surface of your final jewelry piece.

### Other Information
Mastering `FlowAlongSrf` is a critical skill for any professional jewelry CAD designer.

---

## 288. FoldFace

### Short Info
Rotate a polysurface face around an edge.

### Detailed Description
The **FoldFace** command is a direct editing tool that allows you to select a single face of a polysurface and rotate it around one of its edges, as if folding a piece of paper. The adjacent faces will stretch to stay connected.

### Steps to use the command
1.  Run the command `FoldFace`.
2.  At the **Select a polysurface face to fold** prompt, select a face.
3.  At the **Start of hinge axis** prompt, click one end of the edge you want to fold around.
4.  At the **End of hinge axis** prompt, click the other end of the edge.
5.  You will then be prompted to define the angle of the fold.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a quick, interactive way to make angled adjustments to a model without having to separate and rotate faces manually.

### Practical Use Cases
* **Use Case 1 (Adjusting a Bezel Wall):** You have a straight-walled bezel and you want to fold the top edge inward slightly to help hold the stone. You can use `FoldFace` on the inner face of the bezel, using the top edge as the hinge, to fold it in at a slight angle.

### Other Information
This is a useful tool for direct, interactive editing of solid models.

---

## 289. Fullscreen

### Short Info
Display the Rhino window full screen.

### Detailed Description
The **Fullscreen** command hides all of the Rhino interface elements—including toolbars, menus, and the command prompt—to maximize the space available for the modeling viewports.

### Steps to use the command
1.  Run the command `Fullscreen`.
2.  The interface will be hidden.
3.  Run the command again to restore the interface.

### Command Options & Toggles
This command has no options.

### Note for better use
The Escape (Esc) key will also exit fullscreen mode.

### Practical Use Cases
* **Use Case 1 (Client Presentation):** You are showing a design to a client on your screen and you want them to focus only on the model without being distracted by all the toolbars and buttons. `Fullscreen` provides a clean, presentation-friendly view.

### Other Information
This is a simple interface management command.

---

## 290. GCon

### Short Info
Report the geometric continuity between two curves.

### Detailed Description
The **GCon** (Geometric Continuity) command is an analysis tool that reports the level of smoothness, or "continuity," between two curves that meet at an endpoint. It reports the result as G0, G1, or G2.

### Steps to use the command
1.  Run the command `GCon`.
2.  At the **Select first curve to test continuity** prompt, select a curve near the connection point.
3.  At the **Select second curve to test continuity** prompt, select the other curve.
4.  The command history will report the level of continuity.

### Command Options & Toggles
This command has no options.

### Note for better use
* **G0 (Position):** The curves touch at their endpoints. There can be a sharp corner.
* **G1 (Tangency):** The curves are tangent; they are pointing in the same direction at the connection point. There is no sharp corner, but there can be a sudden change in curvature.
* **G2 (Curvature):** The curves are curvature-continuous. The transition is perfectly smooth, with no sudden change in curvature. This is the goal for high-quality surfaces.

### Practical Use Cases
* **Use Case 1 (Verifying a Blend):** You have used the `BlendCrv` command to connect two curves and you set the continuity to "Curvature." To be absolutely certain that you achieved G2 continuity, you can run the `GCon` command on the connection.

### Other Information
This is a technical analysis tool for verifying the quality of your curves.

---

## 291. GetDocumentUserText

### Short Info
Retrieve text user data from a file.

### Detailed Description
The **GetDocumentUserText** command is a utility used to retrieve custom text information that has been attached to the document itself (not to a specific object) using the `SetDocumentUserText` command. This is a way to store metadata within the file.

### Steps to use the command
1.  Run the command `GetDocumentUserText`.
2.  At the **Key to get** prompt, enter the key (the name) of the text data you want to retrieve.
3.  The text value associated with that key will be reported in the command history.

### Command Options & Toggles
This command has no options.

### Note for better use
This is primarily a tool for scripts and advanced workflows where you need to store and retrieve custom data within your 3DM file.

### Practical Use Cases
* **Use Case 1 (Storing Project Info):** You could use `SetDocumentUserText` to store information like "ClientName = John Smith" and "ProjectNumber = 2023-08-A" directly in your file. Later, you or a script could use `GetDocumentUserText` to retrieve this information.

### Other Information
This is a data management tool, not a modeling tool.

---

## 292. GetUserText

### Short Info
Retrieve text user data from an object.

### Detailed Description
The **GetUserText** command is a utility used to retrieve custom text information that has been attached to a specific object using the `SetUserText` command.

### Steps to use the command
1.  Select the object you want to get the text from.
2.  Run the command `GetUserText`.
3.  At the **Key to get** prompt, enter the key (the name) of the text data you want to retrieve.
4.  The text value associated with that key on that object will be reported in the command history.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Storing Manufacturing Notes):** You have a specific prong on a ring that needs special attention during polishing. You can use `SetUserText` to attach a note to that prong with the key "PolishNote" and the value "High polish on this surface." A colleague can then select the prong and use `GetUserText` with the key "PolishNote" to read your instruction.

### Other Information
This is a data management tool for attaching custom information directly to objects.

---

## 293. Grid

### Short Info
Manage grid settings.

### Detailed Description
The **Grid** command opens the "Grid" page within the Document Properties dialog box. This is where you can control all the settings for the construction plane grid, including its visibility, line spacing, and color.

### Steps to use the command
1.  Run the command `Grid`.
2.  The Document Properties > Grid dialog box will open.
3.  Adjust the settings as desired.
4.  Click OK.

### Command Options & Toggles
The options are all contained within the dialog box:
* **Show grid lines:** Toggles the visibility of the grid.
* **Major line every:** Sets the spacing for the darker grid lines.
* **Minor lines every:** Sets the spacing for the lighter grid lines.
* **Grid extents:** Sets the overall size of the grid.

### Note for better use
Configuring your grid to match the scale of your project is an important setup step. For jewelry, setting the minor grid lines to 1 millimeter and the major lines to 5 or 10 millimeters is a common and useful practice.

### Practical Use Cases
* **Use Case 1 (Project Setup):** When you start a new jewelry file, you would run the `Grid` command to set up your workspace with a logical spacing (e.g., 1mm minor lines) that makes it easy to visually gauge the size of your components as you model them.

### Other Information
This is a fundamental workspace setup command.

---

## 294. GroundPlane

### Short Info
Open the Ground Plane panel.

### Detailed Description
The **GroundPlane** command opens a panel that allows you to turn on and configure a ground plane for your model. The ground plane is an infinite surface that appears at a specified Z-height (usually 0) in rendered and shaded views. It is used to give your model a surface to sit on and to catch shadows, which makes renders look much more realistic.

### Steps to use the command
1.  Run the command `GroundPlane`.
2.  The Ground Plane panel will open.
3.  Check the "On" box to activate the ground plane.
4.  Adjust the settings for height, material, and shadow behavior.

### Command Options & Toggles
The options are in the panel:
* **On:** Toggles the ground plane on or off.
* **Height:** Sets the Z-level of the ground plane.
* **Material:** Allows you to assign a material to the ground plane (e.g., a reflective floor or a matte white background).
* **Shadow only:** Makes the ground plane itself invisible but still allows it to catch shadows from your object.

### Note for better use
The "Shadow only" option is very powerful for creating renders where your object appears to be floating over a white background but still has a realistic shadow underneath it.

### Practical Use Cases
* **Use Case 1 (Product Renders):** You are creating a portfolio render of a ring. You turn on the `GroundPlane` to give the ring a surface to sit on and to catch soft shadows, which makes the image look much more professional and grounded in reality.
* **Use Case 2 (Studio Backdrop):** You can assign a matte white material to the ground plane to simulate the seamless white backdrop used in professional product photography.

### Other Information
This is an essential tool for creating high-quality renderings.

---

## 295. Group

### Short Info
Organize objects into a single component.

### Detailed Description
The **Group** command is a fundamental organizational tool that links multiple objects together so they can be selected and transformed (moved, scaled, rotated) as a single item. This is a non-destructive action; the objects remain separate entities and can be ungrouped at any time.

### Steps to use the command
1.  Select two or more objects.
2.  Run the command `Group`.
3.  The objects are now grouped. Clicking on any one of them will select the entire group.

### Command Options & Toggles
This command has no options.

### Note for better use
The opposite of this command is `Ungroup`. To add an object to an existing group, use `AddToGroup`. To remove an object, use `RemoveFromGroup`.

### Practical Use Cases
* **Use Case 1 (Assembling a Setting):** You have modeled a bezel, a gallery wire, and four prongs as separate objects. To make them easy to handle, you can select all of them and use `Group`. Now you can move the entire head assembly as a single unit.
* **Use Case 2 (Managing Stones):** You have placed 50 small pavé stones on a ring. To make it easy to select them all at once (for example, to move them to a different layer), you can select them all and `Group` them.

### Other Information
Grouping is a simpler, more flexible organizational tool than creating a `Block`, but it lacks the powerful "edit-one-edit-all" functionality of blocks.

---

## 296. Gumball

### Short Info
Display a widget on an object for move, scale, and rotate transforms around the object origin.

### Detailed Description
The **Gumball** command toggles the visibility of the Gumball widget. The Gumball is an interactive manipulator that appears on a selected object, providing handles for moving, scaling, and rotating the object directly in the viewport without needing to run separate commands like `Move`, `Scale`, or `Rotate`.

### Steps to use the command
1.  Run the command `Gumball`.
2.  The command line will show the current state (On or Off).
3.  Click the option to toggle it.
4.  Alternatively, click the "Gumball" pane in the Status Bar at the bottom of the Rhino window.

### Command Options & Toggles
This command is a simple toggle between **On** and **Off**.

### Note for better use
The Gumball is one of the most significant workflow improvements in Rhino 5. Most modern users leave it on at all times. You can click on the white circle ("bunny tail") on the Gumball to access its settings, such as changing its alignment or size.

### Practical Use Cases
* **Use Case 1 (Interactive Editing):** You have selected a gemstone and need to nudge it slightly up, rotate it a few degrees, and make it a tiny bit larger. With the Gumball on, you can do all of these things interactively by simply dragging the arrows (move), arcs (rotate), and square handles (scale) on the widget, providing instant visual feedback.
* **Use Case 2 (Numeric Input):** You can click on any Gumball handle (arrow, arc, or scale) to get a text box where you can type in a precise numerical value for the transformation.

### Other Information
Mastering the Gumball is key to a fast and fluid modeling workflow in Rhino.

---

## 297. GumballAlignment

### Short Info
Reset the Gumball.

### Detailed Description
The **GumballAlignment** command is a utility that resets the orientation of the Gumball widget. If you have manually relocated or rotated the Gumball, this command will snap it back to one of its default alignment modes.

### Steps to use the command
1.  Run the command `GumballAlignment`.
2.  The command line will show several alignment options.
3.  Choose an option (e.g., `CPlane`).

### Command Options & Toggles
* **CPlane:** Aligns the Gumball handles to the axes of the active construction plane.
* **Object:** Aligns the Gumball handles to the object's own internal orientation (if it has one).
* **World:** Aligns the Gumball handles to the world X, Y, and Z axes.
* **Reset:** Resets the Gumball to its default position and orientation after it has been manually moved.

### Note for better use
You can also access these options by clicking the white "bunny tail" circle on the Gumball widget itself.

### Practical Use Cases
* **Use Case 1 (Resetting):** You have manually moved the Gumball pivot to a corner of an object to perform a specific rotation. Now you want to go back to scaling it from its center. You can run `GumballAlignment` and choose `Reset` to snap it back to the object's bounding box center.

### Other Information
This is a utility for managing the behavior of the Gumball widget.

---

## 298. GumballDragStrength

### Short Info
Set the Gumball dragging strength.

### Detailed Description
The **GumballDragStrength** command controls how "sensitive" the Gumball's scaling handles are to mouse movement. It sets a percentage that determines how much the object scales relative to how far you drag the mouse.

### Steps to use the command
1.  Run the command `GumballDragStrength`.
2.  At the **Gumball drag strength** prompt, enter a number (percentage) and press Enter.

### Command Options & Toggles
The only option is the numerical percentage value.

### Note for better use
A lower value (e.g., 50%) means you have to drag the mouse a long way to make a small change in scale, which allows for very fine, precise control. A higher value (e.g., 200%) makes the scaling very fast and aggressive.

### Practical Use Cases
* **Use Case 1 (Fine-Tuning):** You are trying to scale a gemstone to fit perfectly inside a bezel and need to make very small, precise adjustments. You could set the `GumballDragStrength` to a low value like 25 to give yourself very fine control over the scaling handles.

### Other Information
This is a user-preference setting to customize the feel of the Gumball widget.

---

## 299. HandleCurve

### Short Info
Draw a curve with handles for editing.

### Detailed Description
The **HandleCurve** command is a specialized curve drawing tool that creates a curve with "handles," similar to the Bézier curves found in graphic design programs like Adobe Illustrator. This provides a different, and for some users more intuitive, way to control the shape and tangency of a curve.

### Steps to use the command
1.  Run the command `HandleCurve`.
2.  Click to place points. At each point, you can drag to define the length and direction of the tangent handles.
3.  Press Enter when finished.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is for users who are accustomed to the Bézier curve workflow from programs like Illustrator or CorelDRAW. For most users native to Rhino, editing with standard NURBS control points is more common.

### Practical Use Cases
* **Use Case 1 (Graphic Design Workflow):** A graphic designer who is new to Rhino might find the `HandleCurve` tool more familiar and easier to use for creating smooth curves than the standard `Curve` command.

### Other Information
This is an alternative curve creation tool that mimics the behavior of other design software.

---

## 300. Hatch

### Short Info
Create a pattern of lines to fill bounding curves.

### Detailed Description
The **Hatch** command creates a 2D pattern (like diagonal lines, squares, or dots) that fills a closed boundary defined by one or more curves. This is an annotation and drafting tool used to indicate materials or fill areas in 2D drawings.

### Steps to use the command
1.  Run the command `Hatch`.
2.  A dialog box will appear. Select a hatch pattern and set its rotation and scale. Click OK.
3.  At the **Select curves or points for boundary** prompt, select a closed curve or click inside a closed region.
4.  Press Enter. The hatch pattern will be created.

### Command Options & Toggles
The options are in the dialog box:
* **Pattern:** A list of available hatch patterns.
* **Rotation:** Sets the angle of the hatch pattern.
* **Scale:** Sets the size/density of the hatch pattern.
* **Boundary:** Allows you to re-select the boundary curves.

### Note for better use
The hatch pattern is a single object. If you change the shape of the boundary curve, the hatch will not update automatically. You would need to delete the old hatch and create a new one.

### Practical Use Cases
* **Use Case 1 (Technical Drawings):** You are creating a 2D cross-section drawing of a ring for a manufacturer. It is standard practice to use a hatch pattern (like angled lines) to indicate the areas that are "cut" solid metal.
* **Use Case 2 (Surface Finishes):** You can use a stippled (dotted) hatch pattern in a 2D drawing to indicate that a particular surface on the final piece should have a sandblasted or textured finish.

### Other Information
This is a fundamental tool for creating professional 2D technical drawings.


---

## 301. HatchBase

### Short Info
Set the starting point for existing hatches.

### Detailed Description
The **HatchBase** command is an editing tool for existing hatch objects. It allows you to change the origin point, or "base," from which a hatch pattern is generated. This is useful for adjusting the alignment of a pattern within a boundary without having to delete and recreate the entire hatch.

### Steps to use the command
1.  Run the command `HatchBase`.
2.  At the **Select hatches to rebase** prompt, select one or more hatch objects and press Enter.
3.  At the **New base point** prompt, pick a new location.
4.  The selected hatches will update their pattern alignment to originate from the new base point.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is useful for aligning hatch patterns between adjacent objects to create a continuous look, or for shifting a pattern to avoid having small, awkward-looking partial shapes along an edge.

### Practical Use Cases
* **Use Case 1 (Aligning Textures):** You are creating a 2D drawing of a ring that has a textured inlay made of two separate pieces. You have hatched both pieces with a brick pattern. To make the pattern look continuous across the seam, you can use `HatchBase` on both hatches, snapping the new base point to a common corner to ensure the brick lines match up perfectly.

### Other Information
This is a simple but important tool for fine-tuning the appearance of hatch patterns in technical drawings.

---

## 302. HatchScale

### Short Info
Scale hatch patterns in model and layout space.

### Detailed Description
The **HatchScale** command is a utility that controls the global scaling of all hatch patterns in your model. It can also be used to toggle whether hatch patterns scale with the view in layout details or maintain a fixed scale relative to the page.

### Steps to use the command
1.  Run the command `HatchScale`.
2.  The command line will show the current settings.
3.  Click on the options to change them.

### Command Options & Toggles
* **Enabled:** Toggles the hatch scaling feature on or off.
* **Scale:** Sets a numerical scaling factor that is applied to all hatch patterns.
* **Toggle:** Toggles the scaling on or off.

### Note for better use
This is a global setting. Changing the scale here will affect every hatch pattern in your file. To scale a single hatch pattern, you should select it and change its "Pattern Scale" in the Properties panel.

### Practical Use Cases
* **Use Case 1 (Adjusting Drawing Standards):** You receive a file from a colleague, but all the hatch patterns appear too dense or too sparse. You can use `HatchScale` to quickly adjust the global scale of all hatches to match your company's drawing standards without having to edit each one individually.

### Other Information
This is a document-wide setting for managing the appearance of hatches.

---

## 303. HBar

### Short Info
Edit curves and surfaces with Bézier-like handles.

### Detailed Description
The **HBar** (Handle Bar) command is a specialized curve and surface editing tool. It creates a temporary "handle bar" on a curve or surface, which provides Bézier-style editing handles. These handles allow for intuitive, interactive editing of the curve's shape and tangency, similar to the pen tool in Adobe Illustrator.

### Steps to use the command
1.  Run the command `HBar`.
2.  At the **Select curve or surface** prompt, select an object.
3.  At the **Pick a point on the object** prompt, click where you want to place the editing bar.
4.  A handle bar with control points will appear. Drag the points to edit the object's shape.
5.  Press Enter to end the command.

### Command Options & Toggles
* **Style (3-point/5-point):** Toggles between a simpler or more complex handle bar.
* **Edit (U/V):** (Surfaces only) Toggles between editing in the U or V direction.

### Note for better use
This is an alternative editing method to directly manipulating an object's control points (`PointsOn`). It can be more intuitive for users who are familiar with graphic design software.

### Practical Use Cases
* **Use Case 1 (Graphic Design Workflow):** A designer with a background in Adobe Illustrator is creating a smooth, flowing curve for a logo. They might find the `HBar` command more familiar and easier to use for achieving the desired shape than manipulating NURBS control points.

### Other Information
This is a specialized editing tool that offers a different paradigm for curve and surface manipulation.

---

## 304. Heightfield

### Short Info
Create a surface from a bitmap image.

### Detailed Description
The **Heightfield** command creates a 3D NURBS surface based on the grayscale color values of an image. It treats the light and dark areas of the image as a "height map," where white represents the highest points and black represents the lowest points. This is a powerful tool for creating complex, organic, or terrain-like surfaces from 2D images.

### Steps to use the command
1.  Run the command `Heightfield`.
2.  A file browser will open. Select an image file.
3.  You will be prompted to draw a rectangle to define the size and location of the resulting surface.
4.  A dialog box will appear with options for controlling the surface.
5.  Click OK to create the surface.

### Command Options & Toggles
The options are in a dialog box:
* **Number of sample points:** Controls the density and detail of the resulting surface. More points create a more accurate but heavier surface.
* **Height:** Sets the maximum height (Z-dimension) of the surface, corresponding to the white areas of the image.

### Note for better use
For the best results, use high-contrast, grayscale images. Blurring the image slightly in a program like Photoshop before using it can result in a smoother surface.

### Practical Use Cases
* **Use Case 1 (Creating a Bas-Relief):** You have a grayscale image of a face or a coin. You can use `Heightfield` to turn this 2D image into a 3D bas-relief surface that can be incorporated into a pendant or signet ring.
* **Use Case 2 (Organic Textures):** You have a texture image of wrinkled fabric or rough stone. `Heightfield` can be used to turn that 2D texture into a real 3D surface, creating a highly realistic textured background for a piece of jewelry.

### Other Information
This command is a bridge between 2D raster images and 3D NURBS geometry.

---

## 305. Helix

### Short Info
Draw a helical curve.

### Detailed Description
The **Helix** command draws a 3D, spring-like helical curve. It provides options to control the number of turns, the pitch (distance between turns), and the orientation of the helix.

### Steps to use the command
1.  Run the command `Helix`.
2.  Follow the prompts to define the start and end points of the helix's axis.
3.  You will then be prompted to define the radius at the start and end.
4.  The command line will show options for controlling the turns or pitch.

### Command Options & Toggles
* **Turns:** Sets the total number of turns in the helix.
* **Pitch:** Sets the distance between each turn.
* **ReverseTwist:** Reverses the direction of the helix (clockwise or counter-clockwise).

### Note for better use
The `Spiral` command is used to create a flat, 2D spiral. `Helix` is for creating a 3D, spring-like shape.

### Practical Use Cases
* **Use Case 1 (Modeling a Rope Texture):** You can create a small helix and then use the `ArrayCrv` command to array a profile curve around it. The resulting surfaces can be twisted together to create a realistic rope or cable to be used as a decorative element on a ring.
* **Use Case 2 (Creating a Coiled Ring):** You can draw a large helix with a low pitch and then use the `Pipe` command on it to create a ring that coils around the finger multiple times.

### Other Information
This is a fundamental tool for creating any kind of coiled or twisted geometry.

---

## 306. Help

### Short Info
Open the Help topic for the current command.

### Detailed Description
The **Help** command opens the main Rhino help file. If you run it while another command is active, it will open the help file directly to the page for that specific command.

### Steps to use the command
1.  Run a command (e.g., `Line`).
2.  While the `Line` command is still active, run the command `Help` (or press the F1 key).
3.  The Rhino help file will open to the page explaining the `Line` command.

### Command Options & Toggles
This command has no options.

### Note for better use
Pressing the **F1** key is the universal shortcut for this command and is much faster than typing it.

### Practical Use Cases
* **Use Case 1 (Learning a Command):** You are using a command for the first time and are unsure of its options. You can press F1 while the command is active to get instant, context-sensitive help.

### Other Information
This is the primary way to access the built-in documentation.

---

## 307. Hide

### Short Info
Conceal objects from view.

### Detailed Description
The **Hide** command makes selected objects temporarily invisible in the viewports. The objects are not deleted; they are simply hidden from view, which helps to de-clutter the screen and makes it easier to see and select other objects.

### Steps to use the command
1.  Select the object(s) you want to hide.
2.  Run the command `Hide`.
3.  The selected objects will disappear.

### Command Options & Toggles
This command has no options.

### Note for better use
The command to make hidden objects visible again is `Show`. The command `ShowSelected` allows you to selectively unhide objects.

### Practical Use Cases
* **Use Case 1 (Working on an Assembly):** You are working on a complex bezel setting with the gemstone in place. To get a clear view of the inside of the bezel where you need to cut the seat, you can select the gemstone and use `Hide` to temporarily remove it from the view.
* **Use Case 2 (Isolating Objects):** You have a complex model with many overlapping parts. You want to work on only one specific component. You can select everything *except* that component and run the `Invert` command, then `Hide` to hide everything else, leaving you with only the object you want to edit.

### Other Information
This is one of the most fundamental and frequently used workflow commands for managing complex scenes.

---

## 308. HideInDetail

### Short Info
Hide objects in a detail view.

### Detailed Description
The **HideInDetail** command is a utility used within the Layout space. It makes selected objects invisible, but only within the currently active detail view. The objects will remain visible in all other detail views and in the main modeling viewports.

### Steps to use the command
1.  Go to a Layout page.
2.  Activate a detail view by double-clicking inside it.
3.  Select the object(s) you want to hide within that view.
4.  Run the command `HideInDetail`.
5.  The objects will become invisible only in that detail view.

### Command Options & Toggles
This command has no options.

### Note for better use
The command to make these objects visible again in the detail view is `ShowInDetail`.

### Practical Use Cases
* **Use Case 1 (Creating an Exploded View):** You are creating a technical drawing. In one detail view, you want to show the fully assembled ring. In another detail view on the same page, you want to show an "exploded" view with the parts separated. You can use `HideInDetail` to hide the assembled ring in the exploded view detail, and hide the separated parts in the assembled view detail.

### Other Information
This is a powerful tool for creating complex, multi-part drawings on a single layout page.

---

## 309. HideLayersInDetail

### Short Info
Hide layers in a detail view.

### Detailed Description
The **HideLayersInDetail** command is a utility used within the Layout space. It makes entire layers invisible, but only within the currently active detail view. All objects on those layers will remain visible in other detail views and in the main modeling viewports.

### Steps to use the command
1.  Go to a Layout page.
2.  Activate a detail view.
3.  Run the command `HideLayersInDetail`.
4.  A dialog box will appear listing all the layers.
5.  Select the layers you want to hide in that detail view and click OK.

### Command Options & Toggles
The options are the layers you select in the dialog box.

### Note for better use
This is often more efficient than `HideInDetail` if the objects you want to hide are already well-organized on layers. The command to make the layers visible again is `ShowLayersInDetail`.

### Practical Use Cases
* **Use Case 1 (Separating Geometry and Dimensions):** You have a drawing where your 3D model is on one set of layers and your 2D dimensions are on another. In your main perspective detail view, you can use `HideLayersInDetail` to hide the "Dimensions" layer. In your 2D top-down detail view, you can use it to hide any unnecessary 3D geometry layers, keeping each view clean and showing only the relevant information.

### Other Information
This is a key tool for managing complex drawing layouts.

---

## 310. HidePt

### Short Info
Hide selected control points and edit points.

### Detailed Description
The **HidePt** (Hide Points) command makes selected control points or edit points temporarily invisible. This is useful for de-cluttering the view when you are editing a complex curve or surface and only want to see the specific control points you are working with.

### Steps to use the command
1.  Turn on the control points for an object (`PointsOn`).
2.  Select the specific control point(s) you want to hide.
3.  Run the command `HidePt`.
4.  The selected points will become invisible.

### Command Options & Toggles
This command has no options.

### Note for better use
The command to make hidden points visible again is `ShowPt`.

### Practical Use Cases
* **Use Case 1 (Isolating a Problem Area):** You have a very long curve with hundreds of control points, but you only need to adjust a small section in the middle. You can select all the control points *except* the ones in the middle, and use `HidePt` to hide them. This leaves you with a clean view of only the points you need to edit.

### Other Information
This is a display management tool for control point editing.

---

## 311. HideRenderMesh

### Short Info
Hide the render mesh.

### Detailed Description
The **HideRenderMesh** command is a utility that hides a render mesh that has been made visible with the `ShowRenderMesh` command.

### Steps to use the command
1.  Select an object whose render mesh is currently visible.
2.  Run the command `HideRenderMesh`.
3.  The visible render mesh will be hidden.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Ending Analysis):** You have used `ShowRenderMesh` to inspect the polygon mesh of a surface. When you are finished, you use `HideRenderMesh` to turn the mesh display off and return to the normal smooth surface display.

### Other Information
This is the companion command to `ShowRenderMesh`.

---

## 312. ShowRenderMesh

### Short Info
Display the render mesh for an object.

### Detailed Description
The **ShowRenderMesh** command is a utility that makes the invisible "render mesh" of a NURBS surface or polysurface visible in the viewport. The render mesh is the polygon mesh that Rhino creates in the background to display smooth objects in shaded and rendered views. This command allows you to see and inspect that underlying mesh structure.

### Steps to use the command
1.  Select one or more NURBS surfaces or polysurfaces.
2.  Run the command `ShowRenderMesh`.
3.  The render mesh will become visible as a wireframe overlay on your object.

### Command Options & Toggles
This command has no options.

### Note for better use
The density and quality of the mesh you see are controlled by the render mesh settings in your Document Properties. This is a temporary display; to create a permanent, editable mesh object, use the `ExtractRenderMesh` command.

### Practical Use Cases
* **Use Case 1 (Checking Mesh Quality):** Before exporting a model to STL for 3D printing, you can use `ShowRenderMesh` to get a preview of what the final mesh will look like. This allows you to check if the mesh is dense enough to capture all of your fine details. If it's too blocky, you know you need to increase the render mesh quality settings before exporting.

### Other Information
This is an important preview and analysis tool for any workflow that involves converting NURBS to meshes.

---

## 313. HideSwap

### Short Info
Hide all visible objects and show all hidden objects.

### Detailed Description
The **HideSwap** command is a display management utility that inverts the visibility state of all objects in the model. All objects that are currently visible will become hidden, and all objects that are currently hidden will become visible.

### Steps to use the command
1.  Run the command `HideSwap`.
2.  The visibility of all objects will be inverted.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Working with Cutters):** You have a ring model and a large number of cutters for the gemstones. You select all the cutters and `Hide` them to see the final ring. Now, you want to work on only the cutters. You can run `HideSwap`, which will hide the ring and show only the cutters.

### Other Information
This is a very fast and efficient way to toggle between two sets of objects (e.g., the model and its construction geometry).

---

## 314. History

### Short Info
Store the connection between input geometry and the result.

### Detailed Description
The **History** command is a powerful feature that creates a parametric link between an object and the input geometry that was used to create it. When History is enabled, if you edit the original input (e.g., change the shape of a curve), the final output (e.g., a surface made from that curve) will automatically update to reflect the change.

### Steps to use the command
1.  Before running a construction command, run the command `History`.
2.  In the dialog box, make sure "Record History" is checked.
3.  Now, run a construction command (e.g., `Loft`).
4.  Select the input curves. The resulting surface is now linked to the curves.
5.  Turn on the control points for one of the original curves and move a point. The lofted surface will update in real-time.

### Command Options & Toggles
The options are in a dialog box:
* **Record History:** The master toggle for the feature.
* **Update History:** Controls whether the update is automatic or manual.
* **Lock Children:** Prevents the output geometry from being accidentally modified directly.

### Note for better use
History can be enabled for a single command by right-clicking the "Record History" pane in the status bar before running the command. Many commands support history, but not all.

### Practical Use Cases
* **Use Case 1 (Parametric Ring Sizing):** You create a ring shank using `Sweep1` with History enabled. The sweep is linked to the ring rail curve and the profile curve. Now, if you need to change the finger size, you can simply `Scale` the ring rail curve, and the entire 3D ring shank will automatically rebuild itself to the new size.
* **Use Case 2 (Non-Destructive Design):** You are designing a pendant by lofting several profile curves. With History enabled, you can continue to adjust the shape of those profile curves, and the final 3D surface will update automatically, allowing for a very flexible and iterative design process.

### Other Information
Mastering History is a key step in moving from basic modeling to a more powerful, parametric workflow.

---

## 315. HistoryPurge

### Short Info
Remove history from an object.

### Detailed Description
The **HistoryPurge** command removes the parametric link between a selected object and its "parent" input geometry. After running this command, the object will no longer update if its parents are edited.

### Steps to use the command
1.  Select an object that has history.
2.  Run the command `HistoryPurge`.
3.  The history link will be broken.

### Command Options & Toggles
This command has no options.

### Note for better use
This is useful when you have finalized a design and want to "bake" it into a static object, or if a history connection is causing unexpected behavior.

### Practical Use Cases
* **Use Case 1 (Finalizing a Design):** You have used History to create a ring and are now completely finished with the design. To prevent any accidental changes, you can select the final ring and run `HistoryPurge` to remove all the parametric links.

### Other Information
This is the command used to break the link created by the `History` feature.

---

## 316. HistoryUpdate

### Short Info
Update an object that has history.

### Detailed Description
The **HistoryUpdate** command manually forces an object that has history to update based on changes made to its parent geometry. This is only used if the "Update History" option in the `History` command is set to "Manual" instead of "Automatic."

### Steps to use the command
1.  Edit the parent object of a history-enabled child.
2.  Select the child object.
3.  Run the command `HistoryUpdate`.
4.  The child object will update to reflect the changes.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Complex Models):** In a very large and complex model with many history connections, automatic updates can sometimes cause a performance lag. A user might set history to update manually. They can then make many changes to the parent curves and, when they are ready, run `HistoryUpdate` once to perform all the updates at the same time.

### Other Information
For most users, leaving history set to "Automatic" is more intuitive.

---

## 317. Hydrostatics

### Short Info
Calculate hydrostatics for surfaces.

### Detailed Description
The **Hydrostatics** command is an extremely specialized analysis tool used for naval architecture. It calculates various hydrostatic values (like displacement, center of buoyancy, and waterplane area) for surfaces that represent a ship's hull.

### Steps to use the command
1.  Select one or more surfaces representing a hull.
2.  Run the command `Hydrostatics`.
3.  You will be prompted to define the waterplane level.
4.  A detailed report of the hydrostatic values will be displayed in the command history.

### Command Options & Toggles
This command has no options in the command line.

### Note for better use
This command has no practical application in jewelry design.

### Practical Use Cases
* **Use Case 1 (Ship Design):** A naval architect uses this command to analyze the stability and displacement of a boat hull they have designed in Rhino.

### Other Information
This is a tool for a very specific engineering discipline.

---

## 318. Hyperbola

### Short Info
Draw a hyperbolic curve.

### Detailed Description
The **Hyperbola** command is a 2D drawing tool used to create a hyperbolic curve. A hyperbola is a specific type of smooth, open curve defined by its focal points and vertices.

### Steps to use the command
1.  Run the command `Hyperbola`.
2.  Follow the prompts to define the curve by picking its focal points and vertices.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Optical Design):** Hyperbolic shapes are important in the design of lenses and reflectors. An optical engineer might use this command to create the precise profile for a reflector. This command has very limited use in typical jewelry design.

### Other Information
This is a specialized curve creation tool for a specific mathematical shape.

---

## 319. Hyperlink

### Short Info
Manage URL hyperlinks.

### Detailed Description
The **Hyperlink** command allows you to attach a clickable web link (a URL) to any object in your model. It also allows you to test existing hyperlinks.

### Steps to use the command
1.  Select an object.
2.  Run the command `Hyperlink`.
3.  A dialog box will appear.
4.  Enter the URL and a description in the fields.
5.  Click OK. The hyperlink is now attached to the object.

### Command Options & Toggles
The options are in the dialog box for setting the URL and description.

### Note for better use
To test a hyperlink, run the command with nothing selected.

### Practical Use Cases
* **Use Case 1 (Project Management):** You are working on a ring that is based on a specific gemstone from an online supplier. You can use `Hyperlink` to attach the URL of the gemstone's product page directly to the gemstone object in your model. Now, anyone who opens the file can easily access the information for that stone.
* **Use Case 2 (Client Files):** You can attach a hyperlink to your company's website on the main object before sending a file to a client.

### Other Information
This is a data management and annotation tool.

---

## 320. IGESStudy

### Short Info
Examine the contents of an IGES file.

### Detailed Description
The **IGESStudy** command is a diagnostic utility for working with IGES files. IGES is a common file format for transferring data between different CAD programs. This command allows you to open an IGES file and examine its internal structure and data before you actually import it into Rhino.

### Steps to use the command
1.  Run the command `IGESStudy`.
2.  A file browser will open. Select an IGES file.
3.  A dialog box will appear, showing a tree-like structure of all the entities within the file.

### Command Options & Toggles
This command has no options.

### Note for better use
This is an advanced tool for troubleshooting problematic IGES files. If a file is failing to import correctly, you can use `IGESStudy` to look inside and see if there are any unusual or unsupported entity types that might be causing the problem.

### Practical Use Cases
* **Use Case 1 (Troubleshooting Imports):** You have received an IGES file from a client that will not open in Rhino. You can use `IGESStudy` to inspect the file's contents to try and diagnose the issue.

### Other Information
This is a tool for advanced users and file translation experts.

---

## 321. Import

### Short Info
Merge objects from another model.

### Detailed Description
The **Import** command merges geometry from an external file into your currently open model. It allows you to bring in objects from other Rhino files (.3dm) or from a wide variety of other file formats (like .STL, .STEP, .AI, etc.).

### Steps to use the command
1.  Run the command `Import`.
2.  A file browser will open.
3.  Select the file you want to import.
4.  Click "Open." The objects from that file will be added to your current scene.

### Command Options & Toggles
The options will vary depending on the file type you are importing. For example, when importing an STL file, you will get options for welding and scaling the mesh.

### Note for better use
Importing is different from opening. `Open` closes your current file and opens a new one. `Import` adds the contents of another file to the one you are currently working on.

### Practical Use Cases
* **Use Case 1 (Combining Components):** You have separate Rhino files for a ring shank, a bezel, and a gemstone. You can start with the shank file, and then use `Import` to bring in the bezel and the gemstone, allowing you to assemble the final ring.
* **Use Case 2 (Using a Client's File):** A client has sent you an Illustrator file (.AI) containing their company logo. You can use `Import` to bring the logo curves directly into your Rhino model to be incorporated into a piece of jewelry.

### Other Information
This is a fundamental command for working with data from other files and applications.

---

## 322. ImportDimStyles

### Short Info
Import dimension styles into the current model.

### Detailed Description
The **ImportDimStyles** (Import Dimension Styles) command is a utility that allows you to import annotation styles from another Rhino file into your current model. This is a very efficient way to ensure that your drawings are consistent across multiple files without having to manually recreate your dimension styles each time.

### Steps to use the command
1.  Run the command `ImportDimStyles`.
2.  A file browser will open. Select the Rhino (.3dm) file that contains the dimension styles you want to import.
3.  A dialog box will appear listing all the dimension styles in that file.
4.  Select the style(s) you want to import and click OK.

### Command Options & Toggles
The options are the styles you select in the dialog box.

### Practical Use Cases
* **Use Case 1 (Using a Template):** Your company has a "template" Rhino file that contains all of your official, standardized dimension styles. When you start a new project file, you can use `ImportDimStyles` to quickly load all of those standard styles into your new file, ensuring all your drawings will be consistent.

### Other Information
This is an important tool for maintaining drafting standards across multiple projects.

---

## 323. ImportLayout

### Short Info
Import a layout from another model.

### Detailed Description
The **ImportLayout** command is a utility that allows you to import a complete layout page from another Rhino file into your current model. This is useful for reusing standard drawing templates and title blocks.

### Steps to use the command
1.  Run the command `ImportLayout`.
2.  A file browser will open. Select the Rhino (.3dm) file that contains the layout you want to import.
3.  A new layout tab will be created in your current file that is a copy of the layout from the other file.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Reusing a Title Block):** You have a standard layout page set up with your company's logo, title block, and standard views. When you create a new model, instead of setting up the layout page from scratch, you can simply use `ImportLayout` to bring in your standard template page.

### Other Information
This is a time-saving utility for creating and managing drawing sheets.

---

## 324. IncrementalSave

### Short Info
Save sequentially numbered versions of a model.

### Detailed Description
The **IncrementalSave** command saves your current file but automatically adds an incrementing number to the end of the filename (e.g., MyRing_001.3dm, MyRing_002.3dm, etc.). This is a very powerful and highly recommended command for saving your work, as it creates a sequential backup of your design process without you having to manually type in new filenames.

### Steps to use the command
1.  Run the command `IncrementalSave`.
2.  The file will be saved with the next number in the sequence.

### Command Options & Toggles
This command has no options.

### Note for better use
It is a very good practice to use `IncrementalSave` frequently instead of just `Save`. This creates a history of your file that you can go back to if you make a mistake, if a file becomes corrupted, or if a client changes their mind and wants to go back to an earlier version of the design.

### Practical Use Cases
* **Use Case 1 (Version Control):** You are working on a complex ring design. Every 15-20 minutes, or after every major step, you run `IncrementalSave`. At the end of the day, you will have a folder containing a complete, step-by-step history of your work (Ring_001, Ring_002, ... Ring_034). If you realize you made a mistake an hour ago, you can simply open one of the earlier files instead of having to undo many steps.

### Other Information
This is one of the most important commands for professional, non-destructive workflow and data safety.

---

## 325. Insert

### Short Info
Insert a block or a file as a block instance.

### Detailed Description
The **Insert** command is the primary tool for placing block instances into your model. It can also be used to import an entire external file as a block. When you insert a file as a block, a link can be maintained to the external file, allowing for powerful collaborative workflows.

### Steps to use the command
1.  Run the command `Insert`.
2.  A dialog box appears. You can choose to insert a block that is already defined in the file, or you can browse to an external file.
3.  Set the insertion options (insertion point, scale, rotation).
4.  Click OK and place the block instance in the model.

### Command Options & Toggles
The options are in the dialog box:
* **Name:** A list of blocks already in the model.
* **File:** A button to browse for an external file.
* **Block / Group:** Choose whether to insert the object as a block instance or as a regular group.
* **Insertion point / Scale / Rotation:** Allows you to set these properties before or after insertion.
* **Link:** (When inserting a file) Creates a dynamic link to the external file.

### Note for better use
When you insert an external file with the "Link" option checked, the block instance in your model will be linked to that file. If the external file is ever updated, the `BlockManager` will notify you, and you can update the block to the new version.

### Practical Use Cases
* **Use Case 1 (Placing Gemstones):** You have created a block definition for a 1.5mm diamond. You use the `Insert` command to place instances of this block all over your model where the stones are needed.
* **Use Case 2 (Using a Component Library):** You have a library of standard components like clasps and bails saved as separate Rhino files. You can use `Insert` with the "Link" option to bring these components into your current design. If you ever improve the design of your standard clasp, all the rings that use it as a linked block can be updated automatically.

### Other Information
This is the main command for working with block definitions.

---

## 326. InsertControlPoint

### Short Info
Add a control point to a curve.

### Detailed Description
The **InsertControlPoint** command is a curve editing tool that allows you to add one or more new control points to a curve. Adding control points provides more localized control for editing and changing the shape of the curve.

### Steps to use the command
1.  Select a curve.
2.  Run the command `InsertControlPoint`.
3.  The curve's control points will be displayed.
4.  Click on the curve's control polygon (the line connecting the control points) where you want to add a new point.
5.  You can continue clicking to add more points.
6.  Press Enter to end the command.

### Command Options & Toggles
This command has no options.

### Note for better use
This command adds points without significantly changing the shape of the curve. The opposite command is `RemoveControlPoint`. For adding a sharp corner, use the `InsertKink` command.

### Practical Use Cases
* **Use Case 1 (Adding Detail):** You have a smooth, simple curve that defines the outline of a pendant. You decide you want to add a small, localized bump or wave to one side. You would use `InsertControlPoint` to add a few new control points in that area, and then pull on the new points to create the detail without affecting the rest of the curve's shape.

### Other Information
This is a fundamental tool for detailed curve editing.

---

## 327. InsertEditPoint

### Short Info
Add an edit point to a curve.

### Detailed Description
The **InsertEditPoint** command is a curve editing tool that allows you to add a new "edit point" to a curve. An edit point is a point that lies directly on the curve. Adding an edit point refines the curve's shape by adding the necessary control points to make the curve pass through the new location.

### Steps to use the command
1.  Select a curve.
2.  Run the command `InsertEditPoint`.
3.  Click on the curve where you want to add a new edit point.
4.  The curve's shape will be updated.

### Command Options & Toggles
This command has no options.

### Note for better use
This command will change the shape of your curve more than `InsertControlPoint` will. It is useful when you need to force a curve to pass through a new, specific point.

### Practical Use Cases
* **Use Case 1 (Forcing a Fit):** You have a curve that defines the edge of a bezel, but it's not quite touching the gemstone at one spot. You can use `InsertEditPoint` and snap to the gemstone's edge to add a point to the curve, forcing it to touch the stone at that exact location.

### Other Information
This is a more specialized curve editing tool than `InsertControlPoint`.

---

## 328. InsertKink

### Short Info
Add a kink to a curve.

### Detailed Description
The **InsertKink** command is a curve editing tool that adds a sharp corner, or "kink," to a smooth curve at a location you specify.

### Steps to use the command
1.  Select a curve.
2.  Run the command `InsertKink`.
3.  Click on the curve where you want to add the sharp corner.
4.  A new control point will be added, and the curve will now have a sharp corner at that location.

### Command Options & Toggles
This command has no options.

### Note for better use
This command works by "stacking" multiple control points at the same location, which is how NURBS curves create sharp corners.

### Practical Use Cases
* **Use Case 1 (Creating a Square Bezel Corner):** You have created a soft, rounded rectangle using the `Rectangle` command with the "Rounded" option. You now decide you want one of the corners to be sharp. You can use `InsertKink` at the midpoint of the rounded corner arc to turn it into a sharp, 90-degree corner.

### Other Information
This is a simple tool for adding sharp corners to smooth curves.

---

## 329. InsertKnot

### Short Info
Add a knot to a curve or surface.

### Detailed Description
The **InsertKnot** command is an advanced curve and surface editing tool. It adds "knots" to the internal mathematical structure of a NURBS object. Adding knots adds more control points without changing the shape of the object. This is a key technique used to gain more localized control over a curve or surface before editing it.

### Steps to use the command
1.  Select a curve or surface.
2.  Run the command `InsertKnot`.
3.  Click on the object where you want to add the knot(s).
4.  New control points will appear near where you clicked.
5.  Press Enter to end the command.

### Command Options & Toggles
* **Symmetrical:** Adds knots symmetrically on both sides of the center of the curve or surface.
* **Midpoints:** Automatically adds a knot at the midpoint between every existing knot.

### Note for better use
This is the preferred method for adding detail to a curve or surface without altering its shape. Unlike `Rebuild`, which re-calculates the entire object, `InsertKnot` simply adds more control locally.

### Practical Use Cases
* **Use Case 1 (Localized Editing):** You have a smooth, simple ring shank surface. You want to pull up a small section to create a single prong base, but you don't want to affect the rest of the shank. You would use `InsertKnot` to add several new rows of control points only in the area where you want to create the prong. Now you can pull on these new points without changing the shape of the rest of the ring.

### Other Information
This is a fundamental and essential command for advanced, high-quality NURBS modeling.

---

## 330. InsertLineIntoCrv

### Short Info
Replace a segment of a curve with a line.

### Detailed Description
The **InsertLineIntoCrv** (Insert Line Into Curve) command is a curve editing tool that replaces a segment of a smooth curve with a straight line segment.

### Steps to use the command
1.  Run the command `InsertLineIntoCrv`.
2.  Select the curve you want to edit.
3.  Pick the start point of the new line segment on the curve.
4.  Pick the end point of the new line segment on the curve.
5.  The curved section between the two points will be replaced with a straight line.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Creating a Flat Spot):** You have a circular ring rail and you need to create a flat spot on the bottom for a "Euro-shank" style ring. You can use `InsertLineIntoCrv` to select the bottom section of the circle and replace it with a straight line.

### Other Information
This is a simple utility for making specific edits to curves.

---

## 331. InterpCrv

### Short Info
Draw a curve that passes through picked locations.

### Detailed Description
The **InterpCrv** (Interpolate Curve) command is a fundamental 2D drawing tool. It creates a smooth NURBS curve that passes directly *through* a series of points that you pick in the viewport. This is different from the `Curve` command, where the curve is pulled towards the control points.

### Steps to use the command
1.  Run the command `InterpCrv`.
2.  At the **Start of curve** prompt, pick the first point.
3.  Continue picking points that you want the curve to pass through.
4.  Press Enter when you are finished.

### Command Options & Toggles
* **Degree:** Sets the mathematical degree of the curve.
* **Close:** Closes the curve by creating a smooth segment from the last point back to the first.
* **Sharp:** Creates sharp corners at the points you pick, resulting in a polyline-like curve with kinked, smooth segments.

### Note for better use
Understanding the difference between interpolated curves (`InterpCrv`) and control-point curves (`Curve`) is a fundamental concept in NURBS modeling. Use `InterpCrv` when you need a curve to hit exact locations.

### Practical Use Cases
* **Use Case 1 (Tracing an Image):** This is the primary command for tracing a sketch or reference image. You can click on the key points of the outline in your `BackgroundBitmap`, and `InterpCrv` will create a smooth curve that passes through all of them.
* **Use Case 2 (Creating a Path):** You need to create a path for a `Sweep` that passes through several specific points in your model. `InterpCrv` is the ideal tool for this, as you can snap to the required locations to define the curve's path.

### Other Information
This is a workhorse command and one of the first that new users learn for 2D drawing.

---

## 332. InterpCrvOnSrf

### Short Info
Draw a curve on a surface by picking points.

### Detailed Description
The **InterpCrvOnSrf** (Interpolate Curve On Surface) command is a specialized drawing tool that creates a smooth curve that lies directly on a target surface. You define the shape of the curve by picking points on the surface, and the resulting curve will follow the contour of that surface.

### Steps to use the command
1.  Run the command `InterpCrvOnSrf`.
2.  At the **Select a surface** prompt, select the surface you want to draw on.
3.  You will then be prompted to pick the start and subsequent points for the curve, directly on the surface.
4.  Press Enter when you are finished.

### Command Options & Toggles
* **Close:** Closes the curve with a smooth segment on the surface.

### Note for better use
This is the most direct way to draw a curve that perfectly conforms to a 3D surface. An alternative method is to draw a flat curve and then use `Project` or `Pull` to place it on the surface, but `InterpCrvOnSrf` is often more intuitive.

### Practical Use Cases
* **Use Case 1 (Defining a Gemstone Layout):** You want to create a winding, flowing line of pavé stones on a complex, organic ring shank. `InterpCrvOnSrf` is the perfect tool to draw this path directly on the 3D surface. You can then use the resulting curve with the `ArrayCrvOnSrf` command.
* **Use Case 2 (Creating Trim Lines):** You want to split a surface for a two-tone design. You can use this command to draw the exact split line you want directly on the model's surface.

### Other Information
This is an essential command for creating decorative elements and construction lines on 3D surfaces.

---

## 333. Intersect

### Short Info
Create curves and points at the intersections of objects.

### Detailed Description
The **Intersect** command is a fundamental analysis and curve creation tool. It calculates the intersection between two or more objects (surfaces, polysurfaces, or meshes) and creates new geometry (curves or points) where they cross.

### Steps to use the command
1.  Select two or more objects that intersect each other.
2.  Run the command `Intersect`.
3.  Curve and/or point objects will be created along the line(s) of intersection.

### Command Options & Toggles
This command has no options.

### Note for better use
The resulting curves can be used for a wide variety of modeling operations, such as trimming, splitting, or as rails and profiles for sweeps and lofts.

### Practical Use Cases
* **Use Case 1 (Creating a Bezel Seat Line):** You have a solid ring and a gemstone that is positioned inside it. To find the exact line where the gemstone's pavilion meets the inside of the ring, you can `Intersect` the two objects. The resulting curve is the perfect guide for cutting the seat.
* **Use Case 2 (Finding a Seam Line):** You have two complex, flowing surfaces that merge into each other. `Intersect` will create the exact curve where the two surfaces meet, which can then be used as a trim object to create a clean, seamless join.

### Other Information
This is a workhorse command used constantly in all forms of 3D modeling.

---

## 334. IntersectTwoSets

### Short Info
Find the intersection between two sets of objects.

### Detailed Description
The **IntersectTwoSets** command is a variation of the `Intersect` command. It allows you to find the intersections between one group of objects and a second, separate group of objects, ignoring any intersections between objects that are in the same group.

### Steps to use the command
1.  Run the command `IntersectTwoSets`.
2.  At the **Select first set of objects** prompt, select one or more objects and press Enter.
3.  At the **Select second set of objects** prompt, select one or more objects and press Enter.
4.  The command will create curves only where an object from the first set intersects an object from the second set.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Complex Assemblies):** You have a complex model of a watch, with all the gears in one group and the watch case in another. You want to find only the points where the gears pass through the case, without calculating all the intersections between the gears themselves. `IntersectTwoSets` is the perfect tool for this, as it allows you to isolate the specific intersections you are interested in.

### Other Information
This is a more controlled version of the `Intersect` command, useful for complex scenes.

---

## 335. Invert

### Short Info
Deselect all selected objects and select all visible unselected objects.

### Detailed Description
The **Invert** command is a selection utility. It reverses the current selection state of all visible objects in the model. Any object that is currently selected will become deselected, and any visible object that is not selected will become selected.

### Steps to use the command
1.  Select one or more objects.
2.  Run the command `Invert`.
3.  The selection will be reversed.

### Command Options & Toggles
This command has no options.

### Note for better use
This command does not affect hidden objects.

### Practical Use Cases
* **Use Case 1 (Hiding Other Objects):** You want to work on a single, specific prong of a complex ring. It can be tedious to select every other object in the model to hide them. Instead, you can simply select the one prong you want to work on, run `Invert` (which will select everything *except* the prong), and then run the `Hide` command.
* **Use Case 2 (Changing Layers):** You want to move every object in your model *except* for the gemstones to a new layer. You can select all the gemstones, run `Invert`, and then run the `ChangeLayer` command.

### Other Information
This is a very powerful and time-saving selection tool.

---

## 336. InvertPt

### Short Info
Deselect all selected points and select all visible unselected points.

### Detailed Description
The **InvertPt** (Invert Points) command is a selection utility that works on control points and edit points. It reverses the current selection state of all visible points on an object.

### Steps to use the command
1.  Turn on the control points for an object (`PointsOn`).
2.  Select one or more control points.
3.  Run the command `InvertPt`.
4.  The point selection will be reversed.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Editing Ends of a Surface):** You have a long surface and you want to select all the control points *except* for the two rows at the very ends. You can drag a window to select the two end rows, then run `InvertPt` to quickly select all the interior points.

### Other Information
This is the point-selection equivalent of the `Invert` command.

---

## 337. Isometric

### Short Info
Change the view to a specified isometric view.

### Detailed Description
The **Isometric** command is a viewport management tool that changes the active viewport to a parallel-projection isometric view. An isometric view is a standard type of 3D technical drawing view where the object is rotated to show three sides at once, with all parallel lines remaining parallel.

### Steps to use the command
1.  Make a viewport active.
2.  Run the command `Isometric`.
3.  The command line will prompt for a viewing direction.
4.  Click one of the options (e.g., `SouthWest`).
5.  The view will change to that isometric orientation.

### Command Options & Toggles
* **SouthWest / SouthEast / NorthWest / NorthEast:** These options set the camera to look from one of the four standard isometric corners.

### Practical Use Cases
* **Use Case 1 (Technical Illustration):** You are creating a technical drawing or a patent illustration of a piece of jewelry. An isometric view is a standard and clear way to represent a 3D object on a 2D page. You can use this command to set the view perfectly before using `Make2D` to generate the line drawing.

### Other Information
This is a standard tool for technical illustration and drafting.

---

## 338. Join

### Short Info
Connect curves, surface edges, or surfaces to form a single object.

### Detailed Description
The **Join** command is a fundamental editing tool that connects multiple curves or surfaces together into a single object. For curves, it will connect them into a single polycurve if they meet at their endpoints. For surfaces, it will connect them into a single polysurface if they share an open ("naked") edge.

### Steps to use the command
1.  Select two or more curves or surfaces that meet at their edges.
2.  Run the command `Join`.
3.  The objects will be joined into a single object.

### Command Options & Toggles
This command has no options.

### Note for better use
The opposite of `Join` is `Explode`. For `Join` to be successful, the objects must be touching at their endpoints (for curves) or have perfectly coincident edges (for surfaces). You can use the `ShowEdges` command to check for open edges that might prevent a join.

### Practical Use Cases
* **Use Case 1 (Creating a Closed Profile):** You have drawn the outline of a shape using several separate lines and arcs. To turn this into a single, closed profile for a command like `ExtrudeCrv`, you must first select all the segments and `Join` them.
* **Use Case 2 (Creating a Solid):** You have modeled the individual surfaces of a bezel (the inner wall, outer wall, top, and bottom). To turn these separate surfaces into a single, solid object, you must select them all and `Join` them.

### Other Information
This is one of the most basic and essential editing commands in Rhino.

---

## 339. JoinEdge

### Short Info
Force two naked edges to join.

### Detailed Description
The **JoinEdge** command is a specialized repair tool. It forces two naked surface edges that are very close together, but not perfectly coincident, to join. This is used to fix small inaccuracies in a model that are preventing a normal `Join` from working.

### Steps to use the command
1.  Run the command `JoinEdge`.
2.  At the **Select open edge** prompt, select a naked edge on a surface.
3.  At the **Select another open edge to join** prompt, select the corresponding edge on the adjacent surface.
4.  If the edges are within tolerance, they will be forced to join.

### Command Options & Toggles
This command has no options.

### Note for better use
This should be used with caution, as it can sometimes create bad geometry if the edges are too far apart. It is a repair tool for fixing small modeling errors, not a standard modeling command.

### Practical Use Cases
* **Use Case 1 (Fixing an Imported Model):** You have imported a model from another program, and due to translation errors, the edges of adjacent surfaces are very slightly separated, preventing you from joining them into a solid. `JoinEdge` can be used to manually force these edges together.

### Other Information
This is an advanced model repair tool.

---

## 340. Lasso

### Short Info
Select objects by drawing a freehand shape.

### Detailed Description
The **Lasso** command is a selection tool that allows you to select objects by drawing a free-form, irregular shape around them. This is useful for selecting objects in a crowded scene where a simple rectangular window selection is not precise enough.

### Steps to use the command
1.  Run the command `Lasso`.
2.  Click and drag the mouse to draw a free-form shape in the viewport.
3.  Any objects that are enclosed by or touching the shape will be selected.

### Command Options & Toggles
* **Crossing (Yes/No):** If Yes, any object the lasso touches will be selected. If No, only objects that are completely inside the lasso will be selected.

### Note for better use
You can start a lasso selection without running the command by simply clicking and dragging in an empty area of the viewport with the right mouse button.

### Practical Use Cases
* **Use Case 1 (Selecting Stones in a Cluster):** You have a dense cluster of pavé stones and you need to select a specific, irregular group of them. A rectangular window would select too many. `Lasso` allows you to draw a precise, free-form shape around only the stones you want to select.

### Other Information
This is a fundamental selection tool for working in complex scenes.

---

## 341. Layer

### Short Info
Manage layer properties.

### Detailed Description
The **Layer** command opens the main Layer panel. This panel is the central interface for creating, deleting, and managing all the layers in your model. It allows you to control the name, visibility (On/Off), locked status, color, and other properties for each layer.

### Steps to use the command
1.  Run the command `Layer`.
2.  The Layer panel will open (or be brought to the front if it's already open).

### Command Options & Toggles
All options are contained within the panel's interface (buttons for New Layer, Delete Layer, and columns for each property).

### Note for better use
Effective layer management is one of the most important skills for professional CAD work. It is essential for keeping complex models organized and easy to edit. You should get in the habit of creating and naming layers for each different type of component in your design (e.g., "Shank," "Bezels," "Center Stone," "Accent Stones," "Curves").

### Practical Use Cases
* **Use Case 1 (Organizing a Model):** As you build a ring, you create new layers for each part. This allows you to, for example, hide all of the gemstones by simply turning off the "Gems" layer, making it easy to work on the metal underneath.
* **Use Case 2 (Setting Print Color):** In the Layer panel, you can set a specific "Print Color" for your "Curves" layer. This means that even if the curves are displayed as blue on your screen, they will print as black in your technical drawings.

### Other Information
This is one of the most fundamental organizational panels in the Rhino interface.

---

## 342. LayerStateManager

### Short Info
Save and restore the current state of layers.

### Detailed Description
The **LayerStateManager** command opens a panel that allows you to save and restore "layer states." A layer state is a snapshot of the current condition of all your layers—which ones are on, off, locked, their colors, etc. This is an incredibly powerful tool for quickly switching between different configurations of your model for different tasks.

### Steps to use the command
1.  Run the command `LayerStateManager`.
2.  The Layer States panel will appear.
3.  Click the "Save" button to save the current state of all your layers with a name.
4.  To restore a state, select it from the list and click "Restore."

### Command Options & Toggles
All options are contained within the panel's interface.

### Note for better use
You can choose which properties are saved and restored with each state (e.g., only visibility, or visibility and color).

### Practical Use Cases
* **Use Case 1 (Switching Between Workflows):** You are working on a complex ring. You can save a "Modeling" layer state where only your geometry layers are visible. Then, you can save a "Rendering" state where only the final, solid objects are visible and the construction curves are hidden. You can then save a "Drafting" state where only the 2D curves and dimensions are visible. The `LayerStateManager` allows you to switch between these complex setups with a single click.

### Other Information
This is a powerful workflow management tool for complex projects.

---

## 343. Layout

### Short Info
Create a new layout viewport.

### Detailed Description
The **Layout** command is used to create a new "layout" page. A layout is a 2D page (like a piece of paper) used for creating technical drawings and presentations. On a layout, you can arrange one or more "detail views" (windows that look into your 3D model), and add dimensions, text, and title blocks.

### Steps to use the command
1.  Run the command `Layout`.
2.  A dialog box will appear asking you to name the new layout and set its properties (printer, page size, initial number of detail views).
3.  Click OK. A new tab will be created at the bottom of the viewports for your new layout page.

### Command Options & Toggles
The options are in the setup dialog box:
* **Name:** The name for the new layout tab.
* **Printer:** The printer the layout will be formatted for.
* **Paper Size:** The size of the virtual page.
* **Initial Detail Count:** The number of detail views to automatically create.

### Note for better use
Working in layouts is a key part of producing professional 2D documentation from your 3D models.

### Practical Use Cases
* **Use Case 1 (Creating a Tech Sheet):** You have finished a 3D model of a ring. You run `Layout` to create a new A4-sized page. On this page, you arrange detail views showing the Top, Front, Right, and Perspective views of the ring. You then add dimensions, notes, and a title block to create a complete technical sheet for your manufacturer.

### Other Information
This is the primary command for entering the "paper space" environment for drafting.

---

## 344. LayoutProperties

### Short Info
Manage layout properties.

### Detailed Description
The **LayoutProperties** command opens the Properties panel for the currently active layout page. This allows you to change the settings you defined when you first created the layout, such as its name, the printer it's assigned to, and the paper size.

### Steps to use the command
1.  Make a layout page active by clicking its tab.
2.  Run the command `LayoutProperties`.
3.  The Properties panel will open, showing the settings for that layout.

### Command Options & Toggles
The options are the settings within the Properties panel.

### Practical Use Cases
* **Use Case 1 (Changing Paper Size):** You have created a drawing on an A4 layout, but the client has requested it on a US Letter size page. You can use `LayoutProperties` to change the paper size for the existing layout.

### Other Information
This is the main command for editing the properties of an existing layout page.

---

## 345. Leader

### Short Info
Create an annotation leader.

### Detailed Description
The **Leader** command is an annotation tool that creates a leader line with attached text. A leader is an arrow that points to a specific feature on a model, with a line leading to text that provides a note or a callout for that feature.

### Steps to use the command
1.  Run the command `Leader`.
2.  At the **Start of leader** prompt, click on the feature you want to point to.
3.  Continue clicking to create the points for the leader line. Press Enter when finished.
4.  A text box will appear. Type your annotation text and click OK.

### Command Options & Toggles
The options for the leader's appearance (arrowhead type, text size, etc.) are controlled by the current Annotation Style.

### Note for better use
This is the standard tool for creating callouts and notes on technical drawings.

### Practical Use Cases
* **Use Case 1 (Specifying a Finish):** In a technical drawing, you need to indicate that a specific surface of a ring should have a matte finish. You can use `Leader` to draw an arrow pointing to that surface with the text "Matte Finish."
* **Use Case 2 (Stone Callouts):** You are creating a drawing with multiple gemstone sizes. You can use `Leader` to point to each type of stone and add text specifying its size and type (e.g., "1.5mm Round Diamond (x12)").

### Other Information
This is a fundamental tool for annotation and drafting.

---

## 346. Length

### Short Info
Report the length of curves or surface edges.

### Detailed Description
The **Length** command is an analysis tool that measures and reports the length of one or more curves or surface edges.

### Steps to use the command
1.  Select the curve(s) or edge(s) you want to measure.
2.  Run the command `Length`.
3.  The command history will report the length of the selected objects.

### Command Options & Toggles
This command has no options.

### Note for better use
If you select multiple curves, the command will report the length of each one individually, as well as the cumulative total length. To create a permanent, visible dimension of a curve's length, use the `DimCurveLength` command.

### Practical Use Cases
* **Use Case 1 (Calculating Chain Length):** You have drawn a curve that represents a necklace chain. You can use the `Length` command to get its exact length to ensure it meets the design specification (e.g., 18 inches).
* **Use Case 2 (Estimating Wire Usage):** You have a filigree design made of many curves. You can select all the curves and run `Length` to get the total length. This can help you estimate how much wire you will need to produce the piece.

### Other Information
This is a fundamental measurement tool.

---

## 347. Libraries

### Short Info
Open the Libraries panel.

### Detailed Description
The **Libraries** command opens a panel that gives you access to your content libraries. These libraries are where you can store and organize your rendering assets, such as materials, textures, and environments, in a location outside of the current file.

### Steps to use the command
1.  Run the command `Libraries`.
2.  The Libraries panel will open.
3.  You can browse through your saved library folders, and drag-and-drop materials or other assets from the library directly onto objects in your model.

### Command Options & Toggles
The options are the file and folder navigation controls within the panel itself.

### Note for better use
Setting up a well-organized material library is a key step for an efficient rendering workflow. You can save your favorite, most frequently used materials (like "18k Yellow Gold," "Polished Silver," "Diamond") to your library so you can quickly apply them to any new project without having to create them from scratch each time.

### Practical Use Cases
* **Use Case 1 (Applying Standard Materials):** You have just finished modeling a ring. You open the `Libraries` panel, navigate to your "Metals" folder, and drag your saved "14k White Gold" material onto the ring to instantly apply it.

### Other Information
This is the main interface for managing your reusable rendering assets.

---

## 348. Lights

### Short Info
Open the Lights panel.

### Detailed Description
The **Lights** command opens a panel that allows you to create and manage the light sources in your scene. This panel is the central hub for adding new lights (spotlights, point lights, etc.), turning them on and off, and adjusting their properties like color and intensity.

### Steps to use the command
1.  Run the command `Lights`.
2.  The Lights panel will open.
3.  You can right-click in the panel to create new lights or select an existing light from the list to edit its properties.

### Command Options & Toggles
The options are all contained within the panel's interface.

### Note for better use
Good lighting is the most important factor in creating a realistic render. The Lights panel is where you control this. A standard "three-point lighting" setup (a main "key" light, a softer "fill" light, and a "back" light) is a great starting point for most product rendering.

### Practical Use Cases
* **Use Case 1 (Setting Up a Render Scene):** You are preparing to render a ring. You open the `Lights` panel and create a new spotlight to act as your main light source. You then select the light in the panel and adjust its intensity and color to get the desired effect.

### Other Information
This is a fundamental panel for controlling the lighting in your renders.

---

## 349. LimitReferenceModel

### Short Info
Limit the display of a worksession reference model to a bounding box.

### Detailed Description
The **LimitReferenceModel** command is a utility used with the `Worksession` feature. A worksession allows you to link to other large Rhino files as reference geometry without having to import them, which keeps your file size small. This command allows you to define a bounding box and only display the parts of the reference model that are inside that box. This is a performance-optimization tool for working with extremely large reference files.

### Steps to use the command
1.  Have a worksession with a reference model attached.
2.  Run the command `LimitReferenceModel`.
3.  Follow the prompts to define a bounding box.
4.  Only the portion of the reference model inside the box will be visible.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a very specialized command for users who work with massive datasets, such as in architecture or civil engineering, where an entire city model might be used as a reference file.

### Practical Use Cases
* **Use Case 1 (Large-Scale Design):** An architect is designing a new building and is using a worksession to reference a 3D model of the entire city block. To improve performance, they can use `LimitReferenceModel` to only show the buildings immediately adjacent to their new design. This command has no practical use in jewelry design.

### Other Information
This is a performance tool for the `Worksession` system.

---

## 350. Line

### Short Info
Draw a single line segment.

### Detailed Description
The **Line** command is one of the most fundamental 2D drawing tools. It creates a single, straight line segment by defining its start and end points.

### Steps to use the command
1.  Run the command `Line`.
2.  At the **Start of line** prompt, pick a point.
3.  At the **End of line** prompt, pick a second point.
4.  A line segment is created.

### Command Options & Toggles
* **BothSides:** Draws the line in both directions from the start point.
* **Normal:** Draws a line that is perpendicular to a surface.
* **Angled:** Constrains the line to be drawn at a specific angle.
* **Vertical:** Draws a line that is vertical to the current CPlane.

### Note for better use
To draw a series of connected line segments, use the `Polyline` command. Holding down the `Shift` key while drawing will toggle Ortho mode, constraining the line to 90-degree increments.

### Practical Use Cases
* **Use Case 1 (Construction Lines):** You are setting up a layout for a ring and need to draw a vertical centerline and a horizontal line to mark the top of the finger rail. The `Line` command is the tool for creating this basic guide geometry.
* **Use Case 2 (Drawing Profiles):** You are drawing the straight-sided profile of a princess-cut gemstone. The `Line` command is used to draw each of the straight facets.

### Other Information
This is one of the most basic and frequently used commands in all of CAD.


---

## 351. LinearLight

### Short Info
Insert a linear light.

### Detailed Description
The **LinearLight** command adds a linear light source to the model, which simulates a light source shaped like a fluorescent tube. This type of light emits rays from an imaginary line, creating softer shadows than a point light and providing a broad, even illumination. It is useful for creating studio-style lighting setups for rendering.

### Steps to use the command
1.  Run the command `LinearLight`.
2.  At the **Start of light** prompt, pick a point to begin the line.
3.  At the **End of light** prompt, pick a second point to define the length and orientation of the light.
4.  A linear light object will be created in your model.

### Command Options & Toggles
This command has no options in the command line. The light's properties, such as color, intensity, and length, are edited in the Properties panel after it has been created.

### Note for better use
Linear lights are excellent for creating soft, rectangular highlights on reflective surfaces, which is a key technique in professional product photography. The length of the light object affects how the shadows are cast.

### Practical Use Cases
* **Use Case 1 (Studio Rendering):** You are setting up a render for a ring and want to create soft, broad highlights that mimic the large softbox lights used in a photography studio. You can place one or two `LinearLight` objects above and to the side of the ring to achieve this effect.
* **Use Case 2 (Illuminating a Channel):** You want to create a render that emphasizes a channel of gemstones. You can place a `LinearLight` directly above and parallel to the channel to create a long, continuous highlight that makes the stones pop.

### Other Information
This is one of the standard light types used for creating realistic rendering setups.

---

## 352. Lines

### Short Info
Draw a series of connected line segments.

### Detailed Description
The **Lines** command is a 2D drawing tool that creates a polyline object, which is a single curve made up of multiple connected straight-line segments. Unlike the `Line` command which creates a single segment, `Lines` allows you to continue clicking to create a chain of segments.

### Steps to use the command
1.  Run the command `Lines`.
2.  At the **Start of line** prompt, pick a point.
3.  Continue picking points to create the vertices of the polyline.
4.  Press Enter when you are finished.

### Command Options & Toggles
* **Close:** Closes the polyline by creating a final segment from the last point back to the first point.

### Note for better use
The `Polyline` command is a more versatile and modern version of this command, as it allows you to switch between drawing straight line segments and arc segments within the same command run. For most new work, `Polyline` is the preferred tool.

### Practical Use Cases
* **Use Case 1 (Creating Faceted Outlines):** You are drawing the outline of a princess-cut or emerald-cut gemstone. The `Lines` command is perfect for creating this type of geometric shape made of connected straight lines.
* **Use Case 2 (Quick Tracing):** You are doing a quick, rough trace of a sketch to block out the basic shape. The `Lines` command allows you to quickly create a multi-segmented outline.

### Other Information
This is a basic 2D drawing tool, largely superseded by the more flexible `Polyline` command.

---

## 353. LineThroughPt

### Short Info
Create the best-fit line through points.

### Detailed Description
The **LineThroughPt** (Line Through Points) command is a construction tool that creates a single straight line that represents the "best fit" through a selection of two or more point objects. This is useful for finding the central axis or average direction of a set of points.

### Steps to use the command
1.  Select two or more point objects.
2.  Run the command `LineThroughPt`.
3.  A new line will be created that passes through the points.

### Command Options & Toggles
This command has no options.

### Note for better use
If you select only two points, the command will create a line that passes directly through them. If you select more than two, the command performs a linear regression to find the line that has the smallest average distance to all the points.

### Practical Use Cases
* **Use Case 1 (Finding an Axis):** You have imported a 3D scan of a ring shank that is slightly crooked. You can place several point objects along the center of the shank and then use `LineThroughPt` to find the true central axis of the shank. You can then use this new line to re-orient the shank so it is perfectly straight.
* **Use Case 2 (Aligning Stones):** You have placed several gemstones in a slightly irregular line and want to create a perfectly straight channel for them. You can place a point at the center of each stone, use `LineThroughPt` to find the average line, and then use this line as a guide to perfectly align the stones.

### Other Information
This is a powerful tool for reverse-engineering and for finding the underlying structure in imprecise geometry.

---

## 354. LinetypeDisplay

### Short Info
Toggle linetype display in the viewports.

### Detailed Description
The **LinetypeDisplay** command is a global display toggle. It controls whether curves in the model are displayed with their assigned linetype (e.g., dashed, dotted, center-line) or as simple solid lines in the viewports.

### Steps to use the command
1.  Run the command `LinetypeDisplay`.
2.  The command line will show the current state (On or Off).
3.  Click the option to toggle it.

### Command Options & Toggles
This command is a simple toggle between **On** and **Off**.

### Note for better use
This is a display setting only and does not affect how the lines will print. The printing of linetypes is controlled by the settings in the Print dialog box. Turning this off can sometimes improve viewport performance in very complex 2D drawings.

### Practical Use Cases
* **Use Case 1 (Drafting):** You are creating a technical drawing and have assigned a "centerline" linetype to your construction curves. Turning `LinetypeDisplay` on allows you to see this linetype directly in the viewport as you work, confirming that you have assigned the correct properties.

### Other Information
This is a simple display toggle for 2D drafting purposes.

---

## 355. List

### Short Info
Report object properties details.

### Detailed Description
The **List** command is a diagnostic tool that displays detailed technical information about a selected object in the command history window. This includes information about the object's type, layer, render material, and geometric properties like its control points and knot vectors.

### Steps to use the command
1.  Select an object.
2.  Run the command `List`.
3.  Detailed information about the object will be printed in the command history.

### Command Options & Toggles
This command has no options.

### Note for better use
This command provides more in-depth technical data than the standard Properties panel. It is primarily used by advanced users and script writers who need to understand the underlying data structure of an object.

### Practical Use Cases
* **Use Case 1 (Advanced Troubleshooting):** A surface is behaving unexpectedly. A power user can use the `List` command to examine the surface's knot vector and control point structure to diagnose the problem at a mathematical level.

### Other Information
For most users, the standard Properties panel (`Properties` command) provides all the necessary information about an object in a more user-friendly format.

---

## 356. LoadScript

### Short Info
Load a script file.

### Detailed Description
The **LoadScript** command is a utility for scripters. It loads a script file (like a .rvb or .py file) into Rhino's memory so that the functions and aliases defined within that script become available to be run from the command line.

### Steps to use the command
1.  Run the command `LoadScript`.
2.  A file browser will open.
3.  Select the script file you want to load.

### Command Options & Toggles
This command has no options.

### Note for better use
This command only loads the script for the current Rhino session. To have a script load automatically every time Rhino starts, you must add it to the list of startup scripts in the Rhino Options.

### Practical Use Cases
* **Use Case 1 (Testing a Script):** A developer has just written a new script. They can use `LoadScript` to load it into Rhino and then test its functions from the command line without having to restart the program.

### Other Information
This is a utility for developers and advanced users who work with custom scripts.

---

## 357. Lock

### Short Info
Lock objects.

### Detailed Description
The **Lock** command is a fundamental organizational and safety tool. It "locks" selected objects, which prevents them from being selected or modified with the mouse. Locked objects are still visible (they appear in a different color, which can be set in the options), and you can still snap to them, but you cannot accidentally move, edit, or delete them.

### Steps to use the command
1.  Select the object(s) you want to lock.
2.  Run the command `Lock`.
3.  The objects will become locked.

### Command Options & Toggles
This command has no options.

### Note for better use
The command to unlock objects is `Unlock`. The command `LockSwap` will lock all unlocked objects and unlock all locked objects, which is a very fast way to switch between editing two different sets of objects.

### Practical Use Cases
* **Use Case 1 (Protecting Reference Geometry):** You have imported a client's gemstone model and are building a bezel around it. To prevent yourself from accidentally moving the gemstone, you can select it and `Lock` it. You can still snap to its edges to build your bezel, but you cannot accidentally move it out of position.
* **Use Case 2 (Isolating Work):** You are working on the prongs of a setting and don't want to accidentally select the shank or the gem. You can lock the shank and the gem, allowing you to freely select and edit only the prongs.

### Other Information
This is an essential command for maintaining an organized and error-free workflow in complex models.

---

## 358. LockSwap

### Short Info
Lock all unlocked objects and unlock all locked objects.

### Detailed Description
The **LockSwap** command is a display management utility that inverts the locked state of all objects in the model. All objects that are currently unlocked will become locked, and all objects that are currently locked will become unlocked.

### Steps to use the command
1.  Run the command `LockSwap`.
2.  The locked/unlocked state of all objects will be inverted.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Alternating Edits):** You are working on a complex ring and have locked the main shank to work on the prongs. Now you need to edit the shank. Instead of unlocking the shank and then locking all the prongs, you can simply run `LockSwap`. This will instantly lock the prongs and unlock the shank, allowing you to immediately start editing it.

### Other Information
This is a very fast and efficient way to toggle between editing two different sets of objects.

---

## 359. Loft

### Short Info
Fit a surface through profile curves that define the surface shape.

### Detailed Description
The **Loft** command is a fundamental and powerful surface creation tool. It creates a smooth NURBS surface that is fitted through a series of selected "profile" or "cross-section" curves. This is one of the primary methods for creating complex, free-form shapes.

### Steps to use the command
1.  Draw two or more profile curves.
2.  Run the command `Loft`.
3.  At the **Select curves to loft** prompt, select the profile curves in the order you want the surface to pass through them.
4.  Press Enter. A dialog box will appear with options for controlling the surface.
5.  Adjust the options and click OK to create the surface.

### Command Options & Toggles
The options are in the dialog box:
* **Style (Normal, Loose, Tight, Straight sections):** Controls how closely the surface fits to the profile curves. `Normal` is the standard. `Straight sections` creates a faceted, polyhedral surface.
* **Closed:** Creates a closed surface that loops back to the first curve.
* **Align curves:** Allows you to adjust the seam points of the curves to prevent the surface from twisting.
* **Rebuild with X control points:** Rebuilds the surface with a specified number of control points for a cleaner, simpler result.

### Note for better use
The order in which you select the curves is critical. You must select them in the sequence that you want the surface to follow. The direction of the curves is also important; if the resulting surface is twisted, it is likely because the direction of one of your profile curves is opposite to the others. Use the `Dir` command to check and align them.

### Practical Use Cases
* **Use Case 1 (Creating a Ring Shank):** This is a classic use. You can create three circular profile curves: one for the bottom of the shank, one for the shoulders, and one for the top. By using `Loft` through these three profiles, you can create a basic, tapered ring shank.
* **Use Case 2 (Organic Pendants):** You are designing a free-form, organic pendant. You can draw a series of different-shaped cross-section curves at different heights and then use `Loft` to create a smooth, flowing surface that blends between all of them.

### Other Information
Mastering the `Loft` command, especially its options for aligning seams and rebuilding, is an essential skill for any NURBS modeler.


---

## 360. MacroEditor

### Short Info
Open the macro editor.

### Detailed Description
The **MacroEditor** command is a utility that opens a simple text editor window inside Rhino. This editor is used for writing and editing command macros. A macro is a sequence of Rhino commands that can be saved to a button to automate a repetitive task.

### Steps to use the command
1.  Run the command `MacroEditor`.
2.  The Macro Editor window will appear, allowing you to type and test command sequences.

### Command Options & Toggles
This command has no options. The functionality is within the editor window itself.

### Note for better use
This editor is for simple, multi-command macros. For more complex automation involving logic and variables, it is better to use the `EditPythonScript` or `EditScript` commands to open the full scripting editors.

### Practical Use Cases
* **Use Case 1 (Creating a Custom Tool):** You frequently need to create a 1mm pipe, turn on its control points, and then select the points. You could use the `MacroEditor` to write the macro `! _Pipe 1 _Enter _SelLast _PointsOn _SelPt`, and then save this macro to a custom button. Now, one click runs all four commands in sequence.

### Other Information
This is a key tool for customizing the Rhino interface and automating simple, repetitive workflows.

---

## 361. Maelstrom

### Short Info
Deform objects in a spiral.

### Detailed Description
The **Maelstrom** command is a deformation tool that deforms objects by twisting them in a spiral pattern around a central axis. It is similar to the `Twist` command but creates a more complex, swirling deformation.

### Steps to use the command
1.  Select the object(s) to deform.
2.  Run the command `Maelstrom`.
3.  You will be prompted to define the axis of the spiral.
4.  You will then be prompted to define the amount and direction of the deformation.

### Command Options & Toggles
This command has no clickable options. The deformation is controlled by the points you pick.

### Note for better use
This is a very specialized, free-form modeling tool. The results can be unpredictable, and it is often used for creating abstract, sculptural shapes rather than precise mechanical parts.

### Practical Use Cases
* **Use Case 1 (Abstract Pendants):** You have a simple, solid bar and want to turn it into an abstract, swirling pendant. The `Maelstrom` command can be used to apply a chaotic, spiral twist to the bar, creating an interesting and unique organic form.

### Other Information
This is an artistic deformation tool for creating non-traditional shapes.

---

## 362. Make2D

### Short Info
Project geometry to the construction plane.

### Detailed Description
The **Make2D** command is a fundamental drafting and documentation tool. It takes selected 3D objects and creates a flat, 2D line drawing of them from the point of view of the active viewport. This is the primary method for creating traditional 2D technical drawings (top, front, side views) from your 3D models.

### Steps to use the command
1.  Arrange your 3D model in the desired view (e.g., the Front view).
2.  Select the object(s) you want to create a drawing of.
3.  Run the command `Make2D`.
4.  A dialog box will appear with options for the drawing.
5.  Click OK. A new set of 2D curves will be created on the Top view's construction plane.

### Command Options & Toggles
The options are in a dialog box:
* **Projection:** Sets the view to use for the drawing.
* **Object Properties:** Controls how the output curves are organized (e.g., by layer, maintaining source layers).
* **Show hidden lines:** Creates dashed lines to represent the edges that are hidden from the camera.
* **Show tangent edges:** Creates lines at the tangent edges of curved surfaces.

### Note for better use
The 2D drawing is created on the world XY plane, so it's best viewed from the Top viewport. The resulting curves are separate from the original 3D model and can be moved, edited, and dimensioned on a Layout page.

### Practical Use Cases
* **Use Case 1 (Creating Technical Drawings):** This is the command's primary purpose. To create a standard three-view drawing of a ring, you would run `Make2D` once from the Top view, once from the Front view, and once from the Right view. You can then arrange these three 2D line drawings on a Layout page and add dimensions.
* **Use Case 2 (Extracting Profiles):** You need a flat, 2D outline of a complex 3D object. You can position the object in the desired view and use `Make2D` to instantly generate this outline as a clean curve.

### Other Information
This is an essential command for bridging the gap between 3D modeling and 2D documentation.

---

## 363. MakeHole

### Short Info
Project a closed curve to a surface to make a hole.

### Detailed Description
The **MakeHole** command is a specialized trimming tool. It takes one or more closed, planar curves and projects them onto a surface or polysurface to create a hole. It is a faster alternative to using `Project` and then `Trim`.

### Steps to use the command
1.  Select the closed curve(s) that will define the shape of the hole.
2.  Run the command `MakeHole`.
3.  At the **Select surface or polysurface to make hole in** prompt, select the object to be cut.
4.  A hole will be created.

### Command Options & Toggles
This command has no options.

### Note for better use
The command projects the curves in the direction of the active view's CPlane normal. Make sure you are in the correct viewport (e.g., Top view) before running the command to ensure the hole is projected in the right direction.

### Practical Use Cases
* **Use Case 1 (Perforating a Surface):** You have designed a flat pendant and have drawn several small, decorative circles on top of it. You can select all the circles, run `MakeHole`, and select the pendant to cut all the holes in a single operation.
* **Use Case 2 (Creating a Bezel Seat):** You have a flat-topped bezel and have drawn a circle representing the inside edge. `MakeHole` can be used to quickly cut the main opening for the gemstone.

### Other Information
This is a workflow-efficiency command that combines projection and trimming into one step.

---

## 364. MakeNonPeriodic

### Short Info
Add a kink at the start/end of a curve or surface.

### Detailed Description
The **MakeNonPeriodic** command is a technical editing tool that modifies the structure of a closed curve or surface. It adds a "kink" or sharp corner at the seam (the start/end point) of the object. This is done by stacking multiple control points at the seam location.

### Steps to use the command
1.  Select a closed, periodic (smooth) curve or surface.
2.  Run the command `MakeNonPeriodic`.
3.  A kink will be added at the object's seam.

### Command Options & Toggles
This command has no options.

### Note for better use
A "periodic" curve is a smooth, closed curve with no sharp corners. A "non-periodic" curve is a closed curve that has a sharp corner at its seam. Some commands or export formats require non-periodic curves. The opposite command is `MakePeriodic`.

### Practical Use Cases
* **Use Case 1 (Export Compatibility):** You are exporting a circular curve to a file format that does not support smooth, periodic curves. You would use `MakeNonPeriodic` to convert the circle into a non-periodic curve with a kink before exporting to ensure it translates correctly.

### Other Information
This is an advanced tool for controlling the underlying mathematical structure of an object.

---

## 365. MakePeriodic

### Short Info
Remove the kink from the start/end of a curve or surface.

### Detailed Description
The **MakePeriodic** command is a technical editing tool that modifies the structure of a closed curve or surface. It removes the "kink" or sharp corner from the seam of a non-periodic object, making it a smooth, continuous, periodic object.

### Steps to use the command
1.  Select a closed, non-periodic (kinked) curve or surface.
2.  Run the command `MakePeriodic`.
3.  The kink at the seam will be removed, and the object will become smooth.

### Command Options & Toggles
This command has no options.

### Note for better use
This command can change the shape of the object, as it has to adjust the control points to create the smooth transition. The opposite command is `MakeNonPeriodic`.

### Practical Use Cases
* **Use Case 1 (Smoothing a Profile):** You have created a closed profile curve for a ring by joining several segments, which has resulted in a sharp corner at the join. If you want this profile to be perfectly smooth all the way around, you can use `MakePeriodic` to remove the kink.

### Other Information
This is an advanced tool for controlling the underlying mathematical structure of an object.

---

## 366. MakeUniform

### Short Info
Make the knot vector of a curve or surface uniform.

### Detailed Description
The **MakeUniform** command is an advanced editing tool that modifies the internal mathematical structure of a NURBS curve or surface. It re-spaces the "knots" of the object so that they are perfectly uniform (evenly spaced). This can simplify the object's structure and make it behave more predictably with certain commands, but it will also slightly change the object's shape.

### Steps to use the command
1.  Select a curve or surface.
2.  Run the command `MakeUniform`.
3.  The object's knot vector will be made uniform.

### Command Options & Toggles
This command has no options.

### Note for better use
This is an advanced command that should be used with caution, as it will alter the shape of your geometry. For most general simplification or smoothing tasks, the `Rebuild` command is a better and more intuitive choice.

### Practical Use Cases
* **Use Case 1 (Advanced Surfacing):** A designer is creating a "Class-A" surface and needs to ensure that the parameterization of a surface is as clean and simple as possible for analysis. `MakeUniform` is one of the tools they might use to simplify the surface's internal structure.

### Other Information
This is a tool for advanced users who need to directly manipulate the mathematical properties of NURBS objects.

---

## 367. MakeUniformUV

### Short Info
Make the knot vector of a surface uniform in one direction.

### Detailed Description
The **MakeUniformUV** command is a more controlled version of `MakeUniform` that works only on surfaces. It allows you to make the knot vector uniform in only the U direction, only the V direction, or both.

### Steps to use the command
1.  Select a surface.
2.  Run the command `MakeUniformUV`.
3.  The command line will prompt you to choose a direction.
4.  Select U, V, or Both.

### Command Options & Toggles
* **Direction (U/V/Both):** Specifies the direction(s) to make uniform.

### Practical Use Cases
* **Use Case 1 (Advanced Surfacing):** Similar to `MakeUniform`, this is used by advanced modelers to clean up the internal structure of a surface, but with more precise control over which direction is being modified.

### Other Information
This is a tool for advanced users who need to directly manipulate the mathematical properties of NURBS surfaces.

---

## 368. MappingWidgetOff

### Short Info
Turn off the texture mapping widget.

### Detailed Description
The **MappingWidgetOff** command turns off the visibility of texture mapping widgets. Mapping widgets are the wireframe guides (shaped like a box, sphere, or cylinder) that are created when you use commands like `ApplyBoxMapping`. This command hides those guides from view.

### Steps to use the command
1.  Run the command `MappingWidgetOff`.
2.  All visible mapping widgets will be hidden.

### Command Options & Toggles
This command has no options.

### Note for better use
The companion command is `MappingWidget`, which turns the widgets on.

### Practical Use Cases
* **Use Case 1 (De-cluttering the View):** You have applied texture mapping to several objects, and the view is now cluttered with the wireframe mapping widgets. `MappingWidgetOff` will hide them all at once, giving you a clearer view of your model.

### Other Information
This is a simple display management command for rendering workflows.

---

## 369. MappingWidget

### Short Info
Turn on the texture mapping widget.

### Detailed Description
The **MappingWidget** command turns on the visibility of the texture mapping widget for a selected object. This allows you to see the wireframe guide (box, sphere, etc.) and manipulate it with commands like `Move`, `Scale`, and `Rotate` to adjust how the texture is applied to the object.

### Steps to use the command
1.  Select an object that has texture mapping applied.
2.  Run the command `MappingWidget`.
3.  The mapping widget for that object will become visible.

### Command Options & Toggles
This command has no options.

### Note for better use
The companion command is `MappingWidgetOff`.

### Practical Use Cases
* **Use Case 1 (Adjusting a Texture):** You have applied a wood grain texture to a box using `ApplyBoxMapping`, but the grain is running in the wrong direction. You can use `MappingWidget` to turn on the box widget, and then use the `Rotate` command on the widget itself to change the orientation of the texture on the model.

### Other Information
This is a key command for editing and fine-tuning texture map placement.

---

## 370. MarkFoci

### Short Info
Place point objects at the focal points of conic curves.

### Detailed Description
The **MarkFoci** command is an analysis tool that finds the focal points (foci) of conic curves (ellipses, hyperbolas, parabolas) and places point objects at their locations.

### Steps to use the command
1.  Select one or more conic curves.
2.  Run the command `MarkFoci`.
3.  Point objects will be created at the focal points.

### Command Options & Toggles
This command has no options.

### Note for better use
This command only works on true conic section curves.

### Practical Use Cases
* **Use Case 1 (Optical Design):** An engineer designing a reflector would use this command to find the exact focal point of a parabolic curve, which is the location where all reflected rays will converge. This command has very limited use in jewelry design.

### Other Information
This is a specialized geometric analysis tool.

---

## 371. Match

### Short Info
Change a curve end to meet another curve or surface edge with specified continuity.

### Detailed Description
The **Match** command is a powerful curve editing tool that adjusts the end of a curve to smoothly meet another curve or a surface edge. It provides options to control the level of smoothness (continuity) of the connection, allowing you to create perfect G0 (Position), G1 (Tangency), or G2 (Curvature) connections.

### Steps to use the command
1.  Run the command `Match`.
2.  At the **Select curve to change** prompt, click near the end of the curve you want to edit.
3.  At the **Select curve to match** prompt, click near the end of the target curve.
4.  A dialog box will appear with options to control the continuity.
5.  Click OK to modify the curve.

### Command Options & Toggles
The options are in a dialog box:
* **Continuity (Position/Tangency/Curvature):** Sets the level of smoothness for the connection.
* **Preserve other end:** Prevents the start of the curve from changing shape while the end is being matched.
* **Average curves:** Modifies both curves to meet in the middle.

### Note for better use
This command permanently changes the shape of the curve. For creating high-quality, flowing surfaces, matching your input curves for at least Tangency, and preferably Curvature, is a critical step.

### Practical Use Cases
* **Use Case 1 (Preparing for a Sweep):** You have a profile curve and a rail curve for a `Sweep1`. To ensure the sweep starts smoothly, you can use `Match` to force the start of the rail curve to be perfectly tangent to the profile curve.
* **Use Case 2 (Creating Smooth Outlines):** You have drawn two separate curves that form the outline of a pendant, and you want the connection between them to be perfectly smooth. `Match` with the "Curvature" option will adjust the curves to create a seamless G2 transition.

### Other Information
The 3D equivalent for surfaces is the `MatchSrf` command.

---

## 372. MatchCrvDir

### Short Info
Change a curve's direction to match another curve's direction.

### Detailed Description
The **MatchCrvDir** (Match Curve Direction) command is a utility that changes the direction of one curve to match the direction of another curve. This is a quick way to ensure that multiple curves are all pointing in the same direction, which is often a requirement for surfacing commands like `Loft` and `Sweep`.

### Steps to use the command
1.  Run the command `MatchCrvDir`.
2.  At the **Select curve to change direction** prompt, select the curve you want to flip.
3.  At the **Select curve with direction to match** prompt, select the guide curve.
4.  The first curve's direction will be flipped if necessary to match the second.

### Command Options & Toggles
This command has no options.

### Note for better use
This is faster than using the `Dir` command on each curve individually to check and flip them.

### Practical Use Cases
* **Use Case 1 (Preparing for a Loft):** You are about to `Loft` three profile curves to create a ring shank. To prevent the surface from twisting, all three curves must have the same direction. You can select the first curve as your target, and then use `MatchCrvDir` to quickly make sure the other two curves are pointing in the same direction.

### Other Information
This is a simple but very important workflow utility for surfacing.

---

## 373. MatchLayer

### Short Info
Change an object's layer to match another object's layer.

### Detailed Description
The **MatchLayer** command is an organizational tool that changes the layer of one or more selected objects to match the layer of a target object that you specify.

### Steps to use the command
1.  Select the object(s) you want to move to a new layer.
2.  Run the command `MatchLayer`.
3.  At the **Select object on destination layer** prompt, click on an object that is on the layer you want to move to.
4.  The originally selected objects will be moved to that layer.

### Command Options & Toggles
This command has no options.

### Note for better use
This is often faster than using the `ChangeLayer` command, as you don't need to find and select the layer from a list; you can just click on any object that is already on the correct layer.

### Practical Use Cases
* **Use Case 1 (Quick Organization):** You have created a new prong for a setting, and it was created on the default layer. Your other prongs are already on the "Prongs" layer. You can select the new prong, run `MatchLayer`, and then click on one of the old prongs. The new prong will instantly be moved to the "Prongs" layer.

### Other Information
This is a very efficient tool for layer management.

---

## 374. MatchMapping

### Short Info
Match the texture mapping of one object to another.

### Detailed Description
The **MatchMapping** command is a utility that copies the texture mapping properties from one object to another. This is a very fast way to apply the same texture mapping (e.g., the same box mapping widget and its orientation) to multiple objects.

### Steps to use the command
1.  Select the object(s) that you want to apply the mapping to.
2.  Run the command `MatchMapping`.
3.  At the **Select object with mapping to copy** prompt, select the source object that has the correct mapping.
4.  The mapping properties will be copied to the object(s) you originally selected.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Texturing a Pair of Earrings):** You have a pair of earrings. You have spent time carefully applying and adjusting a complex texture map to the first earring. To apply the exact same mapping to the second earring, you can simply select the second earring, run `MatchMapping`, and then click on the first earring.

### Other Information
This is a time-saving utility for rendering workflows.

---

## 375. MatchMeshEdge

### Short Info
Move the open edges of a mesh to meet the edges of an adjacent mesh.

### Detailed Description
The **MatchMeshEdge** command is a mesh editing tool that moves the vertices on a naked (open) edge of one mesh to the corresponding locations of the vertices on a naked edge of another mesh. This is used to make the edges of two separate mesh objects line up perfectly so they can be joined.

### Steps to use the command
1.  Select a mesh object with a naked edge.
2.  Run the command `MatchMeshEdge`.
3.  At the **Select mesh edge to change** prompt, select the naked edge you want to move.
4.  At the **Select mesh edge to match** prompt, select the target naked edge on the other mesh.
5.  The vertices of the first edge will snap to the positions of the second edge's vertices.

### Command Options & Toggles
* **DistanceToAdjust:** Controls how far the vertices are allowed to move.

### Practical Use Cases
* **Use Case 1 (Joining Mesh Parts):** You have two halves of a ring that were modeled as separate mesh objects, and there is a small, inconsistent gap between them. `MatchMeshEdge` can be used to force the edges of one half to snap to the edges of the other. After matching, you can use the `Join` command, followed by the `Weld` command, to stitch the two halves into a single, watertight mesh.

### Other Information
This is an important tool for assembling and repairing models that are made of multiple mesh parts.

---

## 376. MatchProperties

### Short Info
Change the properties of an object to match another object.

### Detailed Description
The **MatchProperties** command is a powerful utility that copies various properties from one object to another. This can include properties like layer, display color, print color, print width, and material assignment.

### Steps to use the command
1.  Select the object(s) you want to change.
2.  Run the command `MatchProperties`.
3.  At the **Select object to match properties from** prompt, select the source object.
4.  A dialog box will appear, allowing you to choose which specific properties you want to copy.
5.  Click OK. The selected properties will be applied to the destination object(s).

### Command Options & Toggles
The options are the checkboxes in the dialog box, allowing you to select which properties to match (e.g., Color, Layer, Linetype, Material, etc.).

### Practical Use Cases
* **Use Case 1 (Standardizing a Drawing):** You have a complex drawing with objects on many different layers and with different colors. You want to make a group of objects match the properties of a "master" object. You can select the group, run `MatchProperties`, select the master object, and then choose to match the Layer and Color properties.
* **Use Case 2 (Applying Materials):** You have assigned a complex "18k Yellow Gold" material to one part of your model. To quickly apply the exact same material to ten other parts, you can select the ten parts, run `MatchProperties`, select the first part as the source, and make sure only the "Material" checkbox is ticked.

### Other Information
This is a very efficient command for managing object properties and maintaining consistency in a model.

---

## 377. MatchSrf

### Short Info
Adjust a surface edge to have continuity with another surface.

### Detailed Description
The **MatchSrf** (Match Surface) command is one of the most important tools for creating high-quality, "Class-A" surfaces. It adjusts the edge of one surface to smoothly and continuously meet the edge of another. It provides precise control over the level of continuity (Position, Tangency, or Curvature), ensuring a seamless transition between the two surfaces.

### Steps to use the command
1.  Run the command `MatchSrf`.
2.  At the **Select edge of surface to change** prompt, select the edge of the surface you want to edit.
3.  At the **Select target edge** prompt, select the edge on the other surface that you want to match to.
4.  A dialog box will appear with options to control the continuity.
5.  Click OK to modify the surface.

### Command Options & Toggles
The options are in the dialog box:
* **Continuity (Position/Tangency/Curvature):** Sets the level of smoothness for the connection.
* **Preserve other end:** Prevents the opposite side of the surface from changing shape.
* **Average surfaces:** Modifies both surfaces to meet in the middle.

### Note for better use
Achieving G2 (Curvature) continuity is the goal for creating professional, high-quality models that will have perfectly smooth reflections across seams. After matching surfaces, you can use the `Zebra` or `EMap` commands to visually verify the quality of the connection.

### Practical Use Cases
* **Use Case 1 (Creating a Seamless Shank):** You have modeled the two halves of a ring shank as separate surfaces. To ensure the seam where they join at the top and bottom is perfectly invisible, you must use `MatchSrf` with Curvature continuity on both halves before you `Join` them.
* **Use Case 2 (Blending a Head to a Shank):** You have a setting and a shank that meet. To create a perfectly smooth, flowing transition between them, you would use `MatchSrf` to make the edge of the shank curvature-continuous with the edge of the setting.

### Other Information
Mastering `MatchSrf` is a critical skill for any advanced NURBS surface modeler.

---

## 378. MaterialEditor

### Short Info
Open the Material Editor panel.

### Detailed Description
The **MaterialEditor** command opens a panel that is the central hub for creating, editing, and managing the render materials in your model. A material defines the appearance of an object's surface in a render, including its color, reflectivity, texture, and transparency.

### Steps to use the command
1.  Run the command `MaterialEditor`.
2.  The Material Editor panel will open.
3.  You can right-click to create new materials, or select an existing material to edit its properties (color, texture maps, etc.).

### Command Options & Toggles
All options are contained within the panel's interface.

### Note for better use
You can assign materials to objects by dragging them from the Material Editor onto the object in the viewport, or by selecting an object and assigning the material in the Properties panel.

### Practical Use Cases
* **Use Case 1 (Creating a Gold Material):** You are preparing a ring for rendering. You open the `MaterialEditor`, create a new material, name it "18k Yellow Gold," and then adjust its color, reflectivity, and polish settings to create a realistic gold appearance.
* **Use Case 2 (Applying a Gemstone Material):** You would use the Material Editor to create a "Diamond" material, where you would set the color to white, increase the transparency, and set the correct Index of Refraction (IOR) to make it look like a real diamond in the render.

### Other Information
This is a fundamental panel for all rendering workflows.

---

## 379. Maximize

### Short Info
Maximize the Rhino window.

### Detailed Description
The **Maximize** command maximizes the main Rhino application window to fill the entire screen.

### Steps to use the command
1.  Run the command `Maximize`.
2.  The Rhino window will maximize.

### Command Options & Toggles
This command has no options.

### Note for better use
This is equivalent to clicking the "Maximize" button in the top-right corner of the Rhino window.

### Practical Use Cases
* **Use Case 1 (Workspace Management):** You are working with multiple programs and have resized your Rhino window. This command quickly expands it back to fill the screen.

### Other Information
This is a simple window management command.

---

## 380. MaxViewport

### Short Info
Maximize the active viewport.

### Detailed Description
The **MaxViewport** (Maximize Viewport) command maximizes the currently active viewport to fill the entire application window. This is used to focus on a single view (e.g., the Perspective view) for detailed modeling.

### Steps to use the command
1.  Make a viewport active by clicking in it.
2.  Run the command `MaxViewport`.
3.  The viewport will expand to fill the screen.

### Command Options & Toggles
This command has no options.

### Note for better use
Double-clicking on a viewport's title is a much faster shortcut for this command. Double-clicking again will restore the previous multi-viewport layout.

### Practical Use Cases
* **Use Case 1 (Detailed 3D Work):** You are doing fine-detail sculpting on a model and need the largest possible view. You can activate the Perspective viewport and run `MaxViewport` to give yourself the maximum amount of screen space to work with.
* **Use Case 2 (2D Tracing):** You are tracing a complex image in the Top view. You can maximize the Top view to make the tracing process easier and more accurate.

### Other Information
This is one of the most frequently used viewport management commands, although it is almost always activated by the double-click shortcut.

---

## 381. Merge2MeshFaces

### Short Info
Merge two triangular mesh faces into one quadrangular mesh face.

### Detailed Description
The **Merge2MeshFaces** command is a low-level mesh editing tool that combines two adjacent triangular mesh faces into a single quadrangular (four-sided) face. This is a key tool for "quadrangulating" a mesh, which is the process of converting a mesh made of triangles into one made primarily of quads. Quad-based meshes are often cleaner and easier to work with in subdivision modeling and sculpting programs.

### Steps to use the command
1.  Run the command `Merge2MeshFaces`.
2.  At the **Select first mesh face** prompt, click on a triangular face.
3.  At the **Select second mesh face to merge** prompt, click on an adjacent triangular face that shares an edge with the first.
4.  The two triangles will be merged into a single quad.

### Command Options & Toggles
This command has no options.

### Note for better use
This command only works on two triangles that share a common edge. It is a manual tool for cleaning up mesh topology. For an automated approach, use the `QuadrangulateMesh` command.

### Practical Use Cases
* **Use Case 1 (Preparing for Subdivision Modeling):** You have an STL file (which is always made of triangles) that you want to import into a subdivision modeling program like ZBrush or Blender for sculpting. To get the best results, you would first try to convert as much of the mesh to quads as possible. `Merge2MeshFaces` allows you to do this manually in specific, critical areas to control the flow of the polygons.

### Other Information
This is an advanced tool for users who are doing detailed mesh topology work.

---

## 382. MergeAllEdges

### Short Info
Merge all possible edges of a single surface.

### Detailed Description
The **MergeAllEdges** command is a surface repair and simplification tool. It inspects a single, un-trimmed surface and attempts to merge any interior edges that are co-linear. This can simplify the surface structure by removing unnecessary breaks.

### Steps to use the command
1.  Select a single surface.
2.  Run the command `MergeAllEdges`.
3.  If possible, interior edges will be merged.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is for single surfaces, not polysurfaces. To merge the faces of a polysurface, use `MergeAllFaces`. This command is most effective on surfaces that have been created by joining simpler, rectangular surfaces together.

### Practical Use Cases
* **Use Case 1 (Cleaning Imported Geometry):** You import a surface from another CAD program, and it is made up of several smaller, co-linear patches. `MergeAllEdges` can sometimes be used to combine these patches into a single, cleaner surface with a simpler structure.

### Other Information
This is a specialized surface cleanup utility.

---

## 383. MergeAllFaces

### Short Info
Merge all possible faces of a polysurface.

### Detailed Description
The **MergeAllFaces** command is a polysurface simplification tool. It inspects a selected polysurface and merges any adjacent faces that are co-planar (lie on the same flat plane). This is a very useful command for cleaning up models, especially after boolean operations or importing files, by removing unnecessary edges from flat areas.

### Steps to use the command
1.  Select a polysurface.
2.  Run the command `MergeAllFaces`.
3.  All co-planar faces on the object will be merged into single faces.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a safe command to run and is good practice for cleaning up models. It simplifies the geometry without changing its shape. The single-face equivalent is `MergeFace`.

### Practical Use Cases
* **Use Case 1 (Cleaning a Signet Ring):** You have created a signet ring by booleaning several box and cylinder shapes together. The flat top surface is now made up of several separate, co-planar faces. Running `MergeAllFaces` will combine them all into a single, clean top surface.
* **Use Case 2 (Simplifying Imported Files):** You import a STEP file, and many of the flat surfaces are broken up into multiple faces. `MergeAllFaces` is the best tool to quickly clean this up and simplify the model.

### Other Information
This is a fundamental command for model cleanup and simplification.

---

## 384. MergeEdge

### Short Info
Merge two edges of the same surface.

### Detailed Description
The **MergeEdge** command is a surface editing tool that merges two adjacent edges on the same surface. This is a manual, single-edge version of the `MergeAllEdges` command.

### Steps to use the command
1.  Run the command `MergeEdge`.
2.  At the **Select edge on surface to merge** prompt, select the first edge.
3.  At the **Select another edge on the same surface to merge** prompt, select an adjacent edge.
4.  The two edges will be merged.

### Command Options & Toggles
This command has no options.

### Note for better use
Both edges must belong to the same surface.

### Practical Use Cases
* **Use Case 1 (Precision Cleanup):** You have a surface where you only want to merge two specific co-linear edges, but leave other co-linear edges on the same surface separate. `MergeEdge` gives you this precise, manual control.

### Other Information
This is a specialized surface cleanup utility for manual control.

---

## 385. MergeFace

### Short Info
Merge two faces of a polysurface.

### Detailed Description
The **MergeFace** command is a polysurface editing tool that merges two adjacent, co-planar faces into a single face. This is the manual, two-face version of the `MergeAllFaces` command.

### Steps to use the command
1.  Run the command `MergeFace`.
2.  At the **Select a face to merge** prompt, select the first face.
3.  At the **Select a second face to merge** prompt, select an adjacent, co-planar face.
4.  The two faces will be merged.

### Command Options & Toggles
This command has no options.

### Note for better use
The two faces must be co-planar for the command to work.

### Practical Use Cases
* **Use Case 1 (Targeted Cleanup):** You have a model where you want to merge two specific co-planar faces, but you want to leave other co-planar faces on the object separate for a specific reason (e.g., for texture mapping). `MergeFace` allows you to perform this targeted merge without affecting the rest of the object.

### Other Information
This is a specialized polysurface cleanup utility for manual control.

---

## 386. MergeSrf

### Short Info
Merge two surfaces.

### Detailed Description
The **MergeSrf** (Merge Surface) command combines two separate surfaces into a single surface. This command only works along un-trimmed edges, and the surfaces must be perfectly aligned and have the same direction.

### Steps to use the command
1.  Run the command `MergeSrf`.
2.  At the **Select surface to merge** prompt, select the first surface near the edge to be merged.
3.  At the **Select surface to merge with** prompt, select the second surface near the shared edge.
4.  The two surfaces will be merged into one.

### Command Options & Toggles
* **Smooth (Yes/No):**
    * **Yes:** Adjusts the control points to make the seam between the surfaces smooth (tangent). This will change the shape of the surface.
    * **No:** Merges the surfaces without changing their shape, which may leave a crease at the seam.
* **Tolerance:** Sets the tolerance for how far apart the edges can be and still be merged.

### Note for better use
The `Join` command is for creating a polysurface from separate surfaces. The `MergeSrf` command is for creating a single, larger surface from two smaller surfaces. For `MergeSrf` to work, the shared edge must be an un-trimmed, natural edge of both surfaces.

### Practical Use Cases
* **Use Case 1 (Extending a Shank):** You have modeled one half of a ring shank. You mirror it to create the other half. If both halves are un-trimmed, you can use `MergeSrf` with the `Smooth=Yes` option to merge them into a single, seamless shank surface.

### Other Information
This is an advanced surfacing tool for creating clean, single-surface objects from multiple parts.

---

## 387. Mesh

### Short Info
Create a mesh from a NURBS surface or polysurface.

### Detailed Description
The **Mesh** command is the primary tool for converting a smooth NURBS object into a polygon mesh. This is a critical step in preparing a model for 3D printing, rendering in other programs, or for any workflow that requires polygonal geometry (like STL or OBJ files). The command opens a dialog box that gives you detailed control over the quality and density of the resulting mesh.

### Steps to use the command
1.  Select the NURBS object(s) you want to convert.
2.  Run the command `Mesh`.
3.  The "Polygon Mesh Options" dialog box will appear.
4.  Adjust the sliders and settings to control the mesh density. A preview is shown in the viewport.
5.  Click OK to create the mesh object.

### Command Options & Toggles
The options are in a dialog box:
* **Simple controls:** A single slider from "Fewer polygons" to "More polygons."
* **Detailed controls:** Allows you to set specific parameters like **Maximum distance, edge to surface**, which is the most common and precise way to control the mesh quality.
* **Preview:** Shows a preview of the mesh in the viewport as you adjust the settings.

### Note for better use
The "Maximum distance, edge to surface" setting is the most important. This tells Rhino the maximum distance the flat edge of a polygon is allowed to be from the true curved NURBS surface. A smaller number (e.g., 0.01mm) will create a very dense, high-quality mesh that is good for 3D printing.

### Practical Use Cases
* **Use Case 1 (Creating an STL for 3D Printing):** This is the most common use. You have a finished, solid NURBS model of a ring. You run `Mesh`, use the detailed controls to set a high tolerance (e.g., 0.01mm), and create a high-quality mesh. You can then export this new mesh object as an STL file.
* **Use Case 2 (Exporting to a Sculpting Program):** You want to add sculpted details to your ring in a program like ZBrush. You would first use `Mesh` to convert your NURBS model into a clean polygon mesh that can be imported into the sculpting application.

### Other Information
This is the fundamental command for converting from the NURBS modeling world to the polygon mesh world.

---

## 388. MeshBooleanDifference

### Short Info
Subtract the volume of one set of meshes from another.

### Detailed Description
The **MeshBooleanDifference** command performs a boolean difference operation specifically on mesh objects. It subtracts the volume of one set of meshes from another.

### Steps to use the command
1.  Run the command `MeshBooleanDifference`.
2.  Select the mesh(es) to subtract from and press Enter.
3.  Select the mesh(es) to subtract with and press Enter.
4.  The volume of the second set will be cut away from the first.

### Command Options & Toggles
This command has no options.

### Note for better use
For this command to work reliably, all input meshes should be "closed" (watertight) and have no errors.

### Practical Use Cases
* **Use Case 1 (Editing STL Files):** You have an STL file of a ring and an STL file of a cutter. You can use `MeshBooleanDifference` to subtract the cutter directly from the ring mesh, without ever converting the objects to NURBS.
* **Use Case 2 (Hollowing a Model):** You have a solid mesh of a pendant. You can create a smaller, interior mesh shape and use `MeshBooleanDifference` to subtract it from the outer mesh, hollowing it out to save material.

### Other Information
This is the mesh-based equivalent of the standard `BooleanDifference` command.

---

## 389. MeshBooleanIntersection

### Short Info
Create a new mesh from meshes' intersected volumes.

### Detailed Description
The **MeshBooleanIntersection** command performs a boolean intersection operation specifically on mesh objects. It creates a new mesh object from only the shared, overlapping volume of the input meshes.

### Steps to use the command
1.  Run the command `MeshBooleanIntersection`.
2.  Select the first set of meshes and press Enter.
3.  Select the second set of meshes and press Enter.
4.  A new mesh object will be created from the overlapping volume.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Complex Mesh Creation):** You have two complex mesh objects that intersect, and you want to create a new object that represents only their shared space. This command will calculate that volume directly.

### Other Information
This is the mesh-based equivalent of the standard `BooleanIntersection` command.

---

## 390. MeshBooleanSplit

### Short Info
Split meshes at intersections.

### Detailed Description
The **MeshBooleanSplit** command splits one set of mesh objects where they are intersected by another set of mesh objects. It keeps all the resulting pieces.

### Steps to use the command
1.  Run the command `MeshBooleanSplit`.
2.  Select the mesh(es) to split and press Enter.
3.  Select the cutting mesh(es) and press Enter.
4.  The first set of meshes will be split into multiple pieces.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Creating Two-Tone Meshes):** You have a single STL file of a ring and want to split it into two pieces for two-tone casting. You can create a simple cutting plane (as a mesh object) and use `MeshBooleanSplit` to divide the ring mesh into two separate parts along that plane.

### Other Information
This is the mesh-based equivalent of the standard `BooleanSplit` command.

---

## 391. MeshBooleanUnion

### Short Info
Combine the volumes of one or more meshes.

### Detailed Description
The **MeshBooleanUnion** command merges two or more overlapping mesh objects into a single, continuous mesh. It removes the interior, overlapping faces.

### Steps to use the command
1.  Select two or more overlapping mesh objects.
2.  Run the command `MeshBooleanUnion`.
3.  The meshes will be merged into a single mesh.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Assembling STL Files):** You have downloaded separate STL files for a ring shank and a setting. You can position them so they overlap and then use `MeshBooleanUnion` to combine them into a single, printable STL file.

### Other Information
This is the mesh-based equivalent of the standard `BooleanUnion` command.

---

## 392. MeshBox

### Short Info
Draw a mesh box.

### Detailed Description
The **MeshBox** command creates a simple box made of mesh faces. It is the mesh-primitive equivalent of the NURBS `Box` command.

### Steps to use the command
1.  Run the command `MeshBox`.
2.  Follow the prompts to define the corners and height of the box.

### Command Options & Toggles
The options allow you to specify the number of polygons in the X, Y, and Z directions, controlling the density of the mesh box.

### Practical Use Cases
* **Use Case 1 (Creating Mesh Primitives):** You are working in a primarily mesh-based workflow and need a simple box shape to use as a cutter or a base for sculpting. `MeshBox` creates this primitive directly, without you needing to create a NURBS box and then convert it.

### Other Information
This is one of several commands for creating primitive mesh shapes.

---

## 393. MeshCone

### Short Info
Draw a mesh cone.

### Detailed Description
The **MeshCone** command creates a simple cone made of mesh faces. It is the mesh-primitive equivalent of the NURBS `Cone` command.

### Steps to use the command
1.  Run the command `MeshCone`.
2.  Follow the prompts to define the base and height of the cone.

### Command Options & Toggles
The options allow you to control the number of polygons around the circumference and along the height of the cone.

### Practical Use Cases
* **Use Case 1 (Mesh Cutters):** You need a simple conical cutter for a mesh boolean operation. `MeshCone` can create this directly.

### Other Information
This is one of several commands for creating primitive mesh shapes.

---

## 394. MeshCylinder

### Short Info
Draw a mesh cylinder.

### Detailed Description
The **MeshCylinder** command creates a simple cylinder made of mesh faces. It is the mesh-primitive equivalent of the NURBS `Cylinder` command.

### Steps to use the command
1.  Run the command `MeshCylinder`.
2.  Follow the prompts to define the base and height of the cylinder.

### Command Options & Toggles
The options allow you to control the number of polygons around the circumference and along the height of the cylinder.

### Practical Use Cases
* **Use Case 1 (Mesh Bezels):** You are working in a mesh-only workflow and need to create a simple bezel shape. `MeshCylinder` can create the basic form.

### Other Information
This is one of several commands for creating primitive mesh shapes.

---

## 395. MeshEllipsoid

### Short Info
Draw a mesh ellipsoid.

### Detailed Description
The **MeshEllipsoid** command creates a simple ellipsoid made of mesh faces. It is the mesh-primitive equivalent of the NURBS `Ellipsoid` command.

### Steps to use the command
1.  Run the command `MeshEllipsoid`.
2.  Follow the prompts to define the center and axes of the ellipsoid.

### Command Options & Toggles
The options allow you to control the number of polygons around the ellipsoid.

### Practical Use Cases
* **Use Case 1 (Mesh Cabochons):** You need a simple, dome-shaped mesh to use as a base for sculpting or as part of a larger mesh assembly. `MeshEllipsoid` can create this shape, which can then be cut in half.

### Other Information
This is one of several commands for creating primitive mesh shapes.

---

## 396. MeshIntersect

### Short Info
Create a polyline at the intersection of two meshes.

### Detailed Description
The **MeshIntersect** command calculates the intersection between two or more mesh objects and creates a new polyline curve where they cross.

### Steps to use the command
1.  Select two or more intersecting mesh objects.
2.  Run the command `MeshIntersect`.
3.  A polyline curve will be created along the line of intersection.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Finding a Seam on an STL):** You have two STL files that are positioned to interlock. You can use `MeshIntersect` to generate the exact curve along the seam where they meet. This curve can then be used as a guide for other modeling operations.

### Other Information
This is the mesh equivalent of the `Intersect` command.

---

## 397. MeshOutline

### Short Info
Create a polyline outline of a mesh.

### Detailed Description
The **MeshOutline** command creates a 2D polyline that represents the silhouette or outline of a selected mesh object as seen from the active viewport.

### Steps to use the command
1.  Select one or more mesh objects.
2.  Make the desired viewport active (e.g., Front view).
3.  Run the command `MeshOutline`.
4.  A flat, 2D polyline of the outline will be created on the CPlane.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Creating a 2D Profile from a Scan):** You have a 3D scan of an organic object (as a mesh) and you need to get a clean 2D outline of its side profile. You can position the object in the Front view and use `MeshOutline` to generate this curve.

### Other Information
This is the mesh equivalent of the `Silhouette` command.

---

## 398. MeshPatch

### Short Info
Create a mesh from curves and points.

### Detailed Description
The **MeshPatch** command creates a mesh by fitting it to a set of input curves and points. It is similar to the NURBS `Patch` command but it generates a mesh object directly. This is useful for creating free-form mesh surfaces.

### Steps to use the command
1.  Select the curves and points that will define the mesh.
2.  Run the command `MeshPatch`.
3.  A dialog box will appear with options to control the mesh density.
4.  Click OK to create the mesh.

### Command Options & Toggles
The options in the dialog box control the density and stiffness of the resulting mesh.

### Practical Use Cases
* **Use Case 1 (Filling a Hole in a Scan):** You have a 3D scan with a large, irregular hole. You can use `DupMeshHoleBoundary` to create a curve around the hole, and then use `MeshPatch` with this curve as input to create a mesh patch that fills the opening.

### Other Information
This is a powerful tool for free-form mesh creation and repair.

---

## 399. MeshPlane

### Short Info
Draw a mesh plane.

### Detailed Description
The **MeshPlane** command creates a simple, flat rectangular plane made of mesh faces. It is the mesh-primitive equivalent of the NURBS `Plane` command.

### Steps to use the command
1.  Run the command `MeshPlane`.
2.  Follow the prompts to define the corners of the plane.

### Command Options & Toggles
The options allow you to specify the number of polygons in the X and Y directions, controlling the density of the mesh plane.

### Practical Use Cases
* **Use Case 1 (Creating a Base):** You are starting a sculpting project in a mesh-based workflow and need a simple, flat base to build upon. `MeshPlane` is the fastest way to create this.

### Other Information
This is one of several commands for creating primitive mesh shapes.

---

## 400. MeshPolyline

### Short Info
Create a mesh from a closed polyline.

### Detailed Description
The **MeshPolyline** command takes a closed, planar polyline and creates a single, flat mesh face that fills its boundary.

### Steps to use the command
1.  Select a closed, planar polyline.
2.  Run the command `MeshPolyline`.
3.  A new mesh object will be created.

### Command Options & Toggles
This command has no options.

### Note for better use
The input curve must be a polyline (made of straight segments) and it must be both closed and planar.

### Practical Use Cases
* **Use Case 1 (Creating Custom Mesh Faces):** You need to create a complex, multi-sided polygon to patch a hole in a mesh. You can draw the outline of the polygon using the `Polyline` command and then use `MeshPolyline` to turn it into a single mesh face that you can then join to your main mesh.

### Other Information
This is a simple but useful tool for creating custom n-gons (polygons with more than 4 sides) in a mesh workflow.

---

## 401. MeshRepair

### Short Info
Open the Mesh Repair wizard.

### Detailed Description
The **MeshRepair** command opens a dedicated, floating panel that provides a suite of tools to help find and fix problems in mesh objects. This is a comprehensive utility for making meshes "watertight" and suitable for 3D printing. The wizard guides you through a series of checks and repair steps, such as checking for bad faces, filling holes, and unifying normals.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `MeshRepair`.
3.  The Mesh Repair panel will open.
4.  Follow the steps in the panel, starting with "Check Mesh."
5.  Use the various buttons like "Fill Holes" or "Unify Normals" to fix any reported problems.

### Command Options & Toggles
All options are contained within the Mesh Repair panel's interface. It includes buttons and readouts for:
* Checking for various mesh problems.
* Filling all holes.
* Unifying mesh normals.
* Rebuilding the mesh.

### Note for better use
The Mesh Repair wizard is an excellent tool for beginners and experts alike, as it consolidates many of the most common mesh repair commands into a single, logical interface. It is a very good practice to run any mesh intended for 3D printing through this wizard to ensure it is a valid, closed, and manifold object.

### Practical Use Cases
* **Use Case 1 (Pre-Print Check):** This is the primary use case. Before exporting a final ring model as an STL file, you would run `MeshRepair` on it. The wizard will immediately tell you if the mesh is closed and valid. If not, you can use the "Fill Holes" and other tools within the panel to fix it.
* **Use Case 2 (Repairing Scans):** You have a raw 3D scan of a piece of jewelry that is full of holes and flipped faces. The `MeshRepair` wizard provides a step-by-step process to identify and fix all of these issues to turn the raw scan into a usable, solid mesh.

### Other Information
This command is a front-end interface that combines the functionality of many other individual mesh repair commands (`FillMeshHoles`, `UnifyMeshNormals`, `CullDegenerateMeshFaces`, etc.).

---

## 402. MeshSphere

### Short Info
Draw a mesh sphere.

### Detailed Description
The **MeshSphere** command creates a simple sphere made of mesh faces. It is the mesh-primitive equivalent of the NURBS `Sphere` command.

### Steps to use the command
1.  Run the command `MeshSphere`.
2.  Follow the prompts to define the center and radius of the sphere.

### Command Options & Toggles
The options allow you to control the density of the mesh:
* **Vertical faces:** Sets the number of polygons around the sphere's circumference.
* **Around faces:** Sets the number of polygons from pole to pole.

### Note for better use
The `MeshSphere` command creates a sphere with a standard "UV" topology, which has poles at the top and bottom where the vertices converge.

### Practical Use Cases
* **Use Case 1 (Creating Milgrain):** You need to create a small bead for a milgrain edge in a mesh-based workflow. `MeshSphere` is the fastest way to create this primitive shape.
* **Use Case 2 (Mesh Cutters):** You need a simple spherical cutter for a mesh boolean operation. `MeshSphere` can create this directly.

### Other Information
This is one of several commands for creating primitive mesh shapes.

---

## 403. MeshSplit

### Short Info
Split a mesh with another object.

### Detailed Description
The **MeshSplit** command divides a mesh object into multiple pieces using another object (a surface, polysurface, or another mesh) as a cutter.

### Steps to use the command
1.  Run the command `MeshSplit`.
2.  At the **Select mesh to split** prompt, select the mesh object(s) and press Enter.
3.  At the **Select cutting object** prompt, select the object(s) that will act as the cutters and press Enter.
4.  The mesh will be split into multiple separate mesh objects.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is the mesh equivalent of the `Split` command for NURBS objects.

### Practical Use Cases
* **Use Case 1 (Creating a Two-Tone Mesh):** You have a single STL file of a ring and want to split it into two pieces for two-tone casting. You can create a simple cutting plane (as a NURBS surface) and use `MeshSplit` to divide the ring mesh into two separate parts along that plane.
* **Use Case 2 (Sizing a Mesh Ring):** You have an STL file of a finished ring that is the wrong size. You can use `MeshSplit` to cut a section out of the bottom of the shank. You can then move the two halves apart and rebuild the bottom section to make the ring larger.

### Other Information
This is a fundamental tool for editing and deconstructing mesh objects.

---

## 404. MeshTCone

### Short Info
Draw a truncated mesh cone.

### Detailed Description
The **MeshTCone** (Mesh Truncated Cone) command creates a simple truncated cone (a cone with its tip cut off) made of mesh faces. It is the mesh-primitive equivalent of the NURBS `TCone` command.

### Steps to use the command
1.  Run the command `MeshTCone`.
2.  Follow the prompts to define the base radius, the top radius, and the height of the truncated cone.

### Command Options & Toggles
The options allow you to control the number of polygons around the circumference and along the height of the cone.

### Practical Use Cases
* **Use Case 1 (Mesh Bezel Base):** You are building a tapered bezel in a mesh-only workflow. `MeshTCone` is the fastest way to create the basic tapered shape.

### Other Information
This is one of several commands for creating primitive mesh shapes.

---

## 405. MeshToNURB

### Short Info
Duplicate each mesh face with a NURBS surface.

### Detailed Description
The **MeshToNURB** command is a conversion tool that takes a mesh object and converts it into a NURBS polysurface. It does this by creating a separate, trimmed NURBS surface for every single face of the original mesh.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `MeshToNURB`.
3.  A new NURBS polysurface will be created that has the exact same faceted appearance as the original mesh.

### Command Options & Toggles
This command has no options.

### Note for better use
This command creates an extremely heavy and complex polysurface, as each triangle or quad in the mesh becomes its own surface. It does **not** create a single, smooth NURBS surface. For that kind of reverse-engineering, you would need to use other tools to draw curves on the mesh and build a new surface with commands like `Loft` or `NetworkSrf`.

### Practical Use Cases
* **Use Case 1 (Converting Simple Geometry):** You have a very simple, low-polygon mesh object with flat faces that you need to convert to a NURBS object to use with commands that only work on NURBS (like some of the Matrix builders). `MeshToNURB` can perform this conversion.
* **Use Case 2 (Preparing for Booleans):** You need to perform a boolean operation between a mesh object and a NURBS object. You could use `MeshToNURB` to convert the mesh into a polysurface so that you can use the standard `BooleanDifference` command.

### Other Information
This is a very literal conversion tool and should be used with caution on dense meshes, as it can create extremely complex polysurfaces that will slow down your computer.

---

## 406. MeshTorus

### Short Info
Draw a mesh torus.

### Detailed Description
The **MeshTorus** command creates a simple torus (a donut shape) made of mesh faces. It is the mesh-primitive equivalent of the NURBS `Torus` command.

### Steps to use the command
1.  Run the command `MeshTorus`.
2.  Follow the prompts to define the center, the major radius, and the minor radius of the torus.

### Command Options & Toggles
The options allow you to control the number of polygons around the major and minor radii, controlling the density of the mesh.

### Practical Use Cases
* **Use Case 1 (Creating Jump Rings):** You are working in a mesh-only workflow and need to create simple jump rings for a chain. `MeshTorus` is the fastest way to create this primitive shape.

### Other Information
This is one of several commands for creating primitive mesh shapes.

---

## 407. MeshTrim

### Short Info
Trim a mesh with a curve on the mesh.

### Detailed Description
The **MeshTrim** command is a mesh editing tool that trims away a portion of a mesh. It is the mesh equivalent of the `Trim` command. It works by splitting the mesh with a cutting curve and then allows you to discard the unwanted pieces.

### Steps to use the command
1.  Run the command `MeshTrim`.
2.  At the **Select cutting objects** prompt, select one or more curves or surfaces and press Enter.
3.  At the **Select mesh to trim** prompt, click on the part of the mesh you want to remove.
4.  The selected portion of the mesh will be deleted.

### Command Options & Toggles
This command has no options.

### Note for better use
This command will create holes in your mesh, making it "non-watertight." You will need to use other tools like `Patch` or `FillMeshHole` if you need to close the mesh again.

### Practical Use Cases
* **Use Case 1 (Creating an Opening in an STL):** You have an STL file of a solid pendant and you want to cut an opening in it. You can draw a closed curve on the surface of the mesh and then use `MeshTrim` to cut out the hole.

### Other Information
This is a fundamental tool for editing and cutting mesh objects.

---

## 408. Minimize

### Short Info
Minimize the Rhino window.

### Detailed Description
The **Minimize** command minimizes the main Rhino application window to the taskbar.

### Steps to use the command
1.  Run the command `Minimize`.
2.  The Rhino window will be minimized.

### Command Options & Toggles
This command has no options.

### Note for better use
This is equivalent to clicking the "Minimize" button in the top-right corner of the Rhino window.

### Practical Use Cases
* **Use Case 1 (Window Management):** You need to quickly access another program or your desktop. `Minimize` will hide the Rhino window.

### Other Information
This is a simple window management command.

---

## 409. Mirror

### Short Info
Create a mirror-image copy of objects.

### Detailed Description
The **Mirror** command is a fundamental transformation tool that creates a mirrored copy of an object across a defined line or plane. This is an essential tool for creating symmetrical objects.

### Steps to use the command
1.  Select the object(s) to mirror.
2.  Run the command `Mirror`.
3.  At the **Start of mirror plane** prompt, pick the first point of your mirror line.
4.  At the **End of mirror plane** prompt, pick the second point.
5.  A mirrored copy of the object will be created.

### Command Options & Toggles
This command has no options in the command line.

### Note for better use
Using Ortho (holding `Shift`) or snapping to grid lines when defining the mirror plane is essential for creating perfect, symmetrical copies.

### Practical Use Cases
* **Use Case 1 (Creating a Symmetrical Ring):** This is a primary use case. You model one half of a detailed, symmetrical ring shank or pendant. When you are finished, you select the half, run `Mirror`, and draw the mirror plane down the center of your design. This creates the other half perfectly. You can then `Join` the two halves to create the final object.
* **Use Case 2 (Placing Accent Stones):** You have carefully placed a group of accent stones on one side of a ring. You can select them all and use `Mirror` to create an identical, symmetrical group on the other side.

### Other Information
This is one of the most frequently used and important commands for efficient modeling.

---

## 410. MirrorHole

### Short Info
Mirror a hole on a planar surface.

### Detailed Description
The **MirrorHole** command is a specialized utility that creates a mirrored copy of a hole on a single, planar surface.

### Steps to use the command
1.  Run the command `MirrorHole`.
2.  At the **Select hole to mirror** prompt, click the edge of the hole.
3.  You will then be prompted to define the start and end of the mirror plane.
4.  A mirrored copy of the hole will be created on the same surface.

### Command Options & Toggles
This command has no options.

### Note for better use
This command only works on flat (planar) surfaces.

### Practical Use Cases
* **Use Case 1 (Symmetrical Patterns):** You are creating a design on a flat plate that requires a symmetrical pattern of holes. You can create the holes on one side, and then use `MirrorHole` to create their perfect counterparts on the other side.

### Other Information
This is a specialized tool that combines mirroring and trimming into a single operation for holes.


---

## 411. ModelBasepoint

### Short Info
Set a base point for the model.

### Detailed Description
The **ModelBasepoint** command sets a location in the current model that will be used as the insertion base point when this file is inserted into another Rhino file as a block instance. By default, a model's base point is the world origin (0,0,0). This command allows you to define a more logical insertion point, such as the center of an object.

### Steps to use the command
1.  Run the command `ModelBasepoint`.
2.  At the **Model base point** prompt, pick a location.
3.  The base point for the model is now set to that location.

### Command Options & Toggles
This command has no options.

### Note for better use
Setting a logical base point is crucial when creating a library of parts that will be inserted into other models. For example, the base point for a gemstone model should be its center (culet or table), and the base point for a setting should be the center where the stone will sit. This makes assembling parts much easier.

### Practical Use Cases
* **Use Case 1 (Creating a Component Library):** You have designed a standard 4-prong setting that you will use in many different ring designs. Before saving the setting as its own file, you run `ModelBasepoint` and set the base point to the exact center where the gemstone's culet would be. Now, when you `Insert` this setting file into a new ring project, it will insert from that logical center point, making it easy to snap to a ring rail.
* **Use Case 2 (Aligning Imports):** You are exporting a pendant to be inserted into a separate file containing a chain. You can set the model base point of the pendant to the center of its bail. When the pendant is inserted into the other file, its insertion point will be at the bail, making it easy to snap to the chain.

### Other Information
This is a file-level property, not an object property. It affects how the entire file behaves when used as a component in another project.

---

## 412. ModifyRadius

### Short Info
Change the radius of circles and arcs.

### Detailed Description
The **ModifyRadius** command is a simple editing tool that allows you to change the radius of existing circles and arcs by specifying a new radius value.

### Steps to use the command
1.  Run the command `ModifyRadius`.
2.  At the **Select circle or arc to change radius** prompt, select the object. The current radius will be displayed.
3.  At the **New radius** prompt, type a new value and press Enter.
4.  The circle or arc will be resized.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a direct and precise way to edit the size of circles and arcs without having to rescale them.

### Practical Use Cases
* **Use Case 1 (Resizing a Gemstone Outline):** You have drawn a 5mm circle to represent a gemstone, but the client decides they want a 6mm stone instead. You can run `ModifyRadius`, select the circle, and simply type "3" (since the radius is half the diameter) to instantly resize it to the correct dimension.
* **Use Case 2 (Adjusting a Bezel):** You have created the inner wall of a bezel from an arc. You realize the radius is slightly too small. `ModifyRadius` allows you to enter the precise, correct radius value to fix it.

### Other Information
This is a simple but frequently used editing command for basic geometric shapes.

---

## 413. Move

### Short Info
Move objects from one location to another.

### Detailed Description
The **Move** command is one of the most fundamental transformation tools. It relocates selected objects from a base point to a new destination point.

### Steps to use the command
1.  Select the object(s) to move.
2.  Run the command `Move`.
3.  At the **Point to move from** prompt, pick a base point.
4.  At the **Point to move to** prompt, pick a destination point.
5.  The object(s) will be moved.

### Command Options & Toggles
* **Vertical:** Constrains the movement to be vertical to the current construction plane.

### Note for better use
Using object snaps is critical for moving objects with precision. For example, to move a prong so its tip touches the surface of a gemstone, you would pick the tip of the prong as the "point to move from" and use the `OnSrf` snap for the "point to move to." The Gumball widget is often a faster, more interactive way to perform simple moves.

### Practical Use Cases
* **Use Case 1 (Positioning a Gemstone):** You have a ring shank and a gemstone. You need to move the gemstone into the correct position above the shank. You would select the stone, run `Move`, snap the base point to the stone's culet (bottom point), and snap the destination point to the top of the ring rail.
* **Use Case 2 (Adjusting Components):** You have placed a bezel on a ring, but it is slightly off-center. You can use the `Move` command, snapping from the center of the bezel to the center of the ring, to perfectly align it.

### Other Information
This is a core command that is used constantly in every modeling workflow.

---

## 414. MoveCrv

### Short Info
Move a polycurve segment.

### Detailed Description
The **MoveCrv** (Move Curve) command is a specialized editing tool that allows you to move an entire segment of a polycurve. The adjacent segments stretch to stay connected to the moved segment.

### Steps to use the command
1.  Run the command `MoveCrv`.
2.  At the **Select polycurve segment to move** prompt, click on the segment you want to move.
3.  Follow the prompts to define the move, similar to the standard `Move` command.
4.  The segment will be moved, and the adjacent segments will stretch to meet it.

### Command Options & Toggles
This command has no options.

### Note for better use
This command only works on polycurves (curves made of multiple joined segments).

### Practical Use Cases
* **Use Case 1 (Adjusting a Profile):** You have drawn the cross-section of a ring shank as a polycurve. You decide that the flat bottom segment needs to be wider. You can use `MoveCrv` to select the top segment and move it upwards, which will cause the vertical side segments to stretch, making the entire profile taller.

### Other Information
This is a specialized tool for editing polycurves.

---

## 415. MoveEdge

### Short Info
Move a polysurface edge.

### Detailed Description
The **MoveEdge** command is a direct solid editing tool that allows you to select an edge of a polysurface and move it. The surfaces connected to that edge will be stretched or compressed to follow the moved edge.

### Steps to use the command
1.  Run the command `MoveEdge`.
2.  At the **Select edges to move** prompt, select one or more edges and press Enter.
3.  Follow the prompts to define the move, similar to the standard `Move` command.
4.  The edge will be moved, and the adjacent surfaces will be modified.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a powerful tool for making direct edits to solid models without having to explode them. It works best on simple, planar shapes.

### Practical Use Cases
* **Use Case 1 (Widening a Bezel Wall):** You have a solid bezel, and you decide the wall is too thin. You can run `MoveEdge`, select the top outer edge of the bezel, and move it outward. The outer wall surface will stretch, making the entire bezel thicker.
* **Use Case 2 (Adjusting a Signet Ring):** You have a box-shaped signet ring top and want to make it longer. You can select the front edge and use `MoveEdge` to pull it forward, stretching the top and side surfaces to the new length.

### Other Information
This is a key command for direct solid modeling.

---

## 416. MoveFace

### Short Info
Move a polysurface face.

### Detailed Description
The **MoveFace** command is a direct solid editing tool that allows you to select a face of a polysurface and move it. The adjacent faces will be stretched or compressed to stay connected.

### Steps to use the command
1.  Run the command `MoveFace`.
2.  At the **Select faces to move** prompt, select one or more faces and press Enter.
3.  Follow the prompts to define the move.
4.  The face will be moved, and the surrounding surfaces will be modified.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a very powerful and intuitive way to make changes to solid models. It allows you to push and pull the faces of an object as if it were made of clay.

### Practical Use Cases
* **Use Case 1 (Making a Shank Thicker):** You have a solid ring shank and decide it needs to be thicker at the bottom. You can use `MoveFace` to select the outer bottom face of the shank and simply pull it outward to add thickness.
* **Use Case 2 (Tapering a Bezel):** You have a straight-walled bezel. You can select the outer face and use the `Rotate` command on it to give the wall a tapered angle.

### Other Information
This is a fundamental command for direct solid modeling workflows.

---

## 417. MoveHole

### Short Info
Move a hole in a planar surface.

### Detailed Description
The **MoveHole** command is a specialized editing tool that allows you to move a hole within a single, planar surface.

### Steps to use the command
1.  Run the command `MoveHole`.
2.  At the **Select hole edge(s) to move** prompt, select the edge of the hole.
3.  Follow the prompts to define the move, similar to the standard `Move` command.
4.  The hole will be moved to the new location, and the surface will be repaired.

### Command Options & Toggles
This command has no options.

### Note for better use
This command only works on holes within a single, flat (planar) surface. It will not work on holes that cross multiple faces or on curved surfaces.

### Practical Use Cases
* **Use Case 1 (Repositioning a Setting):** You have cut a hole in the flat top of a signet ring for a gemstone, but you realize it is slightly off-center. `MoveHole` allows you to select the hole and move it to the correct, centered position without having to undo and re-trim.

### Other Information
This is a time-saving utility for editing features on flat surfaces.

---

## 418. MoveTargetToObjects

### Short Info
Move the viewport camera target to the center of selected objects.

### Detailed Description
The **MoveTargetToObjects** command is a viewport navigation tool. It changes the "target" or pivot point of the active viewport's camera to be the center of the bounding box of the selected objects.

### Steps to use the command
1.  Select one or more objects.
2.  Run the command `MoveTargetToObjects`.
3.  The camera's target will be moved.

### Command Options & Toggles
This command has no options.

### Note for better use
After running this command, when you tumble or rotate the view with the mouse, the camera will now pivot around the center of the objects you selected. This is very useful for inspecting a specific part of a large model.

### Practical Use Cases
* **Use Case 1 (Inspecting a Prong):** You are working on a large, complex ring and you want to zoom in and rotate the view to inspect a single, tiny prong. If you just zoom in, the camera will still be pivoting around the center of the entire ring, which can be awkward. Instead, you would select the prong, run `MoveTargetToObjects`, and then run `Zoom` with the `Selected` option. Now, when you rotate the view, the camera will tumble perfectly around that single prong.

### Other Information
This is a key command for efficient navigation in complex scenes.

---

## 419. MoveUntrimmedEdge

### Short Info
Move an un-trimmed edge of a polysurface face.

### Detailed Description
The **MoveUntrimmedEdge** command is an advanced direct editing tool. It allows you to move an edge of a single face within a polysurface, but only if that edge is an "un-trimmed" or natural edge of the underlying surface.

### Steps to use the command
1.  Run the command `MoveUntrimmedEdge`.
2.  Select an un-trimmed edge of a polysurface face.
3.  Follow the prompts to define the move.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a more technical and less commonly used command than `MoveEdge`. `MoveEdge` works on any edge, while this command is restricted to the natural edges of the surfaces that make up the polysurface.

### Practical Use Cases
* **Use Case 1 (Advanced Surface Editing):** An advanced user is editing a polysurface that was built from simple, un-trimmed surfaces. This command gives them a way to modify the underlying structure of one of those surfaces without having to `Explode` the object.

### Other Information
For most direct editing tasks, `MoveEdge` and `MoveFace` are more intuitive and versatile.

---

## 420. MoveUntrimmedFace

### Short Info
Move an un-trimmed polysurface face.

### Detailed Description
The **MoveUntrimmedFace** command is an advanced direct editing tool. It allows you to move a single face of a polysurface, but only if that face is an "un-trimmed" or natural surface. The adjacent faces will be extended to meet the new location of the moved face.

### Steps to use the command
1.  Run the command `MoveUntrimmedFace`.
2.  Select an un-trimmed face of a polysurface.
3.  Follow the prompts to define the move.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a more technical and less commonly used command than `MoveFace`. `MoveFace` works on any face, while this command is restricted to faces that have not been trimmed.

### Practical Use Cases
* **Use Case 1 (Advanced Solid Editing):** An advanced user is editing a polysurface that was built from simple, un-trimmed surfaces (like a box). This command allows them to move one of the original faces and have the adjacent faces automatically extend to stay connected.

### Other Information
For most direct editing tasks, `MoveFace` is more intuitive and versatile.


---

## 421. MoveUVN

### Short Info
Move surface control points along u-, v-, and normal-directions.

### Detailed Description
The **MoveUVN** command opens a special panel with sliders that allow you to move selected surface control points along the surface's natural U, V, and Normal directions. This is an extremely powerful and intuitive tool for making smooth, controlled edits to a curved surface. Instead of guessing the correct direction to move a point with the standard `Move` command, this tool ensures your edits flow along the surface's own coordinate system.

### Steps to use the command
1.  Turn on the control points for a surface (`PointsOn` or F10).
2.  Select one or more control points.
3.  Run the command `MoveUVN`.
4.  The Move UVN panel will appear.
5.  Use the U, V, and N sliders to move the selected points. The surface will update in real-time.

### Command Options & Toggles
The options are all contained within the Move UVN panel:
* **U, V, N sliders:** Control the movement of the points along the surface's directions.
* **Scale:** Controls the sensitivity or "speed" of the sliders. A smaller value allows for finer adjustments.
* **Un-Do:** Reverts the last slider adjustment.

### Note for better use
The "N" slider, which moves points along the surface normal (straight in or out from the surface), is particularly useful for creating bumps or depressions. This tool is often superior to the standard `Move` command for editing curved surfaces because it prevents you from accidentally creating wrinkles or flat spots by moving points in an unnatural direction.

### Practical Use Cases
* **Use Case 1 (Creating a Depression):** You want to create a smooth, concave "thumbprint" depression on the surface of a ring. You can select a group of control points in the center, open the `MoveUVN` panel, and use the "N" slider to push the points inward along the surface normal, creating a perfect depression.
* **Use Case 2 (Sliding a Feature):** You have a feature on a curved surface defined by a group of control points, and you need to slide it slightly along the surface's length. The "U" and "V" sliders allow you to do this precisely, without the feature lifting off the surface or changing its orientation.

### Other Information
This is a fundamental tool for high-quality, organic surface editing.

---

## 422. MPlane

### Short Info
Set up a mobile construction plane.

### Detailed Description
The **MPlane** (Mobile Plane) command is an advanced utility that sets up a construction plane that is linked to a specific object. This "mobile" CPlane will move and rotate along with the object it is attached to.

### Steps to use the command
1.  Select an object.
2.  Run the command `MPlane`.
3.  The construction plane in the active viewport will now be attached to that object.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a highly specialized command and is not used in typical modeling workflows. Its primary purpose is for use with specific hardware controllers (like a 6-axis mouse) that can manipulate objects and the CPlane simultaneously.

### Practical Use Cases
* **Use Case 1 (Advanced Navigation):** A user with a 6-axis controller could use `MPlane` to link the CPlane to an object. Then, as they use the controller to move the object through 3D space, the construction plane would move with it, allowing them to draw new objects that are always relative to the moving part. This has very limited application in jewelry design.

### Other Information
This is a specialized command for alternative input devices.

---

## 423. NamedCPlane

### Short Info
Save and restore named construction planes.

### Detailed Description
The **NamedCPlane** command opens a panel that allows you to save and restore custom construction planes. If you have created a specific, custom CPlane using the `CPlane` command that you need to use frequently, you can save it with a name. This command allows you to instantly recall that saved CPlane at any time.

### Steps to use the command
1.  Run the command `NamedCPlane`.
2.  The Named CPlanes panel will open.
3.  To save a CPlane, set up your custom CPlane in a viewport and click the "Save" icon in the panel.
4.  To restore a CPlane, select its name from the list and click the "Restore" icon.

### Command Options & Toggles
All options are contained within the panel's interface for saving, restoring, and deleting CPlanes.

### Note for better use
Saving your custom CPlanes is essential when you are working on a model with multiple angled or complex surfaces. It saves you from having to redefine the CPlane every time you want to work on a specific part of the model.

### Practical Use Cases
* **Use Case 1 (Working on a Tilted Bezel):** You are designing a ring where the main bezel is tilted at a 15-degree angle. You create a custom CPlane aligned to this bezel. You can then save this as "TiltedBezel_CPlane." Now, you can switch back to the default World Top CPlane to work on the shank, and whenever you need to work on the bezel again, you can simply restore your saved CPlane to instantly align your grid and drawing tools to the bezel's angle.

### Other Information
This is a fundamental tool for staying organized and working efficiently on complex, multi-angled objects.

---

## 424. NamedPosition

### Short Info
Save and restore the position of objects.

### Detailed Description
The **NamedPosition** command opens a panel that allows you to save and restore the exact location, scale, and rotation of objects in your model. This is like a bookmark for the position of your geometry.

### Steps to use the command
1.  Run the command `NamedPosition`.
2.  The Named Positions panel will open.
3.  Select the object(s) whose position you want to save.
4.  Click the "Save" icon in the panel and give the position a name.
5.  You can now move the objects. To return them to the saved position, select the objects, select the saved position name in the panel, and click the "Restore" icon.

### Command Options & Toggles
All options are contained within the panel's interface.

### Practical Use Cases
* **Use Case 1 (Creating Exploded Views):** You have a complex, assembled ring. You can save the current state as a "Closed" named position. Then, you can move the parts away from each other to create an "exploded" view for a diagram. You can save this state as an "Exploded" named position. Now you can instantly switch the objects between the two states.
* **Use Case 2 (Design Options):** You are trying out several different positions for a side-stone setting. You can save each position with a name ("Position A," "Position B," etc.) to easily switch between them and show a client the different options.

### Other Information
This is a powerful tool for presentations, animations, and managing design variations.

---

## 425. NamedView

### Short Info
Save and restore views.

### Detailed Description
The **NamedView** command opens a panel that allows you to save and restore specific camera views. This includes the camera's position, rotation, target, and lens length. It's like creating a bookmark for a specific way of looking at your model.

### Steps to use the command
1.  Run the command `NamedView`.
2.  The Named Views panel will open.
3.  Arrange your viewport to the exact camera angle you want to save.
4.  Click the "Save" icon in the panel and give the view a name.
5.  To return to that view later, simply double-click its name in the list.

### Command Options & Toggles
All options are contained within the panel's interface.

### Note for better use
Saving your views is essential for creating consistent renders and for easily returning to a specific perspective when working on a complex model.

### Practical Use Cases
* **Use Case 1 (Consistent Renders):** You have found the perfect "hero shot" perspective angle for rendering your ring. You use `NamedView` to save this as "Render_Angle_01." Now, you can make changes to your model, and whenever you are ready to render, you can instantly return to that exact same camera angle, ensuring all your renders are consistent.
* **Use Case 2 (Working Views):** You are working on a very detailed area of a model that requires you to be zoomed in at a specific, awkward angle. You can save this as a "Working_View" so you can quickly navigate back to it after zooming out to look at the whole model.

### Other Information
This is a fundamental tool for rendering, presentation, and workflow management.

---

## 426. NetworkSrf

### Short Info
Create a surface from a network of crossing curves.

### Detailed Description
The **NetworkSrf** (Network Surface) command is one of the most powerful and versatile surface creation tools in Rhino. It creates a smooth NURBS surface that is fitted through a network of intersecting curves. This command can handle very complex shapes and gives you a high degree of control over the resulting surface by allowing you to specify the continuity at the edges.

### Steps to use the command
1.  Create a network of curves that intersect each other, forming a grid-like pattern.
2.  Run the command `NetworkSrf`.
3.  At the **Select curves in network** prompt, select all of your curves.
4.  Press Enter. A dialog box will appear with options for controlling the surface fit.
5.  Adjust the tolerances and edge continuity as needed and click OK.

### Command Options & Toggles
The options are in a dialog box:
* **Edge matching (Loose/Position/Tangency/Curvature):** Allows you to set the desired level of smoothness (continuity) for the surface edges that lie on other surfaces.
* **Tolerances:** Control how accurately the surface fits the input curves.

### Note for better use
For the best results, the curves in your network should intersect cleanly. The command works best with a grid of curves running in roughly perpendicular directions (U and V). `NetworkSrf` is often the best tool for creating a single, clean surface over a complex four-sided area where other commands like `Sweep2` or `Loft` do not provide enough control.

### Practical Use Cases
* **Use Case 1 (Complex Ring Surfaces):** You are modeling a ring with a very complex, organic top surface that is not a simple dome. You can create a series of cross-section curves in one direction, and then create several longitudinal curves that cross them. `NetworkSrf` can then be used to create a single, smooth surface that perfectly fits this entire curve network.
* **Use Case 2 (Closing a Difficult Hole):** You have a complex, irregular four-sided hole in your model that needs to be filled. You can use `DupEdge` to extract the four boundary curves and then use `NetworkSrf` to create a patch surface that is perfectly continuous (tangent or curvature) with the surrounding geometry.

### Other Information
Mastering `NetworkSrf` is a key skill for advanced free-form surface modeling.

---

## 427. New

### Short Info
Create a new model.

### Detailed Description
The **New** command closes the current file and creates a new, blank model. It will prompt you to select a template file, which sets up the units, grid, and default layers for your new project.

### Steps to use the command
1.  Run the command `New`.
2.  If your current file has unsaved changes, you will be prompted to save it.
3.  A dialog box will appear, asking you to choose a template file.
4.  Select a template and click "Open." A new, blank model will be created.

### Command Options & Toggles
The only option is the template file you choose.

### Note for better use
It is a very good practice to create your own custom template file that has all of your preferred settings (units set to millimeters, your standard layers already created, your favorite dimension style, etc.). You can create a template by setting up a blank file exactly how you like it and then using the `SaveAsTemplate` command.

### Practical Use Cases
* **Use Case 1 (Starting a Project):** This is the command you run when you want to start modeling a new piece of jewelry from scratch.

### Other Information
This is a fundamental file management command.

---

## 428. NewFloatingViewport

### Short Info
Create a new floating viewport.

### Detailed Description
The **NewFloatingViewport** command creates a new modeling viewport that is contained within its own separate, floating window. This window can be moved around your screen (or to a second monitor) and resized independently of the main Rhino window.

### Steps to use the command
1.  Run the command `NewFloatingViewport`.
2.  A new floating viewport window will appear.

### Command Options & Toggles
This command has no options.

### Note for better use
Floating viewports are useful for creating a persistent detail view or for taking advantage of a multi-monitor setup.

### Practical Use Cases
* **Use Case 1 (Multi-Monitor Workflow):** You have two monitors. You can keep your main 4-view layout on your primary monitor, and create a large, floating perspective view on your second monitor, giving you a massive, dedicated 3D view at all times.
* **Use Case 2 (Persistent Detail View):** You are working on a very fine detail on a large model. You can create a small, floating viewport that is permanently zoomed in on that one detail. You can keep this window in the corner of your screen as a constant reference while you work on the main model.

### Other Information
This is a workspace customization tool.

---

## 429. NewViewport

### Short Info
Create a new viewport.

### Detailed Description
The **NewViewport** command adds a new, standard, docked viewport to your main Rhino window.

### Steps to use the command
1.  Run the command `NewViewport`.
2.  A new viewport with the default perspective view will be added to your layout.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Custom Layout):** You want to create a custom 5-view layout. You could start with the default `4View` layout and then use `NewViewport` to add a fifth viewport, which you could then resize and arrange as needed.

### Other Information
This is a simple workspace customization tool.

---

## 430. NextOrthoViewport

### Short Info
Activate the next viewport with a parallel projection.

### Detailed Description
The **NextOrthoViewport** command is a viewport navigation utility. It cycles through and activates the next viewport that has a parallel (orthographic) projection, such as Top, Front, or Right. It skips any perspective viewports.

### Steps to use the command
1.  Run the command `NextOrthoViewport`.
2.  The next orthographic viewport in the sequence will become the active viewport.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is most useful when assigned to a keyboard shortcut, allowing you to quickly cycle through your 2D views without using the mouse.

### Practical Use Cases
* **Use Case 1 (Keyboard Navigation):** A power user might assign this command to a shortcut like Ctrl+Tab to allow them to quickly jump between their Top, Front, and Right views while keeping their hands on the keyboard.

### Other Information
This is a workflow efficiency and navigation tool.

---

## 431. NextPerspectiveViewport

### Short Info
Activate the next viewport with a perspective projection.

### Detailed Description
The **NextPerspectiveViewport** command is a viewport navigation utility. It cycles through and activates the next viewport that has a perspective projection.

### Steps to use the command
1.  Run the command `NextPerspectiveViewport`.
2.  The next perspective viewport in the sequence will become the active viewport.

### Command Options & Toggles
This command has no options.

### Note for better use
This is most useful if you have created multiple perspective viewports.

### Practical Use Cases
* **Use Case 1 (Multiple 3D Views):** You have set up your main Perspective view and also a second, floating perspective view. This command allows you to quickly toggle which one is active.

### Other Information
This is a workflow efficiency and navigation tool.

---

## 432. NextU

### Short Info
Select the next control point in the u-direction.

### Detailed Description
The **NextU** command is a control point selection utility. It deselects the currently selected control point(s) and selects the very next control point in the positive U direction.

### Steps to use the command
1.  Turn on control points for a curve or surface.
2.  Select one control point.
3.  Run the command `NextU`.
4.  The original point will be deselected, and the next point in the U direction will be selected.

### Command Options & Toggles
This command has no options.

### Note for better use
This is different from `AddNextU`, which *adds* to the selection. `NextU` *replaces* the selection. This command is designed to be used with keyboard shortcuts to "walk" a single selection along a row of control points.

### Practical Use Cases
* **Use Case 1 (Sequential Adjustments):** You need to adjust each control point in a row, one at a time. You can select the first point, make your adjustment, then use `NextU` to move the selection to the next point, make another adjustment, and so on, without having to re-select each point with the mouse.

### Other Information
This is a specialized selection command for advanced control point editing.

---

## 433. NextV

### Short Info
Select the next control point in the v-direction.

### Detailed Description
The **NextV** command is a control point selection utility. It deselects the currently selected control point(s) and selects the very next control point in the positive V direction on a surface.

### Steps to use the command
1.  Turn on control points for a surface.
2.  Select one control point.
3.  Run the command `NextV`.
4.  The original point will be deselected, and the next point in the V direction will be selected.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the V-direction equivalent of the `NextU` command.

### Practical Use Cases
* **Use Case 1 (Sequential Adjustments):** Similar to `NextU`, this allows you to move your selection one step at a time along a column of control points on a surface.

### Other Information
This is a specialized selection command for advanced control point editing.

---

## 434. NextViewport

### Short Info
Activate the next viewport.

### Detailed Description
The **NextViewport** command is a viewport navigation utility. It activates the next viewport in the standard sequence (typically Top > Front > Right > Perspective).

### Steps to use the command
1.  Run the command `NextViewport`.
2.  The next viewport in the sequence will become active.

### Command Options & Toggles
This command has no options.

### Note for better use
The keyboard shortcut Ctrl+Tab is the default and much faster way to perform this action.

### Practical Use Cases
* **Use Case 1 (Keyboard Navigation):** A user who prefers to work with the keyboard can use this command (or its shortcut) to cycle through the viewports without having to move their hand to the mouse to click in a different window.

### Other Information
This is a basic navigation command.

---

## 435. NextViewportToTop

### Short Info
Bring the next viewport to the front.

### Detailed Description
The **NextViewportToTop** command is a viewport management utility for floating viewports. It cycles through the floating viewports, bringing the next one in the sequence to the front of the stack.

### Steps to use the command
1.  Have multiple floating viewports open.
2.  Run the command `NextViewportToTop`.
3.  The next floating viewport will be brought in front of the others.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Managing Floating Views):** You have several floating viewports open on a second monitor. This command allows you to cycle through them, bringing each one to the front in turn.

### Other Information
This is a window management tool for users with complex, multi-viewport layouts.

---

## 436. NoEcho

### Short Info
Stop displaying script commands in the history window.

### Detailed Description
The **NoEcho** command is a utility used in scripting. It prevents the commands being run by a script from being displayed (echoed) in the command history window. This makes the script run faster and silently, without cluttering the command line.

### Steps to use the command
1.  This command is used inside a script file.
2.  Placing the line `Rhino.NoEcho` at the beginning of a script will suppress the display of subsequent commands.

### Command Options & Toggles
This command is a toggle within a script. The opposite command is `Echo`.

### Practical Use Cases
* **Use Case 1 (Creating a Clean Tool):** A developer is creating a custom tool for a designer. They use `NoEcho` at the beginning of the script so that when the designer runs the tool, they are not distracted by hundreds of lines of code flashing through the command prompt. The tool will simply run silently in the background.

### Other Information
This is a utility for script developers.

---

## 437. NonmanifoldMerge

### Short Info
Create a non-manifold polysurface from intersecting surfaces.

### Detailed Description
The **NonmanifoldMerge** command is an advanced surfacing tool. It takes a collection of surfaces and polysurfaces that intersect and joins them into a single "non-manifold" polysurface. A non-manifold object is one that has edges connected to more than two faces, which is not allowed in a valid "solid" model. This command is used to create complex single objects that could not be created with `BooleanUnion`.

### Steps to use the command
1.  Select two or more intersecting surfaces or polysurfaces.
2.  Run the command `NonmanifoldMerge`.
3.  The objects will be joined into a single non-manifold polysurface.

### Command Options & Toggles
This command has no options.

### Note for better use
The result of this command is, by definition, not a valid solid and cannot be 3D printed. This is a tool for creating complex single objects for specific modeling or rendering purposes, not for manufacturing.

### Practical Use Cases
* **Use Case 1 (Creating a Single Mesh):** You have several intersecting surfaces and you want to create a single mesh from all of them using the `Mesh` command. If you `Join` them, you might get multiple separate meshes. By using `NonmanifoldMerge` first, you create a single object that will result in a single, continuous mesh (though it will still be non-manifold).

### Other Information
This is an advanced tool for creating complex geometry that does not need to adhere to the rules of solid modeling.

---

## 438. Notes

### Short Info
Open a text window for notes.

### Detailed Description
The **Notes** command opens a simple, floating text box where you can type and store notes. The content of the notes window is saved with your 3DM file.

### Steps to use the command
1.  Run the command `Notes`.
2.  The Notes window will appear.
3.  Type your text into the window. It is saved automatically.

### Command Options & Toggles
The options are the text formatting controls within the Notes window itself.

### Note for better use
This is a good place to store general information about a project, such as client details, stone dimensions, or manufacturing instructions that don't need to be attached to a specific object.

### Practical Use Cases
* **Use Case 1 (Project Brief):** When you start a new project for a client, you can open the `Notes` window and paste in the client's name, contact information, due date, and a description of the design requirements. This information will now be permanently stored with the 3D model file.
* **Use Case 2 (Manufacturing Instructions):** You can use the Notes to write detailed instructions for the jeweler or stone setter, such as "Set all 1.5mm stones with a bright cut" or "Final weight should be approx. 8.5g in 14k gold."

### Other Information
This is a simple but very useful tool for keeping project information organized and attached to the relevant file.

---

## 439. Offset

### Short Info
Copy a curve parallel to the original.

### Detailed Description
The **Offset** command is a fundamental 2D editing tool that creates a new curve that is a parallel copy of an existing curve at a specified distance.

### Steps to use the command
1.  Run the command `Offset`.
2.  At the **Select curve to offset** prompt, select a curve.
3.  The command line will show options. Click the **Distance** option and enter a value.
4.  Click on the side of the original curve where you want the new curve to be created.

### Command Options & Toggles
* **Distance:** Sets the distance between the two curves.
* **Corner (Sharp/Round/Smooth):** Controls how the corners of the offset curve are created.
* **ThroughPoint:** Allows you to create the offset by picking a point that the new curve must pass through.

### Note for better use
The `Offset` command is for curves. The 3D equivalent for surfaces is `OffsetSrf`.

### Practical Use Cases
* **Use Case 1 (Creating a Bezel Wall):** You have drawn a single curve representing the outline of a gemstone. To create the bezel, you can use `Offset` to create a second, larger curve around the first one. The space between these two curves defines the thickness of the bezel wall. You can then `Loft` the two curves to create the 3D bezel.
* **Use Case 2 (Creating a Shank Profile):** You have drawn the outer profile of a ring shank. You can use `Offset` to create the inner profile, giving the shank its thickness.

### Other Information
This is one of the most frequently used commands for creating geometry with a consistent thickness.

---

## 440. OffsetCrvOnSrf

### Short Info
Copy a curve on a surface parallel to the original.

### Detailed Description
The **OffsetCrvOnSrf** (Offset Curve On Surface) command creates a parallel copy of a curve that lies on a surface. The new curve will also lie on the surface, following its curvature.

### Steps to use the command
1.  Run the command `OffsetCrvOnSrf`.
2.  At the **Select curve on surface to offset** prompt, select the curve.
3.  At the **Select base surface** prompt, select the surface the curve is on.
4.  Define the offset distance and click on the side you want the new curve to be.

### Command Options & Toggles
* **Distance:** Sets the offset distance.
* **ThroughPoint:** Creates the offset by picking a point on the surface.

### Note for better use
The input curve must lie on the surface for this command to work.

### Practical Use Cases
* **Use Case 1 (Creating a Channel):** You have drawn a single curve down the middle of a curved ring shank where you want a channel setting to be. You can use `OffsetCrvOnSrf` to create two new curves, one on each side of the center curve. These two new curves are the perfect boundaries for your channel.
* **Use Case 2 (Creating an Inlay Boundary):** You have a decorative curve on the surface of a pendant. You can `OffsetCrvOnSrf` to create a parallel boundary curve, defining an area that you can then recess for an enamel or stone inlay.

### Other Information
This is an essential tool for creating parallel line designs on curved 3D surfaces.


---

## 441. OffsetMesh

### Short Info
Copy a mesh parallel to the original.

### Detailed Description
The **OffsetMesh** command creates a new mesh that is a parallel copy of an existing mesh. This is the primary method for giving a mesh object thickness or creating a shell. The command pushes each vertex of the mesh outward or inward along its vertex normal.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `OffsetMesh`.
3.  At the **Offset distance** prompt, enter a numerical value. A positive number offsets outward, a negative number offsets inward.
4.  A new mesh object will be created.

### Command Options & Toggles
* **Direction (Flipped/BothSides):**
    * **Flipped:** Reverses the offset direction.
    * **BothSides:** Offsets in both the inward and outward directions simultaneously.
* **Solid (Yes/No):** If Yes, the command will create connecting faces between the original and offset mesh boundaries to create a closed, solid object.
* **DeleteInput (Yes/No):** Deletes the original mesh.

### Note for better use
For this command to create a clean, solid result, the input mesh must be a good quality, manifold object. The `Solid=Yes` option is essential for creating 3D printable shells from single-surface meshes.

### Practical Use Cases
* **Use Case 1 (Creating a Shell):** You have an STL file of a pendant that is just a single, open surface, but you need it to be a solid object with a 1mm thickness for 3D printing. You would run `OffsetMesh`, enter a distance of 1, and make sure the `Solid` option is set to Yes. This will create a solid, printable shell.
* **Use Case 2 (Hollowing a Solid):** You have a solid mesh model of a large, chunky ring and you want to hollow it out to save material and weight. You can run `OffsetMesh` with a negative distance (e.g., -1.5) and `Solid=Yes`. This will create a smaller, interior surface and connect it to the original, but you will need to manually create an opening (a "sprue hole") and use boolean operations to subtract the new interior volume. A better command for this specific task is often `Shell`.

### Other Information
This is the mesh equivalent of the `OffsetSrf` command.

---

## 442. OffsetNormal

### Short Info
Offset a curve on a surface in the surface normal direction.

### Detailed Description
The **OffsetNormal** command is a specialized curve editing tool. It takes a curve that lies on a surface and creates a parallel copy, offsetting it in the direction of the surface's normals (straight "out" from the surface).

### Steps to use the command
1.  Run the command `OffsetNormal`.
2.  At the **Select curve to offset** prompt, select a curve that is on a surface.
3.  At the **Select base surface** prompt, select the surface the curve lies on.
4.  Define the offset distance.

### Command Options & Toggles
* **Distance:** Sets the offset distance.
* **ThroughPoint:** Creates the offset by picking a point in space.

### Note for better use
This is different from `OffsetCrvOnSrf`, which creates the new curve *on* the surface. `OffsetNormal` creates the new curve *in space*, floating above or below the surface.

### Practical Use Cases
* **Use Case 1 (Creating Rails for a Raised Channel):** You have a curve on the surface of a ring where you want to build a raised channel setting. `OffsetNormal` can be used to lift a copy of that curve straight off the surface. You can then use this new, elevated curve as a rail for a `Sweep` command to build the channel walls.

### Other Information
This is a specialized tool for creating 3D construction geometry based on a surface's form.

---

## 443. OffsetSrf

### Short Info
Copy a surface or polysurface parallel to the original.

### Detailed Description
The **OffsetSrf** (Offset Surface) command is a fundamental solid modeling tool that creates a new surface or polysurface that is a parallel copy of the original. This is the primary method for giving thickness to a NURBS object or creating a shell.

### Steps to use the command
1.  Select the surface or polysurface to offset.
2.  Run the command `OffsetSrf`.
3.  The command line will show several options. Set your desired distance.
4.  Arrows will appear on the object indicating the offset direction. Click the arrows or the `FlipAll` option to change the direction.
5.  Press Enter to create the offset surface.

### Command Options & Toggles
* **Distance:** Sets the distance between the original and offset surface.
* **FlipAll:** Reverses the offset direction for all selected surfaces.
* **Solid (Yes/No):** If Yes, the command will create connecting faces between the original and offset surface boundaries to create a closed, solid object.
* **Tolerance:** Sets the tolerance for the offset operation.

### Note for better use
Offsetting complex, tightly curved surfaces inward can sometimes cause the offset surface to self-intersect or fail. If this happens, you may need to offset by a smaller distance or manually remodel the problematic areas. The `Shell` command is a specialized version of this tool for hollowing out closed solids.

### Practical Use Cases
* **Use Case 1 (Creating a Shell):** This is the most common use. You have modeled a pendant as a single, open surface. To make it a solid for 3D printing, you run `OffsetSrf`, set the `Solid` option to Yes, and enter a thickness (e.g., 1.0mm). This creates a perfect, solid shell.
* **Use Case 2 (Creating an Inlay Pocket):** You have the top surface of a signet ring. You can use `OffsetSrf` with a negative distance to create a second surface just inside the first one. You can then use these two surfaces to create a solid cutter to boolean a shallow pocket for an inlay.

### Other Information
This is a workhorse command for creating solid parts from single surfaces.

---

## 444. OneLayerOff

### Short Info
Turn off the layer of a selected object.

### Detailed Description
The **OneLayerOff** command is a layer management utility that turns off the layer of a selected object. All objects on that layer will become invisible.

### Steps to use the command
1.  Run the command `OneLayerOff`.
2.  At the **Select object on layer to turn off** prompt, click on an object.
3.  The layer that the object resides on will be turned off.

### Command Options & Toggles
This command has no options.

### Note for better use
This is often faster than finding and turning off the layer in the Layer panel, especially in a file with many layers.

### Practical Use Cases
* **Use Case 1 (Quickly Hiding Components):** You are working on a ring and want to quickly hide all the gemstones to see the metalwork underneath. You can simply run `OneLayerOff` and click on any one of the gemstones. The entire "Gems" layer will instantly turn off.

### Other Information
This is a simple but very useful workflow efficiency tool.

---

## 445. OneLayerOn

### Short Info
Turn one layer on and all others off.

### Detailed Description
The **OneLayerOn** command is a layer management utility that isolates a single layer. It turns on the layer of the object you select and turns every other layer in the model off.

### Steps to use the command
1.  Run the command `OneLayerOn`.
2.  At the **Select object on layer to turn on** prompt, click on an object.
3.  The layer that the object resides on will be turned on, and all other layers will be hidden.

### Command Options & Toggles
This command has no options.

### Note for better use
To turn all the layers back on, you can right-click in the Layer panel and choose "Turn on all layers."

### Practical Use Cases
* **Use Case 1 (Isolating a Part):** You are working on a very complex assembly with dozens of layers. You need to focus only on the objects on the "Prongs" layer. You can run `OneLayerOn` and click on any prong. All other geometry in the model will be hidden, leaving you with a clean view of only the prongs.

### Other Information
This is an essential command for focusing on specific parts of a complex model.

---

## 446. Open

### Short Info
Open an existing model.

### Detailed Description
The **Open** command closes the currently active file and opens an existing model file from your computer or network.

### Steps to use the command
1.  Run the command `Open`.
2.  If your current file has unsaved changes, you will be prompted to save it.
3.  A file browser will appear.
4.  Navigate to and select the file you want to open.
5.  Click "Open."

### Command Options & Toggles
The options in the dialog box allow you to see a thumbnail preview and information about the selected file before opening it.

### Note for better use
This is the standard file-opening command. To bring the contents of another file into your *current* model without closing it, use the `Import` or `Insert` commands.

### Practical Use Cases
* **Use Case 1 (Starting Work):** You are starting your workday and need to continue working on a ring project you saved yesterday. You would use the `Open` command to load the ring's .3dm file.

### Other Information
This is a fundamental file management command.

---

## 447. Options

### Short Info
Open the Rhino Options dialog box.

### Detailed Description
The **Options** command opens the main Rhino Options dialog box. This is the central location for managing all of Rhino's global application settings (which affect every file you open) and the current model's Document Properties (which are settings saved with the specific file).

### Steps to use the command
1.  Run the command `Options`.
2.  The Rhino Options dialog box will appear.
3.  Navigate through the different pages on the left to access and change the settings.

### Command Options & Toggles
The options are the vast array of settings contained within the dialog box.

### Note for better use
There is a key distinction between the top section (Rhino Options) and the bottom section (Document Properties). Changes made in "Rhino Options" (like Aliases, Appearance, Mouse settings) are permanent for your Rhino installation. Changes made in "Document Properties" (like Units, Annotation Styles, Grid) are only for the file you currently have open.

### Practical Use Cases
* **Use Case 1 (Setting Units):** Before starting any new jewelry project, the first step is to run `Options` and go to the Document Properties > Units page to ensure your model units are set to Millimeters.
* **Use Case 2 (Creating an Alias):** You use the `BooleanDifference` command very frequently. You can go to Rhino Options > Aliases and create a new alias "bd" that runs the `BooleanDifference` command. Now you can just type "bd" instead of the full command name.

### Other Information
This is the main control panel for all Rhino settings.

---

## 448. OptionsExport

### Short Info
Save options to a file.

### Detailed Description
The **OptionsExport** command saves your custom Rhino Options settings to an external file (.ini). This allows you to back up your settings or transfer your customized workspace environment to another computer.

### Steps to use the command
1.  Run the command `OptionsExport`.
2.  A file save dialog will appear.
3.  Choose a location and name for your settings file.
4.  Click "Save."

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Migrating to a New Computer):** You have just gotten a new computer and want to set up Rhino with all the same custom toolbars, aliases, and display modes that you had on your old machine. On the old computer, you run `OptionsExport` to save your settings to a file. On the new computer, you use the `OptionsImport` command to load that file, instantly restoring your entire custom environment.

### Other Information
This is a key utility for backing up and transferring your personalized workspace.

---

## 449. Options (Duplicate Entry)

### Short Info
Open the Rhino Options dialog box.

### Detailed Description
(This is a duplicate entry in the source documentation list, pointing to the same command as #447). The **Options** command opens the main Rhino Options dialog box, which is the central location for managing all global application settings and the current model's Document Properties.

### Steps to use the command
1.  Run the command `Options`.
2.  The Rhino Options dialog box will appear.

### Command Options & Toggles
The options are the settings within the dialog box.

### Note for better use
It is a good practice to create a template file with all of your preferred Document Properties (like units set to millimeters) and use that template to start all new projects.

### Practical Use Cases
* **Use Case 1 (Setting Up a New Project):** Before you begin any new jewelry model, the first step should be to run `Options` and go to the Document Properties > Units page to ensure your model units are set to Millimeters.

### Other Information
This entry is a duplicate of command #447.

---

## 450. OptionsImport

### Short Info
Restore options from a file.

### Detailed Description
The **OptionsImport** command restores your Rhino Options settings from an external file (.ini) that was created with the `OptionsExport` command. This allows you to load a backed-up or shared workspace environment.

### Steps to use the command
1.  Run the command `OptionsImport`.
2.  A file browser will appear.
3.  Select the .ini settings file you want to load.
4.  A dialog box will appear, allowing you to choose which specific settings you want to import.
5.  Click OK. Your Rhino settings will be updated.

### Command Options & Toggles
The options are the checkboxes in the dialog box that let you choose which categories of settings to import.

### Practical Use Cases
* **Use Case 1 (Restoring a Workspace):** You have just installed Rhino on a new computer. You use `OptionsImport` to load the settings file you saved from your old computer, which instantly restores all of your custom toolbars, aliases, and other preferences.
* **Use Case 2 (Standardizing a Studio):** A CAD manager can create a perfect, standardized Rhino workspace and export the settings. They can then have all the designers in the studio use `OptionsImport` to load this file, ensuring everyone is working with the same interface and tools.

### Other Information
This is the companion command to `OptionsExport`.

---

## 451. Options (Duplicate Entry)

### Short Info
Open the Rhino Options dialog box.

### Detailed Description
(This is a duplicate entry in the source documentation list, pointing to the same command as #447). The **Options** command opens the main Rhino Options dialog box, which is the central location for managing all global application settings and the current model's Document Properties.

### Steps to use the command
1.  Run the command `Options`.
2.  The Rhino Options dialog box will appear.

### Command Options & Toggles
The options are the settings within the dialog box.

### Note for better use
It is a good practice to create a template file with all of your preferred Document Properties (like units set to millimeters) and use that template to start all new projects.

### Practical Use Cases
* **Use Case 1 (Setting Up a New Project):** Before you begin any new jewelry model, the first step should be to run `Options` and go to the Document Properties > Units page to ensure your model units are set to Millimeters.

### Other Information
This entry is a duplicate of command #447.

---

## 452. OptionsPage

### Short Info
Open a specific page in the Options dialog.

### Detailed Description
The **OptionsPage** command is a utility that opens the Rhino Options dialog box directly to a specific page that you name. This is a shortcut to avoid having to open the main dialog and then navigate to the page you want.

### Steps to use the command
1.  Run the command `OptionsPage`.
2.  At the **Page name** prompt, type the name of the page you want to open (e.g., "Units", "Grid").
3.  The Rhino Options dialog box will open with that page already selected.

### Command Options & Toggles
This command has no options other than the page name you provide.

### Note for better use
This command is most useful when creating custom toolbar buttons or macros for quick access to a settings page you use frequently.

### Practical Use Cases
* **Use Case 1 (Custom Toolbar):** You frequently need to adjust the render mesh settings for your models. You could create a custom button on your toolbar with the macro `! _DocumentPropertiesPage Mesh` to instantly open the mesh settings without any extra clicks.

### Other Information
This is a simple workflow efficiency command for power users.

---

## 453. Orient

### Short Info
Transform objects using two reference and two target points.

### Detailed Description
The **Orient** command is a powerful transformation tool that moves, rotates, and scales an object in a single operation. It works by asking you to define a line on the object you want to move (using two reference points) and then a corresponding line in the scene where you want the object to go (using two target points). The command will transform the object so that the reference line perfectly matches the target line.

### Steps to use the command
1.  Select the object(s) to orient.
2.  Run the command `Orient`.
3.  At the **Reference point 1** prompt, pick a first point on or near your object.
4.  At the **Reference point 2** prompt, pick a second point on or near your object.
5.  At the **Target point 1** prompt, pick the destination for the first reference point.
6.  At the **Target point 2** prompt, pick the destination for the second reference point.

### Command Options & Toggles
* **Copy:** Creates a copy of the object instead of moving the original.
* **Scale (None/1D/3D):** Controls whether the object is also scaled to fit the new location. `3D` scaling is common.

### Note for better use
This command is extremely useful for placing components precisely. Using object snaps for all four points is essential.

### Practical Use Cases
* **Use Case 1 (Placing a Gemstone):** You have a ring shank and a gemstone model off to the side. You want to place the stone on the shank. You can run `Orient`, select the stone, and for the reference points, pick the two opposite quadrant points on the stone's girdle. For the target points, you would pick two corresponding points on the top of the shank. The stone will be moved, rotated, and scaled (if the Scale option is on) to fit perfectly between those two points.
* **Use Case 2 (Aligning a Bezel):** You have a bezel that needs to be placed on an angled surface. `Orient` is the perfect tool to take the bezel and align it to the angle of the surface in one step.

### Other Information
The `Orient3Pt` command is an even more powerful version that gives you full 3D control by using three reference and target points.

---

## 454. Orient3Pt

### Short Info
Transform objects using three reference and three target points.

### Detailed Description
The **Orient3Pt** (Orient 3 Points) command is an advanced transformation tool that moves, rotates, and scales an object in full 3D space. It works by asking you to define a plane on the object you want to move (using three reference points) and then a corresponding target plane in the scene (using three target points). The command will transform the object so that the reference plane perfectly matches the target plane.

### Steps to use the command
1.  Select the object(s) to orient.
2.  Run the command `Orient3Pt`.
3.  Pick three reference points on or near your object.
4.  Pick three corresponding target points in the scene.

### Command Options & Toggles
* **Copy:** Creates a copy of the object.
* **Scale (Yes/No):** Controls whether the object is also scaled.

### Note for better use
This command gives you complete control over the position and orientation of an object in 3D space. It is the most precise way to align an object to a complex, angled surface.

### Practical Use Cases
* **Use Case 1 (Setting a Tilted Stone):** You have a ring where a gemstone needs to be set at a complex angle (tilted both forward and sideways). You can use `Orient3Pt` to align the stone perfectly. For the reference points, you could pick the center of the stone's table and two opposite points on its girdle. For the target points, you would pick the corresponding three points on the tilted setting.

### Other Information
This is an advanced transformation tool for complex alignment tasks.

---

## 455. OrientCameraToSrf

### Short Info
Align the view to a surface normal.

### Detailed Description
The **OrientCameraToSrf** (Orient Camera To Surface) command is a viewport navigation tool. It changes the active viewport's camera so that it is looking directly down at a specific point on a surface, aligned with that surface's normal (perpendicular) direction.

### Steps to use the command
1.  Run the command `OrientCameraToSrf`.
2.  At the **Select surface to orient camera to** prompt, select a surface.
3.  At the **Point on surface for camera to look at** prompt, click a location on that surface.
4.  The viewport will change to look straight down at that point.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a very fast way to get a "plan" view of a curved or angled surface, which is essential for working on that surface.

### Practical Use Cases
* **Use Case 1 (Working on a Curved Surface):** You are about to draw a pattern or place objects on a complex, doubly-curved surface. To make it easier to work, you can use `OrientCameraToSrf` to align your view to be perpendicular to your work area. This, combined with setting a custom `CPlane` to the surface, gives you a temporary 2D-like environment for working on a 3D shape.

### Other Information
This is a key command for setting up your view and construction plane for working on non-planar surfaces.

---

## 456. OrientCrvToEdge

### Short Info
Align a curve to a surface edge.

### Detailed Description
The **OrientCrvToEdge** (Orient Curve To Edge) command is a specialized transformation tool that moves and rotates a planar curve to align it with a selected surface edge.

### Steps to use the command
1.  Run the command `OrientCrvToEdge`.
2.  Select a planar curve.
3.  Select a surface edge.
4.  The curve will be moved and rotated to align with the start of the edge.

### Command Options & Toggles
* **Copy:** Creates a copy of the curve.
* **Flip:** Flips the alignment of the curve.

### Note for better use
This command is useful for preparing profile curves for a `Sweep` operation.

### Practical Use Cases
* **Use Case 1 (Preparing a Sweep):** You have a rail curve for a ring shank and a separate profile curve. You can use `OrientCrvToEdge` to quickly snap the profile curve to the start of the rail curve in the correct orientation, ready for the `Sweep1` command.

### Other Information
This is a specialized setup tool for surfacing workflows.

---

## 457. OrientOnCrv

### Short Info
Copy and orient an object on a curve.

### Detailed Description
The **OrientOnCrv** (Orient On Curve) command is a transformation tool that copies and orients an object to a specific location on a path curve. The object is oriented to be perpendicular to the curve at that point.

### Steps to use the command
1.  Select the object(s) to orient.
2.  Run the command `OrientOnCrv`.
3.  Pick a base point on the object.
4.  Select the path curve.
5.  Click a point on the path curve to place the object.

### Command Options & Toggles
* **Copy:** Creates a copy of the object.
* **Rotation:** Allows you to set a rotation angle after placing the object.

### Note for better use
This command is for placing a single object or a few objects at specific, manually picked locations. For placing many objects at even intervals, use the `ArrayCrv` command.

### Practical Use Cases
* **Use Case 1 (Placing a Single Prong):** You have a ring rail and a single prong. You can use `OrientOnCrv` to place the prong precisely at the 12 o'clock position on the ring rail, perfectly oriented to the curve.
* **Use Case 2 (Manual Stone Layout):** You are creating a scattered, asymmetrical layout of gemstones along a curve. `OrientOnCrv` allows you to click and place each stone individually at irregular intervals along the path.

### Other Information
This is a manual placement tool that is a good companion to the automated array commands.

---

## 458. OrientOnSrf

### Short Info
Copy and orient an object on a surface.

### Detailed Description
The **OrientOnSrf** (Orient On Surface) command is a transformation tool that copies and orients an object to a specific location on a target surface. The object is oriented to be normal (perpendicular) to the surface at that point.

### Steps to use the command
1.  Select the object(s) to orient.
2.  Run the command `OrientOnSrf`.
3.  Pick a base point on the object.
4.  Select the target surface.
5.  Click a point on the surface to place the object.

### Command Options & Toggles
* **Copy:** Creates a copy of the object.
* **Rotation:** Allows you to set a rotation angle after placing the object.

### Note for better use
This command is for placing a single object or a few objects at specific, manually picked locations on a surface. For placing many objects in a grid, use `ArraySrf`.

### Practical Use Cases
* **Use Case 1 (Placing a Single Setting):** You have a complex, organic ring shank and a single bezel setting. You can use `OrientOnSrf` to interactively slide the bezel along the surface of the shank until you find the perfect position, ensuring it is always oriented correctly to the curved surface.
* **Use Case 2 (Adding Decorative Elements):** You want to place a few small, decorative spheres on the surface of a pendant in a scattered, random pattern. `OrientOnSrf` is the perfect tool for this manual placement.

### Other Information
This is a fundamental tool for assembling components on curved surfaces.

---

## 459. Ortho

### Short Info
Restrict cursor movement to an angle.

### Detailed Description
The **Ortho** command is a modeling aid that restricts the movement of the mouse cursor to specific angles relative to the construction plane. By default, it restricts movement to 90-degree increments (horizontal and vertical).

### Steps to use the command
1.  Run the command `Ortho`.
2.  The command line will show the current state (On or Off).
3.  Click the option to toggle it.
4.  Alternatively, click the "Ortho" pane in the Status Bar.

### Command Options & Toggles
* **OrthoAngle:** Allows you to change the angle that the cursor snaps to (e.g., you can set it to 45 degrees).

### Note for better use
Holding down the **Shift** key is the universal shortcut to temporarily toggle Ortho mode on or off while you are in the middle of another command. This is one of the most important shortcuts to learn.

### Practical Use Cases
* **Use Case 1 (Drawing Straight Lines):** You need to draw a perfectly horizontal or vertical line. You can turn on Ortho before running the `Line` command to ensure the line is perfectly straight.
* **Use Case 2 (Precise Movement):** You need to move an object exactly 5mm to the right. You can select the object, run the `Move` command, pick a base point, turn on Ortho, drag the mouse to the right, type "5", and press Enter.

### Other Information
This is an essential modeling aid for all forms of precision drawing and modeling.

---

## 460. OrthoAngle

### Short Info
Set the Ortho angle.

### Detailed Description
The **OrthoAngle** command is a utility that sets the angle used by the `Ortho` command. While the default is 90 degrees, you can use this command to set any angle you want.

### Steps to use the command
1.  Run the command `OrthoAngle`.
2.  At the **New angle** prompt, type a number and press Enter.

### Command Options & Toggles
This command has no options other than the angle value.

### Practical Use Cases
* **Use Case 1 (Isometric Drawing):** You are creating a 2D drawing in an isometric style. You can set the `OrthoAngle` to 30 degrees. Now, when you turn on Ortho, your lines will snap to 30-degree increments, making it easy to create the isometric drawing.

### Other Information
This is a user-preference setting for the `Ortho` modeling aid.

---

## 461. Osnap

### Short Info
Set object snaps.

### Detailed Description
The **Osnap** command opens and controls the Object Snap panel. Object snaps (Osnaps) are a critical modeling aid that forces your cursor to snap to precise locations on existing objects, such as endpoints, midpoints, centers, and intersections. The Osnap panel allows you to turn these different types of persistent snaps on and off.

### Steps to use the command
1.  Run the command `Osnap`.
2.  The Osnap panel will appear (or the command line will show options).
3.  Check the boxes for the snaps you want to be persistently active (e.g., `End`, `Mid`, `Cen`).

### Command Options & Toggles
The options are the different types of snaps you can enable:
* **End:** Snaps to the end of a curve.
* **Mid:** Snaps to the midpoint of a curve.
* **Cen:** Snaps to the center of a circle or arc.
* **Int:** Snaps to the intersection of two objects.
* **Perp:** Snaps perpendicular to a curve.
* **Tan:** Snaps tangent to a curve.
* **Quad:** Snaps to the quadrant points of a circle or arc.
* **Knot:** Snaps to a knot on a curve or surface.
* **Point:** Snaps to a point object.
* **Vertex:** Snaps to a mesh vertex.

### Note for better use
You can temporarily activate a single object snap for one pick, even if it is not persistently on, by typing the first three letters of its name while in a command (e.g., typing "end" and pressing Enter). Clicking the "Disable" button in the Osnap panel temporarily turns all persistent snaps off.

### Practical Use Cases
* **Use Case 1 (Precise Drawing):** You need to draw a line that goes from the exact end of one curve to the exact center of a circle. You would make sure that the `End` and `Cen` Osnaps are turned on. When you run the `Line` command, your cursor will automatically jump to these precise locations as you move it near them.

### Other Information
Mastering the use of object snaps is arguably the single most important skill for accurate and professional CAD modeling.

---

## 462. PackTextures

### Short Info
Pack textures of a polysurface.

### Detailed Description
The **PackTextures** command is a specialized utility for managing textures on a polysurface. It is designed to take a polysurface where each face has a different texture and combine all of those textures into a single, efficient image file and a single material.

### Steps to use the command
1.  Select a polysurface that has multiple textures applied to its faces.
2.  Run the command `PackTextures`.
3.  A file save dialog will appear for you to name the new, combined texture file.
4.  The command will create a new material with the packed texture and apply it to the object.

### Command Options & Toggles
This command has no options.

### Note for better use
This is an advanced tool for optimizing models for export to other applications, particularly for game development or real-time rendering, where using a single texture for an object is much more efficient.

### Practical Use Cases
* **Use Case 1 (Game Asset Creation):** A game artist has created a model of a treasure chest in Rhino, with a different wood texture on each face. To optimize it for the game engine, they would use `PackTextures` to combine all the wood textures into a single image map.

### Other Information
This is a specialized texture optimization tool.

---

## 463. Pan

### Short Info
Shift the view camera and target.

### Detailed Description
The **Pan** command is a fundamental viewport navigation tool. It slides the camera's view parallel to the view plane, without rotating or zooming. It is like sliding a piece of paper around on your desk.

### Steps to use the command
1.  Run the command `Pan`.
2.  Click and drag in the viewport to pan the view.

### Command Options & Toggles
This command has no options.

### Note for better use
The universal and much faster way to pan is to hold down the **right mouse button** and drag in any orthographic viewport (Top, Front, Right), or to hold down **Shift + right mouse button** and drag in the Perspective view.

### Practical Use Cases
* **Use Case 1 (Adjusting the View):** You have zoomed in on a detail, but it is in the corner of your screen. You use Pan to slide the view so that the detail is in the center of the viewport, making it easier to work on.

### Other Information
This is a core navigation command, though it is almost always activated with the mouse shortcuts rather than by typing the command.

---

## 464. Parabola

### Short Info
Draw a parabolic curve.

### Detailed Description
The **Parabola** command is a 2D drawing tool used to create a parabolic curve. A parabola is a specific type of smooth, U-shaped curve defined by its focus and vertex.

### Steps to use the command
1.  Run the command `Parabola`.
2.  Follow the prompts to define the parabola by picking its focus, direction, and start/end points.

### Command Options & Toggles
* **3Point:** Creates the parabola by picking three points it must pass through.

### Practical Use Cases
* **Use Case 1 (Reflector Design):** Parabolic shapes are used in the design of reflectors for lights and antennas because they reflect parallel rays to a single focal point. An engineer designing a reflector would use this command to create the precise profile. This command has very limited use in typical jewelry design.

### Other Information
This is a specialized curve creation tool for a specific mathematical shape.

---

## 465. Paraboloid

### Short Info
Draw a parabolic surface.

### Detailed Description
The **Paraboloid** command is a solid creation tool that creates a 3D parabolic surface or a closed solid paraboloid. It is the 3D equivalent of the `Parabola` command.

### Steps to use the command
1.  Run the command `Paraboloid`.
2.  Follow the prompts to define the base and focus of the shape.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Creating a Bullet Shape):** The `Paraboloid` command is a fast way to create a smooth, rounded, bullet-like shape that can be used as a decorative element or as a base for sculpting.

### Other Information
This is a specialized primitive creation tool.

---

## 466. Paste

### Short Info
Insert objects from the Clipboard.

### Detailed Description
The **Paste** command inserts the contents of the Windows clipboard into the current model. This is used after a `Copy` or `Cut` command to place the geometry.

### Steps to use the command
1.  Use `Copy` or `Cut` to place objects on the clipboard.
2.  Run the command `Paste`.
3.  The objects from the clipboard will be added to your model.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the equivalent of the standard Windows shortcut Ctrl+V. Using the shortcut is much faster than typing the command.

### Practical Use Cases
* **Use Case 1 (Moving Objects Between Files):** You have designed a custom clasp in one Rhino file and want to use it in your current ring project. You can open the clasp file, select the clasp, use `Copy` (Ctrl+C), switch to your ring file, and use `Paste` (Ctrl+V) to bring it in.

### Other Information
This is a fundamental command for managing objects within and between files.

---

## 467. Patch

### Short Info
Fit a surface through curves and point objects.

### Detailed Description
The **Patch** command is a powerful free-form surfacing tool. It creates a NURBS surface that fits through a selection of input curves, points, and/or surface edges. It is extremely useful for filling complex, irregular holes or for creating a single, smooth surface over a complex boundary.

### Steps to use the command
1.  Select the curves, points, or edges that will define the boundary and shape of the patch.
2.  Run the command `Patch`.
3.  A dialog box will appear with options for controlling the surface fit.
4.  A preview of the surface will be shown. Adjust the settings and click OK.

### Command Options & Toggles
The options are in a dialog box:
* **U/V Spans:** Controls the number of control points on the resulting surface.
* **Stiffness:** Controls how much the patch surface will "bulge" or how closely it will follow the input curves.
* **Adjust Tangency:** Allows you to make the patch surface tangent to adjacent surfaces for a smoother connection.

### Note for better use
The `Patch` command works best when there is a closed loop of input curves. It can sometimes produce unexpected results if the input is very complex or has large gaps. The `Starting surface` option is very useful for getting a better initial fit.

### Practical Use Cases
* **Use Case 1 (Closing an Irregular Hole):** You have a model with a complex, non-planar, five-sided hole that cannot be closed with simple commands. You can use `DupEdge` to get the curves around the hole, and then use `Patch` with these curves as input to create a smooth surface that fills the opening.
* **Use Case 2 (Creating a Gemstone Top):** You have the girdle outline of a free-form, fantasy-cut gemstone. `Patch` can be used to create a single, smooth domed surface for the crown of the stone using only the outer curve as input.

### Other Information
This is a workhorse command for free-form surfacing and model repair.

---

## 468. PatchSingleFace

### Short Info
Fill a hole in a mesh with a single face.

### Detailed Description
The **PatchSingleFace** command is a mesh repair tool that attempts to fill a hole in a mesh with a single mesh face.

### Steps to use the command
1.  Run the command `PatchSingleFace`.
2.  At the **Select mesh boundary edges** prompt, select the edges of a single hole in your mesh.
3.  Press Enter. A single n-gon (a polygon with more than 4 sides) will be created to fill the hole.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is useful for quickly closing holes where the quality of the patch is not critical. However, creating a single large n-gon can sometimes be problematic for other mesh operations. It is often better to fill a hole with multiple triangles using `FillMeshHole` or manually with `3DFace`.

### Practical Use Cases
* **Use Case 1 (Quick Visual Patch):** You have a hole in a mesh that you need to close quickly for a visual mock-up, and you are not concerned with perfect polygon flow. `PatchSingleFace` can close it in one step.

### Other Information
This is a simple mesh repair tool.

---

## 469. Pause

### Short Info
Stop a script to allow for user input.

### Detailed Description
The **Pause** command is a utility used in scripts and macros. It temporarily halts the execution of the script and allows the user to interact with the model, for example, to select an object, pick a point, or change a view. The script will resume after the user has completed the action.

### Steps to use the command
1.  This command is used inside a macro or script file.
2.  When the script reaches the `Pause` command, it will stop and wait for user input.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Interactive Script):** You are writing a script to automate the process of creating a bezel. You can use `Pause` to stop the script and allow the user to manually select the gemstone they want to create the bezel around. After they select the stone, the script will resume and build the bezel automatically.

### Other Information
This is a fundamental command for creating interactive scripts and macros.

---

## 470. PerspectiveAngle

### Short Info
Set the view angle of a perspective view.

### Detailed Description
The **PerspectiveAngle** command is a viewport management tool that sets the camera's "lens length" or "field of view" for a perspective viewport. A smaller angle is like a telephoto lens (less distortion, flatter look), while a larger angle is like a wide-angle lens (more distortion, greater sense of depth).

### Steps to use the command
1.  Make a perspective viewport active.
2.  Run the command `PerspectiveAngle`.
3.  At the **New perspective view angle** prompt, enter a number (in degrees) and press Enter.

### Command Options & Toggles
This command has no options other than the angle value.

### Note for better use
The default angle is 50 degrees, which is similar to a standard camera lens. For jewelry rendering, a slightly longer lens (a smaller angle, like 30-35 degrees) often produces a more pleasing, less distorted image.

### Practical Use Cases
* **Use Case 1 (Product Rendering):** You are setting up a final render of a ring and want to minimize perspective distortion. You can use `PerspectiveAngle` to change the lens length to 35 degrees to get a more flattering, professional-looking shot.
* **Use Case 2 (Dramatic Shots):** You want to create a dramatic, "in-your-face" render of a piece. You could set the angle to 70 or 80 degrees to create an exaggerated wide-angle effect.

### Other Information
This is the same setting as the "Lens length" found in the Viewport Properties panel.

---

## 471. PerspectiveMatch

### Short Info
Align the view to an image.

### Detailed Description
The **PerspectiveMatch** command is a specialized viewport tool that helps you adjust a perspective view's camera settings to match the perspective of a background photograph. It works by having you place corresponding pairs of points on the 2D background image and on your 3D model. The command then calculates the correct camera position, rotation, and lens length to make the 3D model align with the image.

### Steps to use the command
1.  Place a background image in a perspective viewport using the `BackgroundBitmap` command.
2.  Run the command `PerspectiveMatch`.
3.  Follow the prompts to pick pairs of matching points on the 2D image and the 3D model.
4.  The view will update to match the perspective of the image.

### Command Options & Toggles
This command has no options; it is an interactive, sequential process.

### Note for better use
This command requires a background image with strong, clear perspective lines to work effectively. It is most useful for architectural visualization or for creating composite images where a 3D model needs to look like it is part of a real photograph.

### Practical Use Cases
* **Use Case 1 (Photo Compositing):** You want to create a render of a ring that looks like it is sitting on a specific table in a photograph. You would place the photograph as a background bitmap, model a simple box to represent the table, and then use `PerspectiveMatch` to align your view so that your 3D box perfectly matches the perspective of the table in the photo. You can then place your ring model on the box and it will appear correctly integrated into the scene.

### Other Information
This is an advanced tool for visualization and rendering, with limited use in day-to-day jewelry modeling.

---

## 472. PictureFrame

### Short Info
Create a surface with a bitmap texture.

### Detailed Description
The **PictureFrame** command creates a planar NURBS surface that has an image file already applied to it as a texture. Unlike `BackgroundBitmap`, which is a 2D overlay, the object created by `PictureFrame` is a real piece of geometry in your 3D scene. It can be moved, scaled, rotated, and interacted with like any other surface.

### Steps to use the command
1.  Run the command `PictureFrame`.
2.  A file browser will open. Select an image file.
3.  You will be prompted to draw a rectangle in the viewport to place the picture frame.
4.  A new planar surface with the selected image as its material texture will be created.

### Command Options & Toggles
* **EmbedBitmap:** Determines whether the image file is saved inside your 3DM file or linked to an external file.
* **AutoName:** Automatically names the object based on the image filename.

### Note for better use
The created surface is automatically placed in a "Picture Frame" material in the V-Ray material editor, with the image in the diffuse slot. This makes it render-ready immediately.

### Practical Use Cases
* **Use Case 1 (3D Reference Images):** This is the most common use. You have a sketch of a ring that you want to trace. Using `PictureFrame` places the sketch into the 3D scene as an object. You can then move it, rotate it, and even set its transparency to make it an easy-to-use reference plane for modeling. This is often preferred over `BackgroundBitmap` because the image is part of the model.
* **Use Case 2 (Render Backdrops):** You are creating a render and want a specific image to appear in the background (e.g., a photo of a landscape). You can use `PictureFrame` to place this image as a large surface behind your model.

### Other Information
This command has largely replaced `BackgroundBitmap` as the preferred method for working with reference images.

---

## 473. Pipe

### Short Info
Create a surface with a circular profile around a curve.

### Detailed Description
The **Pipe** command is a fundamental solid creation tool that creates a 3D tube, or "pipe," with a circular profile along a selected path curve. It is one of the most common ways to turn 2D line work into 3D solid geometry.

### Steps to use the command
1.  Select the curve(s) you want to turn into a pipe.
2.  Run the command `Pipe`.
3.  A dialog box or command line options will appear.
4.  Set the start and end radius for the pipe.
5.  Press Enter to create the pipe object.

### Command Options & Toggles
* **Radius:** Sets the radius of the pipe. You can set different radii for the start and end to create a tapered pipe.
* **Cap (None/Flat/Round):** Determines the shape of the ends of the pipe. `Round` is very common for creating a soft finish on wire work.
* **WallThickness:** Creates a hollow tube instead of a solid pipe.

### Note for better use
The `Pipe` command creates real, editable NURBS geometry. This is different from `ApplyCurvePiping`, which is only a visual display effect. If you need to 3D print or boolean an object, you must use `Pipe`.

### Practical Use Cases
* **Use Case 1 (Creating Wire Work):** This is the primary use. You have drawn a complex filigree or scrollwork pattern using curves. To turn this 2D line drawing into a 3D, solid object, you select all the curves and use the `Pipe` command to give them a physical thickness (e.g., a 0.8mm radius).
* **Use Case 2 (Creating Prongs):** You have drawn a line representing the centerline of a prong. You can use the `Pipe` command with different start and end radii to create a tapered, solid prong in a single step.

### Other Information
This is a workhorse command used constantly in jewelry design to convert curves into solid, manufacturable objects.

---

## 474. PlaceHole

### Short Info
Project a closed curve to a surface to make a hole.

### Detailed Description
The **PlaceHole** command is a specialized trimming tool. It takes one or more closed, planar curves and projects them onto a surface or polysurface to create a hole. It is a faster alternative to using `Project` and then `Trim`. This command is identical in function to `MakeHole`.

### Steps to use the command
1.  Select the closed curve(s) that will define the shape of the hole.
2.  Run the command `PlaceHole`.
3.  At the **Select surface or polysurface to make hole in** prompt, select the object to be cut.
4.  A hole will be created.

### Command Options & Toggles
This command has no options.

### Note for better use
The command projects the curves in the direction of the active view's CPlane normal. Make sure you are in the correct viewport (e.g., Top view) before running the command to ensure the hole is projected in the right direction.

### Practical Use Cases
* **Use Case 1 (Perforating a Surface):** You have designed a flat pendant and have drawn several small, decorative circles on top of it. You can select all the circles, run `PlaceHole`, and select the pendant to cut all the holes in a single operation.

### Other Information
This is a workflow-efficiency command that combines projection and trimming into one step.

---

## 475. Plan

### Short Info
Set the view to a parallel projection plan view.

### Detailed Description
The **Plan** command is a viewport navigation tool that changes the active viewport to a top-down, parallel projection "plan" view. It centers the view on the origin of the current construction plane and makes the camera look straight down at it.

### Steps to use the command
1.  Make a viewport active.
2.  Run the command `Plan`.
3.  The view will change to a plan view of the active CPlane.

### Command Options & Toggles
This command has no options.

### Note for better use
If you have a custom, tilted CPlane active, running `Plan` will give you a top-down view of that tilted plane, which is extremely useful for working on angled surfaces.

### Practical Use Cases
* **Use Case 1 (Returning to Top View):** You have been tumbling the Top viewport and it is now at an angle. Running `Plan` will instantly snap it back to the proper, flat, top-down orientation.
* **Use Case 2 (Working on a Tilted Plane):** You have set a custom CPlane to the angled face of a bezel. Running `Plan` in that viewport will give you a perfect, head-on view of that face, making it easy to draw or place objects on it.

### Other Information
This is a fundamental navigation command for setting and resetting orthographic views.

---

## 476. Planar

### Short Info
Restrict selections to the same plane.

### Detailed Description
The **Planar** command is a modeling aid that restricts point selection to the same elevation as the last point picked. When Planar mode is on, if you pick a point in a perspective view, all subsequent points you pick will be on the same construction plane as that first point, regardless of what you snap to.

### Steps to use the command
1.  Run the command `Planar`.
2.  The command line will show the current state (On or Off).
3.  Click the option to toggle it.
4.  Alternatively, click the "Planar" pane in the Status Bar.

### Command Options & Toggles
This command is a simple toggle between **On** and **Off**.

### Note for better use
This is a powerful tool for ensuring that all the points of a curve you are drawing lie on the same plane, which is a requirement for many commands like `PlanarSrf`.

### Practical Use Cases
* **Use Case 1 (Drawing a Flat Profile):** You are tracing a reference image in a perspective view and want to ensure the resulting curve is perfectly flat. By turning Planar mode on before you start drawing, you can snap to various 3D points on your model, but Rhino will ensure that all the points for your new curve are created on the same flat plane.

### Other Information
This is an important modeling aid for creating clean, planar geometry.

---

## 477. PlanarMesh

### Short Info
Create a mesh from closed planar curves.

### Detailed Description
The **PlanarMesh** command takes one or more closed, planar curves and creates a single, flat mesh object that fills them. It is the mesh equivalent of the `PlanarSrf` command.

### Steps to use the command
1.  Select one or more closed, planar curves.
2.  Run the command `PlanarMesh`.
3.  A dialog box will appear with options for controlling the mesh density.
4.  Click OK. A new, flat mesh object will be created.

### Command Options & Toggles
The options are in a dialog box and allow you to control the quality and density of the resulting mesh, similar to the `Mesh` command.

### Note for better use
The input curves must be closed and planar for this command to work. If you have curves within other curves, it will correctly create a mesh with holes.

### Practical Use Cases
* **Use Case 1 (Creating a Base for Sculpting):** You have drawn a complex, flat outline for a pendant. You can use `PlanarMesh` to instantly create a flat mesh object from this outline, which can then be taken into a sculpting program or deformed in Rhino.
* **Use Case 2 (Creating a Mesh with Holes):** You have drawn the outer and inner outlines for a washer shape. `PlanarMesh` will create a single, flat mesh object with the center already cut out.

### Other Information
This is a useful tool for creating flat mesh objects from 2D line work.

---

## 478. PlanarSrf

### Short Info
Create a planar surface from planar curves.

### Detailed Description
The **PlanarSrf** (Planar Surface) command is a fundamental surface creation tool. It takes one or more closed, planar curves and creates a single, flat NURBS surface that fills them.

### Steps to use the command
1.  Select one or more closed, planar curves.
2.  Run the command `PlanarSrf`.
3.  A new, flat surface will be created.

### Command Options & Toggles
This command has no options.

### Note for better use
The input curves must be closed and they must be perfectly flat (planar). If the command fails, it is almost always because your input curve is not closed (`ShowEnds`) or not planar (`ProjectToCPlane`). If you select curves that are inside other curves, it will correctly create a surface with holes.

### Practical Use Cases
* **Use Case 1 (Creating a Signet Top):** You have drawn the closed outline of a signet ring top. `PlanarSrf` is the one-step command to turn that flat curve into a flat surface. You can then use a command like `ExtrudeSrf` to give it thickness.
* **Use Case 2 (Creating a Bezel with a Hole):** You have drawn two circles, one for the outer edge of a bezel and one for the inner edge. If you select both circles and run `PlanarSrf`, it will create a single, flat, washer-like surface with the center already cut out.

### Other Information
This is a workhorse command for creating flat surfaces from 2D profiles.

---

## 479. Plane

### Short Info
Draw a rectangular planar surface.

### Detailed Description
The **Plane** command is a basic surface creation tool that draws a simple, rectangular NURBS surface.

### Steps to use the command
1.  Run the command `Plane`.
2.  Follow the prompts for the chosen creation method. For the default method:
    a. At the **First corner of plane** prompt, pick a point.
    b. At the **Other corner** prompt, pick the opposite corner.

### Command Options & Toggles
* **3Point:** Creates a rectangular plane by picking three corner points.
* **Vertical:** Creates a plane that is vertical to the active CPlane.
* **Center:** Creates the plane by picking its center and then a corner.

### Note for better use
A plane is a simple, un-trimmed, degree 1 NURBS surface. It is the most basic type of surface in Rhino.

### Practical Use Cases
* **Use Case 1 (Creating a Base Surface):** You are about to model a piece of jewelry and need a flat "work surface" to build on. The `Plane` command is the fastest way to create this.
* **Use Case 2 (Creating a Cutting Object):** You need to cut a model in half. You can use the `Plane` command to create a large rectangular surface that passes through your model, and then use this plane as the cutting object in the `Trim` or `Split` command.

### Other Information
This is a fundamental primitive creation tool.

---

## 480. PlaneThroughPt

### Short Info
Create a rectangular plane best-fit through points.

### Detailed Description
The **PlaneThroughPt** (Plane Through Points) command is a construction tool that creates a rectangular planar surface that represents the "best fit" through a selection of three or more point objects.

### Steps to use the command
1.  Select three or more point objects.
2.  Run the command `PlaneThroughPt`.
3.  A new rectangular plane will be created that passes through the points.

### Command Options & Toggles
This command has no options.

### Note for better use
If the points are not co-planar, the command will create a plane that has the smallest average distance to all the points.

### Practical Use Cases
* **Use Case 1 (Reverse Engineering):** You have used a digitizer to capture several points from a flat surface on a physical object. You can use `PlaneThroughPt` to create a best-fit plane from these points, which gives you the exact orientation of that surface in 3D space. You can then align a CPlane to this new surface to work on it.

### Other Information
This is a useful tool for reverse-engineering and for finding the orientation of a set of points.

---

## 481. PlayAnimation

### Short Info
Play the animation.

### Detailed Description
The **PlayAnimation** command is a utility that opens the "Animation Preview" window and plays back any animation that has been set up in the model. This includes turntable animations, sun studies, or fly-throughs. It allows you to preview the animation directly in the viewport before committing to a full render of all the frames.

### Steps to use the command
1.  Set up an animation using a command like `Turntable` or `SetFlythroughAnimation`.
2.  Run the command `PlayAnimation`.
3.  The Animation Preview window will appear and begin playing the animation.

### Command Options & Toggles
This command has no options in the command line. The playback controls (Play, Pause, Stop) are located within the Animation Preview window.

### Note for better use
This is a preview tool. It does not create a video file. To save your animation as a video or a sequence of images, you must use the `RecordAnimation` command.

### Practical Use Cases
* **Use Case 1 (Checking a Turntable):** You have set up a 360-degree turntable animation for a ring. Before you start the time-consuming process of rendering all 100 frames, you can use `PlayAnimation` to quickly preview the motion in a shaded viewport. This allows you to check that the rotation speed is correct and the object stays centered in the frame.

### Other Information
This is the primary tool for previewing any animation set up in Rhino.

---

## 482. Point

### Short Info
Draw a single point object.

### Detailed Description
The **Point** command is a fundamental object creation tool. Its sole purpose is to create a single point object at a location you specify in the viewport. Point objects are often used as markers, placeholders, or as reference geometry for other commands.

### Steps to use the command
1.  Run the command `Point`.
2.  At the **Location of point object** prompt, click in the viewport or type coordinates.
3.  A point object is created.

### Command Options & Toggles
This command has no options.

### Note for better use
To create multiple point objects in a sequence, use the `Points` command.

### Practical Use Cases
* **Use Case 1 (Marking a Center):** You need to mark the exact center of a ring for future operations like a polar array. You can use the `Cen` object snap and the `Point` command to place a permanent point object at the center.
* **Use Case 2 (Reference for a Loft):** You are creating a complex lofted surface and need it to pass through a specific location in space. You can place a `Point` object at that location and include it in your selection when you run the `Loft` command.

### Other Information
This is one of the most basic geometric objects in Rhino.

---

## 483. PointCloud

### Short Info
Create a point cloud from point objects.

### Detailed Description
The **PointCloud** command takes a selection of individual point objects and converts them into a single, more efficient "point cloud" object. A point cloud is a single object that contains many points. This is primarily a performance and organization tool, as it is much faster for Rhino to handle one object containing thousands of points than it is to handle thousands of individual point objects.

### Steps to use the command
1.  Select two or more point objects.
2.  Run the command `PointCloud`.
3.  The selected point objects will be converted into a single point cloud object.

### Command Options & Toggles
This command has no options.

### Note for better use
The opposite of this command is `Explode`. If you explode a point cloud, it will be broken back down into its individual point objects.

### Practical Use Cases
* **Use Case 1 (Managing Scan Data):** You have imported data from a 3D scanner, which has come in as thousands of separate point objects. This can make the file slow and difficult to manage. By selecting all the points and running `PointCloud`, you can combine them into a single object, which will significantly improve viewport performance.

### Other Information
This is a data management tool for working with large sets of points.

---

## 484. PointCloudSection

### Short Info
Create a planar curve from the intersection of a plane and a point cloud.

### Detailed Description
The **PointCloudSection** command creates a polyline by intersecting a cutting plane with a point cloud object. It finds all the points in the cloud that lie on or very close to the plane and creates a polyline that connects them.

### Steps to use the command
1.  Select a point cloud object.
2.  Run the command `PointCloudSection`.
3.  You will be prompted to draw a line that defines the cutting plane.
4.  A polyline will be created where the plane intersects the point cloud.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a key tool in the reverse-engineering process. It allows you to extract 2D cross-section curves from 3D scan data.

### Practical Use Cases
* **Use Case 1 (Reverse Engineering a Ring):** You have a 3D scan of a ring as a point cloud. To remodel it as a clean NURBS object, you need its profile curves. You can use `PointCloudSection` to create several cross-section curves along the shank. You can then use these curves as the input for a `Loft` or `Sweep` command to rebuild the 3D shank.

### Other Information
This is a specialized tool for working with point cloud data.

---

## 485. PointDeviation

### Short Info
Report the distance from a surface to points.

### Detailed Description
The **PointDeviation** command is an analysis tool that measures the distance between a set of point objects and a surface. It is used to check how accurately a surface fits a set of reference points. The command displays a "comb" graph on the surface and reports the minimum, maximum, and average distances in the command line.

### Steps to use the command
1.  Run the command `PointDeviation`.
2.  At the **Select points to test** prompt, select one or more point objects and press Enter.
3.  At the **Select surface to test against** prompt, select a surface.
4.  A dialog box will appear, and a visual graph will be displayed in the viewport.

### Command Options & Toggles
The options are in a dialog box:
* **Display Scale:** Controls the length of the "hairs" on the deviation comb graph.
* **Hair Density:** Controls how many lines are displayed.

### Note for better use
This command is very useful for verifying the accuracy of a reverse-engineered surface.

### Practical Use Cases
* **Use Case 1 (Verifying a Rebuilt Surface):** You have captured a set of points from a physical model and have created a new surface that is supposed to fit them. You can use `PointDeviation` to get a detailed report and a visual graph showing exactly how close your new surface is to the original data points at all locations.

### Other Information
This is a high-precision analysis tool for quality control and reverse engineering.

---

## 486. PointGrid

### Short Info
Draw a rectangular grid of point objects.

### Detailed Description
The **PointGrid** command is a point creation tool that creates a rectangular grid of point objects. You define the number of points in the X and Y directions, as well as the spacing between them.

### Steps to use the command
1.  Run the command `PointGrid`.
2.  Follow the prompts to define the number of points and the spacing for the grid.
3.  A grid of point objects will be created on the active construction plane.

### Command Options & Toggles
The options are presented as prompts in the command line for setting the number of points and the grid spacing.

### Practical Use Cases
* **Use Case 1 (Layout for Pavé):** You are about to create a rectangular field of pavé stones. You can use `PointGrid` to create a perfectly spaced grid of points that you can then use as snap points to place your gemstones.
* **Use Case 2 (Base for a Surface):** You want to create a surface using the `SrfPtGrid` (Surface From Point Grid) command. `PointGrid` is the tool you use to create the input grid of points for that command.

### Other Information
This is a simple but useful tool for creating layout and construction geometry.

---

## 487. PointLight

### Short Info
Insert a point light.

### Detailed Description
The **PointLight** command adds a point light source to the model. A point light, also known as an omni-directional light, is a light source that shines in all directions from a single point in space, like a bare light bulb.

### Steps to use the command
1.  Run the command `PointLight`.
2.  At the **Location of point light** prompt, pick a location.
3.  A point light object will be created in your model.

### Command Options & Toggles
This command has no options in the command line. The light's properties (color, intensity, shadow settings) are edited in the Properties panel after it has been created.

### Note for better use
Point lights tend to create sharp, well-defined shadows. For softer, more realistic lighting for jewelry, it is often better to use `RectangularLight` or `LinearLight` objects, which simulate larger light sources.

### Practical Use Cases
* **Use Case 1 (General Illumination):** You need to add some general, overall lighting to your scene. Placing a few `PointLight` objects around your model can provide this base illumination.
* **Use Case 2 (Creating Sparkle):** To create small, sharp "specular" highlights that make a gemstone sparkle in a render, you can place several low-intensity `PointLight` objects very close to the stone's surface.

### Other Information
This is one of the fundamental light types used in 3D rendering.

---

## 488. Points

### Short Info
Draw multiple point objects.

### Detailed Description
The **Points** command is a point creation tool that allows you to create multiple, separate point objects in a single command run. Unlike the `Point` command which ends after creating one point, `Points` will continue to create a new point object every time you click in the viewport until you press Enter.

### Steps to use the command
1.  Run the command `Points`.
2.  At the **Location of point object** prompt, click to place a point.
3.  The prompt will repeat, allowing you to click to place more points.
4.  Press Enter when you are finished.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Marking Multiple Locations):** You are planning a layout for several gemstones on a surface and need to mark the location for each one. The `Points` command allows you to quickly place all the marker points without having to run the command over and over again.

### Other Information
This is the multi-point version of the `Point` command.

---

## 489. PointsFromUV

### Short Info
Create point objects at surface u- and v-coordinates.

### Detailed Description
The **PointsFromUV** command is a utility that creates point objects on a surface at specific U and V coordinate locations that you enter numerically. This allows for the precise, data-driven placement of points on a surface's internal parameter space.

### Steps to use the command
1.  Select a surface.
2.  Run the command `PointsFromUV`.
3.  You will be prompted to enter a U-coordinate and then a V-coordinate.
4.  A point object will be created at that exact parametric location on the surface.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Scripting and Automation):** This command is primarily used in scripts. A script could calculate a specific UV coordinate on a surface and then use `PointsFromUV` to place a point there, which could then be used as a reference for another operation.

### Other Information
This is an advanced tool for users who are scripting or working directly with the mathematical parameter space of a surface.

---

## 490. PointsOff

### Short Info
Turn off control points and edit points.

### Detailed Description
The **PointsOff** command turns off the visibility of control points and edit points for all objects in the model. It is the universal command to exit any point-editing mode.

### Steps to use the command
1.  Run the command `PointsOff`.
2.  All visible control points and edit points will be hidden.

### Command Options & Toggles
This command has no options.

### Note for better use
The keyboard shortcut **F11** is the fastest way to run this command. Pressing the **Esc** key twice will also usually turn off control points.

### Practical Use Cases
* **Use Case 1 (Ending an Edit):** You have finished editing the control points of a curve or surface. You run `PointsOff` (or press F11) to hide the points and see the final, clean shape of the object.

### Other Information
This is the companion command to `PointsOn` and `EditPtOn`.

---

## 491. PointsOn

### Short Info
Display curve and surface control points.

### Detailed Description
The **PointsOn** command turns on the visibility of an object's control points. Control points are the primary method for editing the shape of NURBS curves and surfaces. They form a "cage" or "hull" around the object, and moving a control point will pull the smooth geometry towards it.

### Steps to use the command
1.  Select the object(s) whose control points you want to see.
2.  Run the command `PointsOn`.
3.  The control points will appear.

### Command Options & Toggles
This command has no options.

### Note for better use
The keyboard shortcut **F10** is the fastest way to run this command. To turn the points off, use the `PointsOff` command (F11).

### Practical Use Cases
* **Use Case 1 (Editing a Curve):** You have drawn a curve and need to adjust its shape. You select the curve and run `PointsOn` (or press F10). You can then select and drag the individual control points to fine-tune the curve's shape.
* **Use Case 2 (Editing a Surface):** You have created a surface for a ring shank and want to make it slightly wider in one area. You can turn on its control points, select a row of points, and use the `Scale` command or the Gumball to move them outward, changing the shape of the surface.

### Other Information
This is one of the most fundamental and frequently used editing commands in Rhino.

---

## 492. Polygon

### Short Info
Draw a polygon with a specified number of sides.

### Detailed Description
The **Polygon** command is a 2D drawing tool used to create a closed, equilateral polygon (a shape with equal-length sides), such as a triangle, square, pentagon, hexagon, etc.

### Steps to use the command
1.  Run the command `Polygon`.
2.  At the **Center of polygon** prompt, pick a location.
3.  Drag the mouse to set the size and rotation, and click.

### Command Options & Toggles
* **NumSides:** Allows you to set the number of sides for the polygon.
* **Edge:** Allows you to define the polygon by drawing one of its edges instead of from the center.
* **Inscribed/Circumscribed:** Controls whether the polygon is drawn inside or outside of the defining radius.

### Practical Use Cases
* **Use Case 1 (Drawing Gemstone Shapes):** You need to draw the outline for a trillion (3 sides), princess (4 sides), or hexagonal gemstone. The `Polygon` command is the fastest way to create these perfect, equilateral shapes.
* **Use Case 2 (Creating a Nut Shape):** You are modeling a piece with an industrial aesthetic and need to create a hexagonal nut or bolt head. You would use `Polygon` with `NumSides=6` to create the initial 2D profile.

### Other Information
This is a basic 2D primitive creation tool.

---

## 493. PolygonCount

### Short Info
Report the number of polygons in a mesh.

### Detailed Description
The **PolygonCount** command is a simple analysis tool that reports the number of polygons (faces) in a selected mesh object.

### Steps to use the command
1.  Select one or more mesh objects.
2.  Run the command `PolygonCount`.
3.  The command history will display the total number of polygons in the selection.

### Command Options & Toggles
This command has no options.

### Note for better use
This is useful for checking the density of a mesh before exporting it for 3D printing or to another application. Many applications have limits on the number of polygons they can handle efficiently.

### Practical Use Cases
* **Use Case 1 (Preparing for 3D Printing):** Some 3D printing services have a maximum polygon count for uploaded files. Before exporting your final ring mesh, you can run `PolygonCount` to make sure your file is within the acceptable limits. If it's too high, you may need to use the `ReduceMesh` command.

### Other Information
This is a simple mesh analysis tool.

---

## 494. Polyline

### Short Info
Draw a multi-segment polyline.

### Detailed Description
The **Polyline** command is a fundamental 2D drawing tool that creates a single curve object made up of multiple connected straight-line and/or arc segments. It is one of the most versatile and frequently used drawing tools.

### Steps to use the command
1.  Run the command `Polyline`.
2.  At the **Start of polyline** prompt, pick a point.
3.  Continue picking points to create straight line segments.
4.  To switch to drawing an arc segment, click the `Mode=Arc` option.
5.  Press Enter when you are finished.

### Command Options & Toggles
* **Mode (Line/Arc):** Toggles between drawing straight line segments and arc segments within the same command run.
* **Close:** Closes the polyline by creating a final segment from the last point back to the first.

### Note for better use
The `Polyline` command creates a single object, even if it has many segments. To break it apart into its individual segments, you must use the `Explode` command.

### Practical Use Cases
* **Use Case 1 (Drawing a Shank Profile):** You are drawing the cross-section of a D-shaped ring shank. You can use the `Polyline` command to draw the straight bottom segment, then switch to Arc mode to draw the curved top segment, all while creating a single, clean, closed curve.
* **Use Case 2 (Tracing):** `Polyline` is an excellent tool for tracing reference images that have a combination of straight lines and curves.

### Other Information
This command has largely superseded the older `Lines` command due to its ability to create both lines and arcs.

---

## 495. PolylineOnMesh

### Short Info
Draw a polyline on a mesh.

### Detailed Description
The **PolylineOnMesh** command is a specialized drawing tool that allows you to draw a polyline directly onto the surface of a mesh object. The points you pick are constrained to the mesh surface, and the resulting polyline will follow the contours of the mesh.

### Steps to use the command
1.  Run the command `PolylineOnMesh`.
2.  At the **Select a mesh** prompt, select the mesh you want to draw on.
3.  You will then be prompted to pick the start and subsequent points for the polyline, directly on the mesh surface.
4.  Press Enter when you are finished.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the mesh equivalent of the `InterpCrvOnSrf` command.

### Practical Use Cases
* **Use Case 1 (Marking a Trim Line on an STL):** You have an STL file of a ring and you need to define a line where you want to split it. You can use `PolylineOnMesh` to draw this line directly on the mesh surface. The resulting curve can then be used as a cutter with the `MeshSplit` command.
* **Use Case 2 (Creating a Path on a Scan):** You have a 3D scan of an organic object and you want to draw a path on its surface for placing decorative elements. `PolylineOnMesh` allows you to draw this path directly on the irregular scanned surface.

### Other Information
This is an essential tool for workflows that involve editing or adding details to mesh objects.

---

## 496. PopupMenu

### Short Info
Display the context menu at the cursor.

### Detailed Description
The **PopupMenu** command is a utility that displays a context-sensitive menu at the current location of the mouse cursor. The contents of this menu can be customized.

### Steps to use the command
1.  Run the command `PopupMenu`.
2.  A menu will appear at your cursor.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is almost always used in a macro that is assigned to a mouse button or keyboard shortcut to provide quick access to a custom set of tools.

### Practical Use Cases
* **Use Case 1 (Custom UI):** A power user could create a custom menu with their 10 most-used commands and assign the `PopupMenu` command to their middle mouse button. Now, clicking the middle mouse button will instantly bring up their favorite tools right at their cursor.

### Other Information
This is an advanced interface customization tool.

---

## 497. PopupPopular

### Short Info
Display the most-used commands list at the cursor.

### Detailed Description
The **PopupPopular** command is a utility that displays a menu containing a list of your most recently and frequently used commands, right at your mouse cursor. This provides very fast access to the commands you use most often.

### Steps to use the command
1.  Run the command `PopupPopular`.
2.  A menu listing your popular commands will appear at your cursor.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a great command to assign to a keyboard shortcut or a mouse button for a significant workflow speed increase.

### Practical Use Cases
* **Use Case 1 (Fast Access):** Instead of moving your mouse up to the toolbars or typing a command name, you can press a single shortcut key. The `PopupPopular` menu will appear, and the command you just used (like `FilletEdge`) will likely be at the top of the list, allowing you to select it again instantly.

### Other Information
This is a powerful workflow efficiency tool.

---

## 498. PopupToolbar

### Short Info
Open a toolbar at the cursor.

### Detailed Description
The **PopupToolbar** command is a utility that opens a specified toolbar as a floating menu at the current location of the mouse cursor.

### Steps to use the command
1.  Run the command `PopupToolbar`.
2.  At the **Name of toolbar to popup** prompt, enter the name of an existing toolbar (e.g., "Solid Tools").
3.  That toolbar will appear as a floating menu at your cursor.

### Command Options & Toggles
This command has no options other than the toolbar name.

### Practical Use Cases
* **Use Case 1 (Custom UI):** A designer could assign the macro `! _PopupToolbar "Curve Tools"` to a keyboard shortcut. Now, whenever they press that key, their entire curve drawing toolbar will appear right where they are working, saving them from having to move the mouse to the edge of the screen.

### Other Information
This is an advanced interface customization tool.

---

## 499. PrevU

### Short Info
Select the previous control point in the u-direction.

### Detailed Description
The **PrevU** (Previous U) command is a control point selection utility. It deselects the currently selected control point(s) and selects the very next control point in the negative U direction.

### Steps to use the command
1.  Turn on control points for a curve or surface.
2.  Select one control point.
3.  Run the command `PrevU`.
4.  The original point will be deselected, and the previous point in the U direction will be selected.

### Command Options & Toggles
This command has no options.

### Note for better use
This is different from `AddPrevU`, which *adds* to the selection. `PrevU` *replaces* the selection. This command is designed to be used with keyboard shortcuts to "walk" a single selection along a row of control points.

### Practical Use Cases
* **Use Case 1 (Sequential Adjustments):** You need to adjust each control point in a row, one at a time, moving from right to left. You can select the last point, make your adjustment, then use `PrevU` to move the selection to the previous point, make another adjustment, and so on.

### Other Information
This is a specialized selection command for advanced control point editing.

---

## 500. PrevV

### Short Info
Select the previous control point in the v-direction.

### Detailed Description
The **PrevV** (Previous V) command is a control point selection utility. It deselects the currently selected control point(s) and selects the very next control point in the negative V direction on a surface.

### Steps to use the command
1.  Turn on control points for a surface.
2.  Select one control point.
3.  Run the command `PrevV`.
4.  The original point will be deselected, and the previous point in the V direction will be selected.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the V-direction equivalent of the `PrevU` command.

### Practical Use Cases
* **Use Case 1 (Sequential Adjustments):** Similar to `PrevU`, this allows you to move your selection one step at a time along a column of control points on a surface, in the negative V direction.

### Other Information
This is a specialized selection command for advanced control point editing.

---

## 501. PrevViewport

### Short Info
Activate the previous viewport.

### Detailed Description
The **PrevViewport** (Previous Viewport) command is a viewport navigation utility. It makes the previously active viewport the current active viewport. This allows you to quickly toggle back and forth between two different views.

### Steps to use the command
1.  Click in one viewport to make it active (e.g., Perspective).
2.  Click in a second viewport to make it active (e.g., Top).
3.  Run the command `PrevViewport`.
4.  The first viewport (Perspective) will become active again.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is most useful when assigned to a keyboard shortcut or a mouse button, allowing for a very fast toggle between two primary working views.

### Practical Use Cases
* **Use Case 1 (Toggling Views):** You are doing detailed work in the Top view but frequently need to check the result in the Perspective view. You can use `PrevViewport` to instantly switch back and forth between your Top and Perspective views without having to move your mouse to click on the viewport titles.

### Other Information
This is a simple but effective workflow efficiency tool for viewport navigation.

---

## 502. Print

### Short Info
Print the view or layouts.

### Detailed Description
The **Print** command opens the main Print dialog box, which allows you to send the current view, a selection of objects, or your layout pages to a physical printer or to a file (like a PDF). This dialog contains all the necessary options for controlling the scale, position, line types, colors, and output device for your print.

### Steps to use the command
1.  Make the viewport or layout page you want to print active.
2.  Run the command `Print`.
3.  The Print dialog box will appear.
4.  Configure the settings (Destination, Scale, Margins, etc.).
5.  Click "Print."

### Command Options & Toggles
The options are all contained within the dialog box:
* **Destination:** Choose a physical printer or a file format like PDF.
* **View and Output Scale:** This is the most critical section for setting the drawing scale (e.g., 1:1, 1:2) and position on the page.
* **Linetypes and Line Widths:** Controls how different line styles and thicknesses are printed.
* **Visibility:** Allows you to print items like the background color, wallpaper, or lights.

### Note for better use
Before printing, it is a very good practice to use the `PrintDisplay` command to get a preview in your viewport of how the line weights and colors will look when printed. This can help you catch errors before wasting paper.

### Practical Use Cases
* **Use Case 1 (Creating a PDF for a Client):** You have created a technical drawing on a layout page with dimensions. You run `Print`, select "Rhino PDF" as the destination, set the scale to 1:1, and create a high-quality PDF file that you can email to the client or manufacturer.
* **Use Case 2 (Printing a Reference Sheet):** You want a quick printout of your perspective view to sketch over. You can activate the Perspective view, run `Print`, choose your office printer, and use the "Scale to Fit" option to quickly print the view.

### Other Information
This is the fundamental command for creating physical or digital 2D output from your models.

---

## 503. PrintDisplay

### Short Info
Toggle print preview display.

### Detailed Description
The **PrintDisplay** command is a display mode toggle. It changes the active viewport to a "print preview" mode. In this mode, objects are displayed with the print colors and print widths assigned in their properties or layer settings. This provides an on-screen preview of how the line weights and colors will look when the view is actually printed.

### Steps to use the command
1.  Run the command `PrintDisplay`.
2.  The command line will show the current state (On or Off).
3.  Click the option to toggle it.

### Command Options & Toggles
* **State (On/Off):** The main toggle for the feature.
* **Color (Display/Print):** Toggles whether to preview print colors.
* **Thickness (On/Off):** Toggles whether to preview print widths.

### Note for better use
This is a crucial command to use before running the `Print` command. It allows you to visually check your line weight hierarchy and ensure that important lines are thick and guide lines are thin, just as they will appear on the final printed page or PDF.

### Practical Use Cases
* **Use Case 1 (Checking a Technical Drawing):** You have created a layout for a ring and have assigned different print widths to your object lines, hidden lines, and dimension lines. Before creating the final PDF, you turn on `PrintDisplay` to get an accurate preview of how these line weights will look, allowing you to make adjustments for clarity and readability.

### Other Information
This is an essential quality control tool for anyone producing 2D documentation.

---

## 504. Project

### Short Info
Project curves/points toward a construction plane to intersect a surface.

### Detailed Description
The **Project** command is a fundamental curve creation and editing tool. It takes one or more curves or points and "projects" them, like a shadow, onto a selected surface or polysurface. The projection happens in the direction of the active construction plane's Z-axis (straight "down" in the Top view).

### Steps to use the command
1.  Select the curve(s) or point(s) you want to project.
2.  Run the command `Project`.
3.  At the **Select surfaces, polysurfaces, or meshes to project onto** prompt, select the target object(s) and press Enter.
4.  New curves or points will be created on the target surface.

### Command Options & Toggles
* **DeleteInput (Yes/No):** Deletes the original curves after the projection.

### Note for better use
The direction of the projection is critical. For example, to project a pattern onto the top of a ring, you must run the command from the Top viewport. If you run it from the Front view, it will project sideways through the ring. The `Pull` command is a similar tool, but it pulls the curve to the *closest* point on the surface, which is not always the same as a straight projection.

### Practical Use Cases
* **Use Case 1 (Creating Trim Curves):** You have drawn a flat, 2D pattern above the curved surface of a ring. You can use `Project` to cast this pattern down onto the ring's surface. The resulting 3D curves can then be used to `Trim` or `Split` the surface to create an inlay or decorative feature.
* **Use Case 2 (Creating a Path for Gems):** You have drawn a simple, straight line in the Top view over a complex, wavy surface. `Project` will turn this straight line into a 3D curve that follows the up-and-down contour of the surface, creating a perfect path for setting gemstones.

### Other Information
This is a workhorse command for transferring 2D geometry onto 3D surfaces.

---

## 505. ProjectOsnap

### Short Info
Project object snaps to the construction plane.

### Detailed Description
The **ProjectOsnap** (Project Object Snaps) command is a modeling aid. When it is active, any object snap location you pick is projected onto the current construction plane. This forces your selections to be planar, even if you are snapping to 3D geometry.

### Steps to use the command
1.  Run the command `ProjectOsnap`.
2.  The command line will show the current state (On or Off).
3.  Click the option to toggle it.
4.  Alternatively, click the "Project" pane in the Status Bar.

### Command Options & Toggles
This command is a simple toggle between **On** and **Off**.

### Note for better use
This is extremely useful for creating clean, planar 2D drawings while using existing 3D geometry as a reference.

### Practical Use Cases
* **Use Case 1 (Creating a Flat Outline):** You are in the Top view and need to draw a flat, 2D outline of a complex 3D ring. You want to snap to the edges of the 3D model, but you need your new curve to be perfectly flat. You turn on `ProjectOsnap`. Now, even though you are snapping to points that have different Z-heights, Rhino will create all the points for your new curve on the CPlane, resulting in a perfectly flat outline.

### Other Information
This is a key modeling aid for creating 2D drawings from 3D models.

---

## 506. ProjectToCPlane

### Short Info
Flatten objects onto the construction plane.

### Detailed Description
The **ProjectToCPlane** (Project to Construction Plane) command takes selected objects and creates flattened copies of them on the active construction plane.

### Steps to use the command
1.  Select the object(s) you want to flatten.
2.  Run the command `ProjectToCPlane`.
3.  At the **Delete input objects?** prompt, choose Yes or No.
4.  New, flattened versions of the objects will be created on the CPlane.

### Command Options & Toggles
* **DeleteInput (Yes/No):** Deletes the original 3D objects after creating the flattened copies.

### Note for better use
This is a fast way to get a 2D representation of 3D geometry. It is similar to `Make2D` but is simpler and less configurable.

### Practical Use Cases
* **Use Case 1 (Creating a Profile):** You have a 3D curve that winds through space, but you need a flat, 2D version of it as seen from the Top view. You can go to the Top view, select the curve, and run `ProjectToCPlane` to get the flattened version.
* **Use Case 2 (Fixing Non-Planar Curves):** You have a curve that is supposed to be flat but has some small variations in the Z-axis, which is preventing a command like `PlanarSrf` from working. You can use `ProjectToCPlane` to create a new, perfectly flat version of the curve.

### Other Information
This is a simple but useful utility for flattening geometry.

---

## 507. Properties

### Short Info
Open the Properties panel.

### Detailed Description
The **Properties** command opens the main Properties panel. This is a dockable panel that displays detailed information and editable properties for the currently selected object(s). This is the primary interface for changing an object's name, layer, color, material, and other specific attributes.

### Steps to use the command
1.  Run the command `Properties`.
2.  The Properties panel will open.
3.  Select an object in the viewport.
4.  The panel will populate with the properties for that object.

### Command Options & Toggles
The options are all contained within the panel's interface, which has different tabs depending on the type of object selected (e.g., Object, Material, Texture Mapping).

### Note for better use
Most experienced users keep the Properties panel open and docked at all times. It provides constant, context-sensitive information and control over your model.

### Practical Use Cases
* **Use Case 1 (Changing an Object's Layer):** The most common way to change an object's layer is to select the object, go to the Properties panel, and choose a new layer from the dropdown menu.
* **Use Case 2 (Assigning a Material):** To assign a render material to an object, you select the object, go to the "Material" section of the Properties panel, and choose a material from the list.
* **Use Case 3 (Checking Object Type):** If you are unsure what type of object you have selected (e.g., is it a single surface or a polysurface?), the top of the Properties panel will tell you exactly what it is.

### Other Information
This is one of the most fundamental and essential panels in the Rhino interface.

---

## 508. PropertiesPage

### Short Info
Open a specific page in the Properties panel.

### Detailed Description
The **PropertiesPage** command is a utility that opens the Properties panel and brings a specific tab to the front.

### Steps to use the command
1.  Run the command `PropertiesPage`.
2.  At the **Page name** prompt, enter the name of the tab you want to open (e.g., "Material").
3.  The Properties panel will open with that page selected.

### Command Options & Toggles
This command has no options other than the page name you provide.

### Practical Use Cases
* **Use Case 1 (Custom Toolbar):** You could create a custom button with the macro `! _PropertiesPage Material` to instantly open the Properties panel to the Material tab, which might be slightly faster than opening the panel and then clicking the tab manually.

### Other Information
This is a simple workflow efficiency command for power users.

---

## 509. PtOffSelected

### Short Info
Turn off control points for selected objects.

### Detailed Description
The **PtOffSelected** (Points Off Selected) command turns off the visibility of control points and edit points, but only for the objects that are currently selected. This is a more targeted version of the global `PointsOff` command.

### Steps to use the command
1.  Have several objects with their control points turned on.
2.  Select the specific object(s) whose points you want to hide.
3.  Run the command `PtOffSelected`.
4.  The control points for only the selected objects will be hidden.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (De-cluttering a Complex Edit):** You are editing a complex model and have the control points turned on for five different surfaces at once. The view is very cluttered. If you are finished editing two of the surfaces, you can select them and run `PtOffSelected` to hide their points, leaving the points on for only the surfaces you are still working on.

### Other Information
This command gives you more granular control over point visibility than the global `PointsOff` (F11) command.

---

## 510. Pull

### Short Info
Pull a curve or points to a surface.

### Detailed Description
The **Pull** command is a curve creation and editing tool that "pulls" curves or points onto a target surface. It works by finding the closest point on the surface for each point on the curve and creating a new curve from these new locations.

### Steps to use the command
1.  Select the curve(s) or point(s) you want to pull.
2.  Run the command `Pull`.
3.  At the **Select surfaces, polysurfaces, or meshes to pull to** prompt, select the target object(s) and press Enter.
4.  New curves or points will be created on the target surface.

### Command Options & Toggles
* **DeleteInput (Yes/No):** Deletes the original curves after the pull.

### Note for better use
This command is different from `Project`. `Project` casts a shadow in a specific direction. `Pull` finds the closest point, which is always perpendicular to the target surface. For a complex, doubly-curved surface, these two commands will produce very different results.

### Practical Use Cases
* **Use Case 1 (Creating a Trim Curve):** You have a complex, organic surface and a curve that is floating near it. You want to create a trim line on the surface that exactly matches the shape of the curve. `Pull` will create this curve for you.
* **Use Case 2 (Placing Points on a Surface):** You have a set of point objects that are near a surface, and you need to snap them directly onto the surface. `Pull` will move each point to the closest location on the surface.

### Other Information
This is a fundamental tool for transferring geometry onto curved surfaces.

---

## 511. Purge

### Short Info
Delete unused block definitions, groups, layers, and other unused objects.

### Detailed Description
The **Purge** command is a file maintenance utility that cleans up your current model by deleting unused items. This can include block definitions that have no instances, empty layers, unused materials, and other data that is saved with the file but is not currently being used. This is an excellent way to reduce your final file size.

### Steps to use the command
1.  Run the command `Purge`.
2.  A dialog box will appear, listing all the unused items that can be deleted.
3.  Check the boxes for the items you want to purge.
4.  Click OK.

### Command Options & Toggles
The options are the checkboxes in the dialog box, allowing you to choose which types of unused items to delete.

### Note for better use
It is a very good practice to run `Purge` on a model before you send it to a client or to a 3D printer. This removes any old, unnecessary data and makes the file as clean and small as possible.

### Practical Use Cases
* **Use Case 1 (Finalizing a File):** You have finished a ring design. During the process, you created several test layers and imported some block definitions that you ended up not using. Before sending the file to be printed, you run `Purge` and check all the boxes. This cleans the file, removes the unused data, and reduces the final file size.

### Other Information
This is an essential command for good file hygiene.

---

## 512. PurgeRefObjects

### Short Info
Delete worksession reference objects.

### Detailed Description
The **PurgeRefObjects** (Purge Reference Objects) command is a utility used with the `Worksession` feature. It deletes any reference objects from a worksession that are no longer needed.

### Steps to use the command
1.  Have a worksession active.
2.  Run the command `PurgeRefObjects`.
3.  Follow the prompts to select and delete the unused reference objects.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Worksession Management):** You are working in a large, collaborative worksession and some of the linked reference files are no longer needed for your part of the project. This command allows you to clean up your session by removing them.

### Other Information
This is a specialized utility for the `Worksession` system.

---

## 513. PushViewportToBack

### Short Info
Send a named viewport behind all other viewports.

### Detailed Description
The **PushViewportToBack** command is a viewport management utility used with floating viewports. It takes the currently active floating viewport and sends it behind all other floating viewports in the stack.

### Steps to use the command
1.  Make a floating viewport active.
2.  Run the command `PushViewportToBack`.
3.  The viewport will be sent to the back of the display order.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the opposite of the `BringViewportToTop` command.

### Practical Use Cases
* **Use Case 1 (Managing Floating Views):** You have a large, floating perspective view and a smaller, floating detail view. You want to send the large view to the back so you can see the smaller detail view on top of it.

### Other Information
This is a window management tool, not a modeling tool.

---

## 514. Pyramid

### Short Info
Draw a pyramid.

### Detailed Description
The **Pyramid** command is a solid creation tool that creates a pyramid with a specified number of sides at its base.

### Steps to use the command
1.  Run the command `Pyramid`.
2.  Follow the prompts to define the center and radius of the pyramid's base, and then its height.

### Command Options & Toggles
* **NumSides:** Sets the number of sides for the base of the pyramid.
* **Edge:** Allows you to define the base by drawing one of its edges.

### Note for better use
A pyramid with 3 sides is a tetrahedron. A pyramid with 4 sides is a standard pyramid.

### Practical Use Cases
* **Use Case 1 (Creating a Spike):** You are designing a piece of punk-style jewelry and need to create a pointed spike with a square base. The `Pyramid` command with `NumSides=4` is the fastest way to create this shape.
* **Use Case 2 (V-Shaped Prongs):** The basic shape of a "v-prong" used for setting princess-cut stones can be created with a 3-sided pyramid.

### Other Information
This is one of the basic solid modeling primitives.

---

## 515. QuadrangulateMesh

### Short Info
Merge mesh triangles into quadrangles.

### Detailed Description
The **QuadrangulateMesh** command is an automated mesh topology tool. It inspects a mesh that is made of triangles and attempts to merge adjacent pairs of triangles into four-sided faces (quads). This is useful for preparing a mesh for export to subdivision modeling or sculpting programs, which often work better with quad-based geometry.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `QuadrangulateMesh`.
3.  The command will attempt to convert the mesh to quads.

### Command Options & Toggles
This command has no options.

### Note for better use
This is an automated process and the results can vary. It may not be able to convert all triangles to quads, and it can sometimes produce undesirable polygon flows. For precise control, it is often better to manually merge triangles using the `Merge2MeshFaces` command.

### Practical Use Cases
* **Use Case 1 (Preparing for ZBrush):** You have an STL file of a ring that you want to sculpt on in ZBrush. You can run `QuadrangulateMesh` on the object first to convert as much of it as possible to quads, which will often lead to better and smoother sculpting results.

### Other Information
This is an advanced tool for managing mesh topology.

---

## 516. Radius

### Short Info
Report the radius of a curve.

### Detailed Description
The **Radius** command is an analysis tool that measures the radius of a circle or arc at a specified point.

### Steps to use the command
1.  Run the command `Radius`.
2.  At the **Select curve for radius measurement** prompt, select a circle or arc.
3.  The command will report the radius in the command history and place a temporary marker.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a quick measurement tool. To create a permanent, visible dimension on your model, use the `DimRadius` command instead.

### Practical Use Cases
* **Use Case 1 (Verifying Fillets):** You have created a filleted corner and want to quickly check its radius. `Radius` will give you an instant measurement.
* **Use Case 2 (Checking a Ring Rail):** You want to confirm the radius of your ring rail to ensure the finger size is correct.

### Other Information
This is a simple analysis command for quick verification of circular objects.

---

## 517. RailRevolve

### Short Info
Revolve a profile curve around an axis and along a rail curve.

### Detailed Description
The **RailRevolve** command is a powerful and complex surface creation tool. It creates a surface by revolving a profile curve around a central axis, but with a key difference from the standard `Revolve` command: the shape is also guided by a "rail" curve. This means the resulting surface has the rotational quality of a revolve, but its outer profile is controlled by the rail curve.

### Steps to use the command
1.  Create a profile curve, an axis of revolution, and a rail curve.
2.  Run the command `RailRevolve`.
3.  At the **Select profile curve** prompt, select the profile.
4.  At the **Select rail curve** prompt, select the rail.
5.  At the **Start of revolve axis** prompt, define the axis line.
6.  The surface will be created.

### Command Options & Toggles
This command has no options in the command line.

### Note for better use
This is an advanced surfacing tool. The profile curve must intersect the rail curve, and the rail curve must intersect the revolve axis.

### Practical Use Cases
* **Use Case 1 (Creating a Domed Ring with a Square Profile):** You want to create a domed ring, but you want its cross-section to be square, not circular. You can draw a square as your profile curve, a circle as your rail curve, and a line through the center as your axis. `RailRevolve` will sweep the square profile around the axis, while forcing its outer corner to follow the circular rail, resulting in a perfectly domed ring with a square profile.
* **Use Case 2 (Modeling a Wine Glass):** The shape of a wine glass is a classic example. The profile curve would be the cross-section of the glass wall, the rail curve would be the complex, curved outline of the glass's side profile, and the axis would be the vertical centerline.

### Other Information
This is a very powerful command for creating complex surfaces that have both rotational and profiled characteristics.

---

## 518. ReadCommandFile

### Short Info
Read and execute a command script from a text file.

### Detailed Description
The **ReadCommandFile** command is a utility for scripting. It allows you to run a script of Rhino commands that has been saved in an external text file (.txt).

### Steps to use the command
1.  Create a text file where each line is a Rhino command.
2.  Run the command `ReadCommandFile`.
3.  A file browser will open. Select your text file.
4.  Rhino will execute the commands in the file, one by one.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Running External Scripts):** A user who is not familiar with the script editor can be sent a simple text file containing a macro. They can then use this command to easily run the script without having to open the editor.

### Other Information
This is a simple way to execute macros that are stored outside of the Rhino interface.

---

## 519. ReadEveryIGESEntity

### Short Info
Read all IGES entities.

### Detailed Description
The **ReadEveryIGESEntity** command is a specialized utility for importing IGES files. It forces Rhino to attempt to read all the data from an IGES file, even entities that it does not normally support or recognize. This is a "brute force" import method used for troubleshooting problematic files.

### Steps to use the command
1.  This command is used before importing. You would run `ReadEveryIGESEntity` to toggle the mode on.
2.  Then, you would use the `Import` command to open the IGES file.

### Command Options & Toggles
This command is a toggle.

### Note for better use
This should only be used as a last resort when a standard `Import` fails on an IGES file. It may result in the import of "bad" or unsupported geometry, but it can sometimes recover data from a file that would otherwise not open at all.

### Practical Use Cases
* **Use Case 1 (Troubleshooting Imports):** You have received a critical IGES file from a client, but it fails to import. You can try turning on `ReadEveryIGESEntity` to see if it can recover at least some of the geometry from the file.

### Other Information
This is an advanced tool for file translation experts.

---

## 520. ReadViewportsFromFile

### Short Info
Set the viewports to a layout saved in another model.

### Detailed Description
The **ReadViewportsFromFile** command is a utility that changes your current viewport layout to match the viewport layout from another, saved Rhino file.

### Steps to use the command
1.  Run the command `ReadViewportsFromFile`.
2.  A file browser will open. Select the .3dm file that has the viewport layout you want to copy.
3.  Your current viewport layout will be replaced with the one from the selected file.

### Command Options & Toggles
This command has no options.

### Note for better use
This is useful for standardizing a workspace across multiple files or users.

### Practical Use Cases
* **Use Case 1 (Standard Workspace):** A design studio has a standard viewport layout that all designers are required to use. A new designer can use `ReadViewportsFromFile` and select a template file to instantly configure their workspace to the company standard.

### Other Information
This is a workspace customization utility.

---

## 521. Rebuild

### Short Info
Reconstruct curves, surfaces, and extrusion objects to a specified degree and control point number.

### Detailed Description
The **Rebuild** command is a fundamental and extremely important editing tool. It reconstructs a curve or surface to have a specific, uniform number of control points and a specific mathematical degree. This is the primary command for simplifying overly complex objects, smoothing out messy ones, or for preparing objects to have a matching structure before using commands like `Loft` or `Sweep`.

### Steps to use the command
1.  Select the object(s) to rebuild.
2.  Run the command `Rebuild`.
3.  A dialog box will appear.
4.  Enter the desired **Point Count** and **Degree**. A preview will show the deviation from the original.
5.  Click OK. A new, rebuilt object will be created.

### Command Options & Toggles
The options are in the dialog box:
* **Point Count:** The number of control points the new object will have.
* **Degree:** The mathematical degree (usually 3 for smooth curves/surfaces).
* **Delete input:** Deletes the original object.
* **Display deviation:** Shows you how far the new object deviates from the original.

### Note for better use
Rebuilding will almost always change the shape of your object slightly. The key is to use the lowest possible point count that keeps the deviation within your acceptable tolerance. A curve or surface with fewer control points is easier to edit and results in smoother, higher-quality models.

### Practical Use Cases
* **Use Case 1 (Simplifying a Curve):** You have a curve that resulted from an `Intersect` operation, and it has 500 control points. It is very difficult to edit. You can use `Rebuild` to change it to a clean, degree 3 curve with only 12 control points, making it smooth and easy to modify.
* **Use Case 2 (Matching for Lofting):** You are about to `Loft` three profile curves. To get the cleanest possible surface, all three curves should have the same structure. You can select all three, run `Rebuild`, and give them all the same point count and degree. Now, the `Loft` will produce a much cleaner and simpler surface.

### Other Information
Mastering the `Rebuild` command is an essential skill for creating high-quality, editable NURBS models.

---

## 522. RebuildCrvNonUniform

### Short Info
Interactively rebuild a curve with a specified tolerance.

### Detailed Description
The **RebuildCrvNonUniform** (Rebuild Curve Non-Uniform) command is an interactive version of `Rebuild` for curves. It allows you to rebuild a curve by specifying a tolerance, and it provides a real-time preview of the result with sliders to adjust the control point count.

### Steps to use the command
1.  Select a curve.
2.  Run the command `RebuildCrvNonUniform`.
3.  A dialog box appears with sliders and a preview.
4.  Adjust the sliders to get the desired balance of simplicity and accuracy.
5.  Click OK.

### Command Options & Toggles
The options are in the dialog box, allowing you to control tolerance and point count.

### Practical Use Cases
* **Use Case 1 (Interactive Smoothing):** You have a slightly jittery curve from a trace and want to smooth it out. This command provides an interactive way to see exactly how much detail you are losing as you reduce the point count, allowing you to find the perfect balance.

### Other Information
This is a more interactive and user-friendly alternative to the standard `Rebuild` command, but it only works on curves.

---

## 523. RebuildEdges

### Short Info
Restore surface edges to their surface.

### Detailed Description
The **RebuildEdges** command is a surface repair tool. It restores the edges of a surface to be perfectly aligned with its underlying geometry. Sometimes, due to complex trimming operations or import errors, a surface's trim edges can deviate slightly from the actual edge of the surface. This command fixes that discrepancy.

### Steps to use the command
1.  Select a surface.
2.  Run the command `RebuildEdges`.
3.  The surface's edges will be rebuilt.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Fixing a Failed Join):** You are trying to `Join` two surfaces that look like they are touching, but the join fails. This could be because one of the trim edges is slightly inaccurate. Running `RebuildEdges` on both surfaces can often fix the problem and allow them to be joined correctly.

### Other Information
This is a useful tool in an advanced model repair workflow.

---

## 524. RebuildMesh

### Short Info
Remove texture coordinates, surface parameters, vertex colors, and surface curvature from a mesh.

### Detailed Description
The **RebuildMesh** command is a mesh utility that strips a mesh object of all extra data, such as texture coordinates, vertex colors, and other parameters, leaving only the basic vertex and face information.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `RebuildMesh`.
3.  The extra data will be removed.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Resetting a Mesh):** You have an imported mesh that has problematic texture coordinates that are causing issues. `RebuildMesh` can be used to completely remove this data, giving you a clean mesh to work with.

### Other Information
This is a specialized mesh cleanup tool.

---

## 525. RebuildMeshNormals

### Short Info
Recalculate mesh normals.

### Detailed Description
The **RebuildMeshNormals** command is a mesh repair tool that recalculates all the vertex and face normals of a mesh object to ensure they are pointing in the correct, averaged direction. This can sometimes fix shading or rendering artifacts on a mesh.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `RebuildMeshNormals`.
3.  The normals will be recalculated.

### Command Options & Toggles
This command has no options.

### Note for better use
For ensuring all normals point outward on a closed mesh, the `UnifyMeshNormals` command is often more effective.

### Practical Use Cases
* **Use Case 1 (Fixing Shading Errors):** You have a mesh that has strange dark or light patches on it in a shaded viewport. This can sometimes be caused by incorrect vertex normals. `RebuildMeshNormals` can often fix these shading errors.

### Other Information
This is a mesh repair tool for fixing shading issues.

---

## 526. RebuildUV

### Short Info
Reconstruct a surface to a specified degree and control point number in the u- or v-direction.

### Detailed Description
The **RebuildUV** command is a more controlled version of the `Rebuild` command that works only on surfaces. It allows you to rebuild the surface with a new point count and degree in only the U direction, or only the V direction, leaving the other direction unchanged.

### Steps to use the command
1.  Select a surface.
2.  Run the command `RebuildUV`.
3.  The command line will prompt you to choose a direction (U or V) and to enter the new point count and degree.
4.  The surface will be rebuilt in that one direction.

### Command Options & Toggles
The options are presented as prompts in the command line.

### Note for better use
This is an advanced surfacing tool for users who need precise control over the structure of their surfaces.

### Practical Use Cases
* **Use Case 1 (Adding Detail in One Direction):** You have a smooth, simple surface for a ring shank. You want to add detail along the length of the shank, but keep the cross-section profile simple. You could use `RebuildUV` to add more control points only in the U direction (along the length), which would give you the control you need without making the profile more complex.

### Other Information
This is a specialized tool for advanced surface editing.

---

## 527. RecordAnimation

### Short Info
Render and save all animation frames.

### Detailed Description
The **RecordAnimation** command is the final step in creating an animation. After you have set up an animation using a command like `Turntable` or `SetFlythroughAnimation`, this command will go through every single frame of the animation, render it, and save it as an image file. The result is a sequence of images that can be combined into a video.

### Steps to use the command
1.  Set up an animation.
2.  Run the command `RecordAnimation`.
3.  A dialog box will appear.
4.  Choose a target folder, a filename, and the number of frames to record.
5.  Click "Record." Rhino will then render each frame sequentially.

### Command Options & Toggles
The options are in the dialog box:
* **Target folder:** The location to save the image sequence.
* **Number of frames:** The total number of images to create.
* **Capture method:** The display mode to use for the animation (e.g., Rendered, Shaded, Wireframe).

### Note for better use
Rendering an animation can be a very time-consuming process, as it involves creating hundreds or even thousands of individual renders. Always do a low-frame-count test first to make sure the motion and lighting are correct.

### Practical Use Cases
* **Use Case 1 (Creating a Turntable Video):** You have set up a 360-degree turntable animation of a ring. You use `RecordAnimation` to render all 100 frames as separate JPG images. You can then use a video editing program to compile these images into a smooth video to send to a client or post on your website.

### Other Information
This is the primary command for outputting a finished animation.

---

## 528. Rectangle

### Short Info
Draw a rectangle from two corner points.

### Detailed Description
The **Rectangle** command is a fundamental 2D drawing tool used to create a closed, rectangular polyline or surface.

### Steps to use the command
1.  Run the command `Rectangle`.
2.  Follow the prompts for the chosen creation method. For the default method:
    a. At the **First corner of rectangle** prompt, pick a point.
    b. At the **Other corner or length** prompt, pick the opposite corner.

### Command Options & Toggles
* **3Point:** Creates a rectangle by picking three points.
* **Vertical:** Creates a rectangle that is vertical to the CPlane.
* **Center:** Creates the rectangle from its center point.
* **Rounded:** Creates a rectangle with filleted or chamfered corners.

### Practical Use Cases
* **Use Case 1 (Drawing a Princess Cut Stone):** The `Rectangle` command (specifically, the `Square` sub-option) is the fastest way to draw the outline of a square, princess-cut gemstone.
* **Use Case 2 (Creating a Base Plate):** You are designing a nameplate pendant. The `Rectangle` command is the tool you would use to create the basic rectangular shape of the plate.

### Other Information
This is one of the most basic and frequently used 2D drawing commands.

---

## 529. RectangularLight

### Short Info
Insert a rectangular light.

### Detailed Description
The **RectangularLight** command adds a rectangular light source to the model. This type of light simulates a light source shaped like a photographer's "softbox" or a window. It emits light from a planar, rectangular area, which creates very soft, diffuse shadows and broad, gentle highlights.

### Steps to use the command
1.  Run the command `RectangularLight`.
2.  Draw a rectangle in the viewport to define the size and location of the light.
3.  A rectangular light object will be created.

### Command Options & Toggles
The options are for drawing the rectangle, similar to the `Rectangle` command.

### Note for better use
Rectangular lights are one of the best tools for creating realistic, soft studio lighting for jewelry renders. The larger the rectangle, the softer the shadows will be.

### Practical Use Cases
* **Use Case 1 (Studio Lighting):** To create a professional studio lighting setup, you can place a large `RectangularLight` above and to one side of your ring to act as the main "key" light, and a second, less intense one on the other side to act as a "fill" light. This will produce beautiful, soft shadows and highlights.

### Other Information
This is a key tool for creating high-quality, photorealistic renderings.

---

## 530. Redo

### Short Info
Reverse the last Undo.

### Detailed Description
The **Redo** command is a fundamental editing utility that reverses the last action that was undone with the `Undo` command.

### Steps to use the command
1.  Run the `Undo` command.
2.  Run the command `Redo`.
3.  The action that was undone will be restored.

### Command Options & Toggles
This command has no options.

### Note for better use
The keyboard shortcut **Ctrl+Y** is the universal and much faster way to perform this action.

### Practical Use Cases
* **Use Case 1 (Correcting an Undo):** You have just performed a complex operation. You accidentally press `Undo` (Ctrl+Z) one too many times. `Redo` (Ctrl+Y) will bring your complex operation back without you having to do it all over again.

### Other Information
This is a standard feature in almost all software.

---

## 531. RedoMultiple

### Short Info
Redo multiple undone actions.

### Detailed Description
The **RedoMultiple** command opens a dialog box that shows a list of the most recent actions that have been undone. It allows you to select one or more of these actions and redo them all at once.

### Steps to use the command
1.  Run the command `RedoMultiple`.
2.  The "Redo List" dialog box will appear.
3.  Select the actions you want to redo from the list.
4.  Click OK.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Step-by-Step Recovery):** You have undone a long sequence of 10 commands. You realize you only wanted to undo the first 5. You can use `RedoMultiple` to select the last 5 undone actions and bring them back in one step.

### Other Information
This is the multi-action version of the `Redo` command.

---

## 532. RedoView

### Short Info
Reverse the last UndoView.

### Detailed Description
The **RedoView** command is a viewport navigation utility. It reverses the last view change that was undone with the `UndoView` command.

### Steps to use the command
1.  Use `UndoView` to go back to a previous camera position.
2.  Run the command `RedoView`.
3.  The camera will return to the position it was in before you ran `UndoView`.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Navigating Camera History):** You are trying to find a specific camera angle you were at a few minutes ago. You use `UndoView` several times to go back, but you go one step too far. `RedoView` will take you forward one step in your camera history.

### Other Information
This is a simple navigation tool for managing your view history.

---

## 533. ReduceMesh

### Short Info
Reduce the number of mesh polygons.

### Detailed Description
The **ReduceMesh** command is a powerful mesh editing tool that reduces the number of polygons in a mesh while trying to preserve its overall shape and detail as much as possible. This is a key tool for simplifying very dense meshes (like those from 3D scanners) to make them more manageable.

### Steps to use the command
1.  Select a mesh object.
2.  Run the command `ReduceMesh`.
3.  A dialog box will appear.
4.  You can specify the number of polygons you want the final mesh to have, or a percentage reduction.
5.  Click OK. A new, simplified mesh will be created.

### Command Options & Toggles
The options are in the dialog box:
* **Initial polygon count:** Shows you how many polygons the mesh currently has.
* **Reduce to X polygons:** Allows you to specify the exact number of polygons for the final mesh.
* **Reduce by X percent:** Allows you to specify a percentage reduction.

### Note for better use
This is a destructive process that permanently alters the mesh. Always work on a copy. Reducing the polygon count too much will result in a loss of detail. It is a balancing act between file size/performance and visual quality.

### Practical Use Cases
* **Use Case 1 (Optimizing a 3D Scan):** You have a 3D scan of a ring that has 2 million polygons, making it very slow to work with. You can use `ReduceMesh` to reduce it to a more manageable 200,000 polygons. For a small, organic object, this reduction will often have very little visible impact on the quality but will make the file much faster.
* **Use Case 2 (Preparing for a Game Engine):** You are creating a piece of jewelry to be used in a real-time application, which requires very low-polygon models. `ReduceMesh` is the primary tool for taking a high-poly model and simplifying it to meet the performance requirements of the application.

### Other Information
This is an essential command for any workflow that involves 3D scanning or exporting to real-time applications.

---

## 534. RefreshAllTextures

### Short Info
Reload all texture bitmaps from their files.

### Detailed Description
The **RefreshAllTextures** command is a rendering utility. It forces Rhino to reload all of the external texture image files that are used in your model's materials.

### Steps to use the command
1.  Run the command `RefreshAllTextures`.
2.  Rhino will re-read all the image files from their saved locations on your computer.

### Command Options & Toggles
This command has no options.

### Note for better use
This command is useful if you have edited a texture image in an external program (like Photoshop) while your Rhino file was open. Rhino will not automatically detect the change. This command forces it to load the new, edited version of the image.

### Practical Use Cases
* **Use Case 1 (Editing a Texture):** You are working on a render and decide that the wood grain texture you are using is too dark. You open the texture's JPG file in Photoshop, adjust its brightness, and save it (overwriting the original). Back in Rhino, you run `RefreshAllTextures`. The material in your viewport and in your next render will now show the updated, lighter version of the texture.

### Other Information
This is a simple but important utility for rendering workflows that involve external image editors.

---

## 535. RefreshShade

### Short Info
Regenerate the render mesh.

### Detailed Description
The **RefreshShade** command forces a shaded viewport to regenerate its render meshes. This can sometimes fix display errors or artifacts that may appear in shaded or rendered modes.

### Steps to use the command
1.  Run the command `RefreshShade`.
2.  The display meshes in the shaded viewports will be recalculated.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Fixing Display Glitches):** You are working on a complex model, and you notice some strange black patches or missing faces in your shaded viewport that you know are not real holes in your model. Running `RefreshShade` will often fix these temporary display errors.
* **Use Case 2 (After Changing Mesh Settings):** You have gone into the Document Properties and increased the quality of your render mesh. The change may not be immediately visible in the viewport. `RefreshShade` will force the viewport to update and display the new, higher-quality mesh.

### Other Information
This is a simple display utility for troubleshooting visual artifacts.

---

## 536. ReleaseFromCage

### Short Info
Detach objects from a control object.

### Detailed Description
The **ReleaseFromCage** command is a utility used with the `CageEdit` command. It breaks the parametric link between a "captive" object and its "control" cage object. After running this command, the object will no longer be deformed if you edit the cage.

### Steps to use the command
1.  Run the command `ReleaseFromCage`.
2.  At the **Select captive objects to release** prompt, select the object(s) that you want to detach from their cage.
3.  The link will be broken.

### Command Options & Toggles
This command has no options.

### Note for better use
This is useful when you have finished deforming an object with `CageEdit` and want to "bake" the deformation, making the object independent again.

### Practical Use Cases
* **Use Case 1 (Finalizing a Deformation):** You have used `CageEdit` to give a ring shank a custom, organic shape. You are happy with the result and want to finalize it. You run `ReleaseFromCage` on the shank. You can now delete the cage object without the shank reverting to its original shape.

### Other Information
This is the companion command to `CageEdit`.

---

## 537. RelocateGumball

### Short Info
Move the Gumball widget origin.

### Detailed Description
The **RelocateGumball** command is a utility that allows you to manually move the pivot point of the Gumball widget to a new location on an object.

### Steps to use the command
1.  Select an object.
2.  Run the command `RelocateGumball`.
3.  You will be prompted to pick a new location for the Gumball.
4.  The Gumball widget will move to the new location.

### Command Options & Toggles
This command has no options.

### Note for better use
After manually relocating the Gumball, you can snap it back to its default location by using the `GumballAlignment` command with the `Reset` option.

### Practical Use Cases
* **Use Case 1 (Rotating from a Corner):** You have a square plate and you want to rotate it around one of its corners. By default, the Gumball appears at the center. You can use `RelocateGumball` to snap the Gumball's pivot to the corner. Now, when you use the Gumball's rotation handles, the plate will pivot around that corner instead of its center.

### Other Information
This command gives you precise control over the pivot point for Gumball transformations.

---

## 538. Gumball

### Short Info
Display a widget on an object for move, scale, and rotate transforms around the object origin.

### Detailed Description
(This is a duplicate entry in the source documentation list, pointing to the same command as #296). The **Gumball** command toggles the visibility of the Gumball widget. The Gumball is an interactive manipulator that appears on a selected object, providing handles for moving, scaling, and rotating the object directly in the viewport without needing to run separate commands like `Move`, `Scale`, or `Rotate`.

### Steps to use the command
1.  Run the command `Gumball`.
2.  The command line will show the current state (On or Off).
3.  Click the option to toggle it.
4.  Alternatively, click the "Gumball" pane in the Status Bar at the bottom of the Rhino window.

### Command Options & Toggles
This command is a simple toggle between **On** and **Off**.

### Note for better use
The Gumball is one of the most significant workflow improvements in Rhino 5. Most modern users leave it on at all times. You can click on the white circle ("bunny tail") on the Gumball to access its settings, such as changing its alignment or size.

### Practical Use Cases
* **Use Case 1 (Interactive Editing):** You have selected a gemstone and need to nudge it slightly up, rotate it a few degrees, and make it a tiny bit larger. With the Gumball on, you can do all of these things interactively by simply dragging the arrows (move), arcs (rotate), and square handles (scale) on the widget, providing instant visual feedback.
* **Use Case 2 (Numeric Input):** You can click on any Gumball handle (arrow, arc, or scale) to get a text box where you can type in a precise numerical value for the transformation.

### Other Information
This entry is a duplicate of command #296.

---

## 539. RemapCPlane

### Short Info
Re-orient objects from a construction plane to another.

### Detailed Description
The **RemapCPlane** command is a transformation tool that moves and rotates objects from one construction plane to another. It is useful for transferring geometry that was created on a custom, tilted CPlane back to one of the standard world planes.

### Steps to use the command
1.  Select the object(s) to remap.
2.  Run the command `RemapCPlane`.
3.  At the **Source construction plane** prompt, select the CPlane the objects were created on.
4.  At the **Target construction plane** prompt, select the CPlane you want to move the objects to.
5.  The objects will be re-oriented.

### Command Options & Toggles
This command has no options.

### Note for better use
You can use saved `NamedCPlane`s as your source and target for this command.

### Practical Use Cases
* **Use Case 1 (Flattening a Design):** You have created a detailed pattern on a tilted surface using a custom CPlane aligned to that surface. Now you need a flat, 2D version of that pattern for a laser engraver. You can use `RemapCPlane` to take the 3D pattern and remap it to the flat World Top CPlane.

### Other Information
This is a specialized transformation tool for working with custom construction planes.

---

## 540. RememberCopyOptions

### Short Info
Control if the Copy option in transform commands is remembered.

### Detailed Description
The **RememberCopyOptions** command is a system setting that controls whether the "Copy" option in transformation commands (like `Move`, `Rotate`, `Scale`) stays "on" between commands.

### Steps to use the command
1.  Run the command `RememberCopyOptions`.
2.  The command line will show the current state (Yes or No).
3.  Click the option to toggle it.

### Command Options & Toggles
This command is a simple toggle between **Yes** and **No**.

### Note for better use
If this is set to Yes, and you use the `Copy` option in the `Rotate` command, the next time you run `Rotate`, the `Copy` option will still be on. If it is set to No (the default), the `Copy` option will reset to its default state for each new command.

### Practical Use Cases
* **Use Case 1 (Repetitive Copying):** You are in the process of manually laying out several components and you know you will be making many rotated and scaled copies. You can set `RememberCopyOptions` to Yes. Now you don't have to click the "Copy=Yes" option every single time you run the `Rotate` or `Scale` command.

### Other Information
This is a user-preference setting that can speed up certain repetitive workflows.

---

## 541. RemoveControlPoint

### Short Info
Remove a control point from a curve or surface.

### Detailed Description
The **RemoveControlPoint** command is a curve and surface editing tool that deletes one or more selected control points from an object. Removing control points simplifies the object's structure and will change its shape.

### Steps to use the command
1.  Turn on the control points for a curve or surface (`PointsOn`).
2.  Select the control point(s) you want to delete.
3.  Run the command `RemoveControlPoint`.
4.  The selected points will be deleted, and the object's shape will update.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the opposite of the `InsertControlPoint` command. For general simplification of a curve or surface, the `Rebuild` or `FitCrv` commands are often more effective, as they provide more control over the final result.

### Practical Use Cases
* **Use Case 1 (Manual Simplification):** You have a curve with a small, unnecessary wiggle in it that is caused by a single extra control point. You can select that one point and use `RemoveControlPoint` to delete it, which will smooth out the curve.

### Other Information
This is a direct editing tool for simplifying NURBS objects.

---

## 542. RemoveEdge

### Short Info
Untrim a selected edge of a trimmed surface.

### Detailed Description
The **RemoveEdge** command is a surface editing tool that "un-trims" a selected edge of a trimmed surface. It removes the trim from that specific edge, causing the surface to revert to its original, un-trimmed boundary at that location.

### Steps to use the command
1.  Run the command `RemoveEdge`.
2.  At the **Select surface edge to remove** prompt, click on a trimmed edge of a surface.
3.  The trim on that edge will be removed.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a more precise version of the `Untrim` command. `Untrim` removes all trims from a surface at once, while `RemoveEdge` allows you to remove them one at a time.

### Practical Use Cases
* **Use Case 1 (Partial Untrim):** You have a surface with a complex trim that includes a large outer cut and a small interior hole. You want to keep the outer cut but get rid of the hole. You can use `RemoveEdge` and select only the edges that make up the hole to remove that specific trim.

### Other Information
This is a useful tool for detailed editing of trimmed surfaces.

---

## 543. RemoveFromGroup

### Short Info
Remove an object from a group.

### Detailed Description
The **RemoveFromGroup** command is an organizational tool that removes one or more selected objects from the group they belong to. The rest of the group remains intact.

### Steps to use the command
1.  Select the object(s) you want to remove from a group.
2.  Run the command `RemoveFromGroup`.
3.  The selected objects will no longer be part of the group.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Editing an Assembly):** You have a group of 50 pavé stones. You notice that one of them is out of position. You can select that single stone, run `RemoveFromGroup` to make it independent, move it to the correct position, and then use `AddToGroup` to put it back into the main group.

### Other Information
This is a fundamental command for managing grouped objects.

---

## 544. RemoveKnot

### Short Info
Remove a knot from a curve or surface.

### Detailed Description
The **RemoveKnot** command is an advanced curve and surface editing tool. It removes "knots" from the internal mathematical structure of a NURBS object. Removing knots can simplify an object's structure, but it will also change its shape.

### Steps to use the command
1.  Turn on the control points for a curve or surface.
2.  Run the command `RemoveKnot`.
3.  Click on the object near the control point you want to remove.
4.  The knot and the corresponding control point will be deleted.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a very direct and often unpredictable way to edit a curve. It is generally better to use commands like `Rebuild` or `FitCrv` for simplification.

### Practical Use Cases
* **Use Case 1 (Manual Simplification):** An advanced user is trying to manually clean up a curve and wants to remove a specific knot that is causing a small imperfection.

### Other Information
This is an advanced tool for users who need to directly manipulate the mathematical structure of NURBS objects.

---

## 545. RemoveMappingChannel

### Short Info
Remove a texture mapping channel from an object.

### Detailed Description
The **RemoveMappingChannel** command is a utility for managing texture mapping. It allows you to delete a specific texture mapping channel from an object. Objects can have multiple mapping channels, and this command lets you remove one without affecting the others.

### Steps to use the command
1.  Select an object.
2.  Run the command `RemoveMappingChannel`.
3.  At the **Mapping channel to remove** prompt, enter the channel number.
4.  The mapping channel will be deleted.

### Command Options & Toggles
This command has no options other than the channel number.

### Practical Use Cases
* **Use Case 1 (Cleaning Up Textures):** You have been experimenting with several different texture maps on an object and have created multiple mapping channels. To clean up the object, you can use this command to remove the channels you are no longer using.

### Other Information
This is a utility for advanced texture mapping workflows.

---

## 546. RemoveMultiKnot

### Short Info
Remove multiple knots from curves and surfaces.

### Detailed Description
The **RemoveMultiKnot** (Remove Multiple Knot) command is an advanced editing tool that removes "fully multiple knots" from a curve or surface. A fully multiple knot is a location where several knots are stacked on top of each other, which is what creates a sharp corner or "kink." This command effectively smooths out a sharp corner.

### Steps to use the command
1.  Run the command `RemoveMultiKnot`.
2.  Select a curve or surface at the location of a kink.
3.  The kink will be removed, and the area will become smooth.

### Command Options & Toggles
This command has no options.

### Note for better use
This command will change the shape of your object. It is the opposite of the `InsertKink` command.

### Practical Use Cases
* **Use Case 1 (Smoothing a Corner):** You have a closed polycurve that has a sharp corner where it was joined. You can use `RemoveMultiKnot` at that corner to smooth it out, creating a continuous, flowing curve.

### Other Information
This is an advanced tool for controlling the mathematical structure of NURBS objects.

---

## 547. Render

### Short Info
Render the objects using the current renderer.

### Detailed Description
The **Render** command is the primary command used to create a photorealistic image of your model. It uses the currently active rendering engine (e.g., Rhino Render, V-Ray), the materials you have applied to your objects, the lights you have placed in your scene, and the camera of the active viewport to generate a high-quality image in a separate "Render Window."

### Steps to use the command
1.  Set up your materials, lighting, and camera angle.
2.  Make the viewport you want to render active.
3.  Run the command `Render`.
4.  The rendering process will begin, and the final image will appear in the Render Window when it is complete.

### Command Options & Toggles
The options for rendering (resolution, quality, etc.) are not in the command line. They are set in the Render Properties panel, which can be accessed from the Render menu or by typing `DocumentProperties` and going to the "Render" page.

### Note for better use
Rendering can be a very time-consuming, processor-intensive task. Before starting a final, high-quality render, it is a good practice to do several low-quality test renders to make sure your lighting and materials are correct.

### Practical Use Cases
* **Use Case 1 (Client Presentation):** You have finished modeling a ring and have applied realistic gold and diamond materials. You use the `Render` command to create a beautiful, photorealistic image of the ring that you can send to the client for approval.
* **Use Case 2 (Portfolio Images):** `Render` is the command used to generate all the final, high-quality images of your work for your website or portfolio.

### Other Information
This is the final output command for creating 2D images from your 3D models.

---

## 548. RenderInWindow

### Short Info
Render a selected area in a viewport in the render window.

### Detailed Description
The **RenderInWindow** command allows you to render only a small, rectangular area of the active viewport, instead of the entire view. The result is displayed in the main Render Window. This is useful for quickly test-rendering a specific detail of your model without having to wait for the entire scene to render.

### Steps to use the command
1.  Run the command `RenderInWindow`.
2.  You will be prompted to draw a rectangle in the viewport.
3.  Only the area inside the rectangle will be rendered.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Testing a Material):** You have just applied a new material to a single prong on a ring and want to see how it looks. Instead of rendering the whole ring, you can use `RenderInWindow` to draw a small box around just that prong. This will give you a very fast preview of the new material.

### Other Information
This is a time-saving tool for iterating on your render settings.

---

## 549. RenderOpenLastRendering

### Short Info
Open the most recent rendering in the render window.

### Detailed Description
The **RenderOpenLastRendering** command is a utility that opens the Rhino Render window and displays the last image that was rendered.

### Steps to use the command
1.  Run the command `RenderOpenLastRendering`.
2.  The render window will open, showing your most recent render.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Reviewing a Render):** You have just finished a render but accidentally closed the render window. This command allows you to open it again to view the image without having to re-render it.

### Other Information
This is a simple display utility.

---

## 550. RenderOpenRenderImage

### Short Info
Open a saved rendering (.rimage) file.

### Detailed Description
The **RenderOpenRenderImage** command opens a render window to display an image that was saved in Rhino's native render file format (.rimage). This format can store extra data, like depth information, that is not available in standard formats like JPG.

### Steps to use the command
1.  Run the command `RenderOpenRenderImage`.
2.  A file browser will open.
3.  Select an .rimage file.
4.  The image will be displayed in the render window.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Post-Processing):** You have saved a render in the .rimage format. You can use this command to open it later and then save it out in a different format (like PNG or JPG) or use post-processing effects available in the render window.

### Other Information
This is a file-opening utility for Rhino's native render format.


---

## 551. RenderPreview

### Short Info
Render the view at a lower quality.

### Detailed Description
The **RenderPreview** command creates a render of the active viewport, but at a lower quality and resolution than the final `Render` command. Its purpose is to provide a very fast preview of the lighting, materials, and shadows in a scene without having to wait for a full, high-quality render to complete.

### Steps to use the command
1.  Set up your materials and lighting.
2.  Make the viewport you want to preview active.
3.  Run the command `RenderPreview`.
4.  A fast, lower-quality render will be created in the render window.

### Command Options & Toggles
This command has no options. It uses the current render settings but at a reduced quality.

### Note for better use
This is an essential tool for an efficient rendering workflow. You should use `RenderPreview` frequently to test your lighting and material setups before committing to a final, time-consuming, high-resolution render with the `Render` command.

### Practical Use Cases
* **Use Case 1 (Checking Lighting):** You have just added several new lights to your scene and want to see how they affect the model. Instead of waiting several minutes for a full render, you can use `RenderPreview` to get an almost instant preview of the new lighting scheme.
* **Use Case 2 (Testing Materials):** You are adjusting the reflectivity of a gold material and want to see how it looks. `RenderPreview` allows you to quickly see the result of your changes without a long wait.

### Other Information
This is a key workflow tool for anyone doing rendering.

---

## 552. RenderPreviewInWindow

### Short Info
Render a selected area in a viewport at a lower quality in the render window.

### Detailed Description
The **RenderPreviewInWindow** command renders only a small, rectangular area of the active viewport at a lower quality, and displays the result in the main Render Window. This is a very fast way to test-render a specific detail of your model.

### Steps to use the command
1.  Run the command `RenderPreviewInWindow`.
2.  You will be prompted to draw a rectangle in the viewport.
3.  Only the area inside the rectangle will be rendered at a low quality in the render window.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Testing a Single Gem):** You are adjusting the material for a single accent stone in a large pavé field. Instead of rendering the whole piece, you can use `RenderPreviewInWindow` to draw a small box around just that one stone to get an ultra-fast preview of your material changes.

### Other Information
This is a time-saving tool for iterating on your render settings for a specific part of a model.

---

## 553. RenderPreviewWindow

### Short Info
Render a selected area in a viewport at a lower quality.

### Detailed Description
The **RenderPreviewWindow** command renders a small, rectangular area of the active viewport at a lower quality, but it displays the result directly *in the viewport* itself, rather than opening the separate render window.

### Steps to use the command
1.  Run the command `RenderPreviewWindow`.
2.  You will be prompted to draw a rectangle in the viewport.
3.  The area inside the rectangle will be rendered at a low quality directly within the viewport.

### Command Options & Toggles
This command has no options.

### Note for better use
This is the fastest of all the render preview commands, as it does not need to open a separate window. It's excellent for very quick, iterative checks.

### Practical Use Cases
* **Use Case 1 (Quick Material Feedback):** You are tweaking the color of a material and want to see the result instantly. You can use this command to draw a small window over the object, and it will update with a low-quality render almost immediately, giving you very fast feedback on your changes.

### Other Information
This is the quickest way to get a render preview of a small detail.

---

## 554. RenderWindow

### Short Info
Render a selected area in a viewport.

### Detailed Description
The **RenderWindow** command renders a small, rectangular area of the active viewport at the **full, final render quality**, and displays the result in the main Render Window. This is used to test-render a specific detail at high quality without having to render the entire scene.

### Steps to use the command
1.  Run the command `RenderWindow`.
2.  You will be prompted to draw a rectangle in the viewport.
3.  The area inside the rectangle will be rendered at full quality in the render window.

### Command Options & Toggles
This command has no options.

### Note for better use
This is different from `RenderPreviewInWindow`, which renders at a lower quality. `RenderWindow` uses your final, high-quality settings.

### Practical Use Cases
* **Use Case 1 (Final Detail Check):** You have finished setting up your lighting and materials using the faster preview commands. Before you start the final, full-size render, you can use `RenderWindow` to render a small, critical area (like the main gemstone) at full quality to make sure everything is perfect. This can save you from having to re-render the entire image if you spot a small mistake.

### Other Information
This is an important quality-control step in a professional rendering workflow.

---

## 555. Reparameterize

### Short Info
Recalculate the parameter space of an object.

### Detailed Description
The **Reparameterize** command is an advanced technical tool that rebuilds a curve or surface so that its parameter space is more uniform and more closely related to its 3D geometry. The "parameter space" is the internal U and V coordinate system of an object. This command can sometimes fix problems or make objects behave more predictably with certain commands.

### Steps to use the command
1.  Select a curve or surface.
2.  Run the command `Reparameterize`.
3.  A dialog box will appear with options.
4.  Choose an option (e.g., `Automatic`) and click OK.

### Command Options & Toggles
* **Automatic:** Attempts to automatically re-parameterize the object.
* **Manual:** Gives you more control over the new domain.

### Note for better use
This is an advanced command that should be used with caution, as it can change how textures are mapped to a surface. For most users, this command is not part of a standard workflow.

### Practical Use Cases
* **Use Case 1 (Fixing a Bad Surface):** You have a surface that is causing problems with other commands, and you suspect its internal parameter space is corrupted or uneven. `Reparameterize` can sometimes fix these kinds of deep-level geometry issues.

### Other Information
This is a tool for advanced users who need to work with the underlying mathematical structure of NURBS objects.

---

## 556. Repeat

### Short Info
Repeat the previous command.

### Detailed Description
The **Repeat** command simply runs the most recent command again.

### Steps to use the command
1.  Run any command (e.g., `Circle`).
2.  Run the command `Repeat`.
3.  The `Circle` command will start again.

### Command Options & Toggles
This command has no options.

### Note for better use
Pressing the **Enter** key or the **right mouse button** in a viewport when no command is active is the universal and much faster way to repeat the last command. The `Repeat` command is primarily for use in scripts.

### Practical Use Cases
* **Use Case 1 (Scripting):** You are writing a script that needs to perform the same action multiple times. You could use the `Repeat` command within the script to do this.

### Other Information
For daily interactive use, always use the Enter key or right-click to repeat a command.

---

## 557. ReplaceBlock

### Short Info
Replace block instances with a different block definition.

### Detailed Description
The **ReplaceBlock** command is a powerful block management tool. It allows you to select one or more block instances in your model and replace them with a different block definition. This is an extremely fast way to swap out components in a complex design.

### Steps to use the command
1.  Run the command `ReplaceBlock`.
2.  A dialog box will appear, listing all the block definitions in your file.
3.  Select the block definition you want to replace from the list.
4.  You will be prompted: **"Select block instances to replace"**. Select the block(s) in the viewport.
5.  Another dialog box will appear. Select the new block definition that you want to use as the replacement.
6.  The selected block instances will be swapped with the new block.

### Command Options & Toggles
This command has no options in the command line.

### Practical Use Cases
* **Use Case 1 (Swapping Gemstone Shapes):** You have designed a ring with 10 round diamonds, which you placed as a block. The client decides they want princess-cut (square) diamonds instead. You can create a new block for the princess-cut diamond. Then, use `ReplaceBlock` to select all 10 round diamond instances and instantly swap them for the new princess-cut block.
* **Use Case 2 (Trying Different Settings):** You have a ring with several 4-prong settings placed as blocks. You want to see how it would look with 6-prong settings instead. You can `Insert` the 6-prong setting block, and then use `ReplaceBlock` to swap all the 4-prong settings for the new 6-prong version.

### Other Information
This is an incredibly powerful and time-saving command for any workflow that uses blocks.

---

## 558. Rescue3dmFile

### Short Info
Recover data from a damaged file.

### Detailed Description
The **Rescue3dmFile** command is an emergency utility used to attempt to recover data from a corrupted or damaged Rhino 3DM file that will not open normally.

### Steps to use the command
1.  Run the command `Rescue3dmFile`.
2.  A file browser will open.
3.  Select the damaged .3dm file.
4.  Rhino will attempt to read the file and recover as much of the geometric data as possible.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a "last resort" tool. There is no guarantee that it will be able to recover all of your data, but it is always worth trying if a critical file becomes corrupted. Using `IncrementalSave` regularly is the best way to prevent catastrophic data loss.

### Practical Use Cases
* **Use Case 1 (File Corruption):** You try to `Open` a file you were working on, but you get an error message and the file will not load. `Rescue3dmFile` is the command you would use to try and salvage the geometry from that corrupted file.

### Other Information
This is a file recovery utility.

---

## 559. Restore

### Short Info
Restore the Rhino window.

### Detailed Description
The **Restore** command restores the main Rhino application window to its normal, non-maximized size if it is currently maximized.

### Steps to use the command
1.  Maximize the Rhino window.
2.  Run the command `Restore`.
3.  The window will return to its previous size.

### Command Options & Toggles
This command has no options.

### Note for better use
This is equivalent to clicking the "Restore Down" button in the top-right corner of the Rhino window.

### Practical Use Cases
* **Use Case 1 (Window Management):** You need to see another program that is behind your maximized Rhino window. `Restore` will shrink the Rhino window so you can see your desktop.

### Other Information
This is a simple window management command.

---

## 560. RevCloud

### Short Info
Draw revision cloud curves.

### Detailed Description
The **RevCloud** (Revision Cloud) command is a 2D drafting and annotation tool. It creates a curve made of sequential arcs that looks like a cloud shape. In technical drawings, revision clouds are used to draw attention to areas of a design that have been changed or updated.

### Steps to use the command
1.  Run the command `RevCloud`.
2.  Click points in the viewport to draw the shape of the cloud.
3.  Press Enter to close the cloud.

### Command Options & Toggles
* **ArcLength:** Controls the size of the individual arcs that make up the cloud.

### Practical Use Cases
* **Use Case 1 (Marking Changes):** You have sent a technical drawing of a ring to a client. They ask you to make one of the dimensions smaller. After you make the change, you can use `RevCloud` to draw a cloud shape around the updated dimension. This makes it very easy for the client to see exactly what has been changed in the new version of the drawing.

### Other Information
This is a standard annotation tool used in the drafting and engineering industries.

---

## 561. Revert

### Short Info
Discard changes and revert to the saved document.

### Detailed Description
The **Revert** command discards all the changes you have made to a file since the last time you saved it. It reloads the last saved version of the file from your hard drive.

### Steps to use the command
1.  Run the command `Revert`.
2.  A confirmation dialog box will appear, warning you that all changes will be lost.
3.  Click Yes to proceed. The file will be reloaded.

### Command Options & Toggles
This command has no options.

### Note for better use
This is a destructive command. Any work you have done since your last save will be permanently lost. It is often safer to use the `Undo` command repeatedly to go back to a previous state.

### Practical Use Cases
* **Use Case 1 (Starting Over):** You have opened a file and have been experimenting with some design changes for ten minutes, but you decide you don't like any of them and want to go back to exactly how the file was when you opened it. `Revert` is a fast way to do this.

### Other Information
This is a file management command.

---

## 562. Revolve

### Short Info
Create a surface by revolving a profile curve around an axis.

### Detailed Description
The **Revolve** command is a fundamental surface creation tool. It creates a 3D surface or solid by rotating a 2D profile curve around a central axis line. This is the primary method for creating any object that has radial symmetry, such as wine glasses, bowls, or simple ring shanks.

### Steps to use the command
1.  Create a profile curve and a line to act as the axis.
2.  Run the command `Revolve`.
3.  At the **Select curves to revolve** prompt, select your profile curve.
4.  At the **Start of revolve axis** prompt, define the axis line.
5.  You will then be prompted for the start and end angles of the revolution (e.g., 360 for a full circle).

### Command Options & Toggles
* **FullCircle:** Automatically sets the revolve angle to 360 degrees.
* **DeleteInput:** Deletes the original profile curve.
* **Deformable:** Creates a more complex, easily editable NURBS surface.

### Note for better use
The profile curve must not cross the axis of revolution.

### Practical Use Cases
* **Use Case 1 (Creating a Simple Bezel):** You can draw the L-shaped cross-section profile of a bezel. Then, use `Revolve` with a vertical axis at the center of your ring to sweep this profile in a circle, creating the 3D bezel in one operation.
* **Use Case 2 (Modeling a Cabochon):** You can draw the domed profile curve of a cabochon gemstone. By revolving this curve 360 degrees around a central axis, you can create the 3D stone.

### Other Information
This is one of the most basic and essential surfacing commands.

---

## 563. RevolvedHole

### Short Info
Create a hole by revolving a profile curve.

### Detailed Description
The **RevolvedHole** command is a specialized boolean tool. It creates a hole in a solid object by revolving a profile curve around an axis and subtracting the resulting shape. This is a shortcut that combines the `Revolve` and `BooleanDifference` commands into a single step.

### Steps to use the command
1.  Run the command `RevolvedHole`.
2.  At the **Select polysurface for hole** prompt, select the solid object.
3.  You will then be prompted to select a profile curve and define the axis of revolution.
4.  A hole will be cut into the solid.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Creating a Chamfered Hole):** You need to create a hole through a plate, but you want the edge of the hole to be beveled. You can draw a profile curve that includes this bevel, and then use `RevolvedHole` to create the hole and the bevel at the same time.

### Other Information
This is a workflow efficiency command.

---

## 564. Rib

### Short Info
Extrude a curve in two opposite directions to a boundary.

### Detailed Description
The **Rib** command is a specialized extrusion tool. It takes a single curve and extrudes it in two opposite directions until it hits a boundary object. This is useful for creating thin "ribs" or support structures that perfectly connect to a main surface.

### Steps to use the command
1.  Create a boundary object (like a ring shank) and a curve inside it.
2.  Run the command `Rib`.
3.  At the **Select curve to rib** prompt, select the curve.
4.  At the **Select boundary polysurface** prompt, select the boundary.
5.  A solid rib will be created.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Creating a Gallery Wire):** You have the inside surface of a ring head and you have drawn a curve where the gallery wire should be. The `Rib` command can extrude this curve in both directions until it hits the inner surface of the head, creating a perfectly fitting gallery wire.

### Other Information
This is a specialized solid creation tool.

---

## 565. Ribbon

### Short Info
Offset a curve and create a ruled surface between the curves.

### Detailed Description
The **Ribbon** command is a surface creation tool. It first offsets a curve, and then creates a simple ruled surface between the original curve and the new offset curve.

### Steps to use the command
1.  Select a curve.
2.  Run the command `Ribbon`.
3.  Define the offset distance and direction.
4.  A ribbon-like surface will be created.

### Command Options & Toggles
The options are similar to the `Offset` command, allowing you to control the distance and corner style.

### Note for better use
This command is essentially a macro that combines the `Offset` and `RuledSrf` commands.

### Practical Use Cases
* **Use Case 1 (Creating a Flat Shank):** You have drawn a single curve representing the centerline of a flat ring shank. The `Ribbon` command can be used to instantly create a flat, ribbon-like surface of a specified width along that curve. You can then `ExtrudeSrf` to give it thickness.

### Other Information
This is a simple surfacing utility.

---

## 566. Rotate

### Short Info
Rotate objects around an axis.

### Detailed Description
The **Rotate** command is a fundamental transformation tool that rotates objects around a center point in the 2D plane of the active viewport.

### Steps to use the command
1.  Select the object(s) to rotate.
2.  Run the command `Rotate`.
3.  At the **Center of rotation** prompt, pick a point to rotate around.
4.  You will then be prompted to define the angle of rotation by picking reference points or typing an angle.

### Command Options & Toggles
* **Copy:** Creates a rotated copy of the object instead of moving the original.

### Note for better use
For rotating objects in full 3D space, use the `Rotate3D` command. The Gumball widget is often a faster, more interactive way to perform simple rotations.

### Practical Use Cases
* **Use Case 1 (Positioning Prongs):** You have created a single prong at the 12 o'clock position of a setting. You can use `Rotate` with the `Copy=Yes` option to create the other prongs. You would pick the center of the setting as the rotation point and enter 90 degrees to create the next prong for a 4-prong head.
* **Use Case 2 (Adjusting an Element):** You have placed a decorative element on a ring, but it is slightly crooked. You can use `Rotate` to make a small adjustment to its angle.

### Other Information
This is one of the most frequently used commands in all of CAD.

---

## 567. Rotate3D

### Short Info
Rotate objects around a 3-D axis.

### Detailed Description
The **Rotate3D** command is a transformation tool that rotates objects around a 3D axis that you define. Unlike the standard `Rotate` command, which is constrained to the 2D construction plane, `Rotate3D` allows you to rotate objects around any arbitrary axis in 3D space.

### Steps to use the command
1.  Select the object(s) to rotate.
2.  Run the command `Rotate3D`.
3.  At the **Start of rotation axis** prompt, pick a point.
4.  At the **End of rotation axis** prompt, pick a second point to define the axis.
5.  You will then be prompted to define the angle of rotation.

### Command Options & Toggles
* **Copy:** Creates a rotated copy of the object.

### Practical Use Cases
* **Use Case 1 (Tilting a Gemstone):** You have a gemstone that is sitting flat in a bezel, but you want to tilt it forward at a 15-degree angle. You would use `Rotate3D`, define a horizontal rotation axis that passes through the center of the stone, and then enter an angle of 15 degrees.
* **Use Case 2 (Creating Complex Assemblies):** You are modeling a watch and need to rotate one of the gears around its tilted axle. `Rotate3D` is the tool you would use to perform this precise 3D rotation.

### Other Information
This is the primary tool for performing precise, non-planar rotations.

---

## 568. RotateCamera

### Short Info
Rotate the view camera.

### Detailed Description
The **RotateCamera** command is a viewport navigation tool. It rotates the camera's position around the camera's target point. This has the effect of orbiting the view around the center of the scene.

### Steps to use the command
1.  Run the command `RotateCamera`.
2.  Click and drag in the viewport to rotate the view.

### Command Options & Toggles
This command has no options.

### Note for better use
Holding down the **right mouse button** and dragging in a perspective viewport is the universal and much faster way to perform this action.

### Practical Use Cases
* **Use Case 1 (Inspecting a Model):** This is the primary method for tumbling and rotating your view to inspect a 3D model from all sides.

### Other Information
This is a core navigation command, though it is almost always activated with the mouse shortcut.

---

## 569. RotateHole

### Short Info
Rotate a hole on a planar surface.

### Detailed Description
The **RotateHole** command is a specialized editing tool that allows you to rotate a hole within a single, planar surface around a center point.

### Steps to use the command
1.  Run the command `RotateHole`.
2.  At the **Select hole edge(s) to rotate** prompt, select the edge of the hole.
3.  At the **Center of rotation** prompt, pick a point.
4.  Define the rotation angle.
5.  The hole will be rotated to the new position.

### Command Options & Toggles
* **Copy:** Creates a rotated copy of the hole.

### Note for better use
This command only works on holes within a single, flat (planar) surface.

### Practical Use Cases
* **Use Case 1 (Adjusting a Layout):** You have cut a hole for a marquise-shaped stone on a flat plate, but you decide it needs to be rotated 10 degrees. `RotateHole` allows you to do this without having to undo, rotate the original curve, and re-trim the hole.

### Other Information
This is a time-saving utility for editing features on flat surfaces.

---

## 570. RotateView

### Short Info
Rotate the view target.

### Detailed Description
The **RotateView** command is a viewport navigation tool. It rotates the camera's target point around the camera's location. This has the effect of "panning your head" while standing still.

### Steps to use the command
1.  Run the command `RotateView`.
2.  Click and drag in the viewport to rotate the view.

### Command Options & Toggles
This command has no options.

### Note for better use
Holding down **Ctrl + Alt + right mouse button** and dragging is a shortcut for this action.

### Practical Use Cases
* **Use Case 1 (Looking Around):** You are in a perspective view and want to look around the scene from your current camera position. `RotateView` allows you to do this.

### Other Information
This is a standard camera navigation tool.

---

## 571. RoundHole

### Short Info
Create a circular hole.

### Detailed Description
The **RoundHole** command is a specialized tool that creates a circular hole in a surface or polysurface. It is a shortcut that combines drawing a circle and trimming it into a single operation.

### Steps to use the command
1.  Run the command `RoundHole`.
2.  At the **Select surface or polysurface** prompt, select the object to cut.
3.  Follow the prompts to define the center and radius of the circular hole.
4.  A hole will be created.

### Command Options & Toggles
The options are for defining the circle, such as setting the **Diameter** or **Radius**.

### Note for better use
This is often faster than drawing a circle and then using the `Trim` or `MakeHole` commands.

### Practical Use Cases
* **Use Case 1 (Drill Holes):** You need to create a small, circular hole through a pendant for a jump ring to pass through. `RoundHole` is the fastest and most direct way to do this.

### Other Information
This is a simple workflow efficiency command.

---

## 572. RPC

### Short Info
Insert Rich Photorealistic Content.

### Detailed Description
The **RPC** command allows you to insert Rich Photorealistic Content (RPC) objects into your model. RPC objects are special, animated 2D assets (like people, trees, and cars) that are designed to look realistic in renders. They are essentially 2D images on a plane that always turns to face the camera.

### Steps to use the command
1.  Run the command `RPC`.
2.  A dialog box will appear, allowing you to choose an RPC file.
3.  Place the object in your scene.

### Command Options & Toggles
This command has no options in the command line.

### Note for better use
RPC is a proprietary format from a company called ArchVision. You need to have purchased and installed RPC libraries for this command to be useful.

### Practical Use Cases
* **Use Case 1 (Architectural Rendering):** An architect is rendering a building and wants to add realistic-looking people walking on the sidewalk. They would use the `RPC` command to insert these assets into their scene. This command has no practical use in jewelry design.

### Other Information
This is a specialized tool for architectural and environmental visualization.

---

## 573. RPCSetAnimationFrame

### Short Info
Set the animation frame for an RPC object.

### Detailed Description
The **RPCSetAnimationFrame** command is a utility for controlling animated RPC objects. If you have inserted an RPC object that has an animation (like a person walking), this command allows you to set which specific frame of that animation is displayed.

### Steps to use the command
1.  Select an animated RPC object.
2.  Run the command `RPCSetAnimationFrame`.
3.  Enter a frame number at the prompt.

### Command Options & Toggles
This command has no options other than the frame number.

### Practical Use Cases
* **Use Case 1 (Architectural Rendering):** An architect has placed an RPC object of a walking person. To get the perfect pose for their still render, they can use this command to scrub through the animation and choose the exact frame they want.

### Other Information
This is a specialized tool for controlling RPC assets.

---

## 574. Run

### Short Info
Run an external program.

### Detailed Description
The **Run** command is a utility used in scripts and macros. It allows you to launch an external program from within Rhino.

### Steps to use the command
1.  This command is used inside a macro or script.
2.  The syntax is `_Run "C:\Path\To\Program.exe"`.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Scripting):** You could write a script that exports an image and then uses the `Run` command to automatically open that image in Photoshop for post-processing.

### Other Information
This is a utility for script developers.

---

## 575. RunPythonScript

### Short Info
Run a Python script.

### Detailed Description
The **RunPythonScript** command is a utility that executes a Python script file (.py).

### Steps to use the command
1.  Run the command `RunPythonScript`.
2.  A file browser will open.
3.  Select the Python script file you want to run.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Custom Tools):** A designer has downloaded or been given a custom tool that is saved as a Python script. They can use this command to run the tool without having to open the Python editor.

### Other Information
This is the primary command for executing external Python scripts.

---

## 576. RunScript

### Short Info
Run a RhinoScript.

### Detailed Description
The **RunScript** command is a utility that executes a RhinoScript file (.rvb).

### Steps to use the command
1.  Run the command `RunScript`.
2.  A file browser will open.
3.  Select the RhinoScript file you want to run.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Legacy Tools):** A designer is using an older custom tool that was written in RhinoScript. They would use this command to run it.

### Other Information
This is the primary command for executing external RhinoScript files.

---

## 577. Save

### Short Info
Save the current model.

### Detailed Description
The **Save** command saves the currently open model to a file on your computer. If the file has been saved before, this command will overwrite the previous version. If the file is new, it will open the "Save As" dialog box, prompting you for a name and location.

### Steps to use the command
1.  Run the command `Save`.
2.  The file will be saved.

### Command Options & Toggles
This command has no options.

### Note for better use
The keyboard shortcut **Ctrl+S** is the universal and much faster way to perform this action. It is a very good practice to save your work frequently. For creating sequential backups, the `IncrementalSave` command is highly recommended.

### Practical Use Cases
* **Use Case 1 (Saving Progress):** You have just finished a major step in your modeling process. You run `Save` (or press Ctrl+S) to ensure that your progress is saved to the file.

### Other Information
This is one of the most fundamental commands in any software application.

---

## 578. SaveAs

### Short Info
Save the current model with a different name.

### Detailed Description
The **SaveAs** command saves the currently open model to a new file with a different name, location, or file type. The original file is left untouched.

### Steps to use the command
1.  Run the command `SaveAs`.
2.  A file save dialog box will appear.
3.  Choose a new name, location, or file type.
4.  Click "Save."

### Command Options & Toggles
The options are contained within the save dialog box.

### Practical Use Cases
* **Use Case 1 (Creating a Version):** You have opened your "Ring_V1.3dm" file and are about to make some major changes. Before you start, you can use `SaveAs` to save a new copy named "Ring_V2.3dm." Now you can work on the new version without affecting the old one.
* **Use Case 2 (Saving to an Older Version):** You need to send a file to a colleague who is using an older version of Rhino. You can use `SaveAs` and, in the "Save as type" dropdown, choose "Rhinoceros 4.0 3D Model" to save a version that they will be able to open.

### Other Information
This is a fundamental file management command.

---

## 579. SaveAsTemplate

### Short Info
Save the current model as a template file.

### Detailed Description
The **SaveAsTemplate** command saves the current file as a template file (.3dm). Template files appear in the list when you run the `New` command. This allows you to save all of your preferred document properties (units, grid settings, layers, dimension styles, etc.) so that you can easily start new projects with all of your settings already configured.

### Steps to use the command
1.  Set up a blank file exactly how you want your template to be (e.g., set units to millimeters, create your standard layers).
2.  Run the command `SaveAsTemplate`.
3.  Give the template file a name.
4.  Now, when you run the `New` command, your new template will appear in the list.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Standardizing Your Workflow):** You can create a template named "Jewelry_Template_MM" that has your units set to millimeters, your tolerance set to 0.001, and all of your standard layers (Shank, Gems, Prongs, Curves) already created. By starting every new project from this template, you save time and ensure all your files are consistent.

### Other Information
Creating a custom template is one of the most important things a new user can do to set up an efficient and professional workflow.

---

## 580. SaveRenderWindowAs

### Short Info
Save the image in the render window to a file.

### Detailed Description
The **SaveRenderWindowAs** command saves the image that is currently displayed in the Rhino Render window to an external image file, such as a JPG, PNG, or TIFF.

### Steps to use the command
1.  Create a render using the `Render` command.
2.  When the render is finished, make sure the render window is active.
3.  Run the command `SaveRenderWindowAs`.
4.  A file save dialog will appear.
5.  Choose a location, name, and file type for your image.

### Command Options & Toggles
The options in the save dialog allow you to choose the image format and compression settings.

### Practical Use Cases
* **Use Case 1 (Saving a Final Render):** You have just completed a final, high-quality render of a ring for a client. You use this command to save the image as a high-quality JPG file that you can then email to them or post on your website.

### Other Information
This is the primary command for saving your final rendered images.

---

## 581. SaveSmall

### Short Info
Save the current model without render and analysis meshes.

### Detailed Description
The **SaveSmall** command saves the current model, but first it automatically clears all the render and analysis meshes. This results in a significantly smaller file size, as the dense polygon meshes used for display are not saved with the file.

### Steps to use the command
1.  Run the command `SaveSmall`.
2.  The file will be saved without its display meshes.

### Command Options & Toggles
This command has no options.

### Note for better use
When you next open a file that was saved with `SaveSmall`, it may take a moment longer to appear in the shaded viewports, as Rhino has to regenerate the render meshes from the NURBS geometry. This is a very good command to use for final delivery or for archiving files, as it creates the smallest possible .3dm file.

### Practical Use Cases
* **Use Case 1 (Emailing a File):** You need to email a large, complex Rhino file to a colleague. To reduce the file size and make it easier to send, you can use `SaveSmall`.
* **Use Case 2 (Archiving Projects):** When you are finished with a project and are archiving it, using `SaveSmall` will save a significant amount of server or hard drive space.

### Other Information
This is an important file management and optimization command.

---

## 582. Scale

### Short Info
Change the size of objects uniformly in three directions.

### Detailed Description
The **Scale** command is a fundamental transformation tool that resizes objects uniformly in all three dimensions (X, Y, and Z). It is also known as a "3D Scale."

### Steps to use the command
1.  Select the object(s) to scale.
2.  Run the command `Scale`.
3.  At the **Base point** prompt, pick a point that will remain stationary.
4.  At the **Scale factor or first reference point** prompt, you can either type a number (e.g., "2" to double the size, "0.5" to halve it) or pick a reference point.
5.  If you picked a reference point, you will be prompted for a second reference point to define the new size.

### Command Options & Toggles
* **Copy:** Creates a scaled copy of the object.

### Note for better use
The Gumball widget provides a very fast and interactive way to perform uniform scaling by holding down the Shift key and dragging one of the square scale handles.

### Practical Use Cases
* **Use Case 1 (Resizing a Ring):** You have a finished ring at a size 7, but the client needs a size 9. You can calculate the required scaling factor (e.g., 1.05) and use the `Scale` command, with the origin (0,0,0) as the base point, to uniformly scale the entire ring up to the new size.
* **Use Case 2 (Adjusting a Component):** You have imported a gemstone model, but it is slightly too small for your setting. You can use `Scale` with reference points to resize it. You would pick the center as the base point, a quadrant on the gem as the first reference point, and the corresponding point on your bezel as the second reference point to make it fit perfectly.

### Other Information
This is one of the most basic and essential transformation commands.

---

## 583. Scale1D

### Short Info
Change the size of objects in one direction.

### Detailed Description
The **Scale1D** (Scale 1 Dimension) command is a transformation tool that resizes objects in a single direction that you define. This is also known as a non-uniform scale.

### Steps to use the command
1.  Select the object(s) to scale.
2.  Run the command `Scale1D`.
3.  At the **Base point** prompt, pick a point that will remain stationary.
4.  At the **Scale factor or first reference point** prompt, pick a second point to define the original length of the scaling axis.
5.  At the **Second reference point** prompt, pick a third point to define the new length.

### Command Options & Toggles
* **Copy:** Creates a scaled copy of the object.

### Note for better use
This command will stretch or squash your object. It should be used with care on complex geometry, as it can distort the shape in undesirable ways.

### Practical Use Cases
* **Use Case 1 (Making a Ring Taller):** You have a signet ring and you want to make the top part taller without making it wider or longer. You can use `Scale1D`, define a vertical scaling axis, and stretch the ring in the Z-direction.
* **Use Case 2 (Stretching a Pattern):** You have a decorative pattern that you want to fit into an elliptical shape. You could use `Scale1D` to stretch the pattern horizontally to match the width of the ellipse.

### Other Information
This is a key tool for creating non-uniform shapes.

---

## 584. Scale2D

### Short Info
Change the size of objects uniformly in two directions.

### Detailed Description
The **Scale2D** command is a transformation tool that resizes objects uniformly in two dimensions (along the X and Y axes of the active construction plane). The height (Z-axis) of the object is not changed.

### Steps to use the command
1.  Select the object(s) to scale.
2.  Run the command `Scale2D`.
3.  Follow the prompts to define a base point and a scale factor, similar to the `Scale` command.

### Command Options & Toggles
* **Copy:** Creates a scaled copy of the object.

### Practical Use Cases
* **Use Case 1 (Widening a Ring):** You have a ring and you want to make it wider and longer (in the Top view) without making it any thicker (in the Z-direction). `Scale2D` is the perfect tool for this.
* **Use Case 2 (Resizing a Flat Pattern):** You have a flat, 2D filigree pattern and need to make it larger. `Scale2D` will resize it in X and Y while ensuring it remains perfectly flat.

### Other Information
This is a standard 2D scaling tool.

---

## 585. ScaleByPlane

### Short Info
Change the size of objects non-uniformly in three directions.

### Detailed Description
The **ScaleByPlane** command is an advanced transformation tool that scales an object by remapping it from a source plane to a target plane. This is similar to the `Orient` command but is specifically for scaling. It allows for complex, non-uniform scaling operations.

### Steps to use the command
1.  Select the object(s) to scale.
2.  Run the command `ScaleByPlane`.
3.  You will be prompted to define a source plane by picking three points.
4.  You will then be prompted to define a target plane by picking three points.
5.  The object will be scaled and deformed to fit the new plane.

### Command Options & Toggles
* **Copy:** Creates a scaled copy of the object.

### Practical Use Cases
* **Use Case 1 (Fitting a Pattern into a Tapered Shape):** You have a rectangular pattern and you want to fit it into a trapezoidal, tapered area on a ring. You can use `ScaleByPlane`, defining the source plane with the corners of the original pattern and the target plane with the corners of the tapered area. The pattern will be non-uniformly scaled to fit perfectly.

### Other Information
This is an advanced transformation tool for complex scaling tasks.

---

## 586. ScaleDimStyle

### Short Info
Scale a dimension style.

### Detailed Description
The **ScaleDimStyle** command is a utility for managing annotation styles. It scales all the size-related properties of a selected dimension style (like text height, arrowhead size, extension line offsets) by a single factor.

### Steps to use the command
1.  Run the command `ScaleDimStyle`.
2.  At the **Name of dimension style to scale** prompt, enter the name of the style.
3.  At the **Scale factor** prompt, enter a number.
4.  A new dimension style will be created with the scaled values.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Creating a Detail View Style):** You have a standard dimension style for your 1:1 drawings. You are creating a detail view on your layout that is zoomed in at a 4:1 scale. To keep the dimension text the same size on the printed page, you need to create a new style where all the sizes are 1/4 of the original. `ScaleDimStyle` with a factor of 0.25 is the fastest way to do this.

### Other Information
This is a time-saving utility for managing annotation standards for drawings with multiple scales.

---

## 587. ScaleNU

### Short Info
Change the size of objects non-uniformly in three directions.

### Detailed Description
The **ScaleNU** (Scale Non-Uniform) command is a transformation tool that resizes objects non-uniformly in the X, Y, and Z directions. It allows you to specify a different scaling factor for each axis.

### Steps to use the command
1.  Select the object(s) to scale.
2.  Run the command `ScaleNU`.
3.  At the **Base point** prompt, pick a point.
4.  You will then be prompted to enter the scale factor for the X direction, then the Y direction, and then the Z direction.

### Command Options & Toggles
* **Copy:** Creates a scaled copy of the object.

### Practical Use Cases
* **Use Case 1 (Creating an Oval from a Circle):** You have a perfectly round, solid sphere, and you want to turn it into an oval-shaped cabochon. You can use `ScaleNU` to stretch it in the X direction by a factor of 1.5, compress it in the Z direction by a factor of 0.5, and leave the Y direction unchanged.
* **Use Case 2 (Adjusting Proportions):** You have a finished ring model, but you decide it needs to be slightly wider and a little less tall. `ScaleNU` allows you to make these independent adjustments to its proportions.

### Other Information
This is the primary tool for non-uniform scaling in 3D.

---

## 588. ScreenCaptureToClipboard

### Short Info
Save a viewport image to the Clipboard.

### Detailed Description
The **ScreenCaptureToClipboard** command takes a screenshot of the active viewport and copies it to the Windows clipboard. This is a fast way to grab an image of your model to paste into another application.

### Steps to use the command
1.  Arrange your view as desired.
2.  Run the command `ScreenCaptureToClipboard`.
3.  The image is now on your clipboard.

### Command Options & Toggles
The options allow you to choose which viewport to capture and how the scale is handled.

### Practical Use Cases
* **Use Case 1 (Quick Updates):** You are in a chat with a client and want to quickly show them your progress. You can arrange the view, run this command, and then paste the image directly into the chat window.

### Other Information
This is a simple utility for creating quick screenshots. The `ViewCaptureToFile` command is used to save the image as a file.

---

## 589. ScreenCaptureToFile

### Short Info
Save a viewport image to a file.

### Detailed Description
The **ScreenCaptureToFile** command takes a screenshot of the active viewport and saves it as an image file (e.g., JPG, PNG).

### Steps to use the command
1.  Arrange your view as desired.
2.  Run the command `ScreenCaptureToFile`.
3.  A file save dialog will appear.
4.  Choose a location, name, and file type for your image.

### Command Options & Toggles
The options allow you to control the resolution and other properties of the saved image.

### Practical Use Cases
* **Use Case 1 (Work-in-Progress Images):** You want to save a series of images to document the progress of your design. You can use this command to quickly save screenshots of your shaded viewport at various stages.

### Other Information
This is the companion command to `ScreenCaptureToClipboard`.

---

## 590. Section

### Short Info
Create a planar curve from the intersection of a cutting plane and objects.

### Detailed Description
The **Section** command creates cross-section curves by intersecting a cutting plane with one or more objects. It is similar to `Contour` but is used for creating a single cross-section at a specific location rather than a series of evenly spaced ones.

### Steps to use the command
1.  Select the object(s) to section.
2.  Run the command `Section`.
3.  At the **Start of section** prompt, pick a point.
4.  At the **End of section** prompt, pick a second point to define the cutting plane.
5.  A new curve will be created where the plane intersects the object(s).

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Creating a Profile Curve):** You have a complex, solid ring shank and you need to get the exact cross-section profile at one specific location. You can run `Section` and draw a line through the shank at that point. The command will generate the precise profile curve.
* **Use Case 2 (Analysis):** You want to check the wall thickness of a hollow object. You can use `Section` to create a cross-section curve, which will show you the inner and outer profiles, making it easy to measure the thickness.

### Other Information
This is a fundamental tool for analysis and reverse-engineering.

---

## 591. SelAll

### Short Info
Select all objects.

### Detailed Description
The **SelAll** (Select All) command selects every visible object in the model.

### Steps to use the command
1.  Run the command `SelAll`.
2.  All objects will be selected.

### Command Options & Toggles
This command has no options.

### Note for better use
The keyboard shortcut **Ctrl+A** is the universal and much faster way to perform this action.

### Practical Use Cases
* **Use Case 1 (Exporting a Model):** You want to export your entire model to another file format. You can use `SelAll` (Ctrl+A) to select everything before running the `Export` command.
* **Use Case 2 (Grouping):** You want to group every object in your model together to move or scale it as a single unit.

### Other Information
This is a basic selection command.

---

## 592. SelBadObjects

### Short Info
Select all objects that are not valid.

### Detailed Description
The **SelBadObjects** (Select Bad Objects) command is a diagnostic tool. It runs the `Check` command on every object in the model and selects any object that is reported as being "bad" or invalid.

### Steps to use the command
1.  Run the command `SelBadObjects`.
2.  If any bad objects are found, they will be selected.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Model Cleanup):** Before you export a file for 3D printing, it's a good practice to run `SelBadObjects`. If anything is selected, you know you have some geometry that needs to be repaired before you can proceed.

### Other Information
This is a key diagnostic and repair tool.

---

## 593. SelBlockInstance

### Short Info
Select all block instances.

### Detailed Description
The **SelBlockInstance** command is a selection tool that finds and selects all block instances in the model.

### Steps to use the command
1.  Run the command `SelBlockInstance`.
2.  All block instances will be selected.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Finding All Blocks):** You want to quickly see which objects in your model are blocks. Running this command will highlight all of them.

### Other Information
This is a simple selection filter.

---

## 594. SelBlockInstanceNamed

### Short Info
Select block instances by name.

### Detailed Description
The **SelBlockInstanceNamed** command is a selection tool that selects all block instances that have a specific name.

### Steps to use the command
1.  Run the command `SelBlockInstanceNamed`.
2.  A dialog box will appear listing all the block definitions in your file.
3.  Select a name from the list.
4.  All instances of that block will be selected.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Selecting All Gems of One Size):** You have a model with many different gemstone blocks ("Diamond_1.5mm", "Diamond_2.0mm", etc.). You want to select only the 1.5mm diamonds. You can run this command and choose "Diamond_1.5mm" from the list to select all of them instantly.

### Other Information
This is a very powerful and useful tool for working with complex models that use blocks for organization.

---

## 595. SelBoundary

### Short Info
Select objects based on a boundary curve.

### Detailed Description
The **SelBoundary** (Select Boundary) command is a selection tool that selects objects based on whether they are inside, outside, or crossing a closed boundary curve.

### Steps to use the command
1.  Draw a closed curve to act as the selection boundary.
2.  Run the command `SelBoundary`.
3.  At the **Select boundary curve** prompt, select the curve.
4.  The command line will show options for the selection mode.
5.  Choose an option (e.g., `Inside`). All objects inside the boundary will be selected.

### Command Options & Toggles
* **Mode (Inside/Outside/Crossing):** Sets the selection criteria.

### Practical Use Cases
* **Use Case 1 (Selecting Stones in a Region):** You have a pavé field of hundreds of stones and you need to select all the stones that fall within a specific, irregular area. You can draw a closed curve around that area and then use `SelBoundary` with the `Inside` mode to select only those stones.

### Other Information
This is a more precise selection tool than a simple window or crossing selection.

---

## 596. SelBrush

### Short Info
Select objects by painting.

### Detailed Description
The **SelBrush** command is a selection tool that allows you to select objects by "painting" over them with a circular brush.

### Steps to use the command
1.  Run the command `SelBrush`.
2.  Click and drag the mouse in the viewport. A circle will appear at your cursor, and any object it touches will be selected.

### Command Options & Toggles
* **Radius:** Allows you to change the size of the brush.

### Practical Use Cases
* **Use Case 1 (Selecting from a Dense Field):** You have a very dense field of small objects (like pavé stones or mesh faces) and you need to select a specific, organic-shaped group of them. `SelBrush` allows you to "paint" your selection in a very intuitive, free-form way.

### Other Information
This is a useful tool for making complex, organic selections.

---

## 597. SelBrushPoints

### Short Info
Select points by painting.

### Detailed Description
The **SelBrushPoints** command is a selection tool that allows you to select control points or point objects by "painting" over them with a circular brush.

### Steps to use the command
1.  Turn on the control points for an object.
2.  Run the command `SelBrushPoints`.
3.  Click and drag the mouse. Any control point the brush touches will be selected.

### Command Options & Toggles
* **Radius:** Allows you to change the size of the brush.

### Practical Use Cases
* **Use Case 1 (Organic Sculpting):** You are editing a complex, organic surface with thousands of control points. You want to select a soft, circular group of points to pull up to create a dome. `SelBrushPoints` is the perfect tool for "painting" this soft selection.

### Other Information
This is the point-selection equivalent of the `SelBrush` command.

---

## 598. SelNamedViewWidget

### Short Info
Select named view camera widgets.

### Detailed Description
The **SelNamedViewWidget** command is a selection utility that finds and selects all the camera widgets that are created when you save a view with the `NamedView` command.

### Steps to use the command
1.  Run the command `SelNamedViewWidget`.
2.  All named view camera widgets will be selected.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Cleaning a Scene):** You have saved many named views, and your viewports are now cluttered with camera widgets. This command allows you to select them all at once so you can hide or delete them.

### Other Information
This is a simple selection filter.

---

## 599. NamedView

### Short Info
Save and restore views.

### Detailed Description
(This is a duplicate entry in the source documentation list, pointing to the same command as #425). The **NamedView** command opens a panel that allows you to save and restore specific camera views. This includes the camera's position, rotation, target, and lens length. It's like creating a bookmark for a specific way of looking at your model.

### Steps to use the command
1.  Run the command `NamedView`.
2.  The Named Views panel will open.
3.  Arrange your viewport to the exact camera angle you want to save.
4.  Click the "Save" icon in the panel and give the view a name.
5.  To return to that view later, simply double-click its name in the list.

### Command Options & Toggles
All options are contained within the panel's interface.

### Practical Use Cases
* **Use Case 1 (Consistent Renders):** You have found the perfect "hero shot" perspective angle for rendering your ring. You use `NamedView` to save this as "Render_Angle_01." Now, you can make changes to your model, and whenever you are ready to render, you can instantly return to that exact same camera angle, ensuring all your renders are consistent.

### Other Information
This entry is a duplicate of command #425.

---

## 600. SelCaptives

### Short Info
Select captive objects.

### Detailed Description
The **SelCaptives** (Select Captives) command is a selection utility used with the `CageEdit` command. It selects the "captive" objects that are being controlled by a selected "control" cage object.

### Steps to use the command
1.  Run the command `SelCaptives`.
2.  At the **Select control objects** prompt, select a cage object.
3.  All the captive objects that are being deformed by that cage will be selected.

### Command Options & Toggles
This command has no options.

### Practical Use Cases
* **Use Case 1 (Managing Cage Edits):** You have a complex scene with multiple cage deformations active. You can't remember which ring is being controlled by which cage. You can use `SelCaptives` and click on a cage to instantly see which object(s) it is affecting.

### Other Information
This is a utility for managing `CageEdit` relationships.    

