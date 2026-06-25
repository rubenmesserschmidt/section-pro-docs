Creating Sections
=================

This guide walks you through creating a section and adjusting its position.


Step 1: Open the Section Pro Panel
-----------------------------------

In the **3D Viewport**, press :kbd:`N` to open the sidebar and click the **Section Pro** tab.


Step 2: Create the Section
--------------------------

Click the **+** button next to the *Sections* list. A dialog opens with the following settings:

.. list-table::
   :header-rows: 1
   :widths: 25 75

   * - Setting
     - Description
   * - **Name**
     - A descriptive name for the section (e.g. "Floor Plan Cut").
   * - **Scope**
     - Which objects are affected by the cut. See :doc:`/guides/managing-scope` for details.
   * - **Alignment**
     - Where and how the section plane is initially placed.

Alignment options:

.. list-table::
   :header-rows: 1
   :widths: 25 75

   * - Option
     - Description
   * - **Selection Center**
     - Places the section plane at the center of all currently selected objects. This is the default and is usually the most convenient starting point.
   * - **3D Cursor**
     - Places the section plane at the current 3D cursor position and orientation.
   * - **View**
     - Aligns the section plane to the current viewport view direction.
   * - **Custom**
     - Lets you manually enter a world-space location and Euler rotation.

Click **OK** to confirm. A flat plane object (the section) is added to the scene inside the ``SP Sections`` collection, and a first default :doc:`View </concepts/views>` is created automatically if none exists yet.


Step 3: Position the Section
----------------------------

Select the section object in the viewport (it is automatically set as active after creation) and use the standard Blender transform tools to adjust the cut:

- :kbd:`G` to grab / move
- :kbd:`R` to rotate

The orange plane gizmo visualises the cut direction. Geometry *below* the plane (in the opposite direction the gizmo normal faces) is kept; geometry *above* the plane is hidden or removed depending on the active section method.


Step 4: Enable the Section
--------------------------

In the *Sections* list, click the checkbox next to the section name to **enable** the section in the active view. The cut is applied immediately to the scoped objects.

.. note::

   Sections are **disabled by default** when added to a view (can be changed in the preferences). You must explicitly enable them. This makes it easy to create multiple sections and turn them on only when needed.


Alternative: Create Section by Drawing
--------------------------------------

Instead of using one of the alignment options, you can draw the section plane directly in the viewport:

1. Hold :kbd:`Shift` while clicking the same **+** button to add a new section. This automatically switches to *Draw Section* mode, where you can draw a line in the viewport to define the section plane.
2. Click once to set the first edge of the section line.
3. Click again to set the second edge. The section plane is automatically aligned perpendicular to the view and centered on the drawn line.

   - Hold :kbd:`Ctrl` while clicking to snap the line rotation to 45° increments.
   - Hold :kbd:`Alt` to flip the cut direction.


.. seealso::

   :doc:`/guides/managing-scope`
      Adding and removing objects from a section's scope.

   :doc:`/concepts/sections`
      Conceptual overview of sections, scopes, and methods.
