.. |video| raw:: html

	<video controls loop width="700">
		<source src="_static/movetofurthest.mp4" type="video/mp4">
		Your browser does not support the video tag.
	</video>


MeshEdit Ops
===================================

.. _movetofurthest:

Move to Furthest
-------------------

|video|

``Move to Furthest`` is used to quickly align verts/edges/faces along the axis most closely aligned to a selected relative direction.
For example, selecting the **Left** option will flatten all selected elements to the planar axis most aligned with the viewport camera's left direction vector. The position of this plane is the leftmost position in the selection.
There are also **Horizontal** and **Vertical** options which will place the flatten axis plane at the center of the selection.
Selecting a direction from within the **Local** submenu will evaluate all discontinuous geometry separatly.
Selecting a direction from within the **Constrain** submenu will ensure vert transformations to the flatten planar axis are done along adjacent edges.
This tools can also be used in combination with the :ref:`Workplane <workplane>`
Click here to visit the docs for :ref:`UV Move to Furthest <uvmovetofurthest>`

.. note::
	* To use ``Move to Furthest`` bind it to a key in the addon Preferences in the ``Mesh`` context.

``PolyPatch``
``Delete``
``Collapse``
``Dissolve``
``Pop``
``Knife Screen``
``Move to Furthest``
``Screen Reflect``
``Bevel``
``Extend``
``Connect Edges``
``Thicken``
``Create Tube``
``Arc Adjust``
``Unbevel``
``Radial Align``
``Target Weld``