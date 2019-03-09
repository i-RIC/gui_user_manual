[Calculation Result] (R)
=========================

The functions of the items under the [Calculation Results] menu are
explained in the following sections.

[Open New 2D Post-processing Window]
---------------------------------------

**Description**: Opens a new [2D Post-processing Window].

Refer to :ref:`sec_2d_vis_func` for operations related to [2D Post-processing
Window].

[Open New Bird's Eye 2D Post-processing Window]
----------------------------------------------------

**Description**: Opens a new [Bird's Eye 2D Post-processing Window].

Refer to :ref:`sec_2dbirdeye_vis_func` for operations related to [Bird's Eye 2D
Post-processing Window].

[Open New 3D Post-processing Window]
----------------------------------------

**Description**: Opens a new 3D Post-processing Window.

Refer to :ref:`sec_3d_vis_func` for operations related to [3D Post-processing
Window].

[Open New Graph Window]
--------------------------

**Description**: Opens a new [Graph Window].

Refer to :ref:`sec_graph_window` for operations related to [Graph Window].

[Open New Scattered Chart Window]
------------------------------------

**Description**: Opens a new [Scattered Chart Window].

Refer to :ref:`sec_scattered_chart_window_detail` for operations related to
[Scattered Chart Window].

[Compare with measured values]
--------------------------------

**Description**: Opens a dialog to compare measured values with calculation
result.

Refer to :ref:`sec_compare_with_measured_data_window` for operations related to [Compare with measured
values].

[Reload] (R)
--------------

**Description**: Reload calculation result.

When you select [Reload], the calculation result is reloaded, and if new
calculation results are output by the solver, the timesteps on
[Animation Toolbar] is updated.

[Delete] (D)
---------------

**Description**: Delete calculation result.

When you select [Delete], a dialog to confirm whether you really want to
delete the calculation results opens. Click on [Yes] to delete
calculation result.

.. _sec_manage_simple_operation_results:

[Manage simple operation results] (M)
-----------------------------------------------

**Description**: Manage simple operation results.

Simple operation results are values defined as results of
simple numerical operations between calculation results.

"Simple Operation Result List" dialog (
:numref:`image_simple_operation_result_list`) is shown, and you can manage
simple operation result list on this dialog.

.. _image_simple_operation_result_list:

.. figure:: images/simple_operation_result_list.png
   :width: 240pt

   "Simple Operation Result List" dialog

.. note: The order of simple operation results in the list

   As described in the Note on the dialog, the order of simple operation results
   in the list is important. The simple operation result listed lower in the list
   can refer to the values of simple operation results upper in the list, just like
   calculation result values.

Adding and editing simple operation results
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

On "Simple Operation Result List" dialog, you can open 
"Edit Simple Operation Result" dialog
(:numref:`image_simple_operation_result_edit`) by clicking
on "Add" or "Edit" button.

**Name**: Please input the name of the simple operation result

**Calculation results for input**: You can add or delete calculation results
for input by clicking on "Add" or "Delete" button below. Please refer to
:numref:`table_results_for_input` for detail on the items in the table.

**Definitioni of variable**: Please describe how to calculate the
simple operation result value, by JavaScript language.
Please refer to :ref:`sec_simple_operation_result_example` for 
examples of how to describe the definition.
You can use the variables defined in "Calculation results for input"
as input of the definition.

When you click on "Test" button, the value of simple operation result
is calculated from the content of "Definition of variable" and the
values of "Value for testing" in "Calculation results for input".
If the definition contains problems, an error message is shown.

.. _image_simple_operation_result_edit:

.. figure:: images/simple_operation_result_edit.png
   :width: 300pt

   "Edit Simple Operation Result" dialog

.. list-table:: Detail of "Calculation results for input"
   :name: table_results_for_input
   :header-rows: 1

   * - Item name
     - Description

   * - Result name
     - The name of calculation result for input. You can select from combobox
     
   * - Variable name
     - The name of variable that you can use to refer the value
       in "Definition of variable"

   * - Value for testing
     - The value that is input into the variable when the "Test" button is clicked
     
.. _sec_simple_operation_result_example:

Examples of definition of simple operation result
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Examples of simple operation result definitions is shown here.

You can define simple operation results by using functions like below:

* Simple operators (:numref:`simple_operation_result_operator`)
* JavaScript built-in functions (:numref:`simple_operation_result_js_func`)
* Control syntaxes like if, while (:numref:`simple_operation_result_js_if_while`)
* User defined functions (:numref:`simple_operation_result_my_func`)

Please refer to web pages for detail of JavaScript language, like the link below:

https://developer.mozilla.org/en/docs/Web/JavaScript

.. code-block:: JavaScript
   :name: simple_operation_result_operator
   :caption: Examples of definition of simple operation result (Simple operators)

   return D * D;

.. code-block:: JavaScript
   :name: simple_operation_result_js_func
   :caption: Examples of definition of simple operation result (Built-in functions)

   return Math.sqrt(D);

.. code-block:: JavaScript
   :name: simple_operation_result_js_if_while
   :caption: Examples of definition of simple operation result (Control syntaxes)

   var d2 = D;
   while (d2 < 1000) {
     d2 = d2 * 2;
   }
   if (d2 > 1500) {
     d2 = 1500;
   }

   return d2;

.. code-block:: JavaScript
   :name: simple_operation_result_my_func
   :caption: Examples of definition of simple operation result (User defined functions)

   function f1(d) {
     return d * d;
   }

   function f2(d, e) {
     if (d < e) {
       return e;
     } else {
       return d;
     }
   }

   return f1(D) * f2(D, E);

[Import] (I)
--------------

**Description**: Imports calculation result.

The function of this item is the same to [Calculation Result] under
[Import] menu under [File] menu. Refer to :ref:`sec_file_import_calc_result`.

[Export] (E)
---------------

**Description**: Exports the calculation result. Calculation result is
exported to VTK files or CSV files.

The function of this item is the same to [Calculation Result] under
[Export] menu under [File] menu. Refer to :ref:`sec_file_export_calc_result`.

[Import Visualization/Graph Settings]
----------------------------------------

**Description**: Imports the settings of visualization windows and graph
windows.

The function of this item is the same to [Visualization/Graph Settings]
under [Import] menu under [File] menu. Refer to :ref:`sec_file_import_vis_setting`.

[Export Visualization/Graph Settings]
---------------------------------------

**Description**: Exports the settings of visualization windows and graph
windows.

The function of this item is the same to [Visualization/Graph Settings]
under [Export] menu under [File] menu. Refer to :ref:`sec_file_export_vis_setting`.
