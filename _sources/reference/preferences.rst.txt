Preferences
===========

Section Pro preferences are accessible via **Edit → Preferences → Add-ons → Section Pro**, or by clicking the preferences icon in the Section Pro panel header.

The preferences are divided into four groups: Views, Sections, Drawings, and Section Colors.


View Settings
-------------

.. list-table::
   :header-rows: 1
   :widths: 40 60

   * - Setting
     - Description
   * - **Section Method** *(default)*
     - The section method (``Boolean`` or ``Shader``) assigned to newly created views.
   * - **Orientation** *(default)*
     - Whether the *Save Viewport Orientation* option is enabled by default on new views.
   * - **Projection** *(default)*
     - Whether the *Save Viewport Projection* option is enabled by default on new views.
   * - **Shading** *(default)*
     - Whether the *Save Viewport Shading* option is enabled by default on new views. Enabled by default.
   * - **Restore View on Change**
     - When enabled, switching to a view automatically restores its saved section states, drawing states, and viewport configuration. Enabled by default.
   * - **Auto Save Viewport on Change**
     - When enabled, the current viewport state is automatically saved to the outgoing view before switching. Disabled by default.


Section Settings
----------------

.. list-table::
   :header-rows: 1
   :widths: 40 60

   * - Setting
     - Description
   * - **Enabled** *(default)*
     - Whether newly created sections are enabled by default. Disabled by default.
   * - **Hidden** *(default)*
     - Whether newly created sections are hidden by default. Disabled by default.
   * - **Show Plane** *(default)*
     - Whether the section is displayed as a transparent plane in the viewport by default. Enabled by default.
   * - **Plane Color** *(default)*
     - Default color used to display this plane.


Drawing Settings
----------------

.. list-table::
   :header-rows: 1
   :widths: 40 60 

   * - Setting
     - Description
   * - **Hidden** *(default)*
     - Whether newly created drawings are hidden by default. Disabled by default.


Section Color Settings
----------------------

Section colors control the fill color applied to the cut faces when using the :doc:`/concepts/sections`.

.. list-table::
   :header-rows: 1
   :widths: 40 60

   * - Setting
     - Description
   * - **Use Material Section Color** *(default)*
     - When enabled, the section fill color is derived from the object's material rather than the per-object/collection color. Disabled by default.
   * - **Per Material** *(default color)*
     - Default section fill color for materials that do not have a custom section color set.
   * - **Per Collection** *(default color)*
     - Default section fill color assigned to collections.
   * - **Per Object** *(default color)*
     - Default section fill color assigned to individual objects.


Display Settings
----------------

.. list-table::
   :header-rows: 1
   :widths: 40 60

   * - Setting
     - Description
   * - **Show Add Menu**
     - Whether a Section Pro menu is shown in the bottom of the add menu (:kbd:`Shift + A`).
   * - **Show Context Menu**
     - Whether a Section Pro context menu is shown in the bottom of the object context menu (:kbd:`Right Click`).
