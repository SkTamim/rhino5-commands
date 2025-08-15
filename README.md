# Gemvision Matrix & Rhino Command Analysis

---

## 1. 3DFace

### 1. Detailed Description
The **3DFace** command is a fundamental mesh-building tool. Its sole purpose is to create a single, flat mesh face by specifying its corner points (vertices). A mesh face is the most basic building block of a mesh object (like an STL file). This command allows you to construct or repair a mesh one polygon at a time. The resulting face can be either a triangle (3 sides) or a quadrangle (4 sides). This command does not create a NURBS surface; it is used exclusively for working with mesh geometry.

### 2. Steps to Use the Command
1.  Run the command by typing `3DFace` and pressing Enter.
2.  You will be prompted: **"First corner of polygon"**. Click a location in the viewport, typically snapping to an existing vertex on a mesh.
3.  You will be prompted: **"Second corner of polygon"**. Click the second point.
4.  You will be prompted: **"Third corner of polygon"**. Click the third point. At this stage, a triangular face will be previewed.
5.  You will be prompted: **"Fourth corner of polygon. Press Enter for triangle"**.
    * To create a **triangle**, press the **Enter** key. The command completes.
    * To create a **quadrangle**, click the fourth point. The command completes.

### 3. Command Options & Toggles
This command has no clickable options or toggles in the command line. The only "option" is the choice to create a 3-sided or 4-sided face, which is determined by your actions in Step 5.

### 4. Additional Notes for Better Use
* **Snapping is Key:** This command is almost always used with **Vertex** object snap (`Vtx`) turned on. This allows you to precisely snap to the corners of existing mesh faces to patch holes accurately.
* **Planarity:** While you can pick four non-planar points to create a quad face, this is generally not recommended as it will create a non-planar (warped) polygon, which can cause issues in some 3D printing and rendering applications. It's best to ensure all points for a single face lie on the same plane.
* **Direction Matters:** The direction you pick the points (clockwise vs. counter-clockwise) determines the "normal" direction of the face (which way is considered "front" or "out"). If a face appears dark or inverted, its normal is likely facing the wrong way. You can fix this later with the `Flip` command.

### 5. Practical Use Cases
* **Use Case 1 (Repair): Manually Patching Holes in an STL File**
    * **Scenario:** The most common use. You receive an STL file of a ring for 3D printing, but it has a few missing triangles, making it "non-watertight."
    * **Application:** You would zoom in on the hole, turn on Vertex snap, and use `3DFace` to redraw the missing triangle(s) by snapping to the existing vertices around the hole. This closes the mesh, making it printable.
* **Use Case 2 (Creation): Low-Polygon Modeling**
    * **Scenario:** You need to model a very simple, faceted object like a basic pyramid or a custom-shaped, low-poly gemstone for a stylized render.
    * **Application:** You can construct the object face by face. For a pyramid, you would create the 4-sided base with one `3DFace` command, then create the four 3-sided triangular faces for the sides.

### 6. Other Information from Documentation
The Rhino Help documentation confirms this is a basic mesh command. It does not have any hidden options or advanced features. It is a simple, direct tool for creating a single mesh polygon from 3 or 4 points.

---

## 2. 3View

### 1. Detailed Description
The **3View** command is a viewport management tool that instantly resets your workspace to a standard three-viewport layout. This layout is designed to optimize the screen for 3D modeling tasks where a large perspective view is needed alongside key 2D orthographic views for reference and precision. The typical arrangement consists of one large Perspective viewport and two smaller Top and Front viewports.

### 2. Steps to Use the Command
1.  Run the command by typing `3View` and pressing Enter.
2.  The viewport layout will immediately change to the default three-view configuration. There are no further steps.

### 3. Command Options & Toggles
The `3View` command itself has no options in the command line; it is an immediate action. However, you can access different three-view layouts by right-clicking the viewport tabs at the bottom of the screen and selecting from the "Layout" presets.

### 4. Additional Notes for Better Use
* **Quick Reset:** This command is an excellent way to quickly restore a standardized, functional workspace if you have accidentally closed or resized your viewports into a confusing state.
* **Efficiency:** For tasks that are primarily 3D (like sculpting or stone setting), using `3View` is more efficient than constantly maximizing and minimizing the Perspective window from the four-view layout.

### 5. Practical Use Cases
* **Use Case 1: Detailed 3D Modeling and Sculpting**
    * **Scenario:** You are working on the fine details of an organic, sculpted piece, like a flowing leaf motif on a ring. You need the largest possible 3D view to see the form, but also need to check the Top and Front views to ensure the proportions are correct.
    * **Application:** Running `3View` provides the ideal balance, giving you a dominant Perspective workspace without completely losing your 2D reference points.
* **Use Case 2: Modeling from a 2D Reference Image**
    * **Scenario:** You have placed a sketch or photograph of a piece of jewelry in the Front view as a `BackgroundBitmap` and need to model from it.
    * **Application:** The `3View` layout allows you to keep the Front view clearly visible for tracing while giving you a large, real-time 3D preview of your work in the Perspective view.

### 6. Other Information from Documentation
The documentation confirms that this is a direct command to set up a three-viewport workspace. It is a sister command to `4View` and is used for managing the modeling environment.

---

## 3. 4View

### 1. Detailed Description
The **4View** command is the most fundamental viewport management tool. It instantly resets your workspace to the default four-viewport layout, with each viewport having an equal size. This is the standard starting configuration for Rhino and Matrix. The layout consists of:
* **Top** (Orthographic)
* **Front** (Orthographic)
* **Right** (Orthographic)
* **Perspective** (3D View)

This setup provides a comprehensive view of your model from all primary angles simultaneously.

### 2. Steps to Use the Command
1.  Run the command by typing `4View` and pressing Enter.
2.  The viewport layout will immediately change to the default four-view configuration. There are no further steps.

### 3. Command Options & Toggles
Just like `3View`, the `4View` command executes immediately and has no interactive options in the command line. It is a direct command to restore the default four-view layout.

### 4. Additional Notes for Better Use
* **The Standard:** This is the default workspace for a reason. For most modeling tasks, it provides all the necessary visual information at once. It's good practice to return to this view often to check your work from all angles.
* **Double-Click to Maximize:** Remember that you can double-click on any viewport's title (e.g., "Top") to maximize it, and double-click again to return to the `4View` layout.

### 5. Practical Use Cases
* **Use Case 1: The Default Modeling Environment**
    * **Scenario:** This is the starting point for nearly all projects. It allows you to draw a 2D curve in the **Top** view, see its height in the **Front** and **Right** views, and understand its form in the **Perspective** view, all without changing the screen layout.
    * **Application:** This command is most often used to quickly get back to this balanced, all-purpose layout after having maximized a single viewport.
* **Use Case 2: Precise Object Placement and Alignment**
    * **Scenario:** You need to align a gemstone perfectly within a bezel. You must ensure it's centered in the Top view, at the correct height in the Front view, and properly seated from the Right view.
    * **Application:** This layout is essential for such tasks. You can make an adjustment in one viewport and immediately see the result and check for errors in the other three. This prevents mistakes that are easy to make when working in a single perspective view.

### 6. Other Information from Documentation
The documentation confirms this command's function is to restore the default four-viewport workspace.

---

## 4. AcadSchemes

