UV Edit Ops
===========


.. _uvloopringselection:

UVLoop / UVRing Selection
-------------------------

Alternate edge loop and edge ring selection algorithms.

* ``UV Loop`` : Extend current edge selection by loop. Utilizes 3DS Max algorithm.

* ``UV Ring`` : Extend current edge selection by ring. Utilizes 3DS Max algorithm.

.. note::
	* Bind to a key in the addon Preferences in the ``UV Editor`` context or find it in the rmKit section of the UV Editor tools panel.


.. _uvmovetofurthest:

UV Move to Furthest
-------------------

``UV Move to Furthest`` is used to quicly align uv components. Executing the operator opens a radial menu with relative directions. Selecting an option will
move all components of the selection to the furthest point in that direction. For example, selecting the **Left** option will flatten all selected elements to the
left most point included in the selection. This has the effect of aligning the selection along the vertical axis. Selecting the **Local** option will open a submenu
with more relative directions. Selecting one of these will evaluate each uv-discontinuous group of components separatly. This is particularly usefull if you want groups
of uv edges to be parallel to oneanother.
Click here to visit the docs for the 3D View version of this tool:: :ref:`Move to Furthest <movetofurthest>`

.. note::
	* Bind to a key in the addon Preferences in the ``UV Editor`` context.


.. _boundstransform:

Bounds Transform
----------------

``Bounds Transform`` is a modal tool that enables the use to transform the selected uv components using a bounding box toolhandle.
Click and drag within the box to move the entire selection, pull on a corner to resize along **U** and **V**, or pull on an edge
to resize along **U** or **V**.

.. note::
	* Bind to a key in the addon Preferences in the ``UV Editor`` context or find it in the rmKit section of the UV Editor tools panel.


.. _insetscaleuvs:

Inset Scale UVs
---------------

``Inset Scale UVs`` a modal operator that resizes selected uv islands by "insetting" int bounds of the selection.
This is particularly usefull which used in combination with the Hotspot tools.

.. note::
	* Bind to a key in the addon Preferences in the ``UV Editor`` context or find it in the rmKit section of the UV Editor tools panel.


.. _gridify:

Gridify
-------

``Gridify`` will map selected uv faces to a grid and preserve relative aspect ratios of each quad.
This operator is only compatible with grid topologies.

.. note::
	* Bind to a key in the addon Preferences in the ``UV Editor`` context or find it in the rmKit section of the UV Editor tools panel.


.. _rectanguarize:

Rectangularize
--------------

``Rectangularize`` attempts to map the uvs of the current face selection to a rectangle. Is does this by doing a conformal uv unwrap, identifying four corners,
flattening the edges in between, and relaxing the inner uv verts.