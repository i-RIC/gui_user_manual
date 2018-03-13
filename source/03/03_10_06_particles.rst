[Particles] (P)
================

**Description**: Exports the particles.

This item is active only when a [2D Post-processing Window] or [3D
Post-processing Window] is active. Particles are exported into VTK
files.

Wyen you select [Particles], the [Export Particles] dialog
(:numref:`image_export_particles_dialog`)
will open. Edit the setting and click on [OK] to start exporting. File
names of exported files will be "(Prefix) + (Number) + (".vtk")".

When you want to export partial data, remove the check on [All
timesteps] and specify the range of timesteps by editing [Start] and
[End], and [Skip rate].

.. _image_export_particles_dialog:

.. figure:: images/export_particles_dialog.png

   The [Export Particles] dialog