### 1. Detailed Description
The **AcadSchemes** command opens the "AutoCAD Export Schemes" dialog box. This is a configuration utility, not a modeling command. Its purpose is to create, save, and manage different sets of rules (called "schemes") for how your Matrix/Rhino geometry should be translated when you export it to AutoCAD file formats like **.DWG** or **.DXF**. This is crucial because Rhino's 3D NURBS objects must be converted into a format that AutoCAD can understand, and you need control over how that conversion happens.

### 2. Steps to Use the Command
1.  Run the command by typing `AcadSchemes` and pressing Enter.
2.  The "AutoCAD Export Schemes" dialog box will appear.
3.  Select an existing scheme to modify, or click "New" to create one.
4.  Adjust the settings in the "General" and "Curves" tabs to control the export behavior.
5.  Click "Save" or "SaveAs" to store your settings as a named scheme.
6.  Click "Close" to exit the dialog box.

### 3. Command Options & Toggles
The options are all contained within the dialog box:
* **General Tab:** Controls the AutoCAD version for compatibility, and how surfaces and meshes are converted (e.g., into meshes or wireframe curves).
* **Curves Tab:** Gives you precise control over how curves are exported, including options to simplify them or convert them into basic polylines.
* **Scheme Management Buttons:** Includes `New`, `Save`, `SaveAs`, `Delete`, `Rename`, `Import`, and `Export` to manage your saved schemes.

### 4. Additional Notes for Better Use
* **Create Multiple Schemes:** It's highly recommended to create and save different schemes for different tasks (e.g., a "2D for Laser" scheme, a "3D for Engineer" scheme). This saves you from having to remember and change the settings every time you export.
* **Compatibility is Key:** Always ask the person you are sending the file to which version of AutoCAD they are using and set the "AutoCAD Version" dropdown accordingly to avoid compatibility issues.

### 5. Practical Use Cases
* **Use Case 1: Collaborating with a 2D Drafter**
    * **Scenario:** You have designed a complex 3D ring, but another person needs to create a 2D technical drawing from it in AutoCAD.
    * **Application:** You would create a scheme that sets "Export surfaces as" to "Curves" and checks "Project to plane." When you export the Top view of your ring using this scheme, the drafter will receive a perfectly flat, clean 2D line drawing.
* **Use Case 2: Sending a Model for Laser Engraving**
    * **Scenario:** A flat pattern on a signet ring needs to be laser engraved, and the machine's software only accepts simple polylines from a DXF file.
    * **Application:** You would create a scheme where the Curves tab is set to convert all splines to polylines. This ensures the file you send is 100% compatible.

### 6. Other Information from Documentation
* **Note from Documentation:** The settings are saved in the registry. To transfer the settings to another computer, use the Export and Import buttons. When you export curves to DXF/DWG, polylines are created from the curves. In the export dialog box, you can set the way the polylines are created. The settings are saved in the scheme.

---

## 5. AddNextU

### 1. Detailed Description
The **AddNextU** command expands a selection of control points on a curve or surface by adding the next control point in the positive U direction. This is part of a family of commands used for structured, incremental selection of control points.

### 2. Steps to Use the Command
1.  Turn on control points for a surface or curve (`PointsOn` or F10).
2.  Select at least one control point.
3.  Run the command `AddNextU`.
4.  The adjacent control point in the positive U direction will be added to the current selection.

### 3. Command Options & Toggles
This command is a direct action and has no options or toggles.

### 4. Additional Notes for Better Use
* **See `AddNextV`, `AddPrevU`, `AddPrevV`:** This command is almost always used in conjunction with its counterparts to select entire rows or blocks of control points.
* **U Direction:** To see the U direction of a surface, use the `Dir` command.

### 5. Practical Use Cases
* **Use Case 1: Walking a Selection**
    * **Scenario:** You have selected a control point and want to select the next one in its row without deselecting the current one.
    * **Application:** Running `AddNextU` is faster than holding Shift and clicking the next point, especially if assigned to a keyboard shortcut.

### 6. Other Information from Documentation
The documentation confirms this command adds the next control point in the u-direction to the selection.

---

## 6. AddNextV

### 1. Detailed Description
The **AddNextV** command expands a selection of control points on a surface by adding the next control point in the positive V direction.

### 2. Steps to Use the Command
1.  Turn on control points for a surface (`PointsOn` or F10).
2.  Select at least one control point.
3.  Run the command `AddNextV`.
4.  The adjacent control point in the positive V direction will be added to the current selection.

### 3. Command Options & Toggles
This command is a direct action and has no options or toggles.

### 4. Additional Notes for Better Use
* **V Direction:** To see the V direction of a surface, use the `Dir` command.

### 5. Practical Use Cases
* **Use Case 1: Expanding a Selection Across Rows**
    * **Scenario:** You have selected a row of control points using `AddNextU`/`AddPrevU` and now want to select the entire adjacent row as well.
    * **Application:** With the first row selected, running `AddNextV` will add the entire next row of control points to your selection.

### 6. Other Information from Documentation
The documentation confirms this command adds the next control point in the v-direction to the selection.

---

## 7. AddPrevU

### 1. Detailed Description
The **AddPrevU** command expands a selection of control points on a curve or surface by adding the previous control point in the negative U direction.

### 2. Steps to Use the Command
1.  Turn on control points for a surface or curve (`PointsOn` or F10).
2.  Select at least one control point.
3.  Run the command `AddPrevU`.
4.  The adjacent control point in the negative U direction will be added to the current selection.

### 3. Command Options & Toggles
This command is a direct action and has no options or toggles.

### 4. Additional Notes for Better Use
* **See `AddNextU`, `AddNextV`, `AddPrevV`:** This command is part of the control point selection family.

### 5. Practical Use Cases
* **Use Case 1: Selecting a Full Row of Control Points**
    * **Scenario:** You want to adjust the dome height of a signet ring. To do this smoothly, you need to select an entire row of control points that runs across the top.
    * **Application:** Select a single control point in the middle of the row. Then, repeatedly use `AddNextU` until you reach one edge, and `AddPrevU` until you reach the other. This selects the entire row perfectly.

### 6. Other Information from Documentation
The documentation confirms this command adds the previous control point in the u-direction to the selection.

---

## 8. AddPrevV

### 1. Detailed Description
The **AddPrevV** command expands a selection of control points on a surface by adding the previous control point in the negative V direction.

### 2. Steps to Use the Command
1.  Turn on control points for a surface (`PointsOn` or F10).
2.  Select at least one control point.
3.  Run the command `AddPrevV`.
4.  The adjacent control point in the negative V direction will be added to the current selection.

### 3. Command Options & Toggles
This command is a direct action and has no options or toggles.

### 4. Additional Notes for Better Use
* **See `AddNextU`, `AddNextV`, `AddPrevU`:** This command is part of the control point selection family.

### 5. Practical Use Cases
* **Use Case 1: Creating Smooth, Controlled Surface Deformations**
    * **Scenario:** You need to create a gentle, concave dip in the surface of a pendant.
    * **Application:** Select a central control point. Use the `Add...U/V` family of commands to expand your selection to a small, square group of points. You can then move this group down to create a smooth depression.

### 6. Other Information from Documentation
The documentation confirms this command adds the previous control point in the v-direction to the selection.

---

## 9. AddToGroup

### 1. Detailed Description
The **AddToGroup** command allows you to add one or more objects to a group that has already been created. A "group" is a collection of objects that can be selected and transformed together as a single unit, without permanently merging their geometry. This command modifies an existing group rather than creating a new one.

