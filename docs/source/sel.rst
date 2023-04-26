Selection Ops
===================================



.. _backgroundselection:

Background Selection
--------------------

By default, Blender has no concept of a **background selection** where switching from face mode to vertex mode would restore
the face selection when returning to it from a different mode or selection type. The operators below make this possible by
encoding the selection state of an element in the mesh itself.

* ``Change Mode To``: Store the current component selection as a selection set and switch to the arg component mode.

* ``Convert Mode To``: Store the current component selection as a selection set and convert it to the arg component mode.

.. note::
	* All six commands must be bound replacing Blender's default change/convert operator calls.
	* To use ``Change Mode To`` ops, bind it to a key in the addon Preferences in the ``3D View`` context.
	* To use ``Convert Mode To`` ops, bind it to a key in the addon Preferences in the ``Mesh`` context.



.. _loopringselection:

Loop / Ring Selection
---------------------

Alternate edge loop and edge ring selection algorithms.

* ``Loop``: Extend current edge selection by loop. Utilizes 3DS Max algorithm.

	* Setting **Force Boundary** arg to True will always extend loops along open edges.

* ``Ring``: Extend current edge selection by ring. Utilizes 3DS Max algorithm.

In face mode, both ``Loop`` and ``Ring`` extend the face selection by adjacency from last face selection.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-Selection section of the tools panel.


.. _continuousselection:

Continuous Selection
--------------------

* ``Select Continuous`` with **Add** or **Set** args do the same as ``Select Linked`` operator while in vert and face mode. In edge mode, the ``Loop`` operator described above is executed.

* ``Invert Continuous`` will invert the current component selection only on geometry 3d continuous with the current selection.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-Selection section of the tools panel.
