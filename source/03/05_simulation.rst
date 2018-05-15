.. _sec_simulation:

[Simulation] (S)
=================

The functions of the items under the [Simulation] menu are explained in
the following sections.

[Run] (R)
----------

**Description**: Starts the solver.

When you select [Run], a warning dialog will open to ask whether you
want to save the current project. When you have already run solver
before, a dialog will open to ask if you agree to delete the previous
calculation results.

When the solver starts running, the [Solver Console] will open. The
solver console displays real-time output messages to the "Standard
output" or to the "Standard error".
:numref:`image_solver_console_window_sim` shows an example of the
[Solver Console].

.. _image_solver_console_window_sim:

.. figure:: images/solver_console_window_sim.png
   :width: 380pt

   The [Solver Console]

[Stop] (S)
-------------

**Description**: Stops the solver.

When you select [Stop], the [Confirm Solver Termination] dialog
(:numref:`image_confirm_solver_term_dialog`)
will open. Select [Yes] (Y) to stop running solver. When the
solver has stopped, the [Solver Console] title changes.
:numref:`image_solver_console_title` shows an example of the
[Solver Console] window title after stopping the solver.

.. _image_confirm_solver_term_dialog:

.. figure:: images/confirm_solver_term_dialog.png
   :width: 180pt

   The [Confirm Solver Termination] dialog

.. _image_solver_console_title:

.. figure:: images/solver_console_title.png
   :width: 320pt

   The [Solver Console] window title


[Solver Information] (S)
--------------------------

**Description**: Displays information of the solver that is used for the
current project. An example of the dialog is shown in
:numref:`image_solver_info_dialog`.

.. _image_solver_info_dialog:

.. figure:: images/solver_info_dialog.png
   :width: 300pt

   The [Solver information] dialog

[Export solver console log] (E)
-----------------------------------

**Description**: Exports the solver console log.

The function of this item is the same to [Solver Console Log] under
[Export] menu under [File] menu. Refer to
:ref:`sec_file_export_solver_console_log`.