### 2. Steps to Use the Command
1.  Run the command `AddToGroup`.
2.  You will be prompted: **"Select objects to add"**. Select the object(s) you want to add to a group and press Enter.
3.  You will be prompted: **"Select group to add to"**. Click on any object that is already a member of the target group.
4.  The objects selected in step 2 are now part of the target group.

### 3. Command Options & Toggles
This command has no clickable options or toggles in the command line.

### 4. Additional Notes for Better Use
* **Organization:** Grouping is a non-destructive way to keep complex models organized. Unlike `BooleanUnion`, the parts remain separate objects. Unlike `Block`, editing one object in a group does not change the others.
* **Nested Groups:** You can add a group to another group, creating "nested" groups.

### 5. Practical Use Cases
* **Use Case 1: Adding Prongs to a Head Assembly**
    * **Scenario:** You have created a four-prong head and grouped the parts. Later, you decide to add two more prongs.
    * **Application:** Instead of ungrouping everything and starting over, you can create the two new prongs. Then, run `AddToGroup`, select the two new prongs, and finally click on any of the original prongs. The new prongs are now part of the main head group.
* **Use Case 2: Managing Pavé Fields**
    * **Scenario:** You have a large area of a ring covered in pavé stones, which you have grouped. You then add one more stone to fill a small gap.
    * **Application:** Run `AddToGroup`, select the new stone, and then click on any other stone in the main pavé group. The new stone is now included, keeping your pavé field organized.

### 6. Other Information from Documentation
The documentation confirms this command adds objects to an existing group. It is a fundamental organizational tool.

---

## 10. Alerter

### 1. Detailed Description
The **Alerter** command is a system utility that opens the "Alerter" page within the main Rhino Options window. Its purpose is to control how Rhino notifies you when a time-consuming command has finished processing. This is a user-preference setting to manage workflow interruptions.

### 2. Steps to Use the Command
1.  Run the command `Alerter`.
2.  The Rhino Options window will open to the "Alerter" page.
3.  Check "Enable command alerting" to turn the feature on.
4.  Set your preferences for when and how you want to be alerted.
5.  Click "OK" to save the settings.

### 3. Command Options & Toggles
All options for this command are located within the dialog box:
* **Enable command alerting:** The master checkbox to turn the feature on or off.
* **Elapsed time in minutes:** The alert will only be triggered if the command takes longer than the number of minutes specified here.
* **Play a sound file:** When a command finishes, Rhino will play a sound.
* **Run Rhino commands:** When a command finishes, Rhino can automatically run another command or macro.

### 4. Additional Notes for Better Use
* **Set a Reasonable Time:** Setting the "Elapsed time" too low (e.g., 0.1 minutes) can be annoying, as you will get alerts for many common commands. A setting of 1 or 2 minutes is usually more practical.
* **Automation:** The "Run Rhino commands" feature is a powerful way to automate a sequence. For example, after a long boolean operation, you could automatically run the `SelLast` and `ZoomSelected` commands to immediately inspect the new object.

### 5. Practical Use Cases
* **Use Case 1: High-Resolution Rendering**
    * **Scenario:** You start a high-quality render that you know will take 15-20 minutes.
    * **Application:** Enable the alerter and check "Play a sound file." Now you can minimize Matrix and work on something else. When the render is complete, your computer will play a sound, notifying you that it's ready.
* **Use Case 2: Complex Boolean Operations**
    * **Scenario:** You are performing a complex Boolean operation on two very detailed meshes, which might take several minutes.
    * **Application:** By enabling the alerter, you can step away from your computer and wait for the sound that tells you the operation is complete and you can continue working.

### 6. Other Information from Documentation
The documentation confirms this is a utility for setting up notifications for commands that take a long time to complete.

## 11. Align

### 1. Detailed Description
The **Align** command is a transformation tool used to precisely line up two or more objects. It works by moving selected objects to align the extents of their "bounding boxes" (the smallest imaginary box that can contain an object). You first select the objects to move, then a single target object that remains stationary.

### 2. Steps to Use the Command
1.  Select the object(s) you want to move.
2.  Run the command `Align`.
3.  You will be prompted: **"Press Enter when done"**. Press Enter.
4.  You will be prompted: **"Select target object"**. Click the object that will not move.
5.  Click on one of the alignment options in the command line (e.g., Concentric, Bottom, etc.).
6.  The objects will move into alignment.

### 3. Command Options & Toggles
The command has several clickable options that appear after you select the objects. These determine *how* the objects will be aligned:
* **Bottom:** Aligns the bottom edges of the objects' bounding boxes.
* **Concentric:** Aligns the centers of the objects' bounding boxes in all three axes (X, Y, and Z).
* **HCenter:** Aligns the horizontal centers.
* **Left:** Aligns the left edges of the bounding boxes.
* **Right:** Aligns the right edges of the bounding boxes.
* **Top:** Aligns the top edges of the bounding boxes.
* **VCenter:** Aligns the vertical centers.

### 4. Additional Notes for Better Use
* **View Dependent:** The effect of options like `Top`, `Bottom`, `Left`, `Right`, `HCenter`, and `VCenter` depends on the viewport you are using. For example, `Top` in the Top view aligns to the top of the screen, while `Top` in the Front view aligns to the highest Z-coordinate.
* **Concentric is 3D:** The `Concentric` option is the most powerful for jewelry, as it works in all three dimensions simultaneously, regardless of the view.

### 5. Practical Use Cases
* **Use Case 1: Centering a Gemstone in a Bezel**
    * **Scenario:** You have modeled a bezel and a gemstone and need to perfectly center the stone inside.
    * **Application:** Select the gemstone, run `Align`, press Enter, select the bezel as the target, and click the **Concentric** option. The gemstone will instantly snap to the exact center of the bezel.
* **Use Case 2: Arranging Accent Stones on a Shank**
    * **Scenario:** You have several small accent stones that need to be lined up perfectly along the top of a ring shank.
    * **Application:** In the Front view, select all the accent stones, run `Align`, press Enter, select the shank as the target, and click **VCenter**. All stones will snap to the same height.

### 6. Other Information from Documentation
The documentation confirms this command aligns objects based on their bounding boxes.

---

## 12. AlignMeshVertices

### 1. Detailed Description
The **AlignMeshVertices** command is a mesh editing tool that moves a selection of two or more mesh vertices to a single, averaged location. This command is used to flatten, straighten, or consolidate points on a mesh object. It essentially takes all the selected points and moves them to their collective center point.

### 2. Steps to Use the Command
1.  Select two or more vertices on a mesh object. (You may need to hold Ctrl+Shift to sub-select vertices).
2.  Run the command `AlignMeshVertices`.
3.  The selected vertices will immediately be moved to their averaged position.

### 3. Command Options & Toggles
In the standard version of the command, there are no options. It is an immediate action.

### 4. Additional Notes for Better Use
* **Sub-Object Selection:** To select individual mesh vertices, hold down **Ctrl + Shift** and click or drag a window over the vertices.
* **Use with Care:** This is a destructive editing tool. It can be very useful for cleaning up geometry, but it can also easily ruin the shape of a detailed mesh if used incorrectly.

### 5. Practical Use Cases
* **Use Case 1: Flattening a Wobbly Mesh Edge**
    * **Scenario:** You have an STL model of a bezel, but the top edge is slightly wavy and uneven. You need a perfectly flat top surface.
    * **Application:** Select all the vertices that make up the top edge of the bezel. Run the command. All the selected vertices will be snapped to the same Z-height, instantly creating a perfectly flat and level top edge.
