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



Background Selection:
``Vert Mode``
``Edge Mode``
``Face Mode``
``Convert to Vert Mode``
``Convert to Edge Mode``
``Convert to Face Mode``

Loop/Ring
``Loop``
``Loop Alt``
``Ring``

Continuous
``Set Continuous``
``Add Continuous``
``InvertContinuous``