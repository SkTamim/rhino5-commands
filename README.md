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
* **Use Case 2 (Manufacturing Prep):** A laser engraving machine's software only accepts simple polylines from a DXF file. You would create a scheme where the Curves tab is set to convert all splines to polylines. This ensures the file you send is 100% compatible with the machine.

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
* **Use Case 1 (Walking a Selection):** You have selected a control point and want to select the next one in its row without deselecting the current one. Running `AddNextU` is faster than holding Shift and clicking the next point.
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
The documentation confirms this command constructs a displacement display mesh for surfaces, polysurfaces, or meshes.
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
This is an advanced surfacing tool for creating high-quality transitions.

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
Mastering `BlendSrf` is essential for creating high-quality, freeform surfaces.

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
* **Use Case 1 (Managing Gemstones):** You are designing a piece with dozens of 1.5mm round diamonds. Model one 1.5mm diamond and turn it into a block named "Diamond_1.5mm". Now, insert instances of this block wherever you need a stone. If you later decide to change the diamond's model (e.g., use a more detailed one for rendering), you only need to edit the one block definition, and all the diamonds in your piece will update instantly.
* **Use Case 2 (Reusable Components):** You have designed a custom 4-prong setting that you use frequently in your designs. Turn the entire setting into a block. You can then insert this block into any new design. This saves you from having to remodel it every time and ensures consistency across your work.

### Other Information
Blocks are a powerful tool for efficiency, organization, and file size management in complex models.

---

## 54. BlockEdit

### Short Info
Select a block instance to change the block geometry and update the block definition.

### Detailed Description
The **BlockEdit** command is the tool used to modify the geometry within a block definition. When you run this command and select a block instance, it temporarily opens a special editing session where only the objects inside that block are visible and editable. Any changes you make (moving, deleting, adding objects) are saved to the block definition. When you exit the editing session, all instances of that block throughout your model will update to reflect your changes.

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
* **Use Case 1 (Changing Gem Proportions):** You have used a block for all the 1.5mm diamonds in your model. You now decide that the pavilion (bottom part) of the diamond model is too deep. Run `BlockEdit` on any one of the diamond instances. In the editing session, scale the pavilion to make it shallower. When you exit, all the diamonds in your entire piece will update with the new proportions.
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
You can create blocks that are linked to an external Rhino file. This is very powerful for team collaboration. If one person updates the external file (e.g., changes the design of a standard clasp), everyone else using that linked block will be notified in the `BlockManager` that an update is available. If you have deleted all instances of a block, its definition still exists in the file. You can use the `Purge` command or the `Delete` button in the `BlockManager` to remove these unused definitions and reduce file size.

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
The **Cage** command creates a special "control cage" object. This cage, which can be a box, sphere, or other shape, is not part of your final model. Instead, it is used by the `CageEdit` command as a tool to smoothly deform other objects. You create the cage around the geometry you want to edit, and then you manipulate the control points of the cage to push, pull, and twist the geometry inside it.

### Steps to use the command
1.  Run the command `Cage`.
2.  The command line will show several options for the shape of the cage.
3.  Select an option (e.g., `BoundingBox`).
4.  Follow the prompts to define the cage object. For `BoundingBox`, you would select the objects to be deformed.
5.  A new cage object with its own control points will be created around your selected geometry.

### Command Options & Toggles
* **BoundingBox:** Creates a cage that is the same size as the bounding box of selected objects.
* **Line, Rectangle, Box, Sphere, etc.:** Allows you to create a cage with a specific primitive shape.
* **Deformable:** Creates a NURBS cage instead of a simple cage object.

### Note for better use
`Cage` only creates the control object. The actual deformation is done with the `CageEdit` command. You can define the number of control points in the X, Y, and Z directions when you create the cage. More points allow for more detailed deformation, while fewer points create a smoother, more global deformation.

### Practical Use Cases
* **Use Case 1 (Pinching a Shank):** You have a simple, straight-sided ring shank and you want to create a gentle, organic "pinch" or taper in the middle. Create a `Box` cage around the ring shank. Use `CageEdit` to associate the ring with the cage. Then, select the control points in the middle of the cage and scale them inward. The ring shank inside will deform smoothly.
* **Use Case 2 (Adding Swell):** You have a flat pendant and want to make it swell out in the middle, like it was inflated. Create a cage around the pendant. Use `CageEdit`, and then pull the control points on the top and bottom of the cage outward. The flat pendant will deform into a smooth, domed shape.

### Other Information
This command is the first step in a powerful two-step free-form deformation process.

---

## 70. CageEdit

### Short Info
Deform objects smoothly using control cage objects.

### Detailed Description
The **CageEdit** command is the second part of the cage editing process. It associates a "captive" object (the geometry you want to deform) with a "control" object (the cage you created with the `Cage` command). Once the association is made, you can turn on the control points for the cage and move them. As you move the cage's control points, the captive geometry inside will be smoothly and organically deformed.

