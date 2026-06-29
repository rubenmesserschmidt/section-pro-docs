Sections
========

A **section** is the central element of Section Pro. It defines a cutting plane that slices through your 3D geometry and reveals the cross-section. You create and manage sections from the *Section Pro* panel in the 3D Viewport sidebar (N panel).

Each section is represented by a plane object in the scene. Its position and rotation determine where and how the cut is applied. You can move and rotate the section object like any regular Blender object to adjust the cut.


Section Scope
-------------

Every section has a **scope** that controls which objects are affected by the cut. The scope is set when creating the section and determines what the section "knows about".

.. list-table::
   :header-rows: 1
   :widths: 20 80

   * - Scope
     - Description
   * - **Objects**
     - Only the objects you explicitly assign to the section are cut. You can add or remove objects at any time from the *Scope* sub-panel.
   * - **Collections**
     - All objects inside one or more selected collections are cut. The scope automatically tracks collection membership, and can be refreshed when the collection contents change.
   * - **Scene**
     - All supported objects in the active scene are cut. The scope can be refreshed to pick up newly added objects.


Section Methods
---------------

The way the section cut is rendered depends on the **section method** configured on the active :doc:`View <views>`. There are two methods:

**Boolean**
    A cutter object (a box aligned to the section plane) is applied to each target object as a Geometry Nodes modifier with a boolean operation. This produces a true mesh cut that is compatible with all render engines and solid shading modes. After transforming the section the cut has to be updated manually.

**Shader**
    The section cut is implemented by modifying the material shaders of the target objects. A Section Pro shader node group is injected into each material to discard geometry below the cut plane. This method is faster to set up and does not alter the mesh, but requires the Eevee or Cycles render engine to display correctly.


Section Display
---------------

In the *Display Settings* sub-panel you can control the visual appearance of the section:

- **Show Plane** – Toggles the visibility of the section plane gizmo overlay in the viewport.
- **Plane Color** – The color used to draw the section plane gizmo.


Enabled State
-------------

Sections can be individually **enabled** or **disabled** per :doc:`View <views>`. When a section is disabled in the active view, the cut is not applied to any objects. This makes it easy to compare the model with and without specific cuts across different views.

.. seealso::

   :doc:`/guides/creating-sections`
      Step-by-step guide for creating your first section.

   :doc:`/guides/managing-scope`
      How to add, remove, and refresh objects in a section's scope.