* **Use Case 2: Cleaning Up 3D Scan Data**
    * **Scenario:** You have a 3D scan of a handmade organic shape, and there are some rough, "noisy" areas with jagged vertices that should be smoother.
    * **Application:** Select a small cluster of these jagged vertices and run the command. This will average their positions, effectively smoothing out the rough spot.

### 6. Other Information from Documentation
The documentation notes this command forces mesh vertices to the same location, which is useful for creating flat spots or straight lines in mesh objects.

---

## 13. AlignProfiles

### 1. Detailed Description
The **AlignProfiles** command is a specialized tool used to orient and position open curves relative to each other, preparing them for surface creation commands like `Loft` or `Sweep`. The command is interactive, guiding you through a sequence of selections. It works by moving and rotating one curve to match the position and orientation of another, based on points you pick on each curve.

### 2. Steps to Use the Command
1.  Run the command `AlignProfiles`.
2.  You will be prompted: **"Select curve to align"**. Select the curve you want to move.
3.  You will be prompted: **"Point on curve to align from"**. Click a point on that curve (e.g., its midpoint).
4.  You will be prompted: **"Select curve to align to"**. Select the target curve that will not move.
5.  You will be prompted: **"Point on curve to align to"**. Click a corresponding point on the target curve.
6.  The first curve will snap into position, aligned with the second curve.

### 3. Command Options & Toggles
This command does not have clickable options in the command line when it starts. Instead, it is a sequential, interactive process. After you select the curves, the command line will prompt you for further actions, which may include options to flip the direction of a curve if it aligns incorrectly.

### 4. Additional Notes for Better Use
* **Use Snaps:** Use object snaps like `Mid` or `End` when picking the alignment points to ensure perfect accuracy.
* **One at a Time:** This command works best by aligning one curve to another. If you have multiple curves to align to a single target, repeat the command for each one.

### 5. Practical Use Cases
* **Use Case 1: Preparing Profiles for a Ring Shank Loft**
    * **Scenario:** You have drawn three different profile curves for a ring shank, but they are scattered. Before you can `Loft` them, they need to be positioned correctly.
    * **Application:** Use the command to align the midpoint of the second profile to the midpoint of the first. Then, repeat the command to align the midpoint of the third profile to the midpoint of the first. Now all three are perfectly aligned and ready for lofting.
* **Use Case 2: Creating Symmetrical Geometry**
    * **Scenario:** You are modeling a decorative element that will be mirrored. You have drawn the two profile curves that will define its shape. To ensure the resulting surface is perfectly symmetrical, the two profile curves must be perfectly aligned.
    * **Application:** By aligning the two profiles using their center points, you guarantee they are in the correct position before you create a surface between them.

### 6. Other Information from Documentation
The documentation confirms this command lines up one curve to another by matching points on each curve.

---

## 14. Angle

### 1. Detailed Description
The **Angle** command is an analysis tool that measures and reports the angle between two lines or two vectors defined by points. It does not create any permanent geometry; its sole purpose is to provide a measurement that is displayed in the command line.

### 2. Steps to Use the Command
1.  Run the command `Angle`.
2.  You will be prompted: **"Start of first line"**. Pick the first point.
3.  You will be prompted: **"End of first line"**. Pick the second point to define the first vector.
4.  You will be prompted: **"Start of second line"**. Pick the third point.
5.  You will be prompted: **"End of second line"**. Pick the fourth point to define the second vector.
6.  The angle between the two defined lines is reported in the command history.

### 3. Command Options & Toggles
This command is interactive and does not have clickable options.

### 4. Additional Notes for Better Use
* **Three-Point Angle:** You can also measure the angle between two connected lines by picking three points: the end of the first line, the common corner point, and the end of the second line.
* **Use with `DimAngle`:** `Angle` is for quick checks. If you need to create a permanent dimension that is visible on the model, use the `DimAngle` command instead.

### 5. Practical Use Cases
* **Use Case 1: Checking the Taper Angle on a Bezel**
    * **Scenario:** The inside wall of a bezel must have a specific draft angle (e.g., 5 degrees) for proper stone setting.
    * **Application:** In the Front view, use the `Angle` command to measure between a vertical construction line and the line representing the bezel's inner wall to confirm the angle.
* **Use Case 2: Verifying Prong Spacing**
    * **Scenario:** You are creating a four-prong head and need to ensure the prongs are perfectly spaced at 90-degree intervals.
    * **Application:** In the Top view, use the command to measure the angle between a line from the center to the tip of one prong, and a line from the center to the tip of the next prong.

### 6. Other Information from Documentation
The documentation confirms this command reports the angle between two locations.

---

## 15. ApplyBoxMapping

### 1. Detailed Description
The **ApplyBoxMapping** command is a texture mapping utility. It projects a texture onto an object as if it were being projected from the six sides of an imaginary box. This method is ideal for objects that are squarish or rectangular. When you run the command, it creates a "mapping widget" in the shape of a box that you can then move, scale, or rotate to control how the texture is applied.

### 2. Steps to Use the Command
1.  Select the object(s) you want to apply the texture map to.
2.  Run the command `ApplyBoxMapping`.
3.  You will be prompted to define the corners of the mapping box, or you can click a command-line option. The `BoundingBox` option is most common.
4.  A box-shaped wireframe widget will appear around your object.
5.  Press Enter to accept the mapping.

### 3. Command Options & Toggles
* **BoundingBox:** Automatically creates a mapping widget that is the same size as the object's bounding box. This is the most common and quickest option.
* **CPlane:** Allows you to draw the base of the mapping box on the current construction plane.
* **Cap:** Controls how the texture is applied to the "capped" ends of the box projection.
* **World:** Uses the world axes for the initial orientation of the box.
* **Surface:** Allows you to align the mapping box to a specific surface.

### 4. Additional Notes for Better Use
* **Show the Widget:** After applying the mapping, you may need to run the `MappingWidget` command to turn on the widget's visibility if you want to edit it later.
* **UV Editor:** For very precise control, you can use the `UVEditor` command after applying the box map to see how the texture is unwrapped.

### 5. Practical Use Cases
* **Use Case 1: Applying a Brushed Metal Texture**
    * **Scenario:** You have a signet ring with a flat, rectangular top and want to apply a brushed metal texture that flows correctly over the edges and down the sides.
    * **Application:** Select the ring, run the command, and choose the `BoundingBox` option. This will wrap the brushed texture realistically.
* **Use Case 2: Applying a Pattern to a Square Gem**
    * **Scenario:** You are rendering a princess-cut or emerald-cut stone and want to apply a complex facet map or a custom texture.
    * **Application:** A box map is the perfect way to apply textures to rectilinear gemstone shapes, ensuring the texture is applied evenly to the top, sides, and bottom without distortion.

### 6. Other Information from Documentation
The documentation confirms this command adds a box texture mapping channel to an object.

---

## 16. ApplyCrv

### 1. Detailed Description
The **ApplyCrv** command is a powerful deformation tool that takes a flat, 2D curve and "wraps" or "maps" it onto a 3D surface. The command requires three inputs: the curve you want to apply, a "base surface" (which is often just the flat construction plane the curve is lying on), and the "target surface" where you want the curve to be wrapped. The result is a new 3D curve that follows the contour of the target surface.

