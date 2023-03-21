Utility Ops
===================================


.. _clipboard:

Mesh Clipboard
--------------

Three operators were added to allow the user to copy, cut, and paste selected faces. Outside of face mode, the ``Copy Objects`` and ``Paste Objects`` operators are called.

* ``Copy`` :: Copy the face selection into the clipboard.;

* ``Cut`` :: Copy the face selection into the clipboard then remove it from the mesh.;

* ``Paste`` :: Paste the geo in the clipboard to the active object.

.. note::
	* ``Copy``, ``Cut``, and ``Paste`` can be bound in the addon Preferences in the ``Mesh`` context.;


.. _gridtoggle:

Grid Toggle
-----------

``Grid Toggle`` will toggle the visibility of the grid axis and floor grid, or the workplane, depending on whats currently visible.

.. note::
	* ``Grid Toggle`` can be bound in the addon Preferences in the ``3D View`` context.;


.. _workplane:

Toggle Workplane
----------------

The ``Toggle Workplane`` operatior creates a transform orientation aligned to the current element selection and draws a grid aligned to said orientation.
Subsequent transform tools will automatically align to the active transform orientation.
Many tools in the rmKit addon support the workplane.

.. note::
	* To use ``Toggle Workplane`` bind it to a key in the addon Preferences in the ``3D View`` context.;


.. _cursorpie:

3D Cursor Ops
-------------

A radial menu that contains quick access to default blender operations for managing the 3D Cursor as well as a few custom ones.
The point bellow only cover the custom operators:

* ``Cursor to Origin`` :: Same as ``Cursor to World Origin`` except moves to the center of the workplane when active.

* ``Cursor to Selection and Orient`` :: Moves the 3D Cursor to the current selection and orients it based on the topology.
	
* ``Unrotate Relative to Cursor`` :: Unrotates the selected components based on the orientation of the 3D Cursor.

.. note::
	* To use ``3D Cursor Ops`` bind it to a key in the addon Preferences in the ``3D View`` context.;


.. _dimensionstool:

Toggle Dimensions
-----------------

Toggles the visibility of a set of world axis drawn over the current component or object selection that displays the world space dimensions. Very usefull!

.. note::
	* To use ``3D Cursor Ops`` bind it to a key in the addon Preferences in the ``3D View`` context or access it in the rmKit section of the tools panel.;


.. _itemnametomeshname:

Item Name to Mesh Name
----------------------

Copy the name of each item in the scene to its mesh data object.

.. note::
	* Operator is accessible as a button in the rmKit section of the tools panel.;