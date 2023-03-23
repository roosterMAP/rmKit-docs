.. |video| raw:: html

	<video controls loop width="700">
		<source src="_static/movetofurthest.mp4" type="video/mp4">
		Your browser does not support the video tag.
	</video>

.. |video1| raw:: html

	<video controls loop width="700">
		<source src="_static/screenreflect.mp4" type="video/mp4">
		Your browser does not support the video tag.
	</video>

.. |video2| raw:: html

	<video controls loop width="700">
		<source src="_static/knifescreen.mp4" type="video/mp4">
		Your browser does not support the video tag.
	</video>

.. |video3| raw:: html

	<video controls loop width="700">
		<source src="_static/arcadjust.mp4" type="video/mp4">
		Your browser does not support the video tag.
	</video>



MeshEdit Ops
===================================

.. _movetofurthest:

Move to Furthest
----------------

|video|

``Move to Furthest`` is used to quickly align verts/edges/faces along the axis most closely aligned to a selectedrelative direction.
For example, selecting the **Left** option will flatten all selected elements to the planar axis most aligned with the viewport camera's left direction vector. The position of this plane is the leftmost position in the selection.
There are also **Horizontal** and **Vertical** options which will place the flatten axis plane at the center of the selection.
Selecting a direction from within the **Local** submenu will evaluate all discontinuous geometry separatly.
Selecting a direction from within the **Constrain** submenu will ensure vert transformations to the flatten planar axis are done along adjacent edges.
This tools is designed to be used in combination with the :ref:`Workplane <workplane>`
Click here to visit the docs for :ref:`UV Move to Furthest <uvmovetofurthest>`

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context.


.. _knifescreen:

Knife Screen
------------

|video2|

``Knife Screen`` is a streamlined tool for cutting selected faces with a slice plane. The orientation of the slice plane is
defined by the user depending on the active selecion type, the orientation of the viewport camera, and the operator selected.
This tools is designed to be used in combination with the :ref:`Workplane <workplane>`

* ``Vertex Mode`` :: Spawns one slice plane per selected vertex.;
	* Selecting **Horizontal** / **Vertical** mode will orient each slice plane such that it cuts along a horizontal/vertical axis and into the screen.;
	* Selecting **Grid** mode will align the axis defining the slice to the nearest grid axis. Selecting a **Screen** mode will use the absolute axis defined by the viewport orientation.;

* ``Edge Mode`` :: Spawns one slice plane per selected edge.;
	* **Topo** orients the slice plane along the endpoints of an edge and slices into the normal of said edge.;
	* **Grid** orients the slice plane along the endpoints of an edge and slices into the grid axis most aligned with the edge normal.;
	* **Screen** orients the slice plane along the endpoints of an edge and slices into the screen.;

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.
	* ``Knife Screen`` slices through the background face selection. Thus, the ``Change Mode To`` and ``Convert Mode To`` operators must be bound: :ref:`Background Selection <backgroundselection>`;


.. _screenreflect:

Screen Reflect
--------------

|video1|

``Screen Reflect`` is used to quickly duplicate and mirror the current face selection about an arbitrary point and axis. Each are determined by a combination of viewport orientation and selected relative direction.
Launching the command and selecting a relative direction in the top level radial menu will set the normal of the mirror to the most aligned grid axis to that direction. The position will be the
farthest vert along said grid axis.

Accessing the operators within the nested **Slice** and **Reflect** radial menus will fire similar commands that rely on the position of the **3D Cursor**. This is why the top level radial
menu provides quick access to commands that set the position of the **3D Cursor**:

* **Set Cursor** will move the cursor to the center of the current component selection.;

* **Cursor to Origin** will move the cursor to the world/workplane origin.;

Operators within the nested **Reflect** radial menu will duplicate and mirror the face selection about the **3D Cursor**.
Operators within the nested **Slice** radial menu will do the same as **Reflect** but will also slice faces that intersect with the mirror, delete everything on the other side, and weld verts.
This tools is designed to be used in combination with the :ref:`Workplane <workplane>`

.. note::
	Bind in the addon Preferences in the ``3D View`` context or access it in the rmKit-MeshEdit section of the tools panel.


.. _createtube:

Create Tube
-----------

.. list-table:: Convert a tube over a selection of edges.
	:class: borderless
	:align: center
	:width: 65%

	* - .. image:: _static/createtube_a.jpg
	  - .. image:: _static/createtube_b.jpg

