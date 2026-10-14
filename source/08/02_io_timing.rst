Timing of reading, saving and discarding files
==============================================

This section explains when each file shown in :ref:`sec_project_files` is
read, saved and discarded.

Meta information
-----------------

* **Read**: When the project is opened
* **Save**: When the project is saved
* **Discard**: Never

Actual data
-----------

Geographic data
~~~~~~~~~~~~~~~~~~~~

* **Read**: When the project is opened
* **Save**: When the project is saved, or when data is imported
* **Discard**: When the data is deleted

Hydraulic data
~~~~~~~~~~~~~~~~~~~~

* **Read**: When the project is opened
* **Save**: When the project is saved, or when data is imported
* **Discard**: Never

Grid generation conditions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

See :ref:`io_timing_cgns`

Boundary condition settings
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Read**: When the project is opened
* **Save**: When the project is saved, or when data is imported
* **Discard**: Never

Grid data
~~~~~~~~~~~~~~~~~~~~

See :ref:`io_timing_cgns`

Calculation conditions
~~~~~~~~~~~~~~~~~~~~~~~~~~

See :ref:`io_timing_cgns`

Solver output log
~~~~~~~~~~~~~~~~~~~~

* **Read**: When the project is opened
* **Save**: While the solver is running
* **Discard**: When the calculation results are deleted

Calculation results
~~~~~~~~~~~~~~~~~~~~~~~~

See :ref:`io_timing_cgns`

Measured values
~~~~~~~~~~~~~~~~~~~~

* **Read**: When the project is opened
* **Save**: When the project is saved
* **Discard**: Never

Background images
~~~~~~~~~~~~~~~~~~~~

* **Read**: When the project is opened
* **Save**: When the project is saved, or when data is imported
* **Discard**: When the data is deleted

.. _io_timing_cgns:

Case1_input.cgn, Case1.cgn, tmp/Case1.cgn.copy
-------------------------------------------------------

As shown in :ref:`sec_project_files_real`, most of the actual data that the solver reads
and the data that the solver outputs is stored in CGNS files.

This section explains the roles of Case1_input.cgn, Case1.cgn and tmp/Case1.cgn.copy,
and how iRIC GUI handles these files.

.. note:: The following describes the implementation as of 4.1.

Case1_input.cgn
~~~~~~~~~~~~~~~~~~~~

A file that stores the input data created in iRIC GUI.

The timing is as follows.

* **Read**:
   * When the project is opened
   * When the CGNS file is reloaded

* **Save**:
   * When the project is saved (including when you select [Yes] in the dialog to confirm saving that is displayed after the solver finished running)
   * Immediately before the solver starts running

* **Discard**: Never

The information read from Case1_input.cgn is displayed in iRIC GUI in the following places.

* Pre-processor
* 2D visualization window (inside "Input Grid")
* Cross-section result window (displayed as (input))

It always exists from the time the project is created.

Case1.cgn
~~~~~~~~~~~~

A file in which the solver has appended calculation results to Case1_input.cgn.

.. note:: When outputting to a separate file for each time step, result/Solution1.cgn, etc. follow the description below.

The timing is as follows.

* **Read**:
   * When the project is opened
   * When the solver finishes running

* **Save**: Created immediately before the solver starts running, by copying Case1_input.cgn right after iRIC GUI saves Case1_input.cgn. While running, the solver appends calculation results to this file.
* **Discard**: When the calculation results are discarded

The information read from Case1.cgn is displayed in iRIC GUI in the following places.

* 2D visualization window
* 3D visualization window
* Graph window
* Cross-section result window

It exists only if the solver has been run in the project.

tmp/Case1.cgn.copy
~~~~~~~~~~~~~~~~~~~~~~~~~

A copy of Case1.cgn to which the solver has appended calculation results.

It is created by the solver when the calculation results are reloaded while the solver is running. The details of the process are as follows.

1. When the user reloads the calculation results in the GUI, a file named ".flush" is created in the project folder.
2. When cg_iRIC_Write_Sol_End() is called in the solver, it checks whether the ".flush" file exists. If it does, the following process is performed.

   1. If tmp/Case1.cgn.copy already exists, delete it.
   2. Close Case1.cgn.
   3. Copy Case1.cgn to tmp/Case1.cgn.copy.
   4. Open Case1.cgn in update mode.
   5. Delete .flush.

3. When the GUI detects that .flush has been deleted by the solver, it opens tmp/Case1.cgn.copy in read mode and reads the calculation results.

.. note:: tmp/Case1.cgn.copy is not created when the calculation results are set to be output "to a separate file for each time step".

The timing is as follows.

* **Read**: Read by the GUI when the calculation results are reloaded while the solver is running.
* **Save**: Saved by the solver when the calculation results are reloaded in the GUI while the solver is running. The details are as shown above.
* **Discard**: When the solver finishes running

The information read from tmp/Case1.cgn.copy is used for the same purposes as the information read from Case1.cgn, only while the solver is running.

It exists only while the solver is running.

Remarks
~~~~~~~~

* Case1.cgn stores the calculation grid and calculation results from the last time the solver was run, whereas Case1_input.cgn stores the latest input information created by the user in the pre-processor. Therefore, if the user edits or regenerates the grid after running the solver, the grid displayed in the pre-processor and the grid displayed in the visualization windows will differ.

