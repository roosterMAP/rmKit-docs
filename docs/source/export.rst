Export Manager
===================================

.. _export list view:


.. list-table::
	:class: borderless
	:align: center
	:width: 60%

	* - .. image:: _static/export.jpg

``Export Manager`` is a light weight fbx exported used to quickly add objects in the scene to an export list, and export them individually or in groups.
You can add or remove objects to the **Export List**, and export them by pressing the little export icon on the right of each entry, or pressing the **Export Checked** button at the top of the GUI.


* ``Add`` will add the objects selected in the scene to the export list.
* ``Remove`` will remove items selected in the **Export Manager** from the export list.
* ``Export`` will export the export item and its children in the scene to an fbx based on its name.
* ``Export Checked`` will export all export items that are checked/enabled in the list view.
* ``Settings`` will open a dialog where you can set the base and export path. Combine the **PathStrings** listed in the dialog to control where export items write out their fbx's.

.. note::
	By default, the **Export Manager Path** is set to ``$SceneDir\$SceneName_$ObjectName``. This defines the export path of each export item.
	You can see that each string starting with a ``$`` is provided by blender. The rest is inserted on a per character basis.
	In this case, each export item is exported in the same dir as the current .blend file and the fbx filename is the scene name, followed by an underscore, followed by the export item name.
	This pattern can be customized by the user. For example, if you want to export all fbx's to a subdir called ``work`` and omit the scene name from the filename it could change to ``$SceneDir\work\$ObjectName``.