Selection Ops
===================================



.. _backgroundselection:

Background Selection
--------------------

By default, Blender has no concept of a **background selection** where switching from face mode to vertex mode would preserve
the face selection when returning to it from a different mode or selection type. The commands bellow make this possible but storing
the selection such that it can be retrieved later once you return to that selection type.

* ``Change Mode To`` :: Store the current component selection as a selection set and switch to the arg mode.

* ``Convert Mode To`` :: Store the current component selection as a selection set and convert it to the arg mode.

.. note::
	* All six commands must be bound replacing Blender's default change/convert operator calls.;
	* To use ``Change Mode To`` ops, bind it to a key in the addon Preferences in the ``3D View`` context.
	* To use ``Convert Mode To`` ops, bind it to a key in the addon Preferences in the ``Mesh`` context.



.. _loopringselection:

Loop / Ring Selection
---------------------

Alternate edge loop and edge ring selection algorithms.

* ``Loop`` :: Extend current edge selection by loop. Utilizes 3DS Max algorithm.;
	* Setting **Force Boundary** arg to True will always extend loops along open edges.;

* ``Ring`` :: Extend current edge selection by ring. Utilizes 3DS Max algorithm.;

In face mode, bothe ``Loop`` and ``Ring`` extend the face selection by adjacency from last face selection.

.. note::
	* To use ``Loop`` ops, bind it to a key in the addon Preferences in the ``Mesh`` context. To fire the alt algorithm, check the **Force Boundary** arg.
	* To use ``Ring`` ops, bind it to a key in the addon Preferences in the ``Mesh`` context.


.. _continuousselection:

Continuous Selection
--------------------

* ``Select Continuous`` with **Add** or **Set** args do the same as ``Select Linked`` operator while in vert and face mode. In edge mode, The ``Loop`` described above is fired.;

* ``Invert Continuous`` will invert the current component selection only on geometry continuous to the current selection.;

.. note::
	* To use ``Select Continuous`` ops, bind it to a key in the addon Preferences in the ``Mesh`` context.
	* To use ``Invert Continuous`` ops, bind it to a key in the addon Preferences in the ``Mesh`` context.