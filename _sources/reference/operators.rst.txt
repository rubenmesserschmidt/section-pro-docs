Operators
=========

All Section Pro operators live under the ``section_pro`` prefix. They can be accessed from the Section Pro panels in the 3D Viewport sidebar, or via the operator search (:kbd:`F3`).

.. _op-create-section:

Create Section
--------------

``section_pro.create_section``

Creates a new section in the scene. Opens a properties dialog before executing.

.. list-table::
   :header-rows: 1
   :widths: 25 15 60

   * - Property
     - Type
     - Description
   * - **Name**
     - String
     - Name for the new section object. Defaults to ``"Section"``.
   * - **Scope**
     - Enum
     - Determines which objects are affected: ``Objects``, ``Collections``, or ``Scene``.
   * - **Alignment**
     - Enum
     - Where the section plane is placed: ``Selection Center``, ``3D Cursor``, ``View``, or ``Custom``.
   * - **Location** *(Custom only)*
     - Vector
     - World-space location for the section plane.
   * - **Rotation** *(Custom only)*
     - Euler
     - World-space rotation for the section plane.

A default view is created automatically if no views exist yet.


.. _op-create-section-by-drawing:

Create Section by Drawing
-------------------------

``section_pro.create_section_by_drawing``

Interactive operator that lets you draw the section plane directly in the 3D viewport by clicking two points. The section plane is created perpendicular to the viewport, centred on the drawn line. After the second click, the :ref:`op-create-section` dialog opens with the drawn location and rotation pre-filled as **Custom** alignment and can be further adjusted before creating the section.

**Controls during operation:**

- :kbd:`LMB` Set point 1, then point 2.
- :kbd:`Ctrl` Snap rotation to 45° increments.
- :kbd:`Alt` Flip the cut direction.



.. _op-delete-section:

Delete Section
--------------

``section_pro.delete_section``

Deletes the active section and cleans up all related data (cutter object, modifier assignments, proxy objects). Asks for confirmation.



.. _op-enable-section:

Enable / Disable Section
------------------------

``section_pro.enable_section``

Toggles the enabled state of a section within the active view. When disabled, the section cut is not applied.

.. list-table::
   :header-rows: 1
   :widths: 25 15 60

   * - Property
     - Type
     - Description
   * - **Enable**
     - Boolean
     - ``True`` to enable the section, ``False`` to disable it.



.. _op-align-view-to-section:

Align View to Section
---------------------

``section_pro.align_view_to_section``

Rotates the 3D viewport camera so it looks straight along the active section's normal (i.e., perpendicular to the cut plane). Useful for verifying the section cut or for placing a camera for rendering a section view.



.. _op-add-objs:

Add Objects to Section
-----------------------

``section_pro.add_objs_to_section``

Adds the currently selected objects to the active section's scope. Only applicable when the section scope is set to **Objects**. Unsupported object types are skipped with a warning.



.. _op-remove-objs:

Remove Objects from Section
----------------------------

``section_pro.remove_objs_from_section``

Removes the currently selected objects from the active section's scope. Only applicable when scope is **Objects**.



.. _op-add-cols:

Add Collections to Section
---------------------------

``section_pro.add_cols_to_section``

Adds collections selected in the **Outliner** to the active section's scope. Only applicable when scope is **Collections**. Each object in the collection is registered as a section target.



.. _op-remove-col:

Remove Collection from Section
-------------------------------

``section_pro.remove_col_from_section``

Removes a collection (and all its objects) from the active section's scope. Asks for confirmation.



.. _op-refresh-col-scope:

Refresh Collection Scope
------------------------

``section_pro.refresh_section_col_scope``

Synchronises a single collection's object membership with the section scope. Objects added to the collection since the last refresh are added to the scope; objects removed from the collection are removed from the scope.



.. _op-refresh-all-cols-scope:

Refresh All Collection Scopes
------------------------------

``section_pro.refresh_section_all_cols_scope``

Runs :ref:`Refresh Collection Scope <op-refresh-col-scope>` on every collection in the active section's scope in one step.



.. _op-refresh-scene-scope:

Refresh Scene Scope
-------------------

``section_pro.refresh_section_scene_scope``

Synchronises the section scope with the current set of supported objects in the active scene. Only applicable when scope is **Scene**.



.. _op-select-objs:

Select Objects in Scope
-----------------------

``section_pro.section_select_objects_in_scope``

Deselects all objects and then selects every object that is currently in the active section's scope.