### 2. Steps to Use the Command
1.  Select the curve(s) to apply to the surface.
2.  Run the command `ApplyCrv`.
3.  You will be prompted: **"Select base surface"**. Select a surface that the curve is on, or simply click in the empty space of the viewport where the curve was drawn (this selects the CPlane as the base).
4.  You will be prompted: **"Select target surface"**. Select the 3D surface you want to wrap the curve onto.
5.  A new 3D curve is created on the target surface.

### 3. Command Options & Toggles
This command is a sequential process and has no clickable options in the command line.

### 4. Additional Notes for Better Use
* **Base Surface:** The concept of a "base surface" can be confusing. For most jewelry work, your 2D pattern is drawn on a flat construction plane (like the Top view). In this case, you don't need a literal surface object; just clicking in the empty viewport will work.
* **Direction and Seams:** The position of the seam and the U/V directions of the target surface can affect how the curve is applied. If the curve appears in an unexpected location, try using the `SrfSeam` command to adjust the target surface's seam.

### 5. Practical Use Cases
* **Use Case 1: Applying Filigree or Scrollwork to a Ring**
    * **Scenario:** You have drawn a complex, flat, 2D filigree pattern and you want to apply it to the curved surface of a wide wedding band.
    * **Application:** Select your 2D filigree curves. Run the command, select the CPlane as the base, and select the ring shank as the target. A new set of 3D curves will be created, perfectly following the curvature of the ring.
* **Use Case 2: Engraving Text onto a Curved Surface**
    * **Scenario:** You need to add a name or a date to the inside of a ring. You create the text using the `TextObject` command, which results in flat curves.
    * **Application:** Use `ApplyCrv` to wrap the flat text curves onto the inner surface of the ring. You can then use these new 3D curves to create an engraved effect with a boolean difference.

### 6. Other Information from Documentation
* **Note from Documentation:** Use the `CreateUVCrv` command to generate planar versions of the u and v curves of a surface so you can use them as a guide to orient your text. You must then also map the u and v curves along with the curves you are applying so they will act as a placeholder. The structure of the curve is refit with a tolerance of the value of the `Absolute tolerance` option in Document Properties > Units.

---

## 17. ApplyCurvePiping

### 1. Detailed Description
The **ApplyCurvePiping** command creates a visual mesh pipe around a curve. This is a display feature, not a true geometric object. It makes a curve *look* like a solid pipe in rendered and shaded views, but it does not create a NURBS surface or polysurface that you can edit or use in boolean operations. Its main purpose is for quick visualization and rendering without the overhead of creating heavy geometry.

### 2. Steps to Use the Command
1.  Select the curve(s) you want to apply piping to.
2.  Run the command `ApplyCurvePiping`.
3.  The "Curve Piping" properties panel will open.
4.  Adjust the settings (Radius, Segments, etc.).
5.  The curve will now appear as a pipe in shaded/rendered views.

### 3. Command Options & Toggles
The options are controlled in the Properties panel:
* **On:** Turns the piping effect on or off for the selected curve.
* **Radius:** Sets the thickness of the pipe.
* **Segments:** Controls how many segments are used for the pipe's circumference (higher numbers are smoother).
* **Faceted:** Creates a faceted, low-poly look instead of a smooth pipe.
* **CapType:** Determines if the ends of the pipe are open, flat, or rounded.

### 4. Additional Notes for Better Use
* **Display Only:** Remember that this is a visual effect. If you need to 3D print the pipe or perform a boolean operation with it, you must use the standard `Pipe` command to create real geometry.
* **Performance:** This command is much faster and uses less memory than creating thousands of real pipes, making it ideal for visualizing complex wireframe-style designs before committing to the final geometry.
* **Removal:** To remove the effect, select the curve, go to its Properties panel, and uncheck the "On" box in the Curve Piping section.

### 5. Practical Use Cases
* **Use Case 1: Quick Visualization of a Filigree Design**
    * **Scenario:** You have a complex filigree design made of hundreds of curves. You want to see what it will look like as a solid piece without running the slow `Pipe` command on every single curve.
    * **Application:** Select all the curves and apply curve piping. You can instantly visualize the design's thickness and form.
* **Use Case 2: Creating Render-Only Details**
    * **Scenario:** You are creating a portfolio render and want to add some very fine, decorative wires to a piece that won't be part of the actual 3D printed model.
    * **Application:** Draw the curves and use `ApplyCurvePiping`. They will show up in the final render as solid pipes but won't add unnecessary weight or complexity to the manufacturing file.

### 6. Other Information from Documentation
The documentation confirms this constructs a mesh pipe display around a curve for visualization purposes.

---

## 18. ApplyCustomMapping

### 1. Detailed Description
The **ApplyCustomMapping** command is an advanced texture mapping utility. It wraps a texture onto a target object using another object's shape as the projection guide. This allows for complex, non-standard texture projections that follow specific forms, which is impossible with standard mapping types like box or planar.

### 2. Steps to Use the Command
1.  Select the target object(s) that will receive the texture.
2.  Run the command `ApplyCustomMapping`.
3.  You will be prompted: **"Select a custom mapping object"**. Select the object that will act as the projector.
4.  A dialog box appears to configure the mapping.
5.  The texture is applied to the target object as if it were projected from the custom object.

### 3. Command Options & Toggles
* **UV / UVW:** Chooses the mapping direction.
* **Mapping Primitive:** The type of object used for projection (plane, box, sphere, cylinder).

### 4. Additional Notes for Better Use
* **Complex Projections:** This is the tool to use when standard mapping projections (box, spherical, cylindrical) don't work. For example, applying a texture that needs to follow a twisting, tapered shape.
* **Requires a Projector Object:** Unlike other mapping commands, this one requires a second, separate object to act as the mapping guide.

### 5. Practical Use Cases
* **Use Case 1: Applying a Pattern to a Twisted Shank**
    * **Scenario:** You have a ring shank that twists and changes shape, and you want to apply a repeating pattern that follows the twist perfectly. A standard planar or cylindrical map would stretch and distort.
    * **Application:** You could model a simplified, untwisted version of the shank to act as the "custom mapping object." By applying the texture using this simpler object as a guide, the texture will flow cleanly along the more complex, twisted shank.

### 6. Other Information from Documentation
The documentation confirms this command adds a custom texture mapping channel to an object.

---

## 19. ApplyCylindricalMapping

### 1. Detailed Description
The **ApplyCylindricalMapping** command is a texture mapping utility that projects a texture onto an object as if it were wrapped around a cylinder. This method is ideal for objects that are round or cylindrical in shape, like a ring shank or a round bezel. It creates a cylindrical mapping widget that can be moved, scaled, and rotated to control the texture's application.

### 2. Steps to Use the Command
1.  Select the object(s) to map.
2.  Run the command `ApplyCylindricalMapping`.
3.  You will be prompted to draw the base and height of the cylindrical widget. The `BoundingBox` option is often the easiest starting point.
4.  A cylindrical wireframe widget appears around the object.
5.  Press Enter to accept the mapping.

### 3. Command Options & Toggles
* **BoundingBox:** Automatically creates a mapping cylinder that encloses the object.
* **Capped:** Toggles whether the texture is also projected onto the flat top and bottom ends of the cylinder.

### 4. Additional Notes for Better Use
* **Seam:** The cylindrical projection creates a "seam" where the two ends of the texture map meet. You can rotate the mapping widget to hide this seam in a less visible area of your model.
* **Use for Round Objects:** This is the go-to mapping method for any object that is fundamentally cylindrical, such as shanks, bezels, and even the sides of a round gemstone.

