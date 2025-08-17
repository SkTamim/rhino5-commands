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