``Create Tube`` is a modal tool that creats a sequence of tubes based on sets of discontinuous edge selections.
The user can dynamically change the radius, vert count, and rotation of the tubes before commiting with LMB.

If you wish to rebuild an existing tube, select it in face mode and run the command again. This will create a new tube with the same vert count and radius.
This is particularly usefull when an existing tube has been deformed or manipulated.

.. note::
	* To recreate a tube in face mode, there can only be one tube in the selection and it must have two closed loops of open edges.;
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.


.. _connectedges:

Connect Edges
-------------

.. list-table:: Connect selected edges.
	:class: borderless
	:align: center
	:width: 75%

	* - .. image:: _static/connectedge_a.jpg
	  - .. image:: _static/connectedge_b.jpg

``Connect Edges`` is a modal tool similar to ``Loop Cut``. It creates new edges between adjacent pairs of selected edges.
The Connect Edges settings let you specify the number of new edges, the amount of separation from each other, and their general location.
* **Level** controls the number of connecting edges.
* **Pinch** controls the relative spacing between connecting edges.
* **Slide** controls the position of the connecting edges.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.


.. _arcadjust:

Arc Adjust
----------

|video3|

``Arc Adjust`` is a modal tool that lets the user resize the radius of arcs of edges. By selecting the edge loops that make up an arc, the algorithm
with use the outer most edges to drive the resizing. There are two modes for arc adjust:
* **Default** scales all verts that make up an arc from some point such that the end points of the arc slide along the outermost edges.
This has the benefit of preserving details within each arc.
* **Radial** assumes that all arcs are about the same axis. Each get remapped so a circle with a center along said axis.
This is usefull when you have sequences of bevels that need to radiate from some central point.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.



.. _unbevel:

Unbevel
-------

``Unbevel`` is another tool that operates on arcs of edge loops. Its find the outermost edges of an arc and finds a
point at which they intersect, and welds all verts that make up the art to said point.
This is the same as running ``Arc Adjust`` with **Scale** set to 0.0.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.


.. _radialalign:

Radial Align
------------

``Radial Align`` is a simple command that remaps the verts that make up a closed loop edge selection to a circle. If run in face mode, the boundary verts get remapped.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.


.. _targetweld:

Target Weld
-----------

In vert mode, ``Target Weld`` collapses selected verts to a single point and moves it to the position of the active vertex. In edge mode, sequences ar edge loops are welded to
the edge loop that contains the active edee.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.


.. _thicken:

Thicken
-------

``Thicken`` is a modal tool that behaves similarly to the ``Solidify`` tool except it provides attribute hauling in the 3D View. There is also a **Thicken From Center** option
that can be toggled via checkbox in the modal dialog, or RMB.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.



.. _reduce:

Reduce Operators
----------------

These are slightly modified versions of the similar Bleneder operators that behave more like their 3DS Max equivalants.

* ``Delete`` :: Delete selected components.

* ``Dissolve`` :: Remove the selected components while preserving underlying topology.

* ``Pop`` :: Similar to **Dissolve** except removes endpoint vertices from the resulting topology after removing the edges.

* ``Collapse`` :: Collapse the selection into a single vertex.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.



.. _polypatch:

PolyPatch
---------

``PolyPatch`` is a contextual tool that performes a variety of mesh modifications depending on the selection mode, the type of topology selected, and the number of elements selected.

* **Vert Mode**
	* If two or more verts are selected on a single polygon, an edge is added to connect all selected verts to the others.
* **Edge Mode**
	* If a closed edge is selected the edge is turned.
	* If a closed loop of open edges is selected, it is capped.
	* If two open loops of open ares are selected then they are bridged.
* **Face Mode**
	* If two sets of discontinuous faces are selected, then they are bridged.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.


.. _bevel:

Bevel
-----

``Bevel`` is a contextual tool fires the appropriate bevel tool depending on the selection mode.

* **Vert Mode**
	* ``Vertex Bevel`` is executed.
* **Edge Mode**
	* ``Edge Bevel`` is executed.
* **Face Mode**
	* ``Inset Faces`` is executed.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.


.. _extend:

Extend
------

``Extend`` is a contextual tool fires the appropriate Extend tool depending on the selection mode.

* **Vert Mode**
	* ``Extend Vertices`` is executed.
* **Edge Mode**
	* ``Extrude Only Edges and Move`` is executed.
* **Face Mode**
	* ``Add Duplicate`` is executed.

.. note::
	* Bind in the addon Preferences in the ``Mesh`` context or access it in the rmKit-MeshEdit section of the tools panel.