### 5. Practical Use Cases
* **Use Case 1: Applying a Pattern Around a Ring Shank**
    * **Scenario:** You want to apply a continuous, repeating pattern (like a floral or geometric design) around the outside of a wedding band.
    * **Application:** Select the ring. Run `ApplyCylindricalMapping` and choose the `BoundingBox` option. This will wrap the pattern around the ring smoothly and evenly. You can then rotate the mapping widget to adjust the pattern's starting point.
* **Use Case 2: Creating a Brushed Finish on a Bezel**
    * **Scenario:** You want to render a round bezel with a brushed metal finish where the grain flows circularly around the bezel wall.
    * **Application:** `ApplyCylindricalMapping` is the perfect tool for this. It will wrap the brushed texture around the bezel wall correctly, creating a realistic circular finish.

### 6. Other Information from Documentation
The documentation confirms this command adds a cylindrical texture mapping channel to an object.

---

## 20. ApplyDisplacement

### 1. Detailed Description
The **ApplyDisplacement** command is a rendering and display feature that creates a "displacement mesh" on a surface or polysurface. This mesh deforms the object's appearance at render time, using the light and dark values of a texture map to create real, physical-looking bumps, grooves, and details. Unlike a bump map, which is a lighting trick, displacement actually modifies the object's silhouette.

### 2. Steps to Use the Command
1.  Select the object you want to apply displacement to.
2.  In the Properties panel, go to the Displacement section.
3.  Click "On" and assign a texture map.
4.  Adjust the settings (Black point, White point).
5.  Run the command `ApplyDisplacement` to see a preview of the mesh in the viewport.

### 3. Command Options & Toggles
The options are controlled in the Properties panel:
* **Texture:** The image map used to drive the displacement.
* **Black point:** The amount of inward displacement (indentation) caused by black areas of the texture.
* **White point:** The amount of outward displacement (height) caused by white areas of the texture.
* **Initial Quality:** Controls the density of the displacement mesh for the viewport preview.

### 4. Additional Notes for Better Use
* **Render-Time Effect:** Displacement is a memory-intensive effect that is primarily calculated at render time. The viewport preview is a lower-quality approximation.
* **Requires a Dense Mesh:** For displacement to show fine details, the underlying object must have a dense render mesh. You can increase this in the Document Properties.
* **`ExtractRenderMesh`:** After applying displacement, you can use the `ExtractRenderMesh` command to convert the visual displacement effect into a real, editable mesh object that can be 3D printed.

### 5. Practical Use Cases
* **Use Case 1: Creating a Hammered Finish for a Render**
    * **Scenario:** You want to create a realistic, bumpy hammered texture on a ring for a client presentation, without having to manually sculpt every single dent.
    * **Application:** Find or create a black and white texture map of a hammered pattern. Apply this texture to the ring in the displacement slot. The white areas of the texture will create the raised bumps, giving a highly realistic result in the final render.
* **Use Case 2: Modeling a Knurled Pattern**
    * **Scenario:** You need to create a knurled (cross-hatch diamond) pattern on the edge of a bezel.
    * **Application:** Apply a knurled pattern texture map using displacement. Once you are happy with the look of the preview, use `ExtractRenderMesh` to turn the visual effect into a real, 3D printable mesh.

### 6. Other Information from Documentation
The documentation confirms this command constructs a displacement display mesh for surfaces, polysurfaces, or meshes.

---

---

## 21. ApplyEdgeSoftening

### 1. Detailed Description
The **ApplyEdgeSoftening** command is a display feature that creates a "softening mesh" around the sharp edges of a surface or polysurface. This makes the edges appear rounded or filleted in rendered and shaded views without actually changing the underlying NURBS geometry. It is a visual trick, similar to `ApplyCurvePiping`, designed to create the appearance of a soft edge for quick visualization and rendering.

### 2. Steps to Use the Command
1.  Select the object you want to apply edge softening to.
2.  In the Properties panel, go to the Edge Softening section.
3.  Click "On" and adjust the settings (Radius, etc.).
4.  Run the command `ApplyEdgeSoftening` to see a preview of the mesh in the viewport.

### 3. Command Options & Toggles
The options are controlled in the Properties panel:
* **On:** Turns the edge softening effect on or off for the selected object.
* **Softening:** Sets the radius of the rounded edge effect.
* **Chamfer:** Toggles the effect between a rounded fillet and a flat chamfer.
* **Faceted:** Creates a faceted, low-poly look instead of a smooth round.

### 4. Additional Notes for Better Use
* **Display Only:** This is a visual effect for rendering. If you need to 3D print the object with rounded edges, you must use the `FilletEdge` or `BlendEdge` command to create real geometric fillets.
* **Performance:** This command is much faster than creating dozens of complex fillets, making it ideal for quickly visualizing how a piece will look with soft edges before committing to the final, heavy geometry.
* **`ExtractRenderMesh`:** To convert this visual effect into a real, editable mesh object, you can use the `ExtractRenderMesh` command.

### 5. Practical Use Cases
* **Use Case 1: Quick Render Prototyping**
    * **Scenario:** You have a signet ring with many sharp edges. You want to show a client a quick render of what it would look like with soft, polished edges, but you don't want to spend time creating permanent fillets yet.
    * **Application:** Select the ring, turn on Edge Softening in the properties panel, and set a small radius. The ring will now render with beautiful, soft highlights on all its edges.
* **Use Case 2: Creating a "Comfort Fit" Look**
    * **Scenario:** You want to visualize how the inside edge of a wedding band will look with a soft, "comfort fit" rounding.
    * **Application:** Apply Edge Softening to the ring. This will give a good visual representation of the final polished piece without needing to model the complex comfort fit surface yet.

### 6. Other Information from Documentation
The documentation confirms this command constructs an edge-softening display mesh for surfaces, polysurfaces, or meshes.

---

## 22. ApplyMesh

### 1. Detailed Description
The **ApplyMesh** command deforms a mesh object to match the shape of a target NURBS surface. It is a specialized deformation tool used to wrap or fit an existing mesh onto a new curved form.

### 2. Steps to Use the Command
1.  Select the mesh object you want to deform.
2.  Run the command `ApplyMesh`.
3.  You will be prompted: **"Select the surface to fit the mesh to"**. Select the target NURBS surface.
4.  The mesh object will be deformed to match the surface's shape.

### 3. Command Options & Toggles
This command has no clickable options in the command line.

### 4. Additional Notes for Better Use
* **`ApplyCrv` for Curves:** This command is the mesh equivalent of the `ApplyCrv` command. `ApplyCrv` is for curves, `ApplyMesh` is for meshes.
* **Topology Must Match:** This command works best when the mesh and the surface have a similar rectangular or square-like flow. Applying a complex mesh to a simple surface can produce unpredictable results.

### 5. Practical Use Cases
* **Use Case 1: Applying a Mesh Pattern to a Ring**
    * **Scenario:** You have a flat, pre-made mesh pattern (for example, a complex filigree or grill that was modeled as a mesh) and you want to wrap it around a ring shank.
    * **Application:** Select the flat mesh pattern, run `ApplyMesh`, and select the ring shank surface as the target. The mesh pattern will bend and conform to the shape of the ring.
* **Use Case 2: Conforming a 3D Scan to a New Shape**
    * **Scenario:** You have a 3D scan of a person's fingerprint (as a mesh) and you want to apply it to the curved surface of a signet ring.
    * **Application:** Use `ApplyMesh` to take the flat fingerprint mesh and deform it to the curved top of the ring, creating a custom, personalized piece.