.. _op-update-cutter:

Update Cutter
-------------

``section_pro.update_cutter``

Manually updates the cutter object's transform to match the current position and rotation of the active section object.



.. _op-create-drawing:

Create Drawing
--------------

``section_pro.create_drawing``

Generates a new 2D drawing from the active section. Must be run in **Object Mode**. Opens a properties dialog.

.. list-table::
   :header-rows: 1
   :widths: 30 15 55

   * - Property
     - Type
     - Description
   * - **Name**
     - String
     - Name for the drawing object. Defaults to ``"Drawing"``.
   * - **Create At**
     - Enum
     - Placement of the drawing object: ``Section Origin``, ``World Origin``, or ``Custom``.
   * - **Include Hidden Objects**
     - Boolean
     - Include viewport-hidden objects in the drawing.
   * - **Enable Projection**
     - Boolean
     - Project the visible 3D edges onto the section plane in addition to the section outline.
   * - **Perspective**
     - Boolean
     - Apply perspective distortion to projection edges.
   * - **Distortion**
     - Float
     - Strength of perspective distortion.
   * - **Limit**
     - Boolean
     - Restrict projection to objects within a maximum distance from the section plane.
   * - **Distance**
     - Float
     - Maximum distance for the projection limit (scene units).
   * - **Hidden Edge Detection**
     - Boolean
     - Detect and store edges hidden behind other geometry in a separate edge layer.
   * - **Quality**
     - Enum
     - HED accuracy preset: ``Low``, ``Medium``, ``High``, ``Ultra``, ``Custom``.



.. _op-delete-drawing:

Delete Drawing
--------------

``section_pro.delete_drawing``

Deletes the active drawing object and removes it from the scene. Asks for confirmation.



.. _op-refresh-drawing:

Refresh Drawing
---------------

``section_pro.refresh_drawing``

Regenerates the active drawing in-place using its stored settings and source section. Must be run in **Object Mode**. The drawing object's position in 3D space is preserved.



.. _op-show-drawing:

Show / Hide Drawing
-------------------

``section_pro.show_drawing``

Shows or hides the active drawing object and updates the drawing's state in the active view.

.. list-table::
   :header-rows: 1
   :widths: 25 15 60

   * - Property
     - Type
     - Description
   * - **Show**
     - Boolean
     - ``True`` to show, ``False`` to hide.



.. _op-export-drawing:

Export Drawing
--------------

``section_pro.export_drawing``

Exports the active drawing to a file. Opens a file browser dialog.

.. list-table::
   :header-rows: 1
   :widths: 25 15 60

   * - Property
     - Type
     - Description
   * - **File Type**
     - Enum
     - Output format: ``DXF``, ``SVG``, or ``JSON``.
   * - **Unit**
     - Enum
     - Coordinate unit in the exported file: ``Meters``, ``Centimeters``, ``Millimeters``, ``Inches``, or ``Feet``.



.. _op-select-edge-layer:

Select Drawing Edge Layer
-------------------------

``section_pro.select_drawing_edge_layer``

Enters Edit Mode on the active drawing and selects all edges belonging to the specified edge layer.

.. list-table::
   :header-rows: 1
   :widths: 25 15 60

   * - Property
     - Type
     - Description
   * - **Edge Layer**
     - Enum
     - Layer to select: ``Section``, ``Projection``, or ``Hidden``.



.. _op-create-view:

Create View
-----------

``section_pro.create_view``

Creates a new named view. Opens a properties dialog.

.. list-table::
   :header-rows: 1
   :widths: 25 15 60

   * - Property
     - Type
     - Description
   * - **Name**
     - String
     - Name for the new view.
   * - **Settings**
     - Enum
     - Starting state: ``Copy Active View`` or ``Blank View``.



.. _op-delete-view:

Delete View
-----------

``section_pro.delete_view``

Deletes the active view. Asks for confirmation. The last view cannot be deleted while sections or drawings exist.



.. _op-restore-view:

Restore View
------------

``section_pro.restore_view``

Applies the section states, drawing states, and viewport state of the active view to the current 3D Viewport.



.. _op-save-viewport:

Save Viewport
-------------

``section_pro.view_save_viewport``

Saves the current 3D viewport state (orientation, projection, shading) into the active view. Asks for confirmation before overwriting previously saved data.



.. _op-load-viewport:

Load Viewport
-------------

``section_pro.view_load_viewport``

Restores the saved viewport state of the active view without switching views.