* Case1.cgn is opened by the solver to append calculation results, whereas Case1_input.cgn is opened only by iRIC GUI. Therefore, even if the solver terminates abnormally during calculation and Case1.cgn is corrupted, the input information stored in Case1_input.cgn is not lost.

.. note:: The following describes the implementation as of iRIC 4.0.

Case1_input.cgn
~~~~~~~~~~~~~~~~~~~~

A file that stores the input data created in iRIC GUI.

The timing is as follows.

* **Read**: Never
* **Save**: Created immediately before the solver starts running, by copying Case1.cgn.
* **Discard**: Never
* **Other**: If Case1.cgn is corrupted and cannot be read when the project is opened, Case1_input.cgn is copied to Case1.cgn.

Case1_input.cgn is a backup for the case where Case1.cgn is corrupted and can no longer be read. The information in Case1_input.cgn is never read directly by iRIC GUI.

It exists only if the solver has been run in the project.

Case1.cgn
~~~~~~~~~~

A file that stores the input information created in iRIC GUI and the calculation results appended by the solver.

.. note:: When outputting to a separate file for each time step, result/Solution1.cgn, etc. follow the description below.

The timing is as follows.

* **Read**:
   * When the project is opened
   * When the CGNS file is reloaded
   * When the solver finishes running

* **Save**: Depending on the case, it is saved in one of three ways: "new save", "partial update" and "appending calculation results". The details are shown below.

  New save
     Performed by iRIC GUI. A new file is created based on the information entered by the user in the pre-processor.

     It is performed in the following cases.

     * When saving the project, if either of the following two conditions is not satisfied

       * The solver has been run and calculation results exist
       * The user has not edited the grid

     * Immediately before the solver starts running
     * When the calculation results are discarded

  Partial update
     Performed by iRIC GUI. Only the calculation condition information is updated, leaving the calculation results intact.

     It is performed in the following case.

     * When saving the project, if both of the following two conditions are satisfied

       * The solver has been run and calculation results exist
       * The user has not edited the grid

  Appending calculation results
     Performed by the solver. The calculation results at each time step are appended during the calculation.

* **Discard**: Never

.. note::

   For the above **Read**, the process differs depending on the case as follows.

   * "When the CGNS file is reloaded": only the grid display in the pre-processor is updated.
   * "When the solver finishes running": only the display in the calculation result visualization windows, such as the 2D visualization window, is updated.

It always exists from the time the project is created.

The information read from Case1.cgn is displayed in iRIC GUI in the following places.

* Pre-processor
* 2D visualization window
* 3D visualization window
* Graph window
* Cross-section result window

tmp/Case1.cgn.copy
~~~~~~~~~~~~~~~~~~~~~~~~~

A copy of Case1.cgn to which the solver has appended calculation results.

It is created by the solver when the calculation results are reloaded while the solver is running. The details of the process are as follows.

1. When the user reloads the calculation results in the GUI, a file named ".flush" is created in the project folder.
2. When cg_iRIC_Write_Sol_End() is called in the solver, it checks whether the ".flush" file exists. If it does, the following process is performed.

   1. If tmp/Case1.cgn.copy already exists, delete it.
   2. Close Case1.cgn.
   3. Copy Case1.cgn to tmp/Case1.cgn.copy.
   4. Open Case1.cgn in update mode.
   5. Delete .flush.

3. When the GUI detects that .flush has been deleted by the solver, it opens tmp/Case1.cgn.copy in read mode and reads the calculation results.

.. note:: tmp/Case1.cgn.copy is not created when the calculation results are set to be output "to a separate file for each time step".

The timing is as follows.

* **Read**: Read by the GUI when the calculation results are reloaded while the solver is running.
* **Save**: Saved by the solver when the calculation results are reloaded in the GUI while the solver is running. The details are as shown above.
* **Discard**: When the solver finishes running

The information read from tmp/Case1.cgn.copy is used to visualize the calculation results, only while the solver is running.

It exists only while the solver is running.

Remarks
~~~~~~~~

* As shown above, when the project is saved, Case1.cgn is saved either by "new save" or "partial update" depending on the conditions. When the user edits or deletes the grid, a "new save" is performed, so the calculation results are discarded. In particular, when the project is saved in a project folder instead of a \*.ipro file, the project is always saved when it is closed. Therefore, if you have edited the grid, the calculation results will always be discarded when the project is closed, unless you force-quit iRIC GUI. Please be careful.

* Case1.cgn is opened by the solver to append calculation results, whereas Case1_input.cgn is created by copying Case1.cgn immediately before the solver runs, and is opened by neither iRIC GUI nor the solver. Therefore, even if the solver terminates abnormally during calculation and Case1.cgn is corrupted, the input information stored in Case1_input.cgn is not lost.

Notes
-------------

.. _sec_data_incompatibility:

Inconsistency between meta information and actual data
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

As shown above, meta information is saved when the project is saved, whereas
the timing of file operations differs for other data: for example, geographic data is saved when the data is imported and discarded when the data is deleted.

Therefore, if the project is saved in a project folder instead of a project file (\*.ipro),
an inconsistency between the meta information and the actual data may occur in the following cases, and the project can no longer
be opened normally. In that case, you may be able to open the project normally by editing the meta information with a text editor or similar tool to resolve the inconsistency.

* iRIC terminated abnormally after geographic data was imported and before the project was saved
* iRIC terminated abnormally after geographic data was deleted and before the project was saved

When the project is saved in a project folder, the project is always saved when it is closed, in order to prevent the above inconsistency by updating the meta information.