### 6. Other Information from Documentation
The documentation confirms this command fits a mesh that matches a source mesh onto a surface.

---

## 23. ApplyMeshUVN

### 1. Detailed Description
The **ApplyMeshUVN** command is an advanced deformation tool that deforms meshes and points onto a surface with a high degree of control. It works by associating the X, Y, and Z coordinates of the source object with the U, V, and Normal directions of the target surface. This allows for complex transformations where an object can be wrapped and simultaneously raised or lowered from the target surface.

### 2. Steps to Use the Command
1.  Select the mesh or point objects to deform.
2.  Run the command `ApplyMeshUVN`.
3.  You will be prompted: **"Select surface to apply objects to"**. Select the target NURBS surface.
4.  A dialog box appears with options to control the U, V, and N (Normal) mapping.
5.  Click OK to apply the transformation.

### 3. Command Options & Toggles
The options are in a dialog box:
* **U:** Maps the object's X coordinates to the surface's U direction.
* **V:** Maps the object's Y coordinates to the surface's V direction.
* **N:** Maps the object's Z coordinates to the surface's Normal direction (inward/outward).

### 4. Additional Notes for Better Use
* **Advanced Command:** This is a highly technical command and is not used often in typical jewelry modeling. It is more common in fields like texture baking and game development.
* **The "N" is Key:** The unique feature of this command is the "N" (Normal) mapping. This means that the height (Z-axis) of your original flat mesh can be used to push the wrapped mesh in or out from the target surface.

### 5. Practical Use Cases
* **Use Case 1 (Advanced): Creating Bas-Relief from a Heightmap**
    * **Scenario:** You have a flat mesh that was created from a heightmap image (like a 3D face or coin). You want to wrap this relief onto a curved pendant.
    * **Application:** Using `ApplyMeshUVN`, you can wrap the mesh onto the pendant (U and V mapping) while simultaneously using the original height of the mesh to create the raised relief effect (N mapping).

### 6. Other Information from Documentation
The documentation confirms this command wraps meshes and points onto a surface.

---

## 24. ApplyPlanarMapping

### 1. Detailed Description
The **ApplyPlanarMapping** command is a texture mapping utility that projects a texture onto an object from a single, flat plane. It works like a slide projector, casting the image in a straight line. This method is best for flat or nearly flat surfaces. It creates a rectangular mapping widget that you can move, scale, and rotate to control the projection.

### 2. Steps to Use the Command
1.  Select the object(s) to map.
2.  Run the command `ApplyPlanarMapping`.
3.  You will be prompted to draw a rectangle in the viewport. This rectangle defines the mapping widget.
4.  A rectangular wireframe widget will appear.
5.  Press Enter to accept the mapping.

### 3. Command Options & Toggles
* **BoundingBox:** Automatically creates a mapping widget that is the same size as the object's bounding box.
* **CPlane / World:** Aligns the widget to the active CPlane or the world axes.

### 4. Additional Notes for Better Use
* **Stretching on Sides:** Be aware that planar mapping will cause severe stretching and distortion on any surfaces that are not parallel to the mapping widget (e.g., the sides of a box).
* **Use for Flat Surfaces:** This is the best and simplest mapping method for any object that is primarily flat, like the top of a signet ring, a coin, or a dog tag.

### 5. Practical Use Cases
* **Use Case 1: Applying a Logo to a Signet Ring**
    * **Scenario:** You have a logo image that you need to apply as a texture to the flat top surface of a signet ring for a render.
    * **Application:** Select the ring. In the Top view, run `ApplyPlanarMapping` and draw a rectangle that matches the size of the ring's top. The logo will be projected cleanly onto the flat surface.
* **Use Case 2: Creating an Enamel Effect**
    * **Scenario:** You have a 2D pattern that you want to render as enamel inside a recessed area of a flat pendant.
    * **Application:** `ApplyPlanarMapping` is the perfect way to place the enamel pattern texture precisely into the recessed area.

### 6. Other Information from Documentation
The documentation confirms this command adds a planar texture mapping channel.

---

## 25. ApplyShutLining

### 1. Detailed Description
The **ApplyShutLining** command is a specialized display and rendering feature. It creates a visual effect of grooves, panel lines, or part lines on a surface or polysurface. It works by creating a mesh with rounded indentations wherever there is an edge on the original object. This is a visual effect only and does not change the underlying geometry.

### 2. Steps to Use the Command
1.  Select the object.
2.  In the Properties panel, go to the Shut Lining section.
3.  Click "On" and adjust the settings (Radius, Profile, etc.).
4.  Run the command `ApplyShutLining` to see a preview of the mesh in the viewport.

### 3. Command Options & Toggles
The options are controlled in the Properties panel:
* **On:** Turns the shut lining effect on or off.
* **Radius:** Controls the width of the groove.
* **Profile Curve:** Allows you to use a custom curve to define the cross-section shape of the groove.

### 4. Additional Notes for Better Use
* **Industrial Design:** This command is primarily used in industrial and product design to simulate the gaps between panels on a car, phone, or other manufactured product.
* **`ExtractRenderMesh`:** Like other display effects, you can use `ExtractRenderMesh` to convert the visual shut lines into a real, editable mesh object.

### 5. Practical Use Cases
* **Use Case 1 (Non-Jewelry): Visualizing Part Lines**
    * **Scenario:** An industrial designer has modeled a phone case and wants to visualize the thin gap between the main body and a button.
    * **Application:** They would apply shut lining to the model. The command would automatically create a small, rounded groove along the edge where the button meets the body, creating a realistic render. This command has very limited use in traditional jewelry design.

### 6. Other Information from Documentation
The documentation confirms this command constructs a shut-line display mesh for surfaces, polysurfaces, or meshes.

---

## 26. ApplySphericalMapping

### 1. Detailed Description
The **ApplySphericalMapping** command is a texture mapping utility that projects a texture onto an object as if it were being projected from the inside of a sphere. This method is ideal for objects that are round or ball-shaped. It creates a spherical mapping widget that you can move, scale, and rotate to control the texture's application.

### 2. Steps to Use the Command
1.  Select the object(s) to map.
2.  Run the command `ApplySphericalMapping`.
3.  You will be prompted to draw the center and radius of the spherical widget. The `BoundingBox` option is often easiest.
4.  A spherical wireframe widget appears around the object.
5.  Press Enter to accept the mapping.

### 3. Command Options & Toggles
* **BoundingBox:** Automatically creates a mapping sphere that encloses the object.

### 4. Additional Notes for Better Use
* **Pinching at the Poles:** Spherical mapping will always cause some "pinching" or distortion at the top and bottom poles of the sphere. You can rotate the mapping widget to move these poles to a less visible area of your model.
* **Seamless Textures:** This mapping method works best with "seamless" or "tileable" textures that are designed to wrap without showing an obvious seam.

### 5. Practical Use Cases
* **Use Case 1: Applying a Texture to a Pearl or Bead**
    * **Scenario:** You are rendering a pearl necklace and want to apply a pearlescent, iridescent texture map to the spherical pearls.
    * **Application:** Select a pearl, run `ApplySphericalMapping`, and choose the `BoundingBox` option. This will wrap the texture around the pearl in the most natural way for a spherical object.
* **Use Case 2: Creating a Globe Pendant**
    * **Scenario:** You have modeled a spherical pendant and want to apply a texture map of the Earth to create a globe effect.
    * **Application:** `ApplySphericalMapping` is the only standard mapping type that will correctly wrap a world map onto a sphere.