### Steps to use the command
1.  Run the command `CageEdit`.
2.  At the **Select captive object(s)** prompt, select the geometry you want to deform (e.g., your ring) and press Enter.
3.  At the **Select control object** prompt, select the cage you created earlier.
4.  The association is now active.
5.  Select the cage object and turn on its control points (F10).
6.  Move, scale, or rotate the cage's control points to deform the captive object.

### Command Options & Toggles
* **Region to edit:** Allows you to define a falloff distance so that the deformation is localized to a specific area.

### Note for better use
When you are finished deforming the object, you can use the `ReleaseFromCage` command to break the link between the captive and control objects. You can have a single cage control multiple captive objects at the same time.

### Practical Use Cases
* **Use Case 1 (Tapering a Bezel):** You have a straight-walled bezel and want to give it a slight, smooth taper. Create a box cage around the bezel. Use `CageEdit` to link them. Turn on the cage's control points, select the entire top row of points, and use the 2D scale command to shrink them slightly. The bezel will deform into a perfect, smooth taper.
* **Use Case 2 (Asymmetrical Shapes):** You have a perfectly symmetrical pendant and want to give it a more handmade, asymmetrical look by twisting it slightly. Create a cage around the pendant and link them with `CageEdit`. Select one side of the cage's control points and rotate them slightly. The pendant inside will twist and deform in a very smooth, organic way.

### Other Information
This is a powerful free-form modeling technique for creating complex, organic shapes.

---

## 71. Calc

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

## 72. CalcRPN

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

## 73. Camera

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

## 74. Cancel

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

## 75. Cap

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

## 76. Chamfer

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

## 77. ChamferEdge

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

## 78. ChamferSrf

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

## 79. ChangeDegree

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

## 80. ChangeLayer

### Short Info
Change an object's layer.

### Detailed Description
The **ChangeLayer** command moves one or more selected objects to a different layer. Layers are the primary method for organizing a Rhino model. This command opens a dialog box that lists all the layers in your model, allowing you to choose the destination layer for the selected objects.

### Steps to use the command
1.  Select the object(s) you want to move.
2.  Run the command `ChangeLayer`.
3.  The "Change Object Layer" dialog box will appear.
4.  Select the desired destination layer from the list.
5.  Click OK.

### Command Options & Toggles
The options are the buttons within the dialog box, allowing you to select a layer or create a new one.

### Note for better use
There are several ways to change an object's layer. You can also right-click on the layer in the Layer panel and choose "Change Object Layer," or use the pie menu in Matrix. The `ChangeLayer` command is simply the typed-command method.

### Practical Use Cases
* **Use Case 1 (Organization):** You have just created a set of prongs for a ring. To keep your model organized, you select the new prongs, run `ChangeLayer`, and move them to your "Prongs" layer.
* **Use Case 2 (Correcting Mistakes):** You realize you accidentally created a gemstone on your "Metal" layer. You select the gemstone, run `ChangeLayer`, and move it to the correct "Gems" layer.

### Other Information
Proper layer management is one of the most important habits for efficient and professional CAD modeling.

---

## 81. ChangeToCurrentLayer

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
This command is very efficient and is often assigned to a custom toolbar button or keyboard shortcut for rapid layer organization.

### Practical Use Cases
* **Use Case 1 (Fast Workflow):** You are modeling a ring and are currently working on the "Shank" layer. You create a new curve that will be part of the shank. Since the "Shank" layer is already active, you can simply select the curve, run this command, and it will be moved instantly without any extra clicks.

### Other Information
This command streamlines the process of layer management by removing the need to select a layer from a list.

---

## 82. Check

### Short Info
Inspect an object for errors.

### Detailed Description
The **Check** command is a diagnostic tool that examines the data structure of a selected object for any internal errors, corruption, or invalid geometry. If it finds a problem, it will report it in the command history. This is an important tool for troubleshooting problematic objects that are failing in other commands.

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

## 83. CheckInLicense

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

## 84. CheckNewObjects

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
* **Use Case 1 (Troubleshooting a Bad Import):** You are importing a complex IGES file that is known to have some problematic surfaces. Before importing, you can enable `CheckNewObjects`. As Rhino imports the file, it will alert you to each individual bad surface as it is created, making it much easier to find and fix them.
* **Use Case 2 (Diagnosing a Failing Command):** You are using a complex command that is creating bad objects. You can turn on `CheckNewObjects` to get an immediate warning the moment the bad geometry is created, helping you to diagnose the problem with the command's inputs or settings.

### Other Information
This is an advanced diagnostic tool for pinpointing the source of bad geometry.

---

## 85. CheckOutLicense

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

## 86. Circle

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

## 87. ClearAllMeshes

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

## 88. ClearDrawOrder

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

## 89. ClearUndo

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

## 90. ClippingPlane

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
