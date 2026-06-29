Creating Drawings
=================

A drawing captures the 2D line geometry of a section cut at a point in time. This guide walks you through creating a drawing and understanding its options.


Prerequisites
-------------

- At least one :doc:`section <creating-sections>` must exist in the scene.
- You must be in **Object Mode**.


Step 1: Select the Source Section
----------------------------------

In the *Sections* list, click on the section you want to generate a drawing from to make it the active section.


Step 2: Open the Create Drawing Dialog
--------------------------------------

In the *Drawings* panel, click the **+** button. A dialog opens with the following settings:


General Settings
~~~~~~~~~~~~~~~~

.. list-table::
   :header-rows: 1
   :widths: 30 70

   * - Setting
     - Description
   * - **Name**
     - Name for the new drawing object.
   * - **Create At**
     - Where the drawing object is placed after creation (see below).
   * - **Include Hidden Objects**
     - When enabled, objects that are hidden in the viewport are also included in the drawing.

**Create At** options:

- **Section Origin** – The drawing is placed at the section's position and orientation in 3D space. Most common for keeping the drawing aligned with the model.
- **World Origin** – The drawing is placed at (0, 0, 0). Useful when composing multiple drawings on a flat layout plane.
- **Custom** – After creation you can place the object freely in the viewport.


Projection Settings
~~~~~~~~~~~~~~~~~~~

Toggle **Enable Projection** to also include the projected edges of the scoped geometry (not just the section outline).

When projection is enabled:

.. list-table::
   :header-rows: 1
   :widths: 30 70

   * - Setting
     - Description
   * - **Perspective**
     - Applies perspective distortion to projected edges.
   * - **Distortion**
     - Strength of the perspective distortion (only active when Perspective is on).
   * - **Limit**
     - Only include geometry within a maximum distance from the section plane.
   * - **Distance**
     - The maximum distance in scene units (only active when Limit is on).
   * - **Merge**
     - Merge nearby projection vertices before BVH construction. Reduces geometry complexity and can improve hidden edge detection quality.
   * - **Dissolve**
     - Dissolve near-collinear projection edges before BVH construction. Reduces silhouette edge count on smooth or subdivided geometry.
   * - **Hidden Edge Detection**
     - Detect and store edges that are hidden behind other geometry. Stored in a separate edge layer.
   * - **Quality**
     - Preset for hidden edge detection accuracy (Low, Medium, High, Ultra, Custom).


Step 3: Confirm and Inspect
---------------------------

Click **OK** to generate the drawing. Depending on the complexity of the scene and the selected options, this may take a few seconds. For complex scenes with HED enabled, it can take some minutes to complete, don't close Blender or interrupt the process.

The drawing object is created inside the ``SP Drawings`` collection and becomes the active drawing in the *Drawings* list. It is a mesh object containing only edges.


Refreshing a Drawing
--------------------

After changing the scene geometry or moving the section, the drawing is **not** updated automatically. To regenerate it:

1. Select the drawing in the *Drawings* list.
2. Click the **Refresh Drawing** button in the drawing’s actions row.

The drawing is regenerated in-place using all previously stored settings. Its current position in 3D space is preserved.


Working with Edge Layers
------------------------

A drawing can contain up to three edge layers:

- **Section** edges – the cross-section outline (always present).
- **Projection** edges – visible projected geometry (present when projection was enabled).
- **Hidden** edges – occluded edges detected by HED (present when HED was enabled).

To select a specific layer in the viewport, use the **Select Edges** buttons in the *Actions* sub-panel. This enters Edit Mode with the matching edges selected, so you can inspect, modify, or export them independently.

.. seealso::

   :doc:`/guides/exporting-drawings`
      How to export drawings to DXF, SVG, or JSON.

   :doc:`/concepts/drawings`
      Conceptual overview of drawings and edge layers.