### 6. Other Information from Documentation
The documentation confirms this command adds a spherical texture mapping channel to an object.

---

## 27. ApplySurfaceMapping

### 1. Detailed Description
The **ApplySurfaceMapping** command is a texture mapping utility that projects a texture onto an object based on the UV parameter space of a separate surface. This is similar to `ApplyCustomMapping` but is specifically for using a NURBS surface as the projection guide.

### 2. Steps to Use the Command
1.  Select the object(s) that will receive the texture.
2.  Run the command `ApplySurfaceMapping`.
3.  You will be prompted: **"Select a mapping surface"**. Select the NURBS surface that will act as the projector.
4.  The texture is applied.

### 3. Command Options & Toggles
This command has no clickable options.

### 4. Additional Notes for Better Use
* **UV Space:** This command essentially says "take the texture as it would appear on the flat, unwrapped UV space of the guide surface, and project it onto the target object."
* **Advanced Tool:** This is an advanced texturing tool used for very specific situations where other mapping types fail.

### 5. Practical Use Cases
* **Use Case 1: Applying a Pattern to an Irregular Gemstone**
    * **Scenario:** You have a freeform, baroque-shaped gemstone and want to apply a texture (like stripes or spots) that flows cleanly across its irregular surface.
    * **Application:** You could create a simpler, smoother "proxy" surface that roughly matches the shape of the gemstone. Apply a clean planar map to this proxy surface. Then, use the proxy surface as the guide in the `ApplySurfaceMapping` command to project the texture onto the complex gemstone.

### 6. Other Information from Documentation
The documentation confirms this command adds a surface texture mapping channel to an object.

---

## 28. ApplyWatermark

### 1. Detailed Description
The **ApplyWatermark** command is a utility that embeds an invisible, digital watermark into your Rhino 3DM model file. This watermark is a string of text that you provide. It is not visible in the model itself but can be detected by someone else using the `FindWatermark` command. Its purpose is to help prove ownership or authenticity of a file.

### 2. Steps to Use the Command
1.  Run the command `ApplyWatermark`.
2.  A dialog box will appear.
3.  Type your desired watermark text (e.g., your name, company, or a unique ID) into the field.
4.  Click OK. The data is embedded in the file.

### 3. Command Options & Toggles
The only option is the text you enter into the dialog box.

### 4. Additional Notes for Better Use
* **Not a Visual Watermark:** This is not a visible watermark that appears on a render. It is hidden data inside the file itself.
* **Security:** While it can help prove ownership, it is not a foolproof security measure, as someone with advanced knowledge could potentially try to remove the data.

### 5. Practical Use Cases
* **Use Case 1: Proving Design Ownership**
    * **Scenario:** You are sending a preliminary design file to a new client and want a way to prove that the file originated from you if a dispute arises later.
    * **Application:** Before sending the file, use `ApplyWatermark` to embed your company name and the date. If you ever need to, you can ask for the file back and use the `FindWatermark` command to show that your hidden signature is present.
* **Use Case 2: Tracking File Versions**
    * **Scenario:** You have multiple versions of a design and want a way to definitively identify which file is which, even if the filename is changed.
    * **Application:** You can embed a unique version number or code as a watermark in each file (e.g., "Project_Phoenix_V3_Final_Internal").

### 6. Other Information from Documentation
The documentation confirms this command embeds invisible watermarks in Rhino models.

---

## 29. Arc

### 1. Detailed Description
The **Arc** command is a fundamental 2D drawing tool used to create a circular arc. It provides several different methods for defining the arc's shape, size, and position, making it a very versatile command for creating curved geometry.

### 2. Steps to Use the Command
1.  Run the command `Arc`.
2.  The command line will show several options for how to create the arc. Click on the desired method (e.g., `Center,Start,Angle` is a common default).
3.  Follow the prompts for that specific method. For `Center,Start,Angle`, you would:
    a. Pick the center point of the arc's circle.
    b. Pick the starting point of the arc.
    c. Pick the end point or type an angle.

### 3. Command Options & Toggles
The options are different methods for creating the arc:
* **Center,Start,Angle:** Defines the arc by its center point, a starting radius point, and the angle it sweeps.
* **Start,End,Point:** Defines the arc by its start point, end point, and a third point that the arc must pass through.
* **Tangent:** Creates an arc that is tangent to one or more existing curves.
* **Deformable:** Creates a higher-degree NURBS curve that is shaped like an arc but has more control points for easier editing.

### 4. Additional Notes for Better Use
* **Holding Shift:** When drawing an arc, holding the `Shift` key can often be used to toggle between creating a full circle and an arc segment.
* **Combine with `Fillet`:** For creating rounded corners between two lines, the `Fillet` command is often faster than trying to draw a tangent arc manually.

### 5. Practical Use Cases
* **Use Case 1: Creating the Gallery Rail of a Setting**
    * **Scenario:** You need to create the curved lower wire (the gallery) of a four-prong setting.
    * **Application:** In the Top view, you can use the `Arc` command (with the Center, Start, Angle method) to draw a 90-degree arc between two prongs. This can then be copied or arrayed to form the complete gallery.
* **Use Case 2: Designing a Crescent-Shaped Earring**
    * **Scenario:** You want to design an earring in the shape of a crescent moon.
    * **Application:** You can create this shape by drawing two different arcs using the `Start,End,Point` method and then trimming them against each other.

### 6. Other Information from Documentation
* **Note from Documentation:** The degree of the arc is 2. The `Deformable` option creates a degree 3 NURBS curve approximation of an arc.

---

## 30. ArcBlend

### 1. Detailed Description
The **ArcBlend** command creates a special type of blend curve between two other curves. Unlike the standard `BlendCrv` command which creates a complex NURBS curve, `ArcBlend` specifically creates a true circular arc that is tangent to the two input curves. This is useful for situations where a precise, constant-radius connection is required.

### 2. Steps to Use the Command
1.  Run the command `ArcBlend`.
2.  You will be prompted: **"Select first curve to blend"**. Click near the end of the first curve.
3.  You will be prompted: **"Select second curve to blend"**. Click near the end of the second curve.
4.  A preview of the arc blend will appear.
5.  The command completes.

### 3. Command Options & Toggles
This command has no clickable options in the command line.

### 4. Additional Notes for Better Use
* **True Arcs:** The primary advantage of this command is that the resulting blend is a true arc, not a complex spline that approximates an arc. This can be important for manufacturing processes that require simple geometry.
* **Limited Control:** You have less control over the shape of the blend compared to `BlendCrv`. The radius of the arc is determined automatically by the tangency conditions.

### 5. Practical Use Cases
* **Use Case 1: Creating a Smooth Bail Transition**
    * **Scenario:** You have the top of a pendant and a separate loop for the bail. You need to connect them with a perfectly smooth, circular transition.
    * **Application:** You can use `ArcBlend` to create a tangent arc between the curve defining the pendant's top edge and the curve defining the bail. This arc can then be used as part of a sweep or network surface.
* **Use Case 2: Filleting Between Two Separate Curves**
    * **Scenario:** You have two curves that do not intersect, but you want to create a rounded corner between them as if they did. The standard `Fillet` command won't work in this case.
    * **Application:** `ArcBlend` can bridge the gap between the two curves with a tangent arc, effectively creating a "fillet" between non-intersecting geometry.

### 6. Other Information from Documentation
The documentation confirms this command creates an arc blend curve between two curves.

